---
title: Instalando os arquivos principais do Lync Server 2013 e o banco de dados RTCLocal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8502e1af9ddb607c25ed04429f6b5bb7fbfe980
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>Instalando os arquivos principais do Lync Server 2013 e o banco de dados RTCLocal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-20_

Para instalar os arquivos principais do Lync Server 2013 em um computador, conclua o procedimento a seguir. O banco de dados RTCLocal é instalado automaticamente ao instalar os principais arquivos. Observe que não é necessário instalar o SQL Server nos nós do Inspetor. Em vez disso, o SQL Server Express é instalado automaticamente para você.

Para instalar os arquivos principais do Lync Server 2013 e o banco de dados do RTCLocal:

1.  No computador do nó do observador, clique em **Iniciar**, em **Todos os programas**, em **Acessórios**, clique com o botão direito no **Prompt de comando** e clique em **Executar como administrador**.

2.  Na janela do console, digite o seguinte comando e pressione ENTER, usando o caminho apropriado para seus arquivos de instalação do Lync Server:
    
        D:\Setup.exe /BootstrapLocalMgmt

Para verificar se os principais componentes do Lync Server foram instalados com êxito, clique em **Iniciar**, em **todos os programas**, em **Lync Server 2013**e em **Shell de gerenciamento do Lync Server**. No Shell de gerenciamento do Lync Server 2013, digite o seguinte comando do Windows PowerShell e pressione ENTER:

    Get-CsWatcherNodeConfiguration

A primeira vez que você executar este comando, nenhum dado é retornado porque você não configurou qualquer computador do nó do observador. Contanto que o comando seja executado sem retornar um erro, você pode supor que a instalação do Lync Server foi concluída com êxito.

Se seu computador do nó do observador estiver localizado dentro de sua rede de perímetro, você poderá executar o seguinte comando para verificar a instalação do Lync Server 2013:

    Get-CsPinPolicy

Você irá receber informações semelhantes ao seguinte, dependendo do número de políticas de PIN configuradas para uso em sua organização:

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

Se você ver informações sobre suas políticas de PIN, significa que você instalou com sucesso os principais componentes.

</div>

<span> </span>

</div>

</div>

</div>

