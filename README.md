# ollamaenv
docker compose with ollama and open-webui

## Requirements

- docker
- docker-compose
- NVIDIA GPU
- NVIDIA Driver
- NVIDIA CUDA Toolkit
- NVIDIA Container Toolkit

## How to Use 🚀

``` bash
git clone https://github.com/rising3/ollamaenv.git
cd ollamaenv
source ./ollamaenv_alias
envu
ollama pull gemma3
```
You can access Open WebUI at http://localhost:3000. Enjoy! 😄

Ollama is running: http://localhost:11434

### ollamaenv alias

Enable to alias:

``` bash
source ./ollamaenv_alias
```

ALIAS | REMARKS
--- | ---
envu | docker compose up.
envd | docker compose down.
ollama | Ollama CLI.
ollama_login | Login to Ollama Container.
ollama_backup | Backup Ollama LLMs.
ollama_restore | Restore Ollama LLMs.
open-webui_login | Login to Open-WebUi Container.

### For CPU Only/Apple Silicon

Comment out the following:

``` yaml
    deploy:
      resources:
        reservations:
          devices:
            - driver: nvidia
              count: all
              capabilities: [gpu]
```

## Refer to

- [Ollama](https://github.com/ollama/ollama)
- [Open-WebUi](https://github.com/open-webui/open-webui)
