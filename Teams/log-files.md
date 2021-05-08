---
title: Usar arquivos de registro para solucionar problemas no Microsoft Teams
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Saiba mais sobre registros de depuração, mídia e desktop produzidos pelo Microsoft Teams, onde podem ser encontrados e como eles podem ajudar na resolução de problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f816830f24a3d1180cb33a91a3f02d30d360cfef
ms.sourcegitcommit: 2c2176b9d32b8f7218e8d11e82c0ae01318bfdc5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52264871"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Usar arquivos de registro para solucionar problemas no Microsoft Teams
=================================================

Existem três tipos de arquivos de log produzidos automaticamente pelo cliente, que podem ser aproveitados para auxiliar na solução de problemas do Microsoft Teams:

-   Registros de depuração

-   Registros de mídia

-   Registros de desktop

Ao criar uma solicitação de suporte com o Suporte da Microsoft, o engenheiro de suporte precisará dos registros de depuração. Ter os logs de depuração em mãos antes de criar a solicitação de suporte permitirá que a Microsoft comece a solucionar o problema rapidamente. **Os** logs **de** mídia ou área de trabalho só serão necessários se solicitados pela Microsoft.

> [!NOTE]
> Neste artigo, o termo **Logs de depuração** se refere aos logs usados para solução de problemas. No entanto, os arquivos gerados para esses logs conterão o termo **logs de diagnóstico** em seus nomes.  

A tabela a seguir descreve os vários clientes e seus logs associados. Os arquivos de registro são armazenados os locais específicos do cliente e do sistema operacional.


|Cliente |Depuração|Desktop|Mídia|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

Para obter uma lista completa dos sistemas operacionais e navegadores compatíveis, consulte [Obter clientes para o Microsoft Teams](get-clients.md).

<a name="debug-logs"></a>Registros de depuração
---------------------------

Estes são os registros mais comuns e são necessários para todos os casos de suporte da Microsoft. Os logs de depuração são produzidos pelos clientes de desktop Windows e Mac, bem como por clientes baseados em navegador. Os logs são baseados em texto e são lidos de baixo para cima. Eles podem ser lidos usando qualquer editor baseado em texto, e novos logs são criados ao efetuar o registro em log no cliente.

Os registros de depuração mostram os seguintes fluxos de dados:

-   Login

-   Solicitações de conexão para serviços de nível intermediário

-   Chamada/conversa

Os registros de depuração são produzidos usando os seguintes métodos específicos do sistema operacional:

-   Windows:

      Atalho do teclado: Ctrl + Alt + Shift + 1

-   Mac OSX:

      Atalho de teclado: Option + Command + Shift + 1

-   Linux:

      Atalho de teclado: Ctrl + Alt + Shift + 1

Os registros de depuração são baixados automaticamente para as seguintes pastas:

-   Windows: %userprofile%\\Downloads

-   Mac OSX: ~/Downloads

-   Linux: ~/Downloads

-   Navegador: será solicitado que você salve o registro de depuração no local de salvamento padrão

<a name="media-logs"></a>Registros de mídia
---------------------------

Os registros de mídia contêm dados de diagnóstico sobre áudio, vídeo e compartilhamento de tela nas reuniões do Teams. Eles são necessários para casos de suporte vinculados a problemas relacionados a chamadas.

O registro de mídia está desabilitado por padrão. Para registrar dados de diagnóstico para reuniões do Teams, os usuários devem ativar a opção no cliente Teams. Vá para **Configurações** > **Gerais**, marque a caixa de seleção **Habilitar registro para diagnóstico de reunião (requer a reinicialização do Teams**), reinicie o Teams e reproduza o problema. 

A tabela a seguir descreve os locais de registro de mídia. Ao enviar os arquivos de log para o suporte da Microsoft, verifique a data e hora dos arquivos de log para garantir que os logs abrangem o período de tempo em que você reproduziu o problema.

|Cliente |Localização |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack\\*.blog         |
|            |%appdata%\Microsoft\Teams\skylib\\*.blog
|            |%appdata%\Microsoft\Teams\media-stack\\*.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack/*.blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*.blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*.blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*.blog         |

Aqui está uma lista dos arquivos de log gerados e as informações que eles contêm.

|Nome do arquivo de log  |Descrição  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | Contém informações relacionadas à pilha de mídia. Isso inclui o status do canal, como resolução, decodificadores e codificadores usados e o número de quadros enviados e recebidos, além do status da sessão de compartilhamento de tela com base em vídeo e câmera (VBSS).         |
|rtmcontrol.msrtc-0-2415069487.blog      |Registra informações relacionadas a ações de controle remoto, como o carimbo de hora quando o controle é fornecido e informações do ponteiro do mouse.          |
|Teams_MediaStackETW-2-U-xr-U.etl      |Registra eventos de rastreamento de pilha de mídia.         |
|Debug-0-s2790420889.blog    | Contém informações relacionadas ao agente de mídia, incluindo qualidade de renderização.          |
|tscalling-0-2061129496.blog   |Registra eventos na API de chamada de ts.       |

<a name="desktop-logs"></a>Registros de desktop
---------------------

Os logs da área de trabalho, também conhecidos como logs de bootstrapper, contêm dados de log que ocorrem entre o cliente da área de trabalho e o navegador. Como os logs de mídia, esses logs só são necessários se solicitados pela Microsoft. Os logs são baseados em texto e podem ser lidos usando qualquer editor baseado em texto em um formato de cima para baixo.

Windows:

 - Clique com o botão direito no ícone do **Microsoft Teams** na bandeja do sistema e selecione **Obter Logs**.

Mac OsX:

 - Escolha **Obter Logs** no menu suspenso **Ajudar**.

Linux:

 - Clique no ícone do **Microsoft Teams** na bandeja do sistema e selecione **Obter Logs**.

|Cliente |Localização |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


<a name="browser-trace"></a>Rastreamento do navegador
---------------------------

Para algumas categorias de erros, o Suporte da Microsoft pode exigir que você colete um rastreamento do navegador. Essas informações podem fornecer detalhes importantes sobre o estado do cliente Teams quando o erro ocorrer.

Antes de iniciar o rastreamento do navegador, certifique-se de estar Teams. É importante fazer isso antes de iniciar o rastreamento para que o rastreamento não contenha informações confidenciais de login.

Depois de entrar, selecione um dos links a seguir, conforme apropriado para seu navegador, e siga as etapas fornecidas. 

-   [Borda & Chrome (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Borda](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> Nas etapas, substitua todas as referências ao portal do Azure pelo Teams cliente. 

## <a name="related-topics"></a>Tópicos relacionados

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
