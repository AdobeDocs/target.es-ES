---
solution: Target
product: target
title: Autoalojar el servidor MCP de Adobe Target
description: Aprenda a ejecutar su propia instancia del servidor MCP de Adobe Target mediante Python, Docker o un entorno de desarrollo local.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer
level: Experienced
source-git-commit: 7b0c8b18abe2db4e07e3ef979d6d194f4c4c81d6
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 2%

---

# Autoalojar el servidor MCP [!DNL Adobe Target] {#target-mcp-self-hosted}


>[!AVAILABILITY]
>
>El servidor MCP [!DNL Adobe Target] está disponible para todos los clientes en **Public Beta**. Actualmente es compatible con **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** y **ChatGPT**.

Esta página explica cómo clonar, configurar y ejecutar su propia instancia del servidor MCP [!DNL Adobe Target]. El alojamiento propio es útil cuando necesita un entorno de desarrollo local, una configuración de red personalizada o desea contribuir al código base del servidor.

>[!AVAILABILITY]
>
>La implementación autoalojada está dirigida a desarrolladores y usuarios avanzados que necesitan control total sobre el tiempo de ejecución del servidor MCP [!DNL Adobe Target]. Para la mayoría de los usuarios, se recomienda el extremo hospedado (`https://targetmcp.adobe.io/mcp`). Consulte [Trabajar con clientes MCP](target-mcp.md).



## Requisitos previos {#self-hosted-prereqs}

Antes de empezar, asegúrese de que dispone de lo siguiente:

* **Python 3.13 o posterior**
* **[uv](https://github.com/astral-sh/uv){target="_blank"}** — paquete rápido de Python y jefe de proyecto

  ```bash
  curl -LsSf https://astral.sh/uv/install.sh | sh
  ```

* Una licencia activa de [!DNL Adobe Target] con acceso de Adobe Experience Cloud
* **Credenciales de fábrica** (solo usuarios internos de Adobe): necesarias para instalar dependencias internas

## Instalación {#self-hosted-install}

**1. Clonar el repositorio:**

```bash
git clone https://github.com/Adobe-TnT/target-mcp.git
cd target-mcp
```

**2. Crear y activar un entorno virtual:**

```bash
uv venv --python 3.13
source .venv/bin/activate
```

**3. Configurar variables de entorno:**

```bash
cp env.example .env
```

Abra `.env` y reemplace los valores de marcador de posición por sus credenciales y configuración de la organización.

**4. Instalar dependencias:**

```bash
make uv-install
```

**5. Inicie el servidor:**

Elija el modo que coincida con su caso de uso:

| Modo | Comando | Usar cuando |
|---|---|---|
| StreamableHTTP (servidor API) | `make run-api-server` | Conexión de un cliente MCP a través de HTTP |
| STDIO (cliente MCP local) | `make run-mcp-stdio` | Uso de la comunicación directa entre procesos |

## Conectar un cliente MCP a un servidor local {#self-hosted-connect}

### Cursor

Añada lo siguiente a la configuración de MCP del cursor. Reemplace los valores de marcador de posición con el token de IMS y el ID de organización reales:

```json
{
  "mcpServers": {
    "target-local": {
      "url": "http://localhost:8080/mcp",
      "headers": {
        "Authorization": "Bearer {IMS_USER_TOKEN}",
        "x-gw-ims-org-id": "{IMS_ORGANIZATION_ID}"
      }
    }
  }
}
```

### Código Claude

Añada una entrada al archivo de configuración del MCP de Claude Code que apunte al servidor local:

```json
{
  "mcpServers": {
    "target-local": {
      "url": "http://localhost:8080/mcp"
    }
  }
}
```

>[!NOTE]
>
>Al conectarse a un servidor local, los encabezados de autenticación deben pasarse manualmente (como se muestra en el ejemplo del cursor anterior). El flujo del explorador OAuth solo está disponible con el extremo `https://targetmcp.adobe.io/mcp` alojado.

## Implementación de Docker {#self-hosted-docker}

El repositorio incluye una configuración Docker Compose para implementaciones en contenedores.

**Ejecutar con Docker Compose:**

```bash
make run-dc
```

**Genere y ejecute la imagen Docker directamente:**

```bash
make build
make run-docker
```

## Extremos de API {#self-hosted-endpoints}

El servidor autoalojado expone los siguientes extremos HTTP:

| Punto de conexión | Descripción |
|---|---|
| `/mcp` | Extremo de protocolo MCP para clientes de IA |
| `/ping` | Comprobación de actividad — devuelve `"Pong"` |
| `/health` | Comprobación de estado — devuelve `{"status": "healthy"}` |
| `/validate` | Extremo de validación de entrada |
| `/authorize` | Punto final de autorización de OAuth |
| `/token` | Extremo de token de OAuth |

**Ejemplo de comprobación de estado:**

```bash
curl http://localhost:8080/health
# Response: {"status": "healthy"}
```

## Resolución de problemas {#self-hosted-troubleshoot}

+++El servidor no puede iniciarse

1. Verificar que Python 3.13+ esté instalado: `python --version`
1. Confirme que el entorno virtual está activado: `source .venv/bin/activate`
1. Compruebe que todas las variables de entorno de `.env` estén configuradas correctamente.
1. Vuelva a ejecutar `make uv-install` para asegurarse de que todas las dependencias están presentes.

+++

+++No se puede conectar desde el cliente MCP

1. Confirme que el servidor se está ejecutando y que el puerto es accesible: `curl http://localhost:8080/ping`
1. Compruebe que la dirección URL del servidor de la configuración del cliente MCP coincida con la dirección del servidor en ejecución.
1. Para el cursor, asegúrese de que el encabezado `Authorization` contenga un token de IMS válido y no caducado.

+++

+++Error en la instalación de dependencias (usuarios internos de Adobe)

1. Confirme que las credenciales de Artifactory están configuradas correctamente.
1. Compruebe la conexión de red a la instancia interna de Artifactory.
1. Póngase en contacto con el DevOps de su equipo o con el contacto de ingeniería de plataformas para obtener acceso a Artifactory.

+++

## Recursos relacionados {#self-hosted-related}

* [Trabajar con clientes MCP](target-mcp.md): configuración de extremo hospedado y referencia de herramienta
* [Documentación del protocolo de contexto de modelo](https://modelcontextprotocol.io/introduction){target="_blank"}
* [Referencia de la API de administración [!DNL Adobe Target]](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
