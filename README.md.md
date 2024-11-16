**COMO INSTALAR WEBODM GRATUITAMENTE NO WINDOWS COM SUPORTE A GPU**

*Como Processei um Bloco de 1500 Imagens no WebODM Gratuito num I5 com
GPU RTX 3060 e 32GB de RAM*

INTRODUÇÃO:

O **WebODM** é uma poderosa plataforma de código aberto para
processamento de imagens aéreas e criação de modelos tridimensionais,
amplamente utilizada por profissionais e entusiastas de drones para
análise geoespacial. Este tutorial é voltado para usuários que
instalaram o WebODM no **Docker Desktop** em sistemas **Windows 10 ou
11** e fornece orientações detalhadas sobre como operar, atualizar e
corrigir problemas comuns encontrados durante o uso do WebODM. Através
deste guia, você aprenderá como iniciar e utilizar o WebODM, garantir
que sua instalação esteja sempre atualizada e eficiente, e como
solucionar problemas comuns que podem surgir, como a não detecção da GPU
ou erros de permissão. Este tutorial é ideal tanto para usuários
iniciantes quanto para aqueles que já possuem alguma experiência com
Docker e WSL.

# Série de Artigos: Como Instalar WebODM Gratuitamente no Windows com Suporte a GPU

Esta série de artigos foi desenvolvida para guiar usuários da
[GEOONE](https://portal.geoone.com.br/) e demais interessados através do
processo completo de instalação e operação do
[WebODM](https://github.com/OpenDroneMap/WebODM) (Open Drone Map) com
suporte a
[GPU](https://learn.microsoft.com/pt-br/windows/wsl/tutorials/gpu-compute)
no Windows, utilizando o Docker Desktop e o WSL 2. Ao longo de cinco
partes, abordaremos desde a introdução e os requisitos necessários até a
manutenção e otimização do software. Esta série é especialmente útil
para aqueles que desejam utilizar o WebODM de forma gratuita em
ambientes Windows, aproveitando ao máximo o desempenho do hardware
disponível, como processadores gráficos (GPUs).

## Como Instalar WebODM Gratuitamente no Windows com Suporte a GPU -- Parte I

**Subtítulo: Parte 1 - Introdução e Requisitos para Instalação do
WebODM**

Na primeira parte, discutiremos o que é o WebODM, seus principais usos e
benefícios, especialmente para usuários que desejam realizar
processamento de imagens aéreas e criar modelos 3D em seus projetos.
Também cobriremos os requisitos mínimos e recomendados para a instalação
do WebODM com suporte a GPU, incluindo hardware, software e
configurações específicas para garantir um desempenho ideal.

***LINK PARA ESTE ARTIGO***

## Como Instalar WebODM Gratuitamente no Windows com Suporte a GPU -- Parte II

**Subtítulo: Parte 2 - Instalação dos Pré-Requisitos do Sistema**

Nesta segunda parte, detalharemos a instalação de todos os
pré-requisitos necessários para o funcionamento do WebODM no Windows.
Instruções passo a passo serão fornecidas para a instalação do Git,
Docker Desktop, Python, Pip, e qualquer outro componente essencial. Esta
parte é crucial para garantir que o ambiente do usuário esteja pronto
para a instalação do WebODM.

***LINK PARA ESTE ARTIGO***

## Como Instalar WebODM Gratuitamente no Windows com Suporte a GPU -- Parte III

**Subtítulo: Parte 3 - A Preparação do Ambiente com WSL 2 e Docker
Desktop**

A terceira parte foca na preparação do ambiente de trabalho.
Explicaremos como instalar e configurar o Windows Subsystem for Linux
(WSL 2), que permite que o Windows execute uma distribuição Linux
nativamente. Em seguida, cobriremos a instalação e configuração do
Docker Desktop para trabalhar em conjunto com o WSL 2, permitindo que o
WebODM utilize a GPU disponível para acelerar o processamento de
imagens.

***LINK PARA ESTE ARTIGO***

## Como Instalar WebODM Gratuitamente no Windows com Suporte a GPU -- Parte IV

**Subtítulo: Parte 4 - Instalação e Teste do WebODM com GPU**

Nesta parte, abordaremos a instalação do WebODM propriamente dita.
Explicaremos como clonar o repositório do WebODM, configurá-lo para
utilizar a GPU, e executar o primeiro teste para garantir que tudo está
funcionando corretamente. Vamos incluir dicas de como verificar se o
WebODM está utilizando a GPU corretamente e como solucionar problemas
comuns que possam surgir durante a instalação e o teste.

***LINK PARA ESTE ARTIGO***

## Como Instalar WebODM Gratuitamente no Windows com Suporte a GPU -- Parte V

**Subtítulo: Parte 5 - Manutenção do WebODM e Conclusão**

A parte final é dedicada à manutenção contínua e à solução de problemas
do WebODM. Instruções sobre como atualizar o software, otimizar o
desempenho, corrigir problemas comuns e manter o ambiente de trabalho em
bom estado serão discutidas. Finalizaremos com uma conclusão que reforça
a importância de manter o WebODM atualizado e funcionando de maneira
otimizada, aproveitando todos os recursos disponíveis no sistema.

***LINK PARA ESTE ARTIGO***

## Conclusão da Série de Artigos

Para instalar o WebODM no Docker Desktop no Windows 10/11, você precisa
garantir que todos os pré-requisitos estejam atendidos. Abaixo estão
todos os pré-requisitos e etapas que você deve seguir para preparar o
ambiente para uma instalação bem-sucedida do WebODM com suporte a GPU.

**1. Sistema Operacional**

-   **Windows 11** ou **Windows 10** versão 21H2 ou superior.

**2. Hardware**

-   **CPU**: Processador compatível com virtualização (Intel VT-x ou
    AMD-V).

-   **Memória RAM**: Pelo menos 16 **GB** de RAM (recomenda-se 32 GB ou
    mais).

-   **GPU** (Opcional para aceleração de GPU): Placa de vídeo NVIDIA
    compatível com CUDA.

**3. Docker Desktop Instalado e Configurado**

**4. WSL 2(Windows Subsystem for Linux) Instalado e configurado.**

**5. Todos os Drivers NVIDIA CUDA Instalados e Configurados no Windows e
no WSL2**

**6. Proceder a instalação Manual do WebODM.**

**7. Testar o WebODM e o Uso da GPU**

Esta série de artigos é ideal para qualquer pessoa interessada em
utilizar o WebODM de forma eficiente no Windows, utilizando a GPU para
melhorar o desempenho do processamento de imagens. Ao final da leitura,
o usuário estará equipado com todas as informações e passos necessários
para instalar, configurar, operar, atualizar e manter o WebODM,
aproveitando ao máximo os recursos de seu hardware.
