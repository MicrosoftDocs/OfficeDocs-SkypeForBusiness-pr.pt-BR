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
ms.openlocfilehash: 295886e7a5c50107672d17dcfa06067ba1b0ac9b
ms.sourcegitcommit: 48b8801b86a6c900c224853590daa3cb3c8d4ded
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49761089"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Usar arquivos de registro para solucionar problemas no Microsoft Teams
=================================================

Há três tipos de arquivos de log produzidos automaticamente pelo cliente, que podem ser aproveitados para ajudar na solução de problemas do Microsoft Teams:

-   Registros de depuração

-   Registros de mídia

-   Registros de desktop

Ao criar uma solicitação de suporte com o Suporte da Microsoft, o engenheiro de suporte precisará dos registros de depuração. Ter os logs de depuração em mãos antes de criar a solicitação de suporte permitirá que a Microsoft comece rapidamente a solucionar o problema. **Logs**  de mídia ou área de trabalho só são necessários se solicitados pela Microsoft.

> [!NOTE]
> Neste artigo, o termo **Logs de depuração** refere-se aos logs usados para solução de problemas. No entanto, os arquivos gerados para esses logs conterão os logs de diagnóstico de termos **em** seus nomes.  

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

Estes são os registros mais comuns e são necessários para todos os casos de suporte da Microsoft. Logs de depuração são produzidos pelos clientes da área de trabalho do Windows e mac, bem como por clientes baseados em navegador. Os logs são baseados em texto e são lidos de baixo para cima. Eles podem ser lidos usando qualquer editor baseado em texto, e novos logs são criados ao entrar no cliente.

Os registros de depuração mostram os seguintes fluxos de dados:

-   Login

-   Solicitações de conexão para serviços de nível intermediário

-   Chamada/conversa

Os logs de depuração são produzidos usando os seguintes métodos específicos do sistema operacional:

-   Windows:

      Atalho do teclado: Ctrl + Alt + Shift + 1

-   Mac OSX:

      Atalho do teclado: Opção + Comando + Shift+1

-   Linux:

      Atalho do teclado: Ctrl + Alt + Shift + 1

Os logs de depuração são baixados automaticamente para as seguintes pastas:

-   Windows: %userprofile%\\Downloads

-   Mac OSX: ~/Downloads

-   Linux: ~/Downloads

-   Navegador: Você será instruído para salvar o registro de depuração no local padrão de salvamento

<a name="media-logs"></a>Registros de mídia
---------------------------

Logs de mídia contêm dados de diagnóstico sobre áudio, vídeo e compartilhamento de tela em reuniões do Teams. Eles são necessários para casos de suporte vinculados a problemas relacionados a chamada.

O log de mídia está desligado por padrão. Para registrar dados de diagnóstico em reuniões do Teams, os usuários devem ativar a opção no cliente do Teams. Vá para **Configurações Gerais,** marque a caixa de seleção Habilitar log para diagnóstico de reunião (requer a reinicialização do Teams), reinicie o Teams e  >  reproduza o problema.  

A tabela a seguir descreve os locais do log de mídia. Ao enviar os arquivos de log para o suporte da Microsoft, verifique o data/hora dos arquivos de log para garantir que os logs cubram o período de tempo quando você reproduziu o problema.

|Cliente |Localização |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *.blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *.blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack/*.blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*.blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*.blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*.blog         |

Aqui está uma lista dos arquivos de log gerados e as informações que eles contêm.

|Nome do arquivo de log  |Descrição  |
|---------|---------|
|Blog do Teams.msrtc-0-s1039525249.blog     | Contém informações relacionadas à pilha de mídia. Isso inclui o status do canal, como resolução, decodificadores e codificadores usados, e o número de quadros enviados e recebidos e o status da sessão de compartilhamento de tela baseado em câmera e vídeo (VBSS).         |
|rtmcontrol.msrtc-0-2415069487.blog      |Registra informações relacionadas a ações de controle remoto, como o carimbo de data/hora quando o controle é dado e informações do ponteiro do mouse.          |
|Teams_MediaStackETW-2-U-xr-U.etl      |Grava eventos de rastreamento de pilha de mídia.         |
|Depurar-0-s2790420889.blog    | Contém informações relacionadas ao agente de mídia, incluindo qualidade de renderização.          |
|tscalling-0-2061129496.blog   |Grava eventos na API de chamada ts.       |

<a name="desktop-logs"></a>Registros de desktop
---------------------

Logs da área de trabalho, também conhecidos como logs de inicialização, contêm dados de log que ocorrem entre o cliente da área de trabalho e o navegador. Assim como os registros de mídia, esses registros só são necessários se forem solicitados pela Microsoft. Os logs são baseados em texto e podem ser lidos usando qualquer editor baseado em texto em um formato de cima para baixo.

Windows:

 - Clique com o botão direito do mouse no ícone do **Microsoft Teams** na bandeja do sistema e selecione **Obter Logs.**

Mac OsX:

 - Escolha **Obter Logs** no menu **suspenso** Ajuda.

Linux:

 - Clique no ícone **do Microsoft Teams** na bandeja do sistema e selecione Obter **Logs.**

|Cliente |Localização |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>Tópicos relacionados

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
