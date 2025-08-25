# Install n8n
If you have already install **Docker**, **WSL Ubuntu-22.04** and **Created n8n Volume**. you can just go to [here](#4-install-n8n-image-and-run).


### 1. Install Docker
Go to [here](https://docs.docker.com/desktop/setup/install/windows-install/) and download.
### 2. Install WSL Ubuntu-22.04
`Win` + `R` and run `pwsh`.
```bash
wsl --install -d Ubuntu-22.04
```
### 3. Create n8n Volume
You can find the offical documentation [here](https://docs.n8n.io/hosting/installation/docker/#starting-n8n).

`Win` + `R` and run `wsl`.
```bash
docker volume create n8n_data
```
### 4. Install n8n Image and Run
`Win` + `R` and run `wsl`.
```bash
docker run -it -d \
 --name n8n \
 -p 5678:5678 \
 -e GENERIC_TIMEZONE=Asia/Taipei \
 -e TZ=Asia/Taipei \
 -e N8N_ENFORCE_SETTINGS_FILE_PERMISSIONS=true \
 -e N8N_RUNNERS_ENABLED=true \
 -v n8n_data:/home/node/.n8n \
 --restart unless-stopped \
 docker.n8n.io/n8nio/n8n
```