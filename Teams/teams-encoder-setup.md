---
title: Configuração do codificador para streaming no Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: Este artigo discutirá a configuração de RTMP baseada em codificador para eventos de streaming do Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8a31b8b0de30367401c998d17dbf59ea06fc5687
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767913"
---
# <a name="using-an-encoder-for-live-streaming-in-microsoft-teams"></a>Usando um codificador para transmissão ao vivo no Microsoft Teams

Os codificadores do Teams permitem que os usuários produzam eventos ao vivo diretamente de um codificador externo baseado em hardware ou software com o Microsoft Teams.

## <a name="overview"></a>Visão geral

Um codificador usa conteúdo de áudio e vídeo de várias fontes que você usa durante um evento ao vivo, como uma câmera, um microfone, uma captura de tela da área de trabalho e assim por diante. Ele compacta e converte essa mídia em um formato digital adequado e, em seguida, envia-a ao Teams para transmissão ao vivo para seu público. Consulte nosso [manual de Produção Personalizada](https://aka.ms/CustomProductionVEP) para saber mais sobre como você pode usar tecnologias de produção do Teams (como o NDI) com codificadores externos.

## <a name="production-workflow-when-using-an-encoder"></a>Fluxo de trabalho de produção ao usar um codificador

O fluxo de trabalho para a produção de um Evento Ao Vivo do Teams é o seguinte:

Um evento ao vivo está agendado no Teams ou no Yammer e a opção **Codificador do Teams** está selecionada. Isso provisiona um ponto de extremidade RTMP, que é fornecido com uma URL RTMP(S) e uma chave correspondente. A URL e a chave são usadas pelo codificador para se conectar ao ponto de extremidade RTMP para o evento ao vivo agendado.

### <a name="common-encoders-user-with-live-events"></a>Usuário de codificadores comuns com eventos ao vivo

Os codificadores nas duas listas a seguir foram testados pela Microsoft para transmissão ao vivo com o Teams. A primeira lista é um subconjunto desses codificadores, que foram testados com o produto para facilitar o uso e instalação rápida.

#### <a name="stream-ready-encoders"></a>Codificadores prontos para fluxo

|Codificador                                |Site  |Detalhes  |
|---------------------------------------|---------|---------|
|Haivision                              |[Haivision Makito X](https://www.haivision.com/microsoft/stream) |Fornece vídeo HD de alta qualidade com o Haivision Hub, uma alternativa poderosa ao RTMP. |
|Haivision                              |[Haivision KB](https://www.haivision.com/microsoft/stream) |Codificadores de vídeo H.264 e HEV fornecem cascatas de vídeo ABR de alta qualidade para resoluções de até 4K. |
|Software de Emissora Aberta (OBS Studio) |[Abrir software de emissora](https://obsproject.com/) |Captura e mistura de vídeo/áudio em tempo real de alto desempenho, com suporte a todas as plataformas de streaming e muito mais. |
|vMix                                   |[vMix](https://www.vmix.com/) |Mixer de visão de software que controla a gravação, a mistura e a transmissão ao vivo de câmeras, vídeos, áudio e muito mais. |
|Wirecast                               |[Wirecast](https://www.telestream.net/wirecast) |Software de webcast que abrange todos os conceitos básicos + produção de várias câmeras. |
|Switcher Studio                        |[Switcher Studio](https://www.switcherstudio.com/microsoft-stream) |Sincroniza vários dispositivos Apple com uma ou mais câmeras para captura e edição de vídeo em tempo real. |
|AWS Elemental Live                     |[AWS Elemental Live](https://www.elemental.com/products/aws-elemental-appliances-software/#elemental-live) |Gravação de vídeo e áudio em tempo real para transmissão ao vivo para dispositivos conectados à Internet |
|Emissora XSplit                     |[Emissora XSplit](https://www.xsplit.com/) |Produz, mistura e fornece conteúdo de vídeo avançado, incluindo a jogabilidade para transmissão ao vivo. |
|Ffmpeg                                 |[Ffmpeg](https://ffmpeg.org/) |Pacote de software de código aberto para lidar com vídeo, áudio e outros arquivos multimídia e transmissões ao vivo. |
|Caminhão de Produção          |[Caminhão de Produção](https://www.blueframetech.com/productiontruck) |Filma e transmite eventos no local de uma van móvel ou caminhão. |
|Produtor de IA do Live Arena                 |Produtor de IA |Estúdio de produção integrado ao Microsoft Teams como um aplicativo de reunião.|
|StreamYard                             |StreamYard |Estúdio de streaming ao vivo no navegador.|
|Socialive                              |Socialive |Plataforma de produção de vídeo em nuvem, fornecendo uma experiência all-in-one para produzir e distribuir conteúdo de vídeo de qualidade de estúdio.|
|Brandlive                              |BrandLive |Plataforma de produção baseada em nuvem.|

### <a name="haivision-makito-x-encoder-and-makito-kb-encoder"></a>Codificador Makito X da Haivision e Codificador Makito KB

Se você tiver um codificador Haivision X ou Makito KB existente, poderá escolher a opção apropriada na lista suspensa e seguir a lista de instruções.

1. Selecione **Iniciar configuração** para criar um canal para transmissão ao vivo. Aguarde a conclusão da instalação. Você verá uma mensagem **Pronta para conectar** na tela.
1. Depois que isso for concluído, baixe a predefinição que contém todos os parâmetros de codificação, incluindo a URL de ingestão e o nome do evento. Importe a predefinição para o codificador e inicie o codificador.
1. Voltar para o Teams. Depois de poder ver a visualização do codificador, selecione **Iniciar evento** para ir ao ar para que o público possa ver o evento ao vivo.

> [!NOTE]
> O suporte ao codificador do Haivision KB para RTMPS ainda não foi testado. O Codificador Makito X da Haivision não dá suporte a RTMPS. As predefinições baixadas para ambos os codificadores contêm a URL de ingestão de RTMP.

### <a name="switcher-studio"></a>Switcher Studio

Você pode usar o Switcher Studio para iniciar o streaming para o Teams usando iPhone ou iPad.

1. Selecione **Iniciar configuração** para criar um canal para transmissão ao vivo. Aguarde a conclusão da instalação. Você verá uma mensagem **Pronta para conectar** na tela.
2. O Switcher Studio abrirá o painel do Switcher Studio para adicionar o evento ao vivo à sua conta.

> [!NOTE]
> Se você ainda não tiver uma conta do Switcher Studio, precisará criar uma).

3. Quando isso for concluído, você pode acessar seu aplicativo do Switcher Studio no iPhone ou iPad, selecionar o Teams na guia Saída e iniciar o streaming para o Teams.
4. Voltar para o Teams. Depois de ver a visualização do codificador, selecione **Iniciar evento** para entrar ao vivo para que o público possa ver o evento ao vivo.

> [!NOTE]
> O Switcher Studio usa a URL de ingestão de RTMP.

### <a name="wirecast"></a>Wirecast

Se você for um usuário existente do Wirecast, poderá escolher essa opção na lista suspensa para enviar uma transmissão ao vivo para o Teams. Observe que você precisará do Wirecast versão 10 ou posterior.

1. Selecione **Iniciar configuração** para criar um canal para transmissão ao vivo. Aguarde a conclusão da instalação. Você verá uma mensagem **Pronta para conectar** na tela.
1. O codificador iniciará o aplicativo Wirecast em seu computador pré-configurado com os parâmetros de codificação corretos e ingerirá URL para esse evento ao vivo. Quando estiver pronto, clique no ícone do Teams no aplicativo Wirecast para iniciar o streaming para o Teams.
1. Voltar para o Teams. Depois de ver a visualização do codificador, selecione **Iniciar evento** para entrar ao vivo para que o público possa ver o evento ao vivo.

> [!NOTE]
> O aplicativo Wirecast é iniciado com a URL de ingestão RTMPS pré-configurada.
