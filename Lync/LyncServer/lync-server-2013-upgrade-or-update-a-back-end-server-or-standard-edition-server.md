---
title: Atualizar ou atualizar um servidor back end ou um servidor Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd3617098c42cd38e9928f055a6348a7bf2f9342
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>Atualizar ou atualizar um servidor back end ou um servidor Standard Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Este tópico explica como instalar uma atualização em um servidor de back-end Enterprise Edition ou um servidor Standard Edition.

Se o servidor Back End estiver inoperante por ao menos 30 minutos enquanto você o estiver atualizando, os usuários podem entrar em modo de resiliência. Quando a atualização for concluída e os servidores Back End tiver novamente se conectado aos servidores Front End no pool, os usuários são retornados à funcionalidade total. Se a atualização levar menos de 30 minutos, os usuários não serão afetados.

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Para atualizar um servidor back end ou um servidor Standard Edition

1.  Faça logon no servidor que você estiver atualizando como um membro da função CsAdministrator.

2.  Faça o download do pacote de atualizações e extraia os arquivos para um disco rígido local.

3.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

4.  Pare os serviços do Lync Server. Na linha de comando, digite:
    
        Stop-CsWindowsService

5.  Pare o serviço World Wide Web. Na linha de comando, digite:
    
        net stop w3svc

6.  Feche todas as janelas do Shell de gerenciamento do Lync Server.

7.  Atualize a atualização.

8.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

9.  Pare os serviços do Lync Server novamente para capturar os conjuntos GAC (cache de assembly global) –d. Na linha de comando, digite:
    
        Stop-CsWindowsService

10. Reinicie o serviço World Wide Web. Na linha de comando, digite:
    
        net start w3svc

11. Aplique as alterações feitas pelo LyncServerUpdateInstaller.exe para os bancos de dados SQL Server por meio de uma das seguintes ações:
    
      - Se este for um servidor back-end Enterprise Edition e não houver bancos de dados colocados neste servidor, como os bancos de dados de arquivamento ou monitoramento, digite o seguinte na linha de comando:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - Se este for um servidor back-end Enterprise Edition e houver bancos de dados colocados neste servidor, digite o seguinte em uma linha de comando:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - Se este for um servidor Standard Edition, digite o seguinte em uma linha de comando:
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

