# The challenge 
Enterprise AI agents often need to query a mix of data types simultaneously from the same database, such as structured records and unstructured documents. This creates a challenge of how to provide unified access without exposing the database to the risks of direct AI interaction.

# The solution 
Create a secure API gateway. This separates the AI from the data layer, allowing the agent to request information in a controlled way without ever touching the live database directly.

In Google Cloud, you can implement this solution by building a production-grade agent using this three-tier architecture:
1. Data Layer: An AlloyDB database configured for high-speed vector search.
2. Secure API Layer: The MCP Toolbox for Databases, deployed on Cloud Run as a private, secure API endpoint that exposes specific data access "tools."
3. Agent Layer: An intelligent agent built with the Google Cloud Agent Development Kit (ADK) that securely authenticates and consumes the API layer to answer questions.
This pattern ensures your agent is powerful yet secure, only accessing data through approved, audited channels. Your final agent will securely authenticate and consume the API, empowering an insurance adjuster to query policy details and find repair articles using natural language—all without ever touching the production database directly.

# Objectives
In this lab, you learn how to:

- Configure an AlloyDB database for vector search and store embeddings.
- Create a simple API wrapper for MCP Toolbox for Databases using FastAPI.
- Deploy the MCP Toolbox as a private, secure API service on Cloud Run.
- Set up the Agent Development Kit (ADK) environment according to best practices.
- Build a custom ADK tool that securely calls a private Cloud Run service.
- Create and run an ADK agent that uses the custom tool to answer questions.