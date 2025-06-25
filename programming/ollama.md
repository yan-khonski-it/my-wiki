# Ollama

This page gives some instructions related to ollama.

Ollama allows you to run (large or small) language models locally on your hardware.

It supports fine-tuning and optimization of LLMs to suit specific business or personal needs,
enabling tailored performance for particular tasks or domains.

Since models are run locally, Ollama can function without an active internet connection,
which is beneficial for environments with restricted or not connectivity.

By running models locally, Ollama ensures that sensitive data does not leave your device or network, addressing privacy concerns commonly assosiated with
cloud-based AI systems.

https://ollama.com/

https://github.com/ollama/ollama/tree/main

## Installation on windows

Download from the link https://ollama.com/

https://github.com/ollama/ollama/blob/main/docs/windows.md

If you want to change directory, run the installer with argument DIR
```commandline
OllamaSetup.exe /DIR="d:\some\location"
```

If you want to specify directory where downloaded models are stored, set env variable

## Commands

```commandline
ollama list
```
Example output:
```commandline
PS C:\Users\Yan> ollama list
NAME          ID              SIZE      MODIFIED
gemma3:4b     a2af6cc3eb7f    3.3 GB    About a minute ago
gemma3:27b    a418f5838eaf    17 GB     11 minutes ago
```
List all downloaded models, not necessary running. Could be used by a program that wants to validate that a model is available.

```commandline
ollama ps
```
Returns list of models that are currently running, also tells if a model uses CPU or GPU or their combination.
Example:
```commandline
PS C:\Users\Yan> ollama ps
NAME          ID              SIZE     PROCESSOR          UNTIL
gemma3:27b    a418f5838eaf    21 GB    56%/44% CPU/GPU    Stopping...
```

Start model:
```commandline
ollama run <MODEL_NAME>

ollama run gemma3:27b
```

ctrl + d in the terminal will exit the model.

Stop model:
```commandline
ollama stop <MODEL_NAME>

ollama stop gemma3:27b
```

> Running or stopping a model by id does not work now.
```commandline
PS C:\Users\Yan> ollama stop a418f5838eaf
Error: couldn't find model "a418f5838eaf" to stop
```

Remove model:
```commandline
ollama rm <MODEL_NAME>

ollama rm gemma3:27b
```

On my Windows machine, intel codre i9 10900K 20 threads, 10 cores, 3.7 GHz, 64 GB RAM, I was able to run
gemma3:27b

On macbook pro M3 pro 16 GB RAM, I was able to run gemma3:12b.

## Passing images
Some models may accept an image as parameter.

https://ollama.com/library/llava

- gemma3:4b
- llava:13b

Just paste image path or Base64 data:
