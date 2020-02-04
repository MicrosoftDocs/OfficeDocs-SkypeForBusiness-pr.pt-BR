---
title: Atualizar ou atualizar um servidor back-end do servidor ou Standard Edition
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
ms.openlocfilehash: 0526cc7ba6a6abefd066bf07d845ffed3a4107ca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a>Atualizar ou atualizar um servidor back-end do servidor ou da edição Standard no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Este tópico explica como instalar uma atualização em um servidor back-end da edição Enterprise ou um servidor Standard Edition.

Se um servidor back-end estiver inoperante durante pelo menos 30 minutos enquanto você estiver atualizando, os usuários poderão entrar no modo de resiliência. Quando a atualização estiver concluída e os servidores back-end novamente conectados com os servidores de front-end do pool, os usuários retornarão à funcionalidade completa. Se a atualização levar menos de 30 minutos, os usuários não serão afetados.

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Para atualizar um servidor Back End ou um servidor Standard Edition

1.  Faça logon no servidor que você estiver atualizando como um membro da função CsAdministrator.

2.  Faça o download do pacote de atualizações e extraia os arquivos para um disco rígido local.

3.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

4.  Pare os serviços do Lync Server. Na linha de comando, digite:
    
        Stop-CsWindowsService

5.  Pare o serviço World Wide Web. Na linha de comando, digite:
    
        net stop w3svc

6.  Feche todas as janelas do Shell de gerenciamento do Lync Server.

7.  Atualize a atualização.

8.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

9.  Pare os serviços do Lync Server novamente para capturar assemblies global assembly cache (GAC) – d. Na linha de comando, digite:
    
        Stop-CsWindowsService

10. Reinicie o serviço World Wide Web. Na linha de comando, digite:
    
        net start w3svc

11. Aplique as alterações feitas por LyncServerUpdateInstaller. exe aos bancos de dados do SQL Server seguindo um destes procedimentos:
    
      - Se este for um servidor back-end da edição Enterprise e não houver bancos de dados posicionados neste servidor, como arquivar ou monitorar bancos de dados, digite o seguinte na linha de comando:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - Se este for um servidor back-end do Enterprise Edition e houver bancos de dados posicionados neste servidor, digite o seguinte em uma linha de comando:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - Se esse for um servidor Standard Edition, digite o seguinte em uma linha de comando:
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

