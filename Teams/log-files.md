---
title: Usar arquivos de registro para solucionar problemas no Microsoft Teams
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Saiba mais sobre logs de depuração, mídia e área de trabalho produzidos pelo Microsoft Teams, onde eles podem ser encontrados e como eles podem ajudar no monitoramento e solução de problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a8a58511c3a9562281f162ef1c92d8e01d96228
ms.sourcegitcommit: 45756a51857ed1d8714175d2b715c388e2f0db81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2022
ms.locfileid: "62027584"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>Usar arquivos de log para monitorar e solucionar Microsoft Teams

Há três tipos de arquivos de log produzidos automaticamente pelo cliente, que podem ser aproveitados para ajudar no monitoramento e solução de problemas Teams:

-   [Registros de depuração](#debug-logs)

-   [Registros de mídia](#media-logs)

-   [Registros de desktop](#desktop-logs)

Este artigo descreve esses logs e como eles são usados. Para obter informações sobre como solucionar problemas específicos, consulte: [Teams Solução de Problemas](/MicrosoftTeams/troubleshoot/teams). Para obter informações sobre como contatar o suporte, consulte [Obter suporte](/microsoft-365/business-video/get-help-support). Ao criar uma solicitação de suporte com o Suporte da Microsoft, o engenheiro de suporte precisará dos registros de depuração. Ter os logs de depuração em mãos antes de criar a solicitação de suporte permitirá que a Microsoft comece a solucionar o problema rapidamente. **Os** logs **de** mídia ou área de trabalho só serão necessários se solicitados pela Microsoft.

> [!NOTE]
> Neste artigo, o termo **Logs de depuração** se refere aos logs usados para solução de problemas. No entanto, os arquivos gerados para esses logs conterão o termo **logs de diagnóstico** em seus nomes.  

## <a name="collect-and-enable-logging"></a>Coletar e habilitar o log

É importante coletar logs assim que ocorrer um problema. Os logs podem ser coletados com apenas alguns cliques.

- Windows: clique com o botão direito do mouse no ícone Teams na bandeja do sistema e escolha **Coletar arquivos de suporte**. 

- Mac: selecione o menu Ajuda e escolha **Coletar arquivos de suporte**.

Os logs de depuração, área de trabalho e mídia serão coletados em uma pasta com o nome _MSTeams Diagnostics Log \<local date and time\>_. Essa pasta pode ser compactada e compartilhada quando você abre uma solicitação de suporte com o Suporte da Microsoft. A pasta conterá pastas para Área de Trabalho, Reunião (Mídia) e Depuração (Web). Você pode coletar os arquivos usando os seguintes atalhos de teclado:

- Windows: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>

- Mac: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


O registro de mídia está desabilitado por padrão. Para habilitar o log de mídia, os usuários devem ativar a opção no Teams cliente. Vá para **Configurações** Geral e selecione Habilitar log para diagnóstico de reunião (requer a  >   **reinicialização Teams)**. O Teams cliente deve ser reiniciado para iniciar o registro em log (reinicie-o clicando com o botão direito do mouse no ícone em seu dock (Mac) ou na barra de tarefas (Windows) e selecionando **Quit**. Depois de sair, basta clicar no ícone do aplicativo para abri-lo novamente).

Se ocorrer um problema com uma reunião ou evento ao vivo específico, é útil ter a URL associada à reunião. Isso fornece informações adicionais para ajudar a identificar a reunião exata ou o evento ao vivo nos logs. Essas informações podem ser coletadas de qualquer participante para uma reunião ou de apresentador ou produtor para um evento ao vivo. Essa URL pode ser capturada pairando sobre a URL de junção e escolhendo **Copiar Hiperlink**.

> [!NOTE]
> Se o log de mídia estiver habilitado, haverá arquivos adicionais incluídos na pasta Reunião que são necessários para investigar problemas de áudio e vídeo. Se o log de mídia não estiver habilitado, haverá um número limitado de logs disponíveis.
  
> [!NOTE]
> Os logs de depuração estavam coletando anteriormente usando os atalhos de teclado abaixo. Eles ainda funcionam e concluirão a mesma captura de log que a **opção Coletar arquivos de** suporte.
>
> - Windows: <kbd>Crtl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>
>
> - Mac: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


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

## <a name="debug-logs"></a>Registros de depuração

Consulte a _seção Coletar e habilitar o registro em log_ para obter Windows e instruções do Mac. Os logs de depuração são produzidos pelos clientes de desktop Windows e Mac, bem como por clientes baseados em navegador. Os logs são baseados em texto e são lidos de baixo para cima. Eles podem ser lidos usando qualquer editor baseado em texto, e novos logs são criados ao efetuar o registro em log no cliente.

Os registros de depuração mostram os seguintes fluxos de dados:

-   Login

-   Solicitações de conexão para serviços de nível intermediário

-   Chamada/conversa

Para coletar logs para Linux:
- Atalho do teclado: <kbd>Ctrl</kbd>  +  <kbd>Alt</kbd>  +  <kbd>Shift</kbd>  +  <kbd>1</kbd>  
- Os arquivos estarão disponíveis em `~/Downloads`

Para coletar logs para Navegador e Windows:
- Atalho do teclado: <kbd>Ctrl</kbd>  +  <kbd>Alt</kbd>  +  <kbd>Shift</kbd>  +  <kbd>1</kbd>  
- Os arquivos estarão disponíveis em `%userprofile%\Downloads`

## <a name="media-logs"></a>Registros de mídia

Consulte a _seção Coletar e habilitar o registro em log_ para obter Windows e instruções do Mac. Os registros de mídia contêm dados de diagnóstico sobre áudio, vídeo e compartilhamento de tela nas reuniões do Teams. Eles são necessários para casos de suporte vinculados a problemas relacionados a chamadas.

O registro de mídia está desabilitado por padrão. Para registrar dados de diagnóstico para reuniões do Teams, os usuários devem ativar a opção no cliente Teams. Vá para **Configurações** > **Gerais**, marque a caixa de seleção **Habilitar registro para diagnóstico de reunião (requer a reinicialização do Teams**), reinicie o Teams e reproduza o problema. 

Ao enviar os arquivos de log para o suporte da Microsoft, verifique a data e hora dos arquivos de log para garantir que os logs abrangem o período de tempo em que você reproduziu o problema.

Para coletar logs para Linux:  
- Os arquivos estarão disponíveis nos seguintes locais:
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

Para coletar logs para Windows:  
- Os arquivos estarão disponíveis nos seguintes locais:
  - `%userprofile%\Downloads\MSTeams Diagnostics Log\meeting\media-stack\\\*\.blog`
  - `%userprofile%\Downloads\MSTeams Diagnostics Log\meeting\skylib\\\*\.blog` 

Para coletar logs para Mac:
- Os arquivos estarão disponíveis nos seguintes locais:
  - `~/Library/Application Support/Microsoft/Teams/media-stack\\\*\.blog`
  - `~/Library/Application Support/Microsoft/Teams/skylib\\\*\.blog`

Aqui está uma lista dos arquivos de log gerados e as informações que eles contêm.

<br/>

|Nome do arquivo de log  |Descrição  |
|---------|---------|
|`Teams.msrtc-0-s1039525249.blog`     | Contém informações relacionadas à pilha de mídia. Isso inclui o status do canal, como resolução, decodificadores e codificadores usados e o número de quadros enviados e recebidos, além do status da sessão de compartilhamento de tela com base em vídeo e câmera (VBSS).         |
|`rtmcontrol.msrtc-0-2415069487.blog`      |Registra informações relacionadas a ações de controle remoto, como o carimbo de hora quando o controle é fornecido e informações do ponteiro do mouse.          |
|`Teams_MediaStackETW-2-U-xr-U.etl`      |Registra eventos de rastreamento de pilha de mídia.         |
|`Debug-0-s2790420889.blog`    | Contém informações relacionadas ao agente de mídia, incluindo qualidade de renderização.          |
|`tscalling-0-2061129496.blog`   |Registra eventos na API de chamada de ts.       |

## <a name="desktop-logs"></a>Registros de desktop

Consulte a _seção Coletar e habilitar o registro em log_ para obter Windows e instruções do Mac. Os logs da área de trabalho, também conhecidos como logs de bootstrapper, contêm dados de log que ocorrem entre o cliente da área de trabalho e o navegador. Como os logs de mídia, esses logs só são necessários se solicitados pela Microsoft. Os logs são baseados em texto e podem ser lidos usando qualquer editor baseado em texto em um formato de cima para baixo.

Para coletar logs para Linux:
- Clique no ícone do Microsoft Teams na bandeja do sistema e selecione **Obter Logs**.
- Os arquivos estarão disponíveis em `~/.config/Microsoft/Microsoft Teams/logs.txt` .
  
Para coletar logs para Windows:
- Clique no ícone Microsoft Teams na bandeja do sistema e selecione **Coletar arquivos de suporte.**
- O `logs.txt` arquivo será aberto em Bloco de notas automaticamente.

Ao investigar problemas de Teams, talvez seja necessário coletar manualmente os logs da área de trabalho. Esses arquivos de log estão localizados em %appdata%\Microsoft\Teams em Windows.

## <a name="browser-trace"></a>Rastreamento do navegador

Para algumas categorias de erros, o Suporte da Microsoft pode exigir que você colete um rastreamento do navegador. Essas informações podem fornecer detalhes importantes sobre o estado do cliente Teams quando o erro ocorrer.

Antes de iniciar o rastreamento do navegador, certifique-se de estar Teams. É importante fazer isso antes de iniciar o rastreamento para que o rastreamento não contenha informações confidenciais de login.

Depois de entrar, selecione um dos links a seguir, conforme apropriado para seu navegador, e siga as etapas fornecidas. 

-   [Borda & Chrome (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Borda](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> Nas etapas, substitua todas as referências ao portal do Azure pelo Teams cliente.
  
## <a name="webrtc-logs-in-browsers"></a>Logs webRTC em navegadores
Os logs webRTC podem ajudar o Suporte da Microsoft fornecendo detalhes de conexão para chamadas de áudio e vídeo. Siga as etapas para acessar os logs WebRTC no Edge (Chromium) ou Chrome: 
  
1.  Abra uma nova guia e vá para uma das seguintes URLs:
    -   Borda (Chromium):`edge://webrtc-internals/`
    -   Chrome: `chrome://webrtc-internals/`
  
2.  Abra o Teams Web e reproduza o problema.
  
3.  Volte para a guia acessada na etapa 1 e você verá pelo menos duas guias:
    -   Solicitações GetUserMedia
    -   `https://teams.microsoft.com/url`

4.  Escolha a guia com o nome do aplicativo Teams e salve o conteúdo da página.

## <a name="related-topics"></a>Tópicos relacionados

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
