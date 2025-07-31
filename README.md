## Quick Start

Press `Win` + `R`, then type:
```pwsh
wsl ~
```
Hit `Enter`

If you haven't create `n8n_data` run:
```bash
docker volume create n8n_data
```
and then run:
```bash
docker run -d --name n8n --restart unless-stopped -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n
```
open borswer and go to http://localhost:5678

## detailed
All the commands are running in WSL.
#### n8n_data
1. Create: 
```bash
docker volume create n8n_data
```
2. Inspect:  
```bash
docker volume ls | grep n8n
```
3. Delete:
```bash
docker volume rm n8n_data
```
#### n8n Server
1. Create: 
```bash
docker run -it --rm --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n
```
2. Inspect
```bash
docker ps
```
3. Delete
```bash
docker stop n8n
```


## Concept
When every you doing automation, remember 3 key points to manage resources.
1. How to Create
2. How to Inspect
3. How to Delete
