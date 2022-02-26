# Install Docker Desktop
Install and integrate docker desktop with WSL2

## Requirements
- Install [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows/) from Docker Hub
- Verify WSL2 by running ``wsl -l -v`` in **Powershell** 
> ![Powershell-Check](/Images/pwsh_img.PNG)

- Go to **Settings**->**Resouces**->**WSL Integration**->**Ubuntu**

# Verify 
- Open Ubuntu 
- Run the commands below to check everything is setup before moving on:
> ```
> sudo docker -v
> sudo docker run hello-world
> ```
> - Check Docker-Compose
> `docker-compose -v`

# Install Portainer
Create a portainer volume for data
> ```
> cd 
> docker volume create portainer_data
> docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer
> ```

# Access portainer
- Open a browser and type in:
> `http://localhost:9000`

- Choose Local

# Cleanup Commands
- Remove Container
`sudo docker rm <TAB> `

- Remove Image
`sudo docker rmi <TAB>`

- Remove Volume
`sudo docker volume rm <TAB>`
