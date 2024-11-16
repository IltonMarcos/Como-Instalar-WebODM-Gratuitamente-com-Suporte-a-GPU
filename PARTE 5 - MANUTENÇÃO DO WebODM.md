# PARTE V - MANUTENÇÃO DO WebODM E CONCLUSÃO

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

**SUBTÍTULO: *PARTE 5 - ******MANUTENÇÃO DO WebODM E CONCLUSÃO***

## 

# Sumário {#sumário .TOC-Heading}

[PARTE V - MANUTENÇÃO DO WebODM E CONCLUSÃO
[1](#parte-v---manutenção-do-webodm-e-conclusão)](#parte-v---manutenção-do-webodm-e-conclusão)

[*Como Processei um Bloco de 1500 Imagens no WebODM Gratuito num I5 com
GPU RTX 3060 e 32GB de RAM*
[1](#como-processei-um-bloco-de-1500-imagens-no-webodm-gratuito-num-i5-com-gpu-rtx-3060-e-32gb-de-ram)](#como-processei-um-bloco-de-1500-imagens-no-webodm-gratuito-num-i5-com-gpu-rtx-3060-e-32gb-de-ram)

[INTRODUÇÃO: [2](#introdução)](#introdução)

[1. RODANDO O WebODM [2](#rodando-o-webodm)](#rodando-o-webodm)

[1.1 Iniciar o WebODM [2](#iniciar-o-webodm)](#iniciar-o-webodm)

[1.2 Acessar a Interface Web do WebODM
[5](#acessar-a-interface-web-do-webodm)](#acessar-a-interface-web-do-webodm)

[1.3 Carregar e Processar Imagens
[6](#carregar-e-processar-imagens)](#carregar-e-processar-imagens)

[2. Atualizando o WebODM
[6](#atualizando-o-webodm)](#atualizando-o-webodm)

[2.1 Verificar Atualizações Disponíveis
[6](#verificar-atualizações-disponíveis)](#verificar-atualizações-disponíveis)

[2.2 Reiniciar o WebODM Após a Atualização
[7](#reiniciar-o-webodm-após-a-atualização)](#reiniciar-o-webodm-após-a-atualização)

[3. Corrigindo Problemas Comuns no WebODM
[7](#corrigindo-problemas-comuns-no-webodm)](#corrigindo-problemas-comuns-no-webodm)

[3.1 Problema: WebODM Não Inicia ou inicia mas não aparece que tem GPU
[7](#problema-webodm-não-inicia-ou-inicia-mas-não-aparece-que-tem-gpu)](#problema-webodm-não-inicia-ou-inicia-mas-não-aparece-que-tem-gpu)

[3.2 Problema: A GPU Não Está Sendo Detectada("GPU Not Found")
[7](#problema-a-gpu-não-está-sendo-detectadagpu-not-found)](#problema-a-gpu-não-está-sendo-detectadagpu-not-found)

[3.3 Problema: Erro de Autenticação ou Permissão
[9](#problema-erro-de-autenticação-ou-permissão)](#problema-erro-de-autenticação-ou-permissão)

[3.4 Problema: WebODM Não Processa as Imagens
[9](#problema-webodm-não-processa-as-imagens)](#problema-webodm-não-processa-as-imagens)

[4. Comandos Adicionais Úteis
[9](#comandos-adicionais-úteis)](#comandos-adicionais-úteis)

[CONCLUSÃO [9](#conclusão)](#conclusão)

Este tutorial detalha como operar, atualizar e corrigir problemas comuns
no WebODM instalado com o Docker Desktop no Windows 10/11.

## INTRODUÇÃO:

## 1. RODANDO O WebODM

### 1.1 Iniciar o WebODM

Para iniciar o WebODM ***é imprescindível que o Docker Desktop esteja
aberto e ativo***.

![](./media/media/image1.png){width="7.5in" height="4.25in"}

Assim, é possível rodar o WebODM abrindo o terminal do WSL e navegando
até o diretório onde o WebODM foi instalado.

![](./media/media/image2.png){width="3.9479166666666665in"
height="8.322916666666666in"}

Execute esses comandos quando entrar no WSL:

***cd WebODM***

***./webodm.sh start --gpu***

![](./media/media/image3.png){width="5.552083333333333in"
height="1.5in"}

Outra forma de Abrir o WebODM:

Na maioria das vezes que você abre o Docker Desktop ele já inicia
automaticamente o WebODM(a última imagem que você rodou quando fechou).
Então, uma vez que você abriu o Docker Desktop e o WebODM estiver
rodando, pode entrar na página do localhost:8000.

![](./media/media/image4.png){width="7.489583333333333in"
height="4.677083333333333in"}

Se não estiver rodando, como na imagem abaixo, pode clicar no Play que
ele vai iniciar o WebODM:

![](./media/media/image5.png){width="7.489583333333333in"
height="4.416666666666667in"}

### 1.2 Acessar a Interface Web do WebODM

Abra um navegador da web e acesse:

[***http://localhost:8000***](http://localhost:8000)

![Interface gráfica do usuário, Texto, Aplicativo, Email Descrição
gerada automaticamente](./media/media/image6.png){width="7.5in"
height="4.985416666666667in"}

### 1.3 Carregar e Processar Imagens

Clique em \'Create New Project\' para iniciar um novo projeto. Siga as
instruções para fazer o upload das imagens e definir os parâmetros de
processamento. Clique em \'Start Processing\' para iniciar o
processamento das imagens.

<https://youtu.be/ZDyX-zuvg9g>

## 2. Atualizando o WebODM

### 2.1 Verificar Atualizações Disponíveis

Acesse o repositório oficial do WebODM:
https://github.com/OpenDroneMap/WebODM e verifique se há atualizações
disponíveis.

Se tem uma versão mais nova, no terminal do WSL, execute os seguintes
comandos para navegar até o diretório do WebODM e atualizar o WebODM:

***cd WebODM***

***./webodm.sh update***

### 2.2 Reiniciar o WebODM Após a Atualização

Após a atualização, reinicie o WebODM:

**./webodm.sh restart --gpu**

## 3. Corrigindo Problemas Comuns no WebODM

### 3.1 Problema: WebODM Não Inicia ou inicia mas não aparece que tem GPU

Verifique se o Docker Desktop está em execução. Inicie o Docker Desktop,
se necessário. Certifique-se de que a distribuição Linux do WSL (ex.:
Ubuntu) está em execução. No terminal do WSL, execute:

***docker ps***

Se algum contêiner não estiver em execução, reinicie o WebODM:

***./webodm.sh restart --gpu***

### 3.2 Problema: A GPU Não Está Sendo Detectada("GPU Not Found")

ONDE OBTEMOS ESSA INSTRUÇÃO?

AQUI EM [**Common
Troubleshooting**](https://github.com/OpenDroneMap/WebODM/?tab=readme-ov-file#common-troubleshooting)

![Interface gráfica do usuário, Texto Descrição gerada
automaticamente](./media/media/image7.png){width="6.740523840769904in"
height="0.7709405074365704in"}

Se você tiver qualquer problema com esse aviso de que não há GPU
encontrada "***GPU use was requested, but no GPU has been found***" siga
as instruções abaixo:

No resultado final desse comando deve aparecer algo como o exemplo
abaixo. Assim seu WebODM estará usando os recursos da GPU:

![Texto Descrição gerada
automaticamente](./media/media/image8.png){width="7.197916666666667in"
height="7.0in"}

### 3.3 Problema: Erro de Autenticação ou Permissão

Verifique se seu usuário WSL tem permissões para usar o Docker:

**sudo usermod -aG docker \$USER**

Reinicie o terminal após adicionar o usuário ao grupo Docker.

### 3.4 Problema: WebODM Não Processa as Imagens

-   Verifique os logs de processamento no WebODM para identificar erros
    específicos.

-   Certifique-se de que todos os contêineres Docker necessários estejam
    em execução.

-   Verifique se há espaço em disco e memória RAM suficientes.

-   Revise a instalação.

## 4. Comandos Adicionais Úteis

-   Parar o WebODM:

Com o terminal aberto e rodando o WebODM digite: ***Ctrl + C*** para
parar suavemente. Ou repita esse comando para parar bruscamente.

Ou em outro terminal do ubuntu execute:

**./webodm.sh stop**

-   Reiniciar o WebODM:

***./webodm.sh restart***

-   Verificar Logs de Execução:

***docker logs \<container_id\>***

-   Verificar Uso da GPU:

***nvidia-smi***

Se você quiser revisar todo fluxo de instalação, entre neste link
***SÉRIE DE ARTIGOS - COMO INSTALAR WEBODM GRATUITAMENTE NO WINDOWS COM
SUPORTE A GPU*** ou fale conosco pelo portal da ***GeoOne.***

## CONCLUSÃO

Com este tutorial, você adquiriu os conhecimentos necessários para
operar, atualizar e corrigir problemas comuns no WebODM instalado no
Docker Desktop no Windows 10 ou 11. As instruções fornecidas visam
garantir uma experiência de uso estável e eficiente, maximizando o
aproveitamento dos recursos do sistema, incluindo a aceleração de GPU
para processamento intensivo de imagens. A manutenção contínua e o
monitoramento regular da configuração do WebODM e Docker ajudarão a
evitar problemas futuros e a garantir que o sistema funcione de maneira
otimizada. Seguindo as práticas recomendadas, você estará bem preparado
para utilizar todo o potencial do WebODM em seus projetos de mapeamento
e análise geoespacial.
