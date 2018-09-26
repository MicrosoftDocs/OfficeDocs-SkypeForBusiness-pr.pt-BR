---
title: Usar arquivos de registro para solucionar problemas no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Saiba mais sobre registros de depuração, mídia e desktop produzidos pelo Microsoft Teams, onde podem ser encontrados e como eles podem ajudar na resolução de problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95d28bac036476c417ccbe7929a23ab9fb37f3a8
ms.sourcegitcommit: 090ff859083ace43c08d483f4023009e8b6e79e4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2018
ms.locfileid: "25018896"
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
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |
|Windows Phone     |-         |-         |-         |

Para obter uma lista completa dos sistemas operacionais e navegadores compatíveis, consulte [Obter clientes para o Microsoft Teams](get-clients.md).

<a name="debug-logs"></a>Registros de depuração
---------------------------

Estes são os registros mais comuns e são necessários para todos os casos de suporte da Microsoft. Depurar logs são produzidos por clientes de desktop do Windows e Mac, bem como os clientes baseado no navegador. Os registros são baseados em texto e são lidos de baixo para cima. Eles podem ser lidos usando qualquer editor baseado em texto, e novos registros são criados ao acessar o cliente.

Os registros de depuração mostram os seguintes fluxos de dados:

-   Login

-   Solicitações de conexão para serviços de camada intermediária

-   Chamada/conversa

Os registros de depuração são produzidos usando os seguintes métodos para o sistema operacional específico:

-   Windows:

    1.  Clique com o botão direito do mouse no **ícone do Microsoft Teams** na bandeja do aplicativo e selecione **Obter registros**

    2.  Escolher **Obter registros** no menu suspenso de **Ajuda**

    3.  Atalho do teclado: Ctrl + Alt + Shift + 1

-   Mac OSX:

    1.  Escolher **Obter registros** no menu suspenso de **Ajuda**

    2.  Atalho do teclado: Opção + Comando + Shift+1

Os registros de depuração serão baixados automaticamente nas seguintes pastas.

-   Windows: %userprofile%\\Downloads

-   Mac OSX: Downloads

-   Navegador: Você será instruído para salvar o registro de depuração no local padrão de salvamento

<a name="media-logs"></a>Registros de mídia
---------------------------

Os registros de mídia contêm dados de diagnóstico de áudio, vídeo e compartilhamento de tela. Eles são necessários para casos de suporte apenas mediante solicitação e só podem ser inspecionados pela Microsoft. A tabela a seguir descreve a localização dos arquivos.


|Cliente |Localização |
|---------|---------|
|Windows     |%AppData%\Microsoft\Teams\media-Stack\*. etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack\*.blog         |


<a name="desktop-logs"></a>Registros de desktop
---------------------

Os registros de desktop, também conhecidos como registros de bootstrapper, contém dados de registro que ocorrem entre o clientes desktop e o navegador. Assim como os registros de mídia, esses registros só são necessários se forem solicitados pela Microsoft. Os registros são baseados em texto e podem ser lidos usando qualquer editor baseado em texto no formato de cima para baixo.

|Cliente |Localização |
|---------|---------|
|Windows     |%AppData%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
