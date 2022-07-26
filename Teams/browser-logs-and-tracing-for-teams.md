---
title: Logs e rastreamento do navegador para o Teams
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.date: 06/21/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Saiba mais sobre os logs do Navegador e do WebRTC produzidos pelo Microsoft Teams, onde eles podem ser encontrados, como coletar logs com o Suporte da Microsoft e como eles podem ajudar no monitoramento e na solução de problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9592091d97ad4fb34f02e906888757f0c7ab14ec
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005453"
---
# <a name="browser-logs-and-tracing-for-teams"></a>Logs e rastreamento do navegador para o Teams

Para algumas categorias de erros, Suporte da Microsoft exigir que você colete um rastreamento do navegador. Essas informações podem fornecer detalhes importantes sobre o estado do cliente do Teams quando o erro ocorre. Este artigo descreve como coletar logs do navegador e do WebRTC para o Teams.

## <a name="browser-logs"></a>Logs do navegador

Antes de iniciar o rastreamento do navegador, verifique se você está conectado ao Teams. É importante fazer isso antes de iniciar o rastreamento para que o rastreamento não contenha informações confidenciais de entrada.

Depois de entrar, selecione um dos links a seguir, conforme apropriado para seu navegador, e siga as etapas fornecidas. 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Borda](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> Nas etapas, substitua todas as referências ao portal do Azure pelo cliente do Teams.
  
## <a name="webrtc-logs-in-browsers"></a>Logs do WebRTC em navegadores

Os logs do WebRTC podem ajudar Suporte da Microsoft fornecendo detalhes de conexão para chamadas de áudio e vídeo. Siga as etapas para acessar os logs do WebRTC no Edge (Chromium) ou chrome:
  
1. Abra uma nova guia e vá para uma das seguintes URLs:
    - Borda (Chromium):`edge://webrtc-internals/`
    - Chrome: `chrome://webrtc-internals/`
  
2. Abra o aplicativo Web do Teams e reproduza o problema.
  
3. Voltar à guia que foi acessada na etapa 1 e você verá pelo menos duas guias:
    - Solicitações GetUserMedia
    - `https://teams.microsoft.com/url`

4. Escolha a guia com o nome do aplicativo Teams e salve o conteúdo da página.

## <a name="related-topics"></a>Tópicos relacionados

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)

[Configurar arquivos de log para monitoramento e solução de problemas no Teams](/MicrosoftTeams/log-files)
