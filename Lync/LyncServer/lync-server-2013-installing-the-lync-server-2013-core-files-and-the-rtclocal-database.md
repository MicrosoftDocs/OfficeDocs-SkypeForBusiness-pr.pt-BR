---
title: Instalando os arquivos principais do Lync Server 2013 e o banco de dados do RTCLocal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99eccdd8d6473c25c6096c370f616975c7da141f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a>Instalando os arquivos principais do Lync Server 2013 e o banco de dados do RTCLocal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-20_

Para instalar os arquivos do Lync Server 2013 Core em um computador, conclua o procedimento a seguir. O banco de dados do RTCLocal é instalado automaticamente quando você instala os arquivos principais. Observe que você não precisa instalar o SQL Server nos nós do Inspetor. Em vez disso, o SQL Server Express é instalado automaticamente para você.

Para instalar os arquivos do Lync Server 2013 Core e o banco de dados do RTCLocal:

1.  No computador do nó do Inspetor, clique em **Iniciar**, **em todos os programas**, em **acessórios**, clique com o botão direito do mouse em **prompt de comando**e clique em **Executar como administrador**.

2.  Na janela do console, digite o seguinte comando e pressione ENTER, usando o caminho apropriado para os arquivos de instalação do Lync Server:
    
        D:\Setup.exe /BootstrapLocalMgmt

Para verificar se os componentes principais do Lync Server foram instalados com êxito, clique em **Iniciar**, clique em **todos os programas**, clique em **Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**. No Shell de gerenciamento do Lync Server 2013, digite o seguinte comando do Windows PowerShell e pressione ENTER:

    Get-CsWatcherNodeConfiguration

Na primeira vez que você executar esse comando, nenhum dado será retornado porque você ainda não configurou nenhum computador do nó do Inspetor. Desde que o comando seja executado sem retornar um erro, você pode presumir que a instalação do Lync Server foi concluída com êxito.

Se o seu computador do nó do Inspetor estiver localizado dentro da sua rede de perímetro, você pode executar o seguinte comando para verificar a instalação do Lync Server 2013:

    Get-CsPinPolicy

Você receberá informações semelhantes às seguintes, dependendo do número de políticas de PIN (número de identificação pessoal) configuradas para usar em sua organização:

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

Se você vir informações sobre suas políticas de PIN, isso significa que você instalou os componentes principais com êxito.

</div>

<span> </span>

</div>

</div>

</div>

