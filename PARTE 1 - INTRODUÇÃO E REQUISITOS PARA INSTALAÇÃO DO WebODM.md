# **PARTE I - INTRODUÇÃO E REQUISITOS PARA INSTALAÇÃO DO WebODM**

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

[**PARTE I - INTRODUÇÃO E REQUISITOS PARA INSTALAÇÃO DO WebODM**
[1](#parte-i---introdução-e-requisitos-para-instalação-do-webodm)](#parte-i---introdução-e-requisitos-para-instalação-do-webodm)

[*Como Processei um Bloco de 1500 Imagens no WebODM Gratuito num I5 com
GPU RTX 3060 e 32GB de RAM*
[1](#como-processei-um-bloco-de-1500-imagens-no-webodm-gratuito-num-i5-com-gpu-rtx-3060-e-32gb-de-ram)](#como-processei-um-bloco-de-1500-imagens-no-webodm-gratuito-num-i5-com-gpu-rtx-3060-e-32gb-de-ram)

[1. INTRODUÇÃO E REQUISITOS BÁSICOS
[1](#introdução-e-requisitos-básicos)](#introdução-e-requisitos-básicos)

[1.1. Visão Geral do WebODM
[1](#visão-geral-do-webodm)](#visão-geral-do-webodm)

[1.2. Comparação: Instalação Nativa vs. Instalação Manual
[4](#comparação-instalação-nativa-vs.-instalação-manual)](#comparação-instalação-nativa-vs.-instalação-manual)

[1.3. Requisitos de Instalação
[5](#requisitos-de-instalação)](#requisitos-de-instalação)

[1.4. Avisos Importantes [7](#avisos-importantes)](#avisos-importantes)

[1.5. Verificação do Sistema
[8](#verificação-do-sistema)](#verificação-do-sistema)

# 1. INTRODUÇÃO E REQUISITOS BÁSICOS

## 1.1. Visão Geral do WebODM

#### O que é o WebODM?

O WebODM (Web OpenDroneMap) é uma plataforma open-source destinada ao
processamento de imagens aéreas capturadas por drones, transformando-as
em produtos geoespaciais, como ortomosaicos, modelos digitais de
elevação (MDE), nuvens de pontos 3D, mapas de calor e outros. Utilizando
o WebODM, usuários podem processar grandes volumes de imagens
diretamente em seus computadores, permitindo a geração de produtos
cartográficos precisos sem a necessidade de softwares proprietários.

O WebODM é baseado no software OpenDroneMap (ODM), que é um conjunto de
ferramentas para reconstrução 3D, e oferece uma interface web amigável
que facilita a operação de todo o processo de mapeamento e análise de
dados.

Seu site oficial é o [Drone Mapping Software -
OpenDroneMap™](https://opendronemap.org/) (<https://opendronemap.org>),
onde pode ser encontradas todas as informações necessárias para
compreensão, instalação e uso deste poderoso aplicativo.

![Interface gráfica do usuário, Site Descrição gerada
automaticamente](./media/media/image1.png){width="6.0in"
height="2.9027777777777777in"}

OpenDroneMap é um ecossistema de software destacando os diversos
componentes disponíveis para o processamento e análise de imagens
aéreas. Aqui estão os principais projetos:

1.  **ODM (OpenDroneMap)**: Uma ferramenta de linha de comando para
    processar imagens aéreas. Desde sua criação em 2014, tornou-se o
    padrão de fato para o processamento de imagens de drones em código
    aberto.

2.  **WebODM**: Uma aplicação web amigável que oferece uma interface de
    usuário para o ODM. Permite visualização, armazenamento e análise de
    dados de imagens de drones, tornando o processamento de imagens mais
    acessível.

3.  **NodeODM**: Uma API REST leve para acessar o ODM. Também fornece
    uma interface mínima para executar funções básicas de processamento.

4.  **CloudODM**: Uma ferramenta de linha de comando para processar
    imagens aéreas na nuvem, permitindo o uso de recursos computacionais
    remotos.

5.  **PyODM**: Um SDK em Python para adicionar capacidades de
    processamento de imagens aéreas a outras aplicações.

6.  **ClusterODM**: Uma API para NodeODM que permite balanceamento de
    carga e escalabilidade horizontal fácil para processar grandes
    volumes de dados.

7.  **NodeMICMAC**: Um aplicativo e API REST para acessar o software
    MicMac, usado em projetos fotogramétricos.

8.  **FIELDimageR**: Um pacote em R para analisar imagens ortomosaicas
    de experimentos de campo agrícolas.

9.  **Find-GCP**: Uma ferramenta para localizar marcadores ArUco em
    fotos digitais, facilitando a georreferência de imagens.

Essas ferramentas fazem parte de um ecossistema colaborativo e de código
aberto, proporcionando uma ampla gama de soluções para coleta,
processamento, análise e exibição de dados aéreos, suportando diversas
necessidades e aplicações em fotogrametria e mapeamento.

#### Benefícios de usar WebODM com suporte a GPU

**Em 22 do 11 de 2021, "A densificação da nuvem de pontos da GPU chega
ao ODM e é rápida!"**

![Interface gráfica do usuário, Texto Descrição gerada
automaticamente](./media/media/image2.png){width="6.0in"
height="3.0819444444444444in"}

Ainda que nem todas as etapas ainda possam ser otimizadas pela GPU,
todavia, esse avanço foi notório e permanece em aprimoramento.

Sobre os benefícios podemos listar rapidamente:

-   **Aumento significativo da velocidade de processamento:** O uso de
    uma GPU (Unidade de Processamento Gráfico) pode acelerar
    drasticamente o tempo necessário para processar grandes conjuntos de
    dados, reduzindo horas de trabalho para minutos.

-   **Capacidade de processar grandes volumes de dados:** Com o suporte
    a GPU, o WebODM pode lidar com blocos maiores de imagens, permitindo
    a criação de mapas mais detalhados e precisos.

-   **Redução da carga na CPU:** O suporte a GPU alivia a CPU de grande
    parte do processamento pesado, liberando recursos do sistema para
    outras tarefas e garantindo maior estabilidade durante o
    processamento.

-   **Melhor eficiência energética:** Processar dados usando a GPU é
    geralmente mais eficiente em termos de consumo de energia, o que é
    especialmente útil em ambientes de trabalho prolongado.

-   **Acesso a tecnologias avançadas de processamento:** GPUs modernas
    oferecem suporte a tecnologias avançadas, como a computação
    paralela, que podem melhorar ainda mais o desempenho do WebODM.

Esta visão geral destaca a importância do WebODM como uma ferramenta
acessível e poderosa para profissionais que precisam transformar imagens
aéreas em dados geoespaciais úteis, especialmente quando combinado com o
suporte a GPU para maximizar o desempenho e a eficiência.

## 1.2. Comparação: Instalação Nativa vs. Instalação Manual

Ao instalar o WebODM no Windows, o usuário pode optar por dois métodos
principais: a Instalação Nativa, que é mais direta e simplificada, ou a
Instalação Manual, que oferece maior controle e desempenho,
especialmente com suporte a GPU. Cada método tem suas vantagens e
desvantagens, conforme detalhado abaixo.

#### Instalação Nativa (Windows Installer)

A Instalação Nativa utiliza um instalador específico para o Windows, que
automatiza grande parte do processo, tornando-o acessível mesmo para
usuários com pouca experiência técnica. Este método é ideal para quem
busca uma solução rápida e fácil de configurar.

![Homem de camisa azul Descrição gerada automaticamente com confiança
baixa](./media/media/image3.jpeg){width="2.5208333333333335in"
height="1.410090769903762in"}

[Instalação fácil do WebODM no Windows
(youtube.com)](https://www.youtube.com/watch?v=PQK71p-xD0I)

**IMPORTANTE**: APESAR DE ENSINAR NESTA SÉRIE COMO INSTALAR O WEBODM
MANUALMENTE(SEM A AQUISIÇÃO DE UM INSTALADOR) RECOMENDAMOS FORTEMENTE
QUE O USUÁRIO USE O INSTALADOR NATIVO(PAGO).

#### Instalação Manual (WSL2 + Docker + GPU)

A Instalação Manual envolve a configuração de um ambiente Linux dentro
do Windows usando o WSL2 (Windows Subsystem for Linux), além da
instalação do Docker para gerenciar containers. Este método permite a
integração do suporte a GPU, proporcionando um desempenho superior e
maior flexibilidade, mas requer um conhecimento técnico mais avançado.

#### Instalação Comparada

  --------------------------------------------------------------------------
     Característica        Instalação Nativa      Instalação Manual (WSL2 +
                          (Windows Installer)           Docker + GPU)
  --------------------- ------------------------ ---------------------------
     **Facilidade de         Alta (Processo       Baixa (Processo manual e
      Instalação**           automatizado)                demorado)

     **Desempenho**               Alto                      Médio

    **Suporte a GPU**             Sim                        Sim

      **Requisitos       Baixos (Usuário leigo)  Altos (Conhecimento técnico
       Técnicos**                                        necessário)

       **Tempo de         Rápido (3-5 minutos)     Moderado a Longo (20-30
     Configuração**                                       minutos)

    **Atualizações e      Automática (Simples)     Manual (mais complexo)
      Manutenção**                               

   **Compatibilidade**     Total com Windows      Requer Windows 10/11 com
                                                            WSL2
  --------------------------------------------------------------------------

A Instalação Nativa é recomendada para usuários que precisam de uma
solução rápida e estão dispostos a contribuir com o projeto espetacular
do OpenDroneMap e ainda obter maior desempenho e flexibilidade. Já a
Instalação Manual é mais adequada para usuários que querem experimentar
o WebODM ou mesmo realizar projetos pequenos a intermediário com um
processo de instalação mais complexo.

------------------------------------------------------------------------

## 1.3. Requisitos de Instalação

Antes de iniciar o processo de instalação do WebODM com suporte a GPU no
Windows, é essencial garantir que seu sistema atenda aos requisitos
mínimos e recomendados. Estes requisitos variam conforme o método de
instalação escolhido e o nível de desempenho esperado.

#### Hardware Mínimo e Recomendado

  -------------------------------------------------------------------------------
       Requisito                  Mínimo                     Recomendado
  ------------------- ------------------------------ ----------------------------
        **CPU**        Processador Intel Core i5 ou  Processador Intel Core i7/i9
                               AMD Ryzen 5                 ou AMD Ryzen 7/9

        **RAM**                   16 GB                     32 GB ou mais

   **Armazenamento**   50 GB de espaço livre em SSD   100 GB de espaço livre em
                                                               SSD NVMe

        **GPU**       NVIDIA GPU com suporte CUDA, 4 NVIDIA GPU com suporte CUDA,
                                 GB VRAM                  12 GB VRAM ou mais

       **Rede**        Conexão de internet estável   Conexão de internet estável
                            (para downloads e             de alta velocidade
                              atualizações)          
  -------------------------------------------------------------------------------

NOTA: Requisitos mínimos são aqueles que darão ao software nativo a
capacidade de abrir e processar pouquíssimas imagens. Requisitos
Recomendáveis podem também ser chamados de Básicos -- qualquer
configuração que vá além desta é preferível -- [PARA VER MAIS SOBRE
CONFIGURAÇÕES DE PCs PARA PROCESSAMENTO DE IMAGENS DE DRONES CLIQUE
AQUI](https://geoone.com.br/computador-imagens-drone/)(https://geoone.com.br/computador-imagens-drone).

#### Sistema Operacional: Windows 11 (Pro vs. Home)

O WebODM pode ser instalado tanto no Windows 11 Pro quanto no Home(Isto
também vale para o Windows 10), mas há algumas diferenças que podem
impactar o processo de instalação, especialmente ao usar o WSL2 (Windows
Subsystem for Linux).

-   **Windows 11 Pro:**

    -   Suporta totalmente o WSL2, Docker Desktop, e tecnologias de
        virtualização como o Hyper-V.

    -   Ideal para usuários que precisam de maior controle e
        flexibilidade.

    -   Recomendado para ambientes de trabalho profissionais e
        empresariais.

-   **Windows 11 Home:**

    -   Também suporta WSL2, mas pode ter limitações em funcionalidades
        avançadas como o Hyper-V.

    -   Mais adequado para uso doméstico e pequenas instalações.

    -   Pode exigir configurações adicionais para atingir o desempenho
        desejado.

**Nota:** NÃO RECOMENDAMOS A INSTALAÇÃO NO Windows Home. Embora o
Windows 11 Home suporte o WSL2, algumas funções avançadas necessárias,
disponíveis no Windows 11 Pro, podem não estar presentes ou serem
limitadas, o que pode afetar o desempenho e a facilidade de uso em
ambientes complexos.\
**ESTE TUTORIAL NÃO SE APLICA AO WINDOWS HOME(Leia sobre**
[AQUI](https://community.opendronemap.org/t/how-can-i-change-the-installation-directory-of-the-docker-image-in-windows-home/6647)**)**

#### GPU: Compatibilidade com CUDA

![Nice to know: What is
CUDA?](./media/media/image4.jpeg){width="3.2916666666666665in"
height="3.4791666666666665in"}

(<https://developer.nvidia.com/cuda-downloads>)

Antes de tratarmos sobre a tecnologia CUDA é imprescindível fazer duas
afirmações:

a)  A GPU no WebODM só tem aproveitamento se ela tiver tecnologia CUDA.

b)  Nem todas as etapas do processamento utilizam a GPU.

O suporte a CUDA (Compute Unified Device Architecture) da NVIDIA é
essencial para utilizar a GPU durante o processamento de dados no
WebODM. Abaixo estão os requisitos de compatibilidade:

-   **GPU Compatível:** Uma placa de vídeo NVIDIA com suporte a CUDA
    (por exemplo, séries GTX 10xx, RTX 20xx, RTX 30xx).

-   **Drivers CUDA:** Devem ser instalados tanto no Windows quanto no
    WSL2 para garantir o correto funcionamento.

-   **Versão CUDA:** Recomenda-se utilizar a versão mais recente
    compatível com sua GPU para obter o máximo desempenho.

Esses requisitos garantem que o seu sistema esteja pronto para instalar
e operar o WebODM com suporte a GPU de forma eficiente, proporcionando
um ambiente de trabalho robusto para o processamento de grandes volumes
de dados geoespaciais.

## 1.4. Avisos Importantes

Antes de prosseguir com a instalação do WebODM com suporte a GPU, é
crucial considerar alguns pontos importantes que podem impactar o
processo de instalação e o desempenho do software no seu sistema. Estes
avisos têm como objetivo evitar problemas comuns e alinhar as
expectativas dos usuários.

#### Declaração de Isenção de Responsabilidade

O conteúdo deste tutorial foi elaborado para fornecer orientações gerais
sobre a instalação e configuração do WebODM no Windows 11 com suporte a
GPU. No entanto, devido à diversidade de configurações de hardware e
software existentes, é importante destacar as seguintes limitações:

-   **Suporte Limitado ao Hardware Específico do Usuário:**

    -   Este tutorial foi projetado com base em configurações comuns e
        amplamente disponíveis, como processadores Intel ou AMD, GPUs
        NVIDIA com suporte a CUDA, e sistemas operacionais Windows 11.

    -   Não é possível garantir suporte ou compatibilidade para todas as
        configurações de hardware. Usuários com componentes ou sistemas
        menos comuns podem enfrentar dificuldades que não são abordadas
        diretamente neste guia.

-   **Configurações Podem Variar Conforme o Sistema e Hardware do
    Usuário:**

    -   As instruções fornecidas aqui são aplicáveis em uma ampla gama
        de situações, mas podem necessitar de ajustes conforme as
        especificidades do sistema do usuário.

    -   Configurações como a versão do Windows, a marca e modelo da GPU,
        a quantidade de RAM disponível, e até mesmo a versão dos drivers
        instalados podem influenciar o processo de instalação e o
        desempenho final do WebODM.

    -   Os comandos e configurações mencionados são ilustrativos e podem
        precisar ser adaptados para atender às necessidades do seu
        sistema específico.

Esses avisos servem para preparar o usuário para possíveis variações no
processo de instalação e para incentivá-lo a realizar verificações e
ajustes conforme necessário. A leitura completa e a compreensão dos
requisitos e passos sugeridos ajudarão a minimizar problemas e garantir
uma instalação bem-sucedida.

## 1.5. Verificação do Sistema

Antes de iniciar o processo de instalação do WebODM, é essencial
realizar uma verificação detalhada do sistema para garantir que ele
atende a todos os requisitos necessários. Esta etapa permitirá
identificar possíveis limitações e fazer os ajustes necessários antes de
prosseguir com a instalação.

#### Como Obter Informações Sobre o Sistema (Pro vs. Home)

Há várias maneiras de se obter informações sobre seu PC. Listamos
algumas:

1.  **Verificando a Edição do Windows e outras informações:**

    -   Pressione Win + I para abrir as Configurações do Windows.

    -   Navegue até **Sistema \> Sobre**.

    -   Em \"Especificações do Windows\", você verá a edição do Windows
        (Pro ou Home) que está instalada no seu computador.

> ![Tela de computador com texto preto sobre fundo branco Descrição
> gerada automaticamente](./media/media/image5.png){width="7.5in"
> height="5.59375in"}

-   Se estiver usando o Windows 11 Home e desejar atualizar para o
    Windows 11 Pro, você pode fazê-lo por meio da [Microsoft
    Store](https://support.microsoft.com/pt-br/windows/atualiza%C3%A7%C3%A3o-do-windows-home-para-windows-pro-ef34d520-e73f-3198-c525-d1a218cc2818).

2.  **Verificando a Versão do Windows:**

    -   Na mesma tela de \"Sobre\", verifique a versão do Windows
        instalada. Recomenda-se utilizar a versão mais recente
        disponível para garantir a compatibilidade com o WSL2 e outras
        ferramentas.

#### Verificação de Hardware: CPU, GPU, RAM

1.  **Verificando a CPU e a Possibilidade de Virtualização:**

    -   Pressione Ctrl + Shift + Esc para abrir o Gerenciador de
        Tarefas.

    -   Vá para a aba **Desempenho(ou Performance)** e selecione
        **CPU**.

![Tela de computador com jogo Descrição gerada
automaticamente](./media/media/image6.png){width="7.5in"
height="5.288194444444445in"}

-   Aqui você verá o modelo e as especificações da sua CPU. ***O
    principal item a ser verificado é "Virtualization(Virtualização):
    Enabled(Habilitado) ou Unabled(Inabilitado)***. Em Instalação
    mostraremos como habilitar. Compare isso com os requisitos mínimos e
    recomendados mencionados anteriormente.

2.  **Verificando a GPU:**

    -   Ainda na aba **Desempenho** do Gerenciador de Tarefas, selecione
        **GPU**.

    -   Verifique o modelo da sua GPU e a quantidade de memória VRAM
        disponível.

    -   A GPU deve ser compatível com CUDA para suportar o processamento
        acelerado no WebODM.

![Tela de computador com jogo Descrição gerada
automaticamente](./media/media/image7.png){width="7.5in"
height="4.442361111111111in"}

3.  **Verificando a RAM:**

    -   No Gerenciador de Tarefas, selecione **Memória** na aba
        **Desempenho**.

    -   Verifique a quantidade total de RAM instalada e compare com os
        requisitos recomendados.

    -   Idealmente, deve haver pelo menos 32 GB de RAM
        disponível(Available) para garantir um desempenho ótimo,
        especialmente ao processar grandes volumes de imagens, como é o
        caso testado neste tutorial em que foram processadas 1500 imagem
        em alta resolução.

![Tela de computador com jogo Descrição gerada
automaticamente](./media/media/image8.png){width="6.828674540682415in"
height="4.026388888888889in"}

#### Verificação de Compatibilidade CUDA

1.  **Instalando o NVIDIA Control Panel:**

    -   Se ainda não estiver instalado, baixe o [Painel de Controle
        NVIDIA da Microsoft
        Store](https://apps.microsoft.com/detail/9nf8h0h7wmlt?launch=true&mode=full&hl=pt-br&gl=br&ocid=bingwebsearch).

![Interface gráfica do usuário, Site Descrição gerada
automaticamente](./media/media/image9.png){width="7.5in"
height="4.6875in"}

![Interface gráfica do usuário, Aplicativo Descrição gerada
automaticamente](./media/media/image10.png){width="7.5in"
height="3.6944444444444446in"}

![Interface gráfica do usuário, Texto, Aplicativo, Email Descrição
gerada
automaticamente](./media/media/image11.png){width="5.822916666666667in"
height="4.947916666666667in"}

-   Abra o painel e navegue até **Informações do Sistema** para
    verificar a versão do driver e outras especificações da GPU.

![Interface gráfica do usuário, Aplicativo Descrição gerada
automaticamente](./media/media/image12.png){width="7.5in"
height="4.410416666666666in"}

#### Verificação das Exigências para a Instalação do Docker(adiante veremos como instalar)

1.  **Verifique se há compatibilidade com WSL2:**

    -   Docker Desktop requer o WSL2 como backend para funcionar no
        Windows 10/11.

    -   Verifique se sua versão do Windows suporta WSL2 (disponível em
        Windows 10 versão 1903 ou superior e Windows 11).

    -   Pressione Win + I para abrir as Configurações do Windows.

    -   Navegue até **Sistema \> Sobre**.

    -   Em \"Especificações do Windows\", você verá a edição do Windows
        que está instalada no seu computador.

![Texto Descrição gerada
automaticamente](./media/media/image13.png){width="7.041666666666667in"
height="2.6770833333333335in"}

2.  **Espaço de Armazenamento:**

    -   Docker requer espaço significativo em disco, especialmente se
        você estiver trabalhando com containers grandes ou múltiplos.
        Certifique-se de ter pelo menos 50 GB de espaço livre, com
        preferência para armazenamento em SSD para melhor desempenho.

    -   Veja um exemplo na imagem abaixo do tamanho do Docker depois de
        instalado e utilizado para o processamento do bloco de 1500
        imagens(Recomenda-se para essa quantidade de imagens um SSD de
        1TB)

![](./media/media/image14.png){width="6.0in"
height="0.48194444444444445in"}

Essas verificações adicionais garantem que o Docker Desktop possa ser
instalado e executado corretamente no seu sistema, permitindo que você
utilize o WebODM com suporte a GPU de forma eficaz e sem contratempos.

CONCLUSÃO:

Caso lhe falte requisitos para instalar o WebODM, prossiga para o
próximo artigo da Série clicando no link abaixo:

***PARTE 2 - INSTALAÇÃO DOS PRÉ-REQUISITOS DO SISTEMA***
