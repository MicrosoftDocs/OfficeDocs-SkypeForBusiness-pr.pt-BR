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
ms.openlocfilehash: 468f0f67743f7cd0e11ff28e4484f70a71af3b64
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766755"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Usar arquivos de registro para solucionar problemas no Microsoft Teams
=================================================

Existem três tipos de arquivos de registro produzidos automaticamente pelo cliente que podem ser aproveitados para ajudar na solução de problemas no Microsoft Teams.

-   Registros de depuração

-   Registros de mídia

-   Registros de desktop

Ao criar uma solicitação de suporte com o Suporte da Microsoft, o engenheiro de suporte precisará dos registros de depuração. Ter esses registros em mãos antes de criar a solicitação de suporte permitirá que a Microsoft comece a solucionar o problema rapidamente. Os registros de mídia ou de desktop só são necessários se forem solicitados pela Microsoft.

A tabela a seguir descreve os diversos clientes e seus registros associados. Os arquivos de registro são armazenados os locais específicos do cliente e do sistema operacional.


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

Estes são os registros mais comuns e são necessários para todos os casos de suporte da Microsoft. Os logs de depuração são produzidos pelos clientes de área de trabalho do Windows e do Mac, bem como clientes baseados em navegador. Os registros são baseados em texto e são lidos de baixo para cima. Eles podem ser lidos usando qualquer editor baseado em texto, e novos registros são criados ao acessar o cliente.

Os registros de depuração mostram os seguintes fluxos de dados:

-   Login

-   Solicitações de conexão para serviços de camada intermediária

-   Chamada/conversa

Os registros de depuração são produzidos usando os seguintes métodos para o sistema operacional específico:

-   Windows:

      Atalho do teclado: Ctrl + Alt + Shift + 1

-   Mac OSX:

      Atalho do teclado: Opção + Comando + Shift+1

-   Linux

      Atalho do teclado: Ctrl + Alt + Shift + 1

Os registros de depuração serão baixados automaticamente nas seguintes pastas.

-   Windows: %userprofile%\\Downloads

-   Mac OSX: ~/downloads

-   Linux: ~/downloads

-   Navegador: Você será instruído para salvar o registro de depuração no local padrão de salvamento

<a name="media-logs"></a>Registros de mídia
---------------------------

Os logs de mídia contêm dados de diagnóstico sobre áudio, vídeo e compartilhamento de tela em reuniões do teams. Eles são necessários para casos de suporte apenas mediante solicitação e só podem ser inspecionados pela Microsoft. 

O log de mídia está desativado por padrão. Para registrar dados de diagnóstico para reuniões do Teams, os usuários devem ativar a opção no cliente do teams. Vá para **configurações**  >  **geral**, marque a caixa de seleção **habilitar o registro em log para diagnóstico de reunião (requer a reinicialização de equipes**) e reinicie o Microsoft Teams.

A tabela a seguir descreve os locais dos logs.

|Cliente |Localização |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *. blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *. blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *. etl         |
|Mac OSX     |~/Library/Application Support Support/Microsoft/Teams/Media-Stack/*. blog         |
|            |~/Library/Application Support Support/Microsoft/Teams/skylib/*. blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/Media-Stack/*. blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*. blog         |

Aqui está uma lista dos arquivos de log que são gerados e as informações que eles contêm.

|Nome do arquivo de log  |Descrição  |
|---------|---------|
|Teams. msRTC-0-s1039525249. blog     | Contém informações relacionadas à pilha de mídia. Isso inclui o status do canal, como resolução, decodificadores e codificadores usados, e o número de quadros enviados e recebidos, e o status da sessão de câmera e compartilhamento de tela baseado em vídeo (VBSS).         |
|rtmcontrol. msRTC-0-2415069487. blog      |Registra informações relacionadas a ações de controle remoto, como o carimbo de data/hora quando o controle é fornecido, e informações de ponteiro do mouse.          |
|Teams_MediaStackETW -2-U-xr-U. etl      |Registra eventos de rastreamento de pilha de mídia.         |
|Debug-0-s2790420889. blog    | Contém informações relacionadas ao agente de mídia, incluindo qualidade de renderização.          |
|tscalling-0-2061129496. blog   |Registra eventos na API de chamadas para TS.       |

<a name="desktop-logs"></a>Registros de desktop
---------------------

Os registros de desktop, também conhecidos como registros de bootstrapper, contém dados de registro que ocorrem entre o clientes desktop e o navegador. Assim como os registros de mídia, esses registros só são necessários se forem solicitados pela Microsoft. Os registros são baseados em texto e podem ser lidos usando qualquer editor baseado em texto no formato de cima para baixo.

Windows:

1.  Clique com o botão direito do mouse no ícone do **Microsoft Teams** na bandeja do sistema, selecione **obter logs**

Mac OsX:

1.  Escolher **Obter registros** no menu suspenso de **Ajuda**

Linux

1.  Clique no ícone do **Microsoft Teams** na bandeja do sistema, selecione **obter logs**

|Cliente |Localização |
|---------|---------|
|Windows     |% AppData% \Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>Tópicos relacionados

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

