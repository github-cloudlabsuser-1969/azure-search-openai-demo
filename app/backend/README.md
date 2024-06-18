Backend Documentation
This document provides an overview of the backend directory structure and key components of the Azure Search OpenAI Demo application. The backend is primarily developed in Python, utilizing the Quart framework for asynchronous web applications.

Directory Structure
The backend codebase is located under the app/backend directory. Here's a brief overview of its structure:

app.py: The main entry point for the backend application. It initializes the Quart app, configures routes, and sets up middleware.
approaches/: Contains different classes implementing various Retrieval Augmented Generation (RAG) approaches for the Chat and Ask functionality.
chatreadretrieveread.py: Implements the Chat Read-Retrieve-Read approach.
chatreadretrievereadvision.py: Implements the Chat Read-Retrieve-Read approach with vision capabilities.
retrievethenread.py: Implements the Retrieve-Then-Read approach.
retrievethenreadvision.py: Implements the Retrieve-Then-Read approach with vision capabilities.
config.py: Contains configuration variables used throughout the backend, such as API keys and service endpoints.
core/: Contains core functionality and utilities.
authentication.py: Provides helper functions for authentication.
decorators.py: Contains decorators for route authentication.
error.py: Defines error handling mechanisms and error response formats.
prepdocs/: Contains utilities for preparing documents for ingestion and search.
filestrategy/: Includes strategies for file upload and listing.
UploadUserFileStrategy.py: Strategy for uploading user files.
File.py: Represents a file entity.
Key Components
Quart Application
The backend uses Quart, an asynchronous web framework. It allows for efficient handling of I/O-bound operations and is compatible with the asyncio library in Python.

Azure Services Integration
The application integrates with various Azure services, including Azure AI Search, Azure Blob Storage, and Azure Key Vault, to provide a comprehensive search and AI experience. The integration is facilitated through the use of SDKs provided by Azure.

Authentication
Authentication is handled using the AuthenticationHelper class in the core/authentication.py file. It supports app services authentication and can enforce access control based on Azure AD roles.

Error Handling
Error handling is centralized in the error.py file, which defines a standard error response format and a dictionary of common error types.

Document Preparation and Ingestion
The prepdocs directory contains utilities for document preparation, including cleaning up documents, setting up embeddings for vector search, and configuring file processors for document ingestion.

Customization
For customization details, refer to the customization guide in the project documentation. It covers how to use your own data, customize the UI, and modify backend approaches for Chat and Ask functionality.

This backend documentation aims to provide a clear understanding of the structure and functionality of the backend part of the Azure Search OpenAI Demo application. For further details, please refer to the source code and additional documentation in the docs directory.