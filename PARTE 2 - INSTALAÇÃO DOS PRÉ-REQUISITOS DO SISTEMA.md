# **PARTE II - INSTALAÇÃO DOS PRÉ-REQUISITOS DO SISTEMA**

# *Como Processei um Bloco de 1500 Imagens no WebODM Gratuito num I5 com GPU RTX 3060 e 32GB de RAM*

**ETAPAS DE INSTALAÇÃO DO WebODM**

**1. TÍTULO: COMO INSTALAR WEBODM GRATUITAMENTE NO WINDOWS COM SUPORTE A
GPU -- PARTE I**

**SUBTÍTULO: *PARTE I - INTRODUÇÃO E REQUISITOS PARA INSTALAÇÃO DO
WebODM***

**2. TÍTULO: COMO INSTALAR WEBODM GRATUITAMENTE NO WINDOWS COM SUPORTE A
GPU -- PARTE II**

**SUBTÍTULO: *PARTE 2 - ******INSTALAÇÃO DOS PRÉ-REQUISITOS DO
SISTEMA***

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

[**PARTE II - INSTALAÇÃO DOS PRÉ-REQUISITOS DO SISTEMA**
[1](#parte-ii---instalação-dos-pré-requisitos-do-sistema)](#parte-ii---instalação-dos-pré-requisitos-do-sistema)

[*Como Processei um Bloco de 1500 Imagens no WebODM Gratuito num I5 com
GPU RTX 3060 e 32GB de RAM*
[1](#como-processei-um-bloco-de-1500-imagens-no-webodm-gratuito-num-i5-com-gpu-rtx-3060-e-32gb-de-ram)](#como-processei-um-bloco-de-1500-imagens-no-webodm-gratuito-num-i5-com-gpu-rtx-3060-e-32gb-de-ram)

[1. INSTALAÇÃO E PREPARAÇÃO DO SISTEMA
[2](#instalação-e-preparação-do-sistema)](#instalação-e-preparação-do-sistema)

[1.1. Preparação do Sistema
[2](#preparação-do-sistema)](#preparação-do-sistema)

[1.1.1. Ativar a Virtualização da CPU
[2](#ativar-a-virtualização-da-cpu)](#ativar-a-virtualização-da-cpu)

[1.1.2. Atualizar Todos os Drivers do PC
[6](#atualizar-todos-os-drivers-do-pc)](#atualizar-todos-os-drivers-do-pc)

[1.1.3. Adicionar Recursos Nativos do Windows
[19](#adicionar-recursos-nativos-do-windows)](#adicionar-recursos-nativos-do-windows)

[2. Instalar ou Atualizar o Microsoft Visual C++ e Outros Recursos
[20](#instalar-ou-atualizar-o-microsoft-visual-c-e-outros-recursos)](#instalar-ou-atualizar-o-microsoft-visual-c-e-outros-recursos)

# 1. INSTALAÇÃO E PREPARAÇÃO DO SISTEMA

Se na Etapa anterior, você já verificou os requisitos e estes estão
plenamente satisfeitos, poderá saltar o que está pronto e concentrar-se
apenas no que lhe faltar desta parte da instalação.

## 1.1. Preparação do Sistema

Antes de instalar o WebODM com suporte a GPU no Windows, é necessário
realizar algumas configurações importantes no sistema. A primeira etapa
envolve a ativação da virtualização da CPU, que é essencial para o
funcionamento do WSL2 e do Docker.

### 1.1.1. Ativar a Virtualização da CPU

A virtualização da CPU permite que seu sistema operacional crie e
gerencie máquinas virtuais, o que é crucial para o WSL2 e Docker
operarem corretamente. Dependendo do seu processador, você precisará
ativar a tecnologia Intel VT-x ou AMD-V na BIOS/UEFI.

#### Passos para Acessar BIOS/UEFI e Habilitar a Virtualização:

1.  **Reinicie o Computador para acessar a BIOS/UEFI:**

    -   Durante o boot, pressione a tecla específica para entrar na
        configuração do BIOS/UEFI. Esta tecla varia de acordo com o
        fabricante do seu computador, mas geralmente é uma das
        seguintes: F2, F10, Del, Esc.

![Tela de televisão ligada Descrição gerada
automaticamente](./media/media/image1.png){width="7.5in"
height="4.336805555555555in"}

Quando aparecer a mensagem da tela abaixo, chame o configuração da BIOS
com os comandos que aparecem na mensagem

![Tela de computador com texto preto sobre fundo branco Descrição gerada
automaticamente com confiança
média](./media/media/image2.png){width="7.5in"
height="4.190277777777778in"}

2.  **Localize as Configurações de Virtualização:**

    -   Uma vez no menu do BIOS/UEFI, navegue até a seção de
        configurações avançadas. As configurações de virtualização
        geralmente estão sob nomes como \"CPU Configuration\",
        \"Advanced\", \"Processor\" ou \"Northbridge\".

![Interface gráfica do usuário, Site Descrição gerada
automaticamente](./media/media/image3.jpeg){width="7.5in"
height="4.191666666666666in"}

-   Procure por opções chamadas **Intel VT-x** (para processadores
    Intel) ou **AMD-V** (para processadores AMD).

![Interface gráfica do usuário, Site Descrição gerada
automaticamente](./media/media/image4.jpeg){width="7.5in"
height="4.320138888888889in"}

3.  **Habilitar a Virtualização:**

    -   Se a virtualização estiver desativada, selecione a opção e
        altere para \"Enabled\" ou \"Ativado\".

    -   No caso de placas-mãe mais recentes, a opção pode ser rotulada
        como \"Intel Virtualization Technology\" ou \"SVM Mode\" para
        AMD.

4.  **Salvar e Sair:**

    -   Após habilitar a virtualização, salve as mudanças feitas no
        BIOS/UEFI. Normalmente, isso é feito pressionando F10 e
        confirmando a saída.

![Interface gráfica do usuário, Site Descrição gerada
automaticamente](./media/media/image5.jpeg){width="7.5in"
height="4.209027777777778in"}

![Interface gráfica do usuário Descrição gerada
automaticamente](./media/media/image6.png){width="6.863724846894138in"
height="3.3745778652668417in"}

-   O sistema será reiniciado e a virtualização estará habilitada.

5.  **Verifique se a Virtualização foi Ativada:**

    -   Depois que o sistema reiniciar, você pode verificar se a
        virtualização foi habilitada corretamente usando o Gerenciador
        de Tarefas:

        -   Abra o **Gerenciador de Tarefas** (Ctrl + Shift + Esc).

        -   Vá até a aba **Desempenho/Performance** e selecione **CPU**.

        -   Na seção de **virtualização**, verifique se está marcada
            como \"Ativado\".

![Tela de computador com jogo Descrição gerada
automaticamente](./media/media/image7.png){width="7.5in"
height="5.288194444444445in"}

#### Considerações Importantes:

-   **Segurança:** Habilitar a virtualização não apresenta riscos
    significativos de segurança, mas é essencial garantir que o seu
    BIOS/UEFI esteja atualizado para evitar incompatibilidades ou
    falhas.

-   **Assistência:** Se você não conseguir encontrar as configurações ou
    tiver problemas para habilitar a virtualização, consulte o manual da
    sua placa-mãe ou o site do fabricante para obter instruções
    específicas.

Ativar a virtualização da CPU é um passo fundamental para garantir que o
WSL2 e o Docker possam ser instalados e funcionem corretamente,
possibilitando o uso eficiente do WebODM com suporte a GPU.

### 1.1.2. Atualizar Todos os Drivers do PC

Drivers desatualizados podem causar problemas de desempenho,
incompatibilidades, e até mesmo falhas no sistema. Nesta seção, vamos
abordar as ferramentas recomendadas para atualizar os drivers do seu PC
e fornecer links diretos para os drivers de GPU, incluindo NVIDIA e
outras marcas.

#### Ferramentas Recomendadas para Atualização de Drivers

Existem várias ferramentas que podem ajudar a manter os drivers do seu
sistema atualizados. Mas não vamos sugerir nenhum, exceto a nativa do
Windows e o site oficial dos seus drivers:

1.  **Windows Update:**

    -   Embora não seja uma solução completa para todos os drivers, o
        Windows Update pode ser usado para garantir que os drivers
        principais do sistema estejam atualizados.

    -   Acesse **Configurações \> Atualização e Segurança \> Windows
        Update** e verifique se há atualizações disponíveis.

![Interface gráfica do usuário, Aplicativo Descrição gerada
automaticamente](./media/media/image8.png){width="7.5in"
height="5.302777777777778in"}

2.  **Site Oficial:**

    -   Busque no site oficial da sua máquina/acessório. Geralmente está
        em Suporte =\> Drivers.

#### Links para Drivers da NVIDIA 

1.  **DRIVER STUDIO NVIDIA:**

    -   A NVIDIA oferece drivers otimizados para suas GPUs, incluindo
        suporte a CUDA necessário para o WebODM.

    -   Você pode baixar a versão mais recente dos drivers da NVIDIA
        diretamente do site oficial:

    -   [Link para Drivers
        NVIDIA](https://www.nvidia.com/Download/index.aspx)

    -   Certifique-se de selecionar o modelo exato da sua GPU e o
        sistema operacional correto (Windows 11).

    -   Escolha seu modelo e clique em Find(Buscar):

![Interface gráfica do usuário, Site Descrição gerada
automaticamente](./media/media/image9.png){width="6.958333333333333in"
height="6.6875in"}

-   Faça o download e instale apenas seguindo o passo a passo (next,
    next\...)

![Interface gráfica do usuário, Site Descrição gerada
automaticamente](./media/media/image10.png){width="7.5in"
height="3.6131944444444444in"}

![Interface gráfica do usuário, Texto, Aplicativo, Email Descrição
gerada
automaticamente](./media/media/image11.png){width="3.9276312335958004in"
height="1.6668996062992125in"}

![Tela de computador com texto preto sobre fundo branco Descrição gerada
automaticamente](./media/media/image12.png){width="6.094600831146106in"
height="4.521464348206474in"}

![Tela de celular com aplicativo aberto Descrição gerada
automaticamente](./media/media/image13.png){width="6.1258552055993in"
height="4.563136482939632in"}

![Texto Descrição gerada automaticamente com confiança
média](./media/media/image14.png){width="6.094600831146106in"
height="4.542300962379702in"}

![Tela de celular com aplicativo aberto Descrição gerada
automaticamente](./media/media/image15.png){width="6.136272965879265in"
height="4.531882108486439in"}

2.  **Instale também a versão ToolKit CUDA;**

    -   Link para o driver: [CUDA Toolkit 12.6 Update 1 Downloads \|
        NVIDIA Developer](https://developer.nvidia.com/cuda-downloads)

    -   (https://developer.nvidia.com/cuda-downloads)

![Interface gráfica do usuário, Aplicativo Descrição gerada
automaticamente](./media/media/image16.png){width="7.5in"
height="4.46875in"}

![Interface gráfica do usuário, Texto, Aplicativo Descrição gerada
automaticamente](./media/media/image17.png){width="4.1047397200349955in"
height="1.8231714785651794in"}

![Interface gráfica do usuário, Aplicativo Descrição gerada
automaticamente](./media/media/image18.png){width="4.198502843394576in"
height="1.6356452318460193in"}

![Tela de celular com aplicativo aberto Descrição gerada
automaticamente](./media/media/image19.png){width="6.094600831146106in"
height="4.573555336832896in"}

![Interface gráfica do usuário, Site Descrição gerada
automaticamente](./media/media/image20.png){width="6.115436351706037in"
height="4.604809711286089in"}

![Tela de celular com aplicativo aberto Descrição gerada
automaticamente](./media/media/image21.png){width="6.094600831146106in"
height="4.563136482939632in"}

![Tela de computador com fundo verde Descrição gerada
automaticamente](./media/media/image22.png){width="6.14669072615923in"
height="4.552718722659668in"}

![Tela de celular com aplicativo aberto Descrição gerada
automaticamente](./media/media/image23.png){width="6.1258552055993in"
height="4.531882108486439in"}

![Tela de vídeo game Descrição gerada
automaticamente](./media/media/image24.png){width="6.115436351706037in"
height="4.531882108486439in"}

![Interface gráfica do usuário, Site Descrição gerada
automaticamente](./media/media/image25.png){width="6.14669072615923in"
height="4.6360640857392825in"}

![Interface gráfica do usuário, Aplicativo, Site Descrição gerada
automaticamente](./media/media/image26.png){width="6.1258552055993in"
height="4.552718722659668in"}

3.  **Permita a todos os usuários o acesso a GPU.**

    -   Abra o Painel de Controle da NVIDIA

![Tela de computador com jogo Descrição gerada
automaticamente](./media/media/image27.png){width="7.5in"
height="7.44375in"}

![Interface gráfica do usuário, Texto, Aplicativo, Email Descrição
gerada automaticamente](./media/media/image28.png){width="7.5in"
height="5.402083333333334in"}

Manter seus drivers atualizados com as ferramentas recomendadas e
através dos links fornecidos ajudará a evitar problemas e garantirá que
seu sistema esteja pronto para lidar com as demandas do WebODM com
suporte a GPU.

### 1.1.3. Adicionar Recursos Nativos do Windows

1.  **Recursos Adicionais do Windows:**

    -   Habilite o Hyper-V e a Plataforma de Máquinas Virtuais, que são
        necessários para o Docker Desktop.

    -   Para habilitar, vá para **Painel de Controle \> Programas \>
        Ativar ou desativar recursos do Windows**, e marque as opções
        **Hyper-V** e **Plataforma de Máquina Virtual**.

    -   Recomendamos que seja instalada também .NET Framework

![Interface gráfica do usuário, Aplicativo Descrição gerada
automaticamente](./media/media/image29.png){width="6.0in"
height="7.388888888888889in"}

**[NOTA: Esta Etapa acima exige a reinicialização do
sistema.]{.underline}**

# 2. Instalar ou Atualizar o Microsoft Visual C++ e Outros Recursos

***1. Baixar e Instalar o Visual C++ Redistributable:\
*** - Acesse o site oficial da Microsoft e baixe a versão mais recente
do [Visual C++
Redistributable](https://learn.microsoft.com/pt-br/cpp/windows/latest-supported-vc-redist?view=msvc-170#latest-microsoft-visual-c-redistributable-version).

![Tela de celular com texto branco sobre fundo preto Descrição gerada
automaticamente](./media/media/image30.png){width="6.0in"
height="4.716392169728784in"}

Escolha a Versão que condiz com a versão do Windows no seu Computador

![Interface gráfica do usuário, Texto Descrição gerada
automaticamente](./media/media/image31.png){width="4.927771216097987in"
height="3.0316732283464565in"}

\- Instale ou atualize a versão existente no seu computador(No meu caso
na imagem acima, não há a necessidade de atualizar uma vez que o meu já
está atualizado. Mas se tiver dúvidas quanto a atualização do seu,
clique em Reparar e siga clicando em Próximo até o fim).

Aqui estão os complementos que você deve instalar, com uma breve
descrição e um tutorial para instalação:

**2. .NET Framework**

-   **Descrição:** O .NET Framework é uma plataforma de desenvolvimento
    da Microsoft que fornece uma base para a criação e execução de
    aplicativos no Windows. É essencial para muitos aplicativos e
    ferramentas que utilizam tecnologias .NET.

-   **Para que Serve:** Necessário para a execução de aplicativos
    desenvolvidos com .NET Framework.

-   **Tutorial de Instalação:** Para instalar o .NET Framework, você
    pode baixar o instalador do site oficial e seguir o assistente de
    instalação.

    -   **Link de Download:** [Microsoft .NET
        Framework](https://dotnet.microsoft.com/download/dotnet-framework)

    -   **Tutorial:** [Instalação do .NET
        Framework](https://docs.microsoft.com/pt-br/dotnet/framework/install/)

**3. DirectX End-User Runtime**

-   **Descrição:** O DirectX End-User Runtime é um conjunto de APIs
    desenvolvidas pela Microsoft que permite que jogos e outras
    aplicações gráficas interajam com o hardware gráfico. Ele melhora a
    performance e a compatibilidade gráfica em jogos e aplicativos.

-   **Para que Serve:** Necessário para a execução de jogos e aplicações
    gráficas que utilizam DirectX. Pode ser necessário para algumas
    ferramentas GIS e de modelagem.

-   **Tutorial de Instalação:** Baixe e execute o instalador a partir do
    site oficial.

    -   **Link de Download:** [DirectX End-User
        Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=35)

    -   **Tutorial:** [Instalação do
        DirectX](https://support.microsoft.com/pt-br/help/179113/how-to-install-the-latest-version-of-directx)

**4. Java Runtime Environment (JRE) / Java Development Kit (JDK) -- ESTE
NÃO É NECESSÁRIO**

-   **Descrição:** O JRE fornece as bibliotecas e componentes
    necessários para executar aplicativos Java. O JDK inclui o JRE além
    de ferramentas de desenvolvimento para criar aplicativos Java.

-   **Para que Serve:** Necessário para executar e desenvolver
    aplicativos Java, incluindo algumas ferramentas GIS e de
    processamento de imagens.

-   **Tutorial de Instalação:** Faça o download da versão apropriada
    para o seu sistema e siga o assistente de instalação.

    -   **Link de Download:** [Java
        JDK](https://www.oracle.com/java/technologies/downloads/#jdk22-windows)

    -   **Tutorial:** [Instalação do
        JDK](https://docs.oracle.com/javase/8/docs/technotes/guides/install/install_overview.html)

**5. Python -- ESTE NÃO É NECESSÁRIO**

-   **Descrição:** Python é uma linguagem de programação versátil e
    popular, conhecida por sua simplicidade e legibilidade. É amplamente
    utilizado para desenvolvimento web, análise de dados, automação, e
    mais.

-   **Para que Serve:** Necessário para desenvolvimento em Python e para
    ferramentas que utilizam Python para scripts.

-   **Tutorial de Instalação:** Baixe a versão mais recente do Python e
    siga as instruções do instalador.

    -   **Link de Download:**
        [Python](https://www.python.org/downloads/)

    -   **Tutorial:** [Instalação do
        Python](https://docs.python.org/3/using/windows.html)

Esses complementos garantirão que seu ambiente de trabalho e uso de
ferramentas GIS esteja corretamente configurado e otimizado.

# CONCLUSÃO:

Se você concluiu corretamente esta etapa, prossiga para nosso próximo
artigo da série para preparar o ambiente de instalação do WebODM
clicando no link abaixo:

***A PREPARAÇÃO DO AMBIENTE COM WSL 2 E DOCKER DESKTOP***
