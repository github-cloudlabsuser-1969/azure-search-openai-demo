# Backend Application

## Descripción

La aplicación backend es responsable de manejar la lógica del servidor, la gestión de datos y la comunicación con la base de datos. Proporciona una API para que el frontend interactúe con los datos y servicios del sistema.

## Estructura del Proyecto

El directorio `backend` contiene los siguientes componentes principales:

- **Controllers**: Manejan las solicitudes HTTP y responden con datos o mensajes.
- **Models**: Definen las estructuras de datos y gestionan la interacción con la base de datos.
- **Services**: Contienen la lógica de negocio principal.
- **Routes**: Configuran las rutas de la API.
- **Utils**: Funciones auxiliares y herramientas comunes.

## Requisitos Previos

Asegúrate de tener instalados los siguientes requisitos:

- Python 3.8 o superior
- [Poetry](https://python-poetry.org/) para la gestión de dependencias
- Una base de datos compatible (por ejemplo, PostgreSQL)

## Instalación

1. Clona el repositorio:

   ```bash
   git clone <URL_DEL_REPOSITORIO>
   cd app/backend
   ```

2. Instala las dependencias:

   ```bash
   poetry install
   ```

3. Configura las variables de entorno necesarias en un archivo `.env`.

## Uso

Para iniciar el servidor de desarrollo, ejecuta:

```bash
poetry run uvicorn main:app --reload
```

El servidor estará disponible en `http://127.0.0.1:8000`.

## Pruebas

Ejecuta las pruebas con:

```bash
poetry run pytest
```

## Contribución

Si deseas contribuir al desarrollo del backend, sigue los pasos descritos en el archivo [CONTRIBUTING.md](../../CONTRIBUTING.md).

## Licencia

Este proyecto está licenciado bajo los términos del archivo [LICENSE](../../LICENSE.md).

## Dependencias

```plaintext
azure-core-tracing-opentelemetry==1.0.0b11
azure-identity==1.15.0
azure-keyvault-secrets==4.8.0
azure-monitor-opentelemetry==1.3.0
azure-monitor-opentelemetry-exporter==1.0.0b23
azure-search-documents==11.6.0b1
azure-storage-blob==12.19.1
azure-storage-file-datalake==12.14.0
beautifulsoup4==4.12.3
blinker==1.7.0
certifi==2024.2.2
cffi==1.16.0
charset-normalizer==3.3.2
click==8.1.7
cryptography==42.0.5
deprecated==1.2.14
distro==1.9.0
ecdsa==0.18.0
fixedint==0.1.6
flask==3.0.2
quart==0.19.4
quart-cors==0.7.0
```

## Backend Documentation

This document provides an overview of the backend directory structure and key components of the Azure Search OpenAI Demo application. The backend is primarily developed in Python, utilizing the Quart framework for asynchronous web applications.

### Directory Structure

The backend codebase is located under the app/backend directory. Here's a brief overview of its structure:

- **app.py**: The main entry point for the backend application. It initializes the Quart app, configures routes, and sets up middleware.
- **approaches/**: Contains different classes implementing various Retrieval Augmented Generation (RAG) approaches for the Chat and Ask functionality.
  - **chatreadretrieveread.py**: Implements the Chat Read-Retrieve-Read approach.
  - **chatreadretrievereadvision.py**: Implements the Chat Read-Retrieve-Read approach with vision capabilities.
  - **retrievethenread.py**: Implements the Retrieve-Then-Read approach.
  - **retrievethenreadvision.py**: Implements the Retrieve-Then-Read approach with vision capabilities.
- **config.py**: Contains configuration variables used throughout the backend, such as API keys and service endpoints.
- **core/**: Contains core functionality and utilities.
  - **authentication.py**: Provides helper functions for authentication.
  - **decorators.py**: Contains decorators for route authentication.
  - **error.py**: Defines error handling mechanisms and error response formats.
- **prepdocs/**: Contains utilities for preparing documents for ingestion and search.
- **filestrategy/**: Includes strategies for file upload and listing.
  - **UploadUserFileStrategy.py**: Strategy for uploading user files.
  - **File.py**: Represents a file entity.

### Key Components

#### Quart Application

The backend uses Quart, an asynchronous web framework. It allows for efficient handling of I/O-bound operations and is compatible with the asyncio library in Python.

#### Azure Services Integration

The application integrates with various Azure services, including Azure AI Search, Azure Blob Storage, and Azure Key Vault, to provide a comprehensive search and AI experience. The integration is facilitated through the use of SDKs provided by Azure.

#### Authentication

Authentication is handled using the AuthenticationHelper class in the core/authentication.py file. It supports app services authentication and can enforce access control based on Azure AD roles.

#### Error Handling

Error handling is centralized in the error.py file, which defines a standard error response format and a dictionary of common error types.

#### Document Preparation and Ingestion

The prepdocs directory contains utilities for document preparation, including cleaning up documents, setting up embeddings for vector search, and configuring file processors for document ingestion.

### Customization

For customization details, refer to the customization guide in the project documentation. It covers how to use your own data, customize the UI, and modify backend approaches for Chat and Ask functionality.

This backend documentation aims to provide a clear understanding of the structure and functionality of the backend part of the Azure Search OpenAI Demo application. For further details, please refer to the source code and additional documentation in the docs directory.