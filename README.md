# LLocalSearch

## What it is

This is a completely locally running search engine using LLM Agents. The user can ask a question and the system will use a chain of LLMs to find the answer. The user can see the progress of the agents and the final answer. No OpenAI or Google API keys are needed.

Now with follow-up questions: 

![image](https://github.com/nilsherzig/LLocalSearch/assets/72463901/9f6497aa-8047-4d11-9a12-66aff65d3faa)

## Features 

-  🕵️ Completely local (no need for API keys)
- 💸 Runs on "low end" LLM Hardware (demo video uses a 7b model)
- 🤓 Progress logs, allowing for a better understanding of the search process
- 🤔 Follow-up questions
- 📱 Mobile friendly interface
- 🚀 Fast and easy to deploy with Docker Compose
- 🌐 Web interface, allowing for easy access from any device
- 💮 Handcrafted UI with light and dark mode

## Status 

This project is still in its very early days. Expect some bugs. 

## How it works 

Please read [infra](https://github.com/nilsherzig/LLocalSearch/issues/17) to get the most up-to-date idea.

## Self-hosting & Development

### Requirements

- A running [Ollama](https://ollama.com/) server, reachable from the container
    - GPU is not needed, but recommended
- Docker Compose

### Run the latest release

Recommended, if you don't intend to develop on this project.

```bash
curl -sO https://raw.githubusercontent.com/nilsherzig/LLocalSearch/main/docker-compose.yaml 
# 🔴 check the env vars inside the compose file and add your ollama servers host:port
docker-compose up 
```

🎉 You should now be able to open the web interface on http://localhost:3000. Nothing else is exposed by default.

### Run the current git version 

Newer features, but potentially less stable.

```bash
git clone https://github.com/nilsherzig/LLocalsearch.git
# 1. make sure to check the env vars inside the `docker-compose.dev.yaml`.
# 2. Make sure you've really checked the dev compose file not the normal one.

# 3. build the containers and start the services
make dev 
# Both front and backend will hot reload on code changes. 
```

If you don't have `make` installed, you can run the commands inside the Makefile manually.

Now you should be able to access the frontend on [http://localhost:3000](http://localhost:3000).
