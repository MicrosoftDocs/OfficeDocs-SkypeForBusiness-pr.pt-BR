---
title: Configurar arquivos de log para monitoramento e solução de problemas no Teams
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
description: Saiba mais sobre os logs de Depuração, Mídia e Área de Trabalho produzidos pelo Microsoft Teams, onde eles podem ser encontrados e como eles podem ajudar no monitoramento e na solução de problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae6e6eb0c84eae8293f141940842506fa3f54142
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466029"
---
# <a name="configure-log-files-for-monitoring-and-troubleshooting-in-teams"></a>Configurar arquivos de log para monitoramento e solução de problemas no Teams

Há três tipos de arquivos de log produzidos automaticamente pelo cliente, que podem ser aproveitados para auxiliar no monitoramento e na solução de problemas do Teams:

-   [Registros de depuração](#debug-logs)

-   [Registros de mídia](#media-logs)

-   [Registros de desktop](#desktop-logs)

Este artigo descreve esses logs e como eles são usados. Para obter informações sobre como solucionar problemas específicos, consulte: [Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams). 

Para obter informações sobre como entrar em contato com o suporte, consulte [Obter suporte](/microsoft-365/business-video/get-help-support).

> [!NOTE]
> Neste artigo, o termo **Logs de depuração** se refere aos logs usados para solução de problemas. No entanto, os arquivos gerados para esses logs conterão o termo **logs de diagnóstico** em seus nomes.  

## <a name="logs-overview"></a>Visão geral dos logs

É importante coletar logs assim que ocorrer um problema.

Ao criar uma solicitação de suporte com o Suporte da Microsoft, o engenheiro de suporte precisará dos registros de depuração. Ter os logs de depuração em mãos antes de criar a solicitação de suporte permitirá que a Microsoft comece a solucionar o problema rapidamente. **Os** **logs de** mídia ou área de trabalho só serão necessários se solicitados pela Microsoft.

Os logs de depuração, área de trabalho e mídia serão coletados em uma pasta com o nome Log de Diagnóstico _do MSTeams \<local date and time\>_. Essa pasta pode ser compactada e compartilhada quando você abre uma solicitação de suporte com Suporte da Microsoft. A pasta conterá pastas para Área de Trabalho, Reunião (Mídia) e Depuração (Web). Você pode coletar os arquivos usando os seguintes atalhos de teclado:

- Windows: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>

- Mac: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


Se ocorrer um problema com uma reunião ou evento ao vivo específico, será útil ter a URL associada à reunião. A URL fornece informações adicionais para ajudar a identificar a reunião exata ou o evento ao vivo nos logs. Essas informações podem ser coletadas de qualquer participante de uma reunião ou do apresentador ou produtor de um evento ao vivo. Essa URL pode ser capturada passando o mouse sobre a URL de junção e escolhendo **Copiar Hiperlink**.

> [!NOTE]
> Se o log de mídia estiver habilitado, haverá arquivos adicionais incluídos na pasta Reunião que são necessários para investigar problemas de áudio e vídeo. Se o log de mídia não estiver habilitado, haverá um número limitado de logs disponíveis.
  
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

Os logs de depuração são produzidos pelos clientes de desktop Windows e Mac, bem como por clientes baseados em navegador. Os logs são baseados em texto e são lidos de baixo para cima. Eles podem ser lidos usando qualquer editor baseado em texto, e novos logs são criados ao efetuar o registro em log no cliente.

Os registros de depuração mostram os seguintes fluxos de dados:

-   Login

-   Solicitações de conexão para serviços de nível intermediário

-   Chamada/conversa

Para coletar logs para Linux:
- Atalho de teclado: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>  
- Os arquivos estarão disponíveis em `~/Downloads`

Para coletar logs do Navegador e do Windows:
- Atalho de teclado: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>  
- Os arquivos estarão disponíveis em `%userprofile%\Downloads`

Para coletar logs para Mac:
- Atalho de teclado: <kbd>Opção</kbd> + <kbd>Comando</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>  
- Os arquivos estarão disponíveis em `~/Downloads`

## <a name="media-logs"></a>Registros de mídia

Os registros de mídia contêm dados de diagnóstico sobre áudio, vídeo e compartilhamento de tela nas reuniões do Teams. Eles são necessários para casos de suporte vinculados a problemas relacionados a chamadas.

O log de mídia é ativado por padrão para computadores se a CPU for:
- qualquer Apple M1
- qualquer Intel Xeon
- qualquer Intel i9, exceto para as séries U, G7, M e MQ
- qualquer 6ª geração e posterior Intel i7, exceto para as séries U, G7, M e MQ

Caso contrário, ele será desativado por padrão. Há duas maneiras de registrar dados de diagnóstico para reuniões do Teams:

- Administração configuração- você pode gerenciar logs de mídia para seus usuários finais
- Configuração do usuário final – os usuários finais podem ativar os logs de mídia

### <a name="admin-configuration"></a>Administração configuração

O gerenciamento de logs de mídia para seus usuários finais fornece uma experiência de solução de problemas perfeita, especialmente quando os problemas são intermitentes. Os administradores podem usar o cmdlet TeamsMediaLoggingPolicy para habilitar e gerenciar o log de mídia para usuários.

Leia [Grant-CsTeamsMediaLoggingPolicy](/powershell/module/teams/grant-csteamsmedialoggingpolicy) para cmdlets do PowerShell e mais informações.

### <a name="end-user-configuration"></a>Configuração do usuário final

Para que os usuários finais registrem dados de diagnóstico para reuniões do Teams, eles devem ativar a opção no cliente do Teams. Eles irão para **Configurações Gerais, selecionarão** >  os logs de mídia habilitados (dados de diagnóstico **para áudio, vídeo e compartilhamento de tela. Requer a reinicialização do Teams (** requer a reinicialização do Teams), reiniciar o Teams e reproduzir o problema. O cliente do Teams deve ser reiniciado para que o registro em log comece. Os usuários podem reiniciá-lo clicando com o botão direito do mouse no ícone no dock (Mac) ou na barra de tarefas (Windows) e selecionando Sair. Após o encerramento, eles podem clicar no ícone do aplicativo para abrir o Teams novamente.

> [!NOTE]
> Quando os usuários sairem do Teams, o log de mídia será redefinido para o padrão.

### <a name="collecting-and-sending-media-logs"></a>Coletando e enviando logs de mídia

Antes de enviar os arquivos de log para o suporte da Microsoft, verifique o carimbo de data/hora dos arquivos de log para garantir que os logs cubram o período de tempo quando você reproduziu o problema.

Para coletar logs para Linux:  
- Os arquivos estarão disponíveis nos seguintes locais:
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

Para coletar logs do Windows:  
- Os arquivos estarão disponíveis nos seguintes locais:
  - `%appdata%\Microsoft\Teams\media-stack\\\*\.blog`
  - `%appdata%\Microsoft\Teams\skylib\\\*\.blog` 

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

Os logs da área de trabalho, também conhecidos como logs de bootstrapper, contêm dados de log que ocorrem entre o cliente da área de trabalho e o navegador. Como os logs de mídia, esses logs só são necessários se solicitados pela Microsoft. Os logs são baseados em texto e podem ser lidos usando qualquer editor baseado em texto em um formato de cima para baixo.

Para coletar logs para Linux:
- Clique no ícone do Microsoft Teams na bandeja do sistema e selecione **Obter Logs**.
- Os arquivos estarão disponíveis em `~/.config/Microsoft/Microsoft Teams/logs.txt`.

Para coletar logs para Mac:
- Clique no menu Ajuda no Microsoft Teams e selecione **Coletar arquivos de suporte**.
- O `logs.txt` arquivo estará na pasta Área de Trabalho dentro da pasta _Log \<local date and time>de Diagnóstico do MSTeams_.

Para coletar logs do Windows:
- Clique no ícone do Microsoft Teams na bandeja do sistema e selecione **Coletar arquivos de suporte**.
- O `logs.txt` arquivo será aberto no Bloco de Notas automaticamente.

Ao investigar problemas de entrada no Teams, talvez seja necessário coletar manualmente os logs da área de trabalho. Esses arquivos de log estão localizados em %appdata%\Microsoft\Teams no Windows.

## <a name="related-topics"></a>Tópicos relacionados

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)

[Logs e rastreamento do navegador para o Teams](/MicrosoftTeams/browser-logs-and-tracing-for-teams)
