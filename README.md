### Criando ambiente de Desenvolvimento no Windows.

    -   1° Instalar o VScode

    -   2° Habilitar o recurso de Máquina Virtual
        -   dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
        -   Reinicie o computador

    -   3° Baixar o pacote de atualização do kernel do Linux
        -   https://learn.microsoft.com/pt-br/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package

    -   4° Definir o WSL 2 como a sua versão padrão
        -   wsl --set-default-version 2

    -   5° instalar o wsl
        -   wsl --install -d <Nome da sua Distro de preferência>

### Instalando terminal para funcionameto com o WSL2.

    -   1° Instale o Windows Terminal
        -   Quando for instalado o proprio Windows Terminal irá identificar o WSL
    
    -   2° Para acessar seus diretórios Windows acesse "/mnt/c/Users/User"


### Criando Usuário, Coloca-lo no grupo de Administradores e logar com esse usuário de forma direta.

    -   1° adduser <Nome do usuário>
        -   Passar uma senha
        -   Passar seu nome
        -   ENTER até o final e confirmar com [Y]

    -   2° Colocando o usuário no grupo de administrador
        -   usermod -a -G sudo <Passar o nome do usuário que você criou>

    -   3° Logando no usuário criado
        -   login <Passar o nome do usuário que você criou>
        -   Irá ser requisitado a senha que você configurou para o usuário
        -   Verifique se o comando sudo está funcional

### Definindo o usuário criado como padrão no WSL.

    -   1° Mudando o usuário criado para o usuário padrão do WSL
        -   ubuntu.exe config --default-user <Passar o nome do usuário que você criou>


### Criando um atalho para acesso a pasta WSL no Windows.

    -   1° Digite " explorer.exe ."
        -   Pegue a pasta do WSL e arraste ela para onde desejar para facilitar o acesso de alguma configuração muito rápida


### Instalando o ZSH e o Oh My ZSH.

    -   1° sudo apt-get install zsh

    -   2° Instale o Oh My ZSH
        -   sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

    -   3° Mudando o Tema do ZSH
        -   Abra o arquivo .zshrc
        -   Encontre o campo ZSH_THEME="fletcherm"
        -   Abra a URL "https://github.com/ohmyzsh/ohmyzsh/wiki/Themes"
        -   Encontre o Tema que mais te agrade
        -   Troque o tema no campo ZSH_THEME
        -   Recarregue o arquivo .zshrc "source .zshrc"

    -   4° Instalando o auto-complete do ZSH
        -   Clone o repositório
            -   git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions
        -   Encontre o campo PLUGINS no arquivo .zshrc
        -   Dentro desse campo digite "git zsg-autosuggestions" e salve

    -   5° Instalando o Plugin ssh-agent
        -   Encontre o campo PLUGINS no arquivo .zshrc
        -   Dentro desse campo digite "git ssh-agent zsg-autosuggestions" e salve

    -   6° Configurando o Vscode para edição de arquivos dentro do WSL
        -   Instale a extenção do WSL no próprio Vscode
        -   Após isso você poderá abrir qualquer pasta/arquivo no WSL com comando "code ."