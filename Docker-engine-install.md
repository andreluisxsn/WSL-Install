### Instalando o Docker Engine nativo do Linux no WSL
    
    -   1°  Instale os pré-requisitos:
    -   sudo apt update && sudo apt upgrade
        sudo apt remove docker docker-engine docker.io containerd runc
        sudo apt-get install \
            apt-transport-https \
            ca-certificates \
            curl \
            gnupg \
            lsb-release
        
    -   2°  Adicione o repositório do Docker na lista de sources do Ubuntu:
        -   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
            echo \
                "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
                $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

    -   3°  Instale o Docker Engine
        -   sudo apt-get update
        -   sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

    -   4°  Dê permissão para rodar o Docker com seu usuário corrente:
        -   sudo usermod -aG docker $USER

    -   5°  Inicie o serviço do Docker:
        -   sudo service docker start
        -   Lembre-se de Iniciar o Docker Engine todas as vezes que o Linux for reiniciado, senão será exibio o seguinte erro: Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?

    -   6°  Lembre-se: Se você estiver utilizando o Docker Desktop for Windows e agora irá migrar para o Docker Engine nativo do Linux,
            vá até a pasta ".docker" e delete o arquivo config.json, pois esse arquivo é o arquivo de autenticação utilizado pelo Docker Desktop e quando você for se autenticar com o Docker Engine o arquivo será outro.
