# Enhanced version of Tomaz Bratanic code
# https://medium.com/neo4j/json-based-agents-with-ollama-langchain-9cf9ab3c84ef
#
# How to run

## Prerequisites

- docker
- docker-compose

## Build container
```
./docker_build.sh
```

## Edit the `.env` file

Ensure API keys are set:
```
OPENAI_API_KEY=<YOUR_OPENAI_API_KEY>
NEO4J_URI=<YOUR_NEO4J_URI>
NEO4J_USERNAME=<YOUR_NEO4J_USERNAME>
NEO4J_PASSWORD=<YOUR_NEO4J_PASSWORD>
```

For command line run, make sure the host user variables are set to match the host user:
```
USER
UID
```

## To run the container

Start up the container:
```
docker-compose up -d
```

Get command line in the container:
```
docker-compose exec container su <USER from above> 
```

## From container command line

Run the app:
```
python app/server.py
```

Ctrl-C to stop the app.
exit to leave the container.

## Open app from browser

Open the playground through port 8080:
```
http://<IP or DNS>:8080/neo4j-semantic-ollama/playground/
```

Or open the playground through apache:
```
https://<unique DNS>/neo4j-semantic-ollama/playground/
```

## To stop the container
Stop the container and clean up:
```
docker-compose down -v
```

# ORIGINAL NEO4J-APP README FOR ARCHIVE ONLY

Over the past few months, we've built a large collection of [template](https://templates.langchain.com/) LangServe apps. This repo showcases a template from Neo4J, the [neo4j-semantic-ollama](https://github.com/langchain-ai/langchain/tree/master/templates/neo4j-semantic-ollama). Here, we turn the template into a web service with LangServe. This repo can be deployed using Hosted LangServe.

![template](https://github.com/langchain-ai/neo4j-semantic-ollama/assets/122662504/00ef0d88-8538-42ba-a5e0-dce3d330f378)

## Installation

Install the LangChain CLI if you haven't yet

```bash
pip install -U langchain-cli
```

## Create app and add neo4j-semantic-ollama package

```bash
langchain app new . 
What package would you like to add? (leave blank to skip): neo4j-semantic-ollama  
```

## Run locally
```
langchain serve
```

Open the playground:
```
http://127.0.0.1:8000/neo4j-semantic-ollama/playground/
```

![Screenshot 2024-01-10 at 12 09 58 PM](https://github.com/langchain-ai/neo4j-semantic-ollama/assets/122662504/74fefcc3-dded-49f7-8d85-949899de3ba0)

Ensure API keys are set:

```
OPENAI_API_KEY=<YOUR_OPENAI_API_KEY>
NEO4J_URI=<YOUR_NEO4J_URI>
NEO4J_USERNAME=<YOUR_NEO4J_USERNAME>
NEO4J_PASSWORD=<YOUR_NEO4J_PASSWORD>
```

## Run with hosted LangServe

Use LangSmith console to import this repo.

![Screenshot 2024-01-10 at 12 14 31 PM](https://github.com/langchain-ai/neo4j-semantic-ollama/assets/122662504/16b4ac2a-6e83-45d5-b764-28d9294123b1)
