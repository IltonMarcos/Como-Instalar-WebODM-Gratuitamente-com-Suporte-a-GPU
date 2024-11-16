# **PARTE III -** **A PREPARAÇÃO DO AMBIENTE COM WSL 2 E DOCKER DESKTOP**

# *Como Processei um Bloco de 1500 Imagens no WebODM Gratuito num I5 com GPU RTX 3060 e 32GB de RAM*

**ETAPAS DE INSTALAÇÃO DO WebODM**

**1. TÍTULO: COMO INSTALAR WEBODM GRATUITAMENTE NO WINDOWS COM SUPORTE A
GPU -- PARTE I**

**SUBTÍTULO: *PARTE I - INTRODUÇÃO E REQUISITOS PARA INSTALAÇÃO DO
WebODM***

**2. TÍTULO: COMO INSTALAR WEBODM GRATUITAMENTE NO WINDOWS COM SUPORTE A
GPU -- PARTE II**

**SUBTÍTULO: *PARTE 2 - INSTALAÇÃO DOS PRÉ-REQUISITOS DO SISTEMA***

**3. TÍTULO: COMO INSTALAR WEBODM GRATUITAMENTE NO WINDOWS COM SUPORTE A
GPU -- PARTE III**

**SUBTÍTULO: PARTE 3 - *A PREPARAÇÃO DO AMBIENTE COM WSL 2 E DOCKER
DESKTOP***

**4. TÍTULO: COMO INSTALAR WEBODM GRATUITAMENTE NO WINDOWS COM SUPORTE A
GPU -- PARTE IV**

**SUBTÍTULO: *PARTE 4 - INSTALAÇÃO E TESTE DO WebODM COM GPU***

**5. TÍTULO: COMO INSTALAR WEBODM GRATUITAMENTE NO WINDOWS COM SUPORTE A
GPU -- PARTE V**

**SUBTÍTULO: *PARTE 5 - MANUTENÇÃO DO WebODM E CONCLUSÃO***

# Sumário {#sumário .TOC-Heading}

[**PARTE III - A PREPARAÇÃO DO AMBIENTE COM WSL 2 E DOCKER DESKTOP**
[1](#parte-iii---a-preparação-do-ambiente-com-wsl-2-e-docker-desktop)](#parte-iii---a-preparação-do-ambiente-com-wsl-2-e-docker-desktop)

[*Como Processei um Bloco de 1500 Imagens no WebODM Gratuito num I5 com
GPU RTX 3060 e 32GB de RAM*
[1](#como-processei-um-bloco-de-1500-imagens-no-webodm-gratuito-num-i5-com-gpu-rtx-3060-e-32gb-de-ram)](#como-processei-um-bloco-de-1500-imagens-no-webodm-gratuito-num-i5-com-gpu-rtx-3060-e-32gb-de-ram)

[Tutorial: Instalação do WebODM com Aceleração de GPU no WSL Ubuntu
24.04 [2](#_Toc177408216)](#_Toc177408216)

[Passo 1: Verifique os Pré-requisitos
[2](#passo-1-verifique-os-pré-requisitos)](#passo-1-verifique-os-pré-requisitos)

[Passo 2: Habilitar o WSL 2 e Instalar o Ubuntu Estável mais Recente
[2](#passo-2-habilitar-o-wsl-2-e-instalar-o-ubuntu-estável-mais-recente)](#passo-2-habilitar-o-wsl-2-e-instalar-o-ubuntu-estável-mais-recente)

[Passo 3: Atualize o Ubuntu no WSL e instale os pacotes de
Pré-requisitos exigidos pelo WebODM:
[4](#passo-3-atualize-o-ubuntu-no-wsl-e-instale-os-pacotes-de-pré-requisitos-exigidos-pelo-webodm)](#passo-3-atualize-o-ubuntu-no-wsl-e-instale-os-pacotes-de-pré-requisitos-exigidos-pelo-webodm)

[Passo 4: Instale o Docker Desktop e Habilite a Integração com o WSL
[6](#passo-4-instale-o-docker-desktop-e-habilite-a-integração-com-o-wsl)](#passo-4-instale-o-docker-desktop-e-habilite-a-integração-com-o-wsl)

[2. Configurar Docker Engine e WSL 2 como Virtualização
[7](#configurar-docker-engine-e-wsl-2-como-virtualização)](#configurar-docker-engine-e-wsl-2-como-virtualização)

[Passo 5: Configuração do NVIDIA CUDA com Docker Desktop no WSL para
WebODM
[18](#passo-5-configuração-do-nvidia-cuda-com-docker-desktop-no-wsl-para-webodm)](#passo-5-configuração-do-nvidia-cuda-com-docker-desktop-no-wsl-para-webodm)

# A PREPARAÇÃO DO AMBIENTE COM WSL 2 E DOCKER DESKTOP

Este tutorial orienta a instalação e configuração do WebODM com suporte
a aceleração de GPU utilizando WSL (Windows Subsystem for Linux) e
Docker Desktop no Windows 10/11. Siga as etapas abaixo para garantir que
todas as ferramentas estejam corretamente configuradas e otimizadas para
aproveitar a aceleração de GPU da NVIDIA.

## Passo 1: Verifique os Pré-requisitos

Certifique-se de que está executando Windows 11 ou Windows 10, versão
21H2 ou superior. Confirme que sua GPU NVIDIA tem suporte para CUDA.
Veja os pré-requisitos completos na documentação oficial da Microsoft:
\[Pré-requisitos GPU no
WSL\](https://learn.microsoft.com/pt-br/windows/wsl/tutorials/gpu-compute).

## Passo 2: Habilitar o WSL 2 e Instalar o Ubuntu Estável mais Recente

Onde encontrar Iformações Oficiais para esta etapa: Instalar o
WSL(https://learn.microsoft.com/pt-br/windows/wsl/install).

1.  Abra o PowerShell como administrador(clicando com o botão direito do
    mouse sobre o ícone do Windows).

![Interface gráfica do usuário, Aplicativo Descrição gerada
automaticamente](./media/media/image1.png){width="2.09375in"
height="6.40625in"}

2.  Digite o seguinte comando e dê Enter:

***wsl \--set-default-version 2***

3.  Liste as Versões de Distribuições disponíveis:

***wsl \--list \--online***

4.  Escolha entre as duas Versões de Ubuntu LTS mais recentes. Use o
    comando "wsl \--install -d \<NOME DA VERSÃO ESCOLHIDA\>". Veja o
    exemplo:

***wsl \--install -d Ubuntu-24.04***

-   Será solicitado que você entre com um Nome de Usuário (Enter new
    UNIX username:)

-   E depois com uma senha duas vezes(enquanto você digita a senha o
    texto dela estará oculto):

> **New password:**
>
> **Retype new password:**

-   Você entrará no Ubuntu(geralmente um prompt de cor verde).

**VEJA O EXEMPLO:**

![Texto Descrição gerada
automaticamente](./media/media/image2.png){width="5.989583333333333in"
height="7.083333333333333in"}

## Passo 3: Atualize o Ubuntu no WSL e instale os pacotes de Pré-requisitos exigidos pelo WebODM:

**[Manual installation
(Docker):](https://github.com/OpenDroneMap/WebODM/?tab=readme-ov-file#manual-installation-docker)**
https://github.com/OpenDroneMap/WebODM/?tab=readme-ov-file#manual-installation-docker

![Texto Descrição gerada
automaticamente](./media/media/image3.png){width="6.0in"
height="3.375in"}

O commando abaixo, executado dentro do Ubuntu, fará todo nosso trabalho:

sudo apt update && sudo apt upgrade -y && sudo apt dist-upgrade -y &&
sudo apt autoremove -y && sudo apt install -y python3 python3-pip git
curl

VEJA O EXEMPLO:\
![Texto Descrição gerada
automaticamente](./media/media/image4.png){width="6.0in"
height="0.8298611111111112in"}

**Explicação dos Pacotes Necessários**

-   **sudo apt update: Atualiza a lista de pacotes disponíveis.**

-   **sudo apt upgrade -y: Atualiza todos os pacotes instalados para as
    versões mais recentes.**

-   **sudo apt dist-upgrade -y: Realiza uma atualização completa,
    instalando novas dependências se necessário.**

-   **sudo apt autoremove -y: Remove pacotes obsoletos que não são mais
    necessários.**

-   **python3** e **python3-pip**: Necessários para scripts Python e
    para instalar pacotes Python dependentes do WebODM.

-   **git**: Usado para clonar o repositório do WebODM do GitHub.

-   **curl**: Utilizado para fazer requisições HTTP para baixar arquivos
    ou adicionar repositórios (por exemplo, configurar o NVIDIA
    Container Toolkit para Docker).

## Passo 4: Instale o Docker Desktop e Habilite a Integração com o WSL

#### 1 Download e instalação do Docker Desktop

**Passo 1: Download e Instalação do Docker Desktop**

1.  **Acessar o site oficial do Docker:**

    -   Visite o site [oficial do
        Docker](https://docs.docker.com/desktop/install/windows-install/)(<https://docs.docker.com/desktop/install/windows-install>)
        usando seu navegador.

![Interface gráfica do usuário, Texto, chat ou mensagem de texto
Descrição gerada
automaticamente](./media/media/image5.png){width="7.5in"
height="3.870833333333333in"}

![Interface gráfica do usuário, Texto, Aplicativo Descrição gerada
automaticamente](./media/media/image6.png){width="4.4375in"
height="3.0716283902012247in"}

![Interface gráfica do usuário, Texto, Aplicativo Descrição gerada
automaticamente](./media/media/image7.png){width="4.091683070866142in"
height="2.803886701662292in"}

![Interface gráfica do usuário, Aplicativo, Teams Descrição gerada
automaticamente](./media/media/image8.png){width="4.473022747156605in"
height="3.0947451881014874in"}

### 2. Configurar Docker Engine e WSL 2 como Virtualização

**Passo 1: Configurações no Docker Desktop**

1.  **Abrir o Docker Desktop:**

    -   Após a instalação, abra o Docker Desktop a partir do menu
        **Iniciar** do Windows.

![Tela de computador com texto preto sobre fundo branco Descrição gerada
automaticamente](./media/media/image9.png){width="7.5in"
height="7.629166666666666in"}

![Interface gráfica do usuário, Texto Descrição gerada
automaticamente](./media/media/image10.png){width="7.5in"
height="4.694444444444445in"}

-   Escolha Pular(Skip) ou criar/logar uma conta do Docker.

![Tela de celular Descrição gerada
automaticamente](./media/media/image11.png){width="6.704708005249344in"
height="3.9166666666666665in"}

![Tela de computador com fundo preto Descrição gerada
automaticamente](./media/media/image12.png){width="7.5in"
height="4.377777777777778in"}

Verifique se há atualizações. Se tiver como é o meu caso, clique para
atualizar:

![Tela de celular com publicação numa rede social Descrição gerada
automaticamente](./media/media/image13.png){width="7.5in"
height="4.491666666666666in"}

![Tela de computador com texto preto sobre fundo branco Descrição gerada
automaticamente](./media/media/image14.png){width="7.5in"
height="4.442361111111111in"}

![Tela de computador com texto preto sobre fundo branco Descrição gerada
automaticamente](./media/media/image15.png){width="7.5in"
height="4.434027777777778in"}

Sempre confira se o Docker está funcionando. Para isso, a targa "Engine
Running" no canto esquerdo inferior deve estar verde:\
![Tela de computador com texto preto sobre fundo branco Descrição gerada
automaticamente](./media/media/image16.png){width="7.5in"
height="4.449305555555555in"}

2.  **Modificar as configurações:**

    -   Clique no ícone de engrenagem no canto superior direito da
        janela do Docker Desktop para abrir as **Configurações**.

![Tela de celular com aplicativo aberto Descrição gerada
automaticamente](./media/media/image17.png){width="7.5in"
height="4.418055555555555in"}

3.  **Configurar o backend para WSL2:**

    -   No menu lateral, clique em **\"General\"**.

    -   Verifique se a opção **\"Use the WSL 2 based engine\"** está
        habilitada. Se não estiver, habilite-a.

![Tela de computador com texto preto sobre fundo branco Descrição gerada
automaticamente](./media/media/image18.png){width="7.5in"
height="4.4118055555555555in"}

**Passo 2: Habilitar Integração com WSL2**

1.  **Configurar a integração com WSL2:**

    -   Vá para a seção **\"Resources\" \> \"WSL Integration\"**.

    -   Marque a opção **\"Enable integration with my default WSL
        distro\"** para habilitar a integração com o WSL2.

![Tela de celular com aplicativo aberto Descrição gerada
automaticamente](./media/media/image19.png){width="7.5in"
height="4.254166666666666in"}

2.  **Faça esta alteração no texto de Docker Engine:**

    -   Em Doker Engine, mude Experimental para "true":

![Tela de computador com texto preto sobre fundo branco Descrição gerada
automaticamente](./media/media/image20.png){width="7.5in"
height="4.430555555555555in"}

3.  **Aplicar as configurações:**

    -   Clique em **\"Apply & Restart\"** para salvar as configurações e
        reiniciar o Docker Desktop com o WSL2 como backend.

![Interface gráfica do usuário, Texto, Aplicativo Descrição gerada
automaticamente](./media/media/image21.png){width="3.667178477690289in"
height="1.6668996062992125in"}

**Passo 3: Adicionar Docker a um Grupo no WSL para Acessar Recursos**

1.  **Abrir o terminal da sua distribuição Linux no WSL:**

    -   Use o **Windows Terminal** ou abra o terminal da sua
        distribuição diretamente.

![Interface gráfica do usuário, Aplicativo Descrição gerada
automaticamente](./media/media/image22.png){width="6.510416666666667in"
height="5.416666666666667in"}

2.  **Adicionar seu usuário ao grupo docker:**

    -   Execute o comando abaixo para adicionar seu usuário ao grupo
        docker:

***sudo usermod -aG docker \$USER***

![Interface gráfica do usuário, Aplicativo Descrição gerada
automaticamente](./media/media/image23.png){width="5.458333333333333in"
height="1.3333333333333333in"}

3.  **Aplicar as mudanças:**

    -   Feche e reabra o terminal para aplicar as mudanças ao grupo do
        usuário.

**Passo 4: Verificar o Funcionamento do Docker**

1.  **Verificar o funcionamento do Docker:**

    -   No terminal da sua distribuição Linux, execute o comando:

***docker --version***

![Interface gráfica do usuário, Texto, Aplicativo Descrição gerada
automaticamente](./media/media/image24.png){width="4.6360640857392825in"
height="1.3126837270341207in"}

-   Verifique se a versão do Docker é exibida corretamente.

2.  **Executar um contêiner de teste:**

    -   Execute o comando para testar a instalação:

***docker run hello-world***

-   Se o Docker estiver configurado corretamente, você verá uma mensagem
    confirmando que o contêiner foi executado com sucesso.

![Texto Descrição gerada
automaticamente](./media/media/image25.png){width="7.5in"
height="5.879166666666666in"}

## 

## Passo 5: Configuração do NVIDIA CUDA com Docker Desktop no WSL para WebODM

1.  **Conferir se Driver NVIDIA e as Ferramentas com CUDA estão
    instaladas/reconhecidas no seu ambiente.**

> Geralmente o Ubuntu já instala/reconhece um driver da NVIDIA com CUDA,
> teste isso com o comando:

**nvidia-smi**

![Texto Descrição gerada
automaticamente](./media/media/image26.png){width="5.989583333333333in"
height="3.3333333333333335in"}

Você já pode ver na imagem acima que há um drive NVIDIA e os recursos
CUDA no WSL, inclusive qual é a minha placa de Vídeo.

2.  **Instalar/Atualizar Drive NVIDIA e CUDA ToolKit.**

> É recomendável instalar/atualizar o Drive NVIDIA e os recursos CUDA.

a)  **Entre no site [CUDA Toolkit
    Downloads](https://developer.nvidia.com/cuda-downloads)
    (https://developer.nvidia.com/cuda-downloads). Escolha o que você
    precisa(no meu caso a Arquitetura é x86_64).**

b)  **Note na imagem abaixo, que no meu caso, a versão é a mesma que já
    foi reconhecida acima, isto é, 12.6. Então eu não necessitaria de
    instalar/atualizar.\
    **

![Interface gráfica do usuário Descrição gerada
automaticamente](./media/media/image27.png){width="5.989583333333333in"
height="5.104166666666667in"}

c)  **No caso de instalar/atualizar pasta copiar, colar e dar Enter em
    cada um dos comandos em "instalation instructions" no WSL.**

![Texto Descrição gerada
automaticamente](./media/media/image28.png){width="6.0in"
height="3.9854166666666666in"}

3.  **Instale o NVIDIA Container Toolkit**

<!-- -->

a)  **Entre neste link e Escolha "Installing with Apt": [Installing the
    NVIDIA Container Toolkit --- NVIDIA Container Toolkit 1.16.0
    documentation](https://d.docs.live.net/8d0895fbbe44b0fb/Documentos/Installing%20the%20NVIDIA%20Container%20Toolkit%20—%20NVIDIA%20Container%20Toolkit%201.16.0%20documentation)(https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html#installing-with-apt).**

![Interface gráfica do usuário, Texto, Aplicativo, chat ou mensagem de
texto Descrição gerada
automaticamente](./media/media/image29.png){width="5.989583333333333in"
height="3.8125in"}

b)  **No terminal do WSL, use os comando da instalação com Apt para
    realizar a instalação do NVIDIA CONTAINER TOOLKIT.**

![Interface gráfica do usuário, Texto, Aplicativo Descrição gerada
automaticamente](./media/media/image30.png){width="6.0in"
height="3.2708333333333335in"}

VEJA O EXEMPLO:

![Texto Descrição gerada
automaticamente](./media/media/image31.png){width="6.0in"
height="3.9506944444444443in"}

Digitando novamente o comando **nvidia-smi** você verá o DRIVE e os
Recurso CUDA instalados e ativos.

![Texto Descrição gerada
automaticamente](./media/media/image32.png){width="5.989583333333333in"
height="3.3854166666666665in"}

4.  **OPCIONAL: NVIDIA System Management Interface (nvidia-settings)**

Você pode instalar este pequeno aplicativo da NVIDIA para visualizar sua
GPU. Ela tem uma interface gráfica nativa da NVIDIA para gerenciar
configurações da GPU, incluindo monitoramento de uso de GPU e ajuste de
parâmetros.

**sudo apt install nvidia-settings**

**nvidia-settings**

5.  **Reinicie o Computador e abra o Docker e o WSL**

![Tela de um aparelho eletrônico Descrição gerada
automaticamente](./media/media/image33.png){width="6.0in"
height="7.0625in"}

![Tela de computador Descrição gerada
automaticamente](./media/media/image34.png){width="5.989583333333333in"
height="6.114583333333333in"}

# CONCLUSÃO:

Se você concluiu com êxito esta etapa acima, pode agora em poucos passos
chegar a instalação do WebODM em sua máquina. Basta clicar no link
abaixo e começar.

***INSTALAÇÃO E TESTE DO WebODM COM GPU***
