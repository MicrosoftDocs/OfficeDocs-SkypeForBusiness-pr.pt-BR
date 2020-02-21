---
title: 'Lync Server 2013: fazendo backup de dados e configurações principais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 403a32798f84d2be6d045564e3a3e3803240f4a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a>Fazendo backup de dados principais e configurações no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-04-23_

Os procedimentos a seguir usam cmdlets do Shell de gerenciamento do Lync Server para criar arquivos de backup para configurações e dados para os serviços principais. Para obter detalhes sobre as ferramentas usadas nesta seção, incluindo onde estão localizadas, consulte [requisitos de backup e restauração no Lync Server 2013: ferramentas e permissões](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md). Para obter detalhes sobre como fazer backup de dados de arquivamento e monitoramento, consulte fazendo backup de bancos de dados de [arquivamento e monitoramento no Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).

<div>


> [!NOTE]  
> A etapa desta seção para fazer o backup do repositório de gerenciamento central inclui as configurações e a configuração para arquivamento e monitoramento.



</div>

É possível executar os cmdlets descritos nesta seção local ou remotamente.

<div>

## <a name="to-back-up-core-data-and-settings"></a>Para fazer o backup dos principais dados e configurações

1.  Em uma conta de usuário membro do grupo RTCUniversalServerAdmins, faça logon em qualquer computador em sua implantação interna.

2.  Para armazenar os backups criados nas etapas a seguir, crie uma nova pasta compartilhada e atualize o caminho referido por **$Backup** para a nova pasta compartilhada.

3.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

4.  Faça backup do arquivo de configuração do repositório de gerenciamento central. Na linha de comando, digite o seguinte:
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    Por exemplo:
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > Esta etapa exporta a topologia, as políticas e as definições de configuração do Lync Server para um arquivo. Nenhuma outra etapa é necessária para fazer backup dos dados de topologia.

    
    </div>

5.  Copie o arquivo de configuração do repositório de gerenciamento central de backup para\\$backup.

6.  Faça o backup dos dados do serviço de Informações de Local. Na linha de comando, digite o seguinte:
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    Por exemplo:
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  Copie o arquivo de configuração do serviço de informações de local de backup\\para $backup.

8.  Faça backup dos dados do usuário em cada banco de dados back-end de um pool de front-ends e todos os servidores Standard Edition. Na linha de comando, digite o seguinte:
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    Por exemplo:
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  Copie o arquivo de usuário de backup para $Backup\\.

10. Em todos os pools que executam o aplicativo grupo de resposta, faça backup da configuração do grupo de resposta. Faça o seguinte:
    
    1.  Na linha de comando, digite:
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        Por exemplo:
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. Copie o arquivo de configuração do grupo de resposta de backup\\para $backup.

</div>

</div>

<span> </span>

</div>

</div>

</div>

