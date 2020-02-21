---
title: 'Lync Server 2013: primeiras etapas antes de começar a migrar usuários do Lync Online para o Lync local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4165df6829818b90a22eff4f90ac8072876b4831
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>Primeiras etapas antes de começar a migrar usuários do Lync Online para o Lync local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-08_

Antes de começar a mover os usuários do Lync Online para o seu ambiente local, verifique se todas as opções a seguir são verdadeiras:

  - O ambiente local do Lync Server deve ser totalmente implantado e validado. Para obter mais informações, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).

  - Seu locatário do Lync Online deve ser configurado para acesso ao PowerShell remoto.
    
    Para fazer isso, primeiro instale o módulo do Lync Online para Windows PowerShell, que você pode obter aqui [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911):.
    
    Após instalar o módulo, você pode estabelecer uma sessão remota digitando os seguintes cmdlets no Shell de gerenciamento do Lync Server:
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    Para obter mais informações sobre como estabelecer uma sessão remota do PowerShell com o Lync Online, consulte [conectar-se ao Lync Online usando o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
    Para obter mais informações sobre como usar o módulo PowerShell do Lync Online, consulte [using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

  - O Lync Online deve estar configurado para o espaço de endereçamento SIP compartilhado. Para fazer isso, primeiro inicie uma sessão remota do PowerShell com o Lync Online. Em seguida, execute o seguinte cmdlet:
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

Depois de concluir essas etapas, você pode passar para [migrar os usuários do Lync Online para o Lync no local no Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).

</div>

<span> </span>

</div>

</div>

</div>

