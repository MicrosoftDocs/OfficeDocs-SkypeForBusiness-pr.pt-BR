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
ms.openlocfilehash: 8fd5feffe328083d9e7d5fa6e14cdbdac2ae5ffc
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767912"
---
# <a name="configuring-encoders-for-live-event-streaming-in-microsoft-teams"></a>Configurar codificadores para transmissão de eventos ao vivo no Microsoft Teams

O Teams aceita feeds ao vivo de uma variedade de codificadores diferentes que geram RTMP ou RTMPS. Cada codificador é diferente, portanto, certifique-se de seguir as diretrizes para as configurações do codificador ao enviar para o Teams.

Para saber como configurar um evento ao vivo no Teams, leia sobre como criar eventos ao vivo. Se você já estiver usando um codificador integrado ao Teams, leia sobre [como configurar codificadores para transmissão ao vivo](teams-encoder-setup.md).

## <a name="configuration-steps"></a>Etapas de configuração

Depois de agendar o evento ao vivo usando o Teams ou o Yammer e selecionar a opção **Codificador do Teams** , você poderá recuperar a URL rtmp e a chave do convite da reunião e usá-los para enviar o feed para a interface do usuário do produtor do Teams.

### <a name="gather-the-rtmp-information"></a>Coletar as informações do RTMP

#### <a name="scheduled-in-teams"></a>Agendado no Teams

1. Abra o cliente do Teams e navegue até o **Calendário**.
1. Selecione o evento ao vivo agendado e selecione o botão seta dupla para ver os detalhes do convite.
1. Vá até a seção **RTMP em detalhes** .
1. Selecione o link **Obter RTMP** para copiar a URL de ingestão RTMP na área de transferência.
1. Selecione a **tecla Obter RTMP** para copiar a chave RTMP na área de transferência.

#### <a name="scheduled-in-yammer"></a>Agendado no Yammer

1. Navegue até a comunidade yammer onde o evento foi agendado.
1. Selecione a guia **Eventos** para ver os próximos eventos agendados.
1. Selecione o evento desejado para trazer a página de detalhes.
1. No lado direito, em **Produzir**, selecione o link **de informações RTMP** para expor a URL e a chave RTMP.

## <a name="encoder-setup"></a>Configuração do codificador

1. Depois de coletar as informações do RTMP, verifique se o codificador está configurado com as configurações corretas de acordo com as configurações recomendadas do codificador abaixo.
1. Insira a URL e a Chave RTMP nas configurações de streaming do codificador (consulte a documentação do fabricante para obter detalhes).
1. Configure o codificador com as fontes de áudio e vídeo desejadas.
1. Abra o cliente do Teams e participe da abertura ao vivo como produtor.
1. Inicie o streaming do codificador para a URL de ingestão do Teams RTMP.
1. Na janela Produtor do Teams, após alguns segundos, o feed RTMP do codificador será exibido na área do apresentador.
1. Clique no feed rtmp na área do apresentador para colocá-lo na fila no lado esquerdo.
1. Depois que você estiver satisfeito com o feed, selecione **Enviar Ao Vivo** – o feed também aparecerá no lado direito da janela Produtor.
1. Selecione **Iniciar** para iniciar o fluxo.

## <a name="recommended-encoder-settings"></a>Configurações recomendadas do codificador

### <a name="ingest-protocols"></a>Ingerir protocolos

- RTMPS de taxa de bit único ou RTMP

### <a name="video-format"></a>Formato de vídeo

- Codec: H.264
- Perfil: Alto (nível 4.0)
- Taxa de bits: até 5 Mbps (5000 kbps)
- Taxa de Bit Constante Estrita (CBR)
- Keyframe/GOP: 2 segundos
  - Deve haver um quadro IDR no início de cada GOP
  - Taxa de quadros: 29,97 fps ou 30 fps
  - Resolução: 1280 x 720 (720P)
  - Modo de Interlace: Progressivo

### <a name="audio-format"></a>Formato de áudio

- Codec: AAC (LC)
- Taxa de bits: 192 kbps
- Taxa de exemplo: 48 kHz ou 44,1 kHz (recomendação de 48 kHz)

### <a name="playback-requirements"></a>Requisitos de reprodução

- Um fluxo de áudio e vídeo deve estar presente para reproduzir conteúdo no Teams.

### <a name="configuration-tips"></a>Dicas de configuração

- Sempre que possível, use uma conexão de Internet com fio rígido.
- Ao determinar os requisitos de largura de banda é dobrar as taxas de bits de streaming. Embora isso não seja um requisito obrigatório, ajudará a mitigar o impacto do congestionamento da rede.
- Ao usar codificadores baseados em software, feche todos os programas desnecessários.
- Não altere a configuração do codificador depois que ele começar a pressionar. Ele tem efeitos negativos sobre o evento e pode fazer com que o evento seja instável. Se você quiser fazer isso antes do evento começar, você deve desconectar usando os controles de produtor no Teams e iniciar a instalação novamente.
- Se o codificador for desconectado durante o evento ao vivo, reconecte-o mantendo os mesmos carimbos de data/hora do processo contínuo. Qualquer descontinuidade pode causar problemas de áudio ou vídeo em determinados navegadores e dispositivos.
- Dê a si mesmo tempo suficiente para configurar seu evento. Para eventos de alta escala, é recomendável iniciar a instalação uma hora antes do evento.
