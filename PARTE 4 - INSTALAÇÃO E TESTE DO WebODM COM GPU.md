# PARTE IV - INSTALAÇÃO E TESTE DO WebODM COM GPU

# ***Como Processei um Bloco de 1500 Imagens no WebODM Gratuito num I5 com GPU RTX 3060 e 32GB de RAM***

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

[PARTE IV - INSTALAÇÃO E TESTE DO WebODM COM GPU
[1](#parte-iv---instalação-e-teste-do-webodm-com-gpu)](#parte-iv---instalação-e-teste-do-webodm-com-gpu)

[*Como Processei um Bloco de 1500 Imagens no WebODM Gratuito num I5 com
GPU RTX 3060 e 32GB de RAM*
[1](#como-processei-um-bloco-de-1500-imagens-no-webodm-gratuito-num-i5-com-gpu-rtx-3060-e-32gb-de-ram)](#como-processei-um-bloco-de-1500-imagens-no-webodm-gratuito-num-i5-com-gpu-rtx-3060-e-32gb-de-ram)

[TUTORIAL DE INSTALAÇÃO E TESTE DO WebODM COM GPU
[1](#tutorial-de-instalação-e-teste-do-webodm-com-gpu)](#tutorial-de-instalação-e-teste-do-webodm-com-gpu)

[Abra o WebODM para Teste
[5](#abra-o-webodm-para-teste)](#abra-o-webodm-para-teste)

[Verifique se o WebODM Está Usando a GPU
[7](#verifique-se-o-webodm-está-usando-a-gpu)](#verifique-se-o-webodm-está-usando-a-gpu)

## 

## TUTORIAL DE INSTALAÇÃO E TESTE DO WebODM COM GPU

Uma vez que, seguindo os passos anteriores, você reiniciou seu
computador com o WSL e sua Distribuição instalados, Com o Docker
instalado e configurado e com todos os drivers NVIDIA CUDA atualizados,
prossiga para a instalação do WebODM.

Página oficial de instalação: [WebODM: Manual Installation
(Docker)](https://github.com/OpenDroneMap/WebODM/?tab=readme-ov-file#manual-installation-docker)(
https://github.com/OpenDroneMap/WebODM/?tab=readme-ov-file#manual-installation-docker)

Usaremos esses simples comandos, porém com uma pequena modificação:

![](./media/media/image1.png){width="6.0in"
height="1.6145833333333333in"}

1.  **Clone o Repositório do WebODM:**

***git clone https://github.com/OpenDroneMap/WebODM \--config
core.autocrlf=input \--depth 1***

![](./media/media/image2.png){width="7.489583333333333in"
height="1.5625in"}

2.  **Entre na Pasta do WebODM**

***cd WebODM\
***

> ![](./media/media/image3.png){width="7.5in"
> height="1.6041666666666667in"}

3.  **Inicie o WebODM com Suporte a GPU:**

Vamos modificar o commando de instalação original acrescentando no final
"---gpu" para forçar a instalação e inicialização do WeODM com GPU.

***./webodm.sh start \--gpu\
***

Como se pode observar na imagem abaixo, assim que executado o comando
***./webodm.sh start --gpu***, a GPU_NVIDIA é encontrada.

![](./media/media/image4.png){width="7.489583333333333in"
height="4.677083333333333in"}

OBS: Poderá ocorrer as seguintes mensagens de aviso como na imagem a
seguir, mas elas não comprometerão a instalação:\
![](./media/media/image5.png){width="7.489583333333333in"
height="4.385416666666667in"}

Esta parte irá demorar bastante na primeira execução, mas se tudo
ocorrer bem, no final você terá esta tela:\
![Texto Descrição gerada
automaticamente](./media/media/image6.png){width="7.5in"
height="4.398611111111111in"}

## 

## 

## Abra o WebODM para Teste

Uma vez que a imagem acima indicou o endereço do WebODM, acesse a
Interface do WebODM assim:

1.  Abra um navegador e digite esse endereço para
    \[http://localhost:8000\](<http://localhost:8000>).

![](./media/media/image7.png){width="7.489583333333333in"
height="5.229166666666667in"}

2.  Crie um Novo Usuário e Senha.

**OBS: NUNCA DEIXE DE ANOTAR ESSES DADOS DE LOGIN, POIS UMA VEZ
PERDIDOS, A RECUPERAÇÃO É MUITO DIFÍCIL OU MESMO IMPOSSÍVEL.**

![](./media/media/image8.png){width="7.489583333333333in"
height="3.1979166666666665in"}

Parabéns!\
Seu WebODM foi instalado.

![Interface gráfica do usuário, Texto, Aplicativo, Email Descrição
gerada automaticamente](./media/media/image9.png){width="7.5in"
height="3.779166666666667in"}

3.  Inicie um processamento de teste no WebODM

Indicamos seguir esta aula: **[Como processar um ortomosaico no
WebODM](https://www.youtube.com/watch?v=ZDyX-zuvg9g)(**https://www.youtube.com/watch?v=ZDyX-zuvg9g)

Monitore o Uso da GPU: Use o comando \`nvidia-smi\` no terminal do WSL
para verificar se a GPU está sendo usada pelo Docker durante o
processamento de dados do WebODM.

## Verifique se o WebODM Está Usando a GPU

Uma vez que o processamento acima comece a rodar, para acompanhar o uso
da GPU há vários meios. Destacamos estes:

-   Monitore o Uso da GPU pelo Gerenciador de Tarefas na aba Performance
    =\> Elemento GPU

![Interface gráfica do usuário Descrição gerada
automaticamente](./media/media/image10.png){width="3.7292508748906386in"
height="4.445138888888889in"}

-   Monitore o Uso da GPU nvidia-settings:

![Interface gráfica do usuário Descrição gerada
automaticamente](./media/media/image10.png){width="3.5280030621172354in"
height="4.377140201224847in"}

-   Ou usando o NVIDIA-SMI , abrindo uma nova instância do Ubuntu e
    executando o comando ***watch -n 1 nvidia-smi***.

![Texto Descrição gerada
automaticamente](./media/media/image11.png){width="7.44799978127734in"
height="3.1759995625546806in"}

## CONCLUSÃO:

Agora que você obteve sucesso instalando o WebODM, não é bom deixar de
dar manutenção nessa instalação. Por isso, neste link ***MANUTENÇÃO DO
WebODM E CONCLUSÃO*** você obterá orientações sobre algumas das mais
comuns dúvidas de como lidar com problemas.
