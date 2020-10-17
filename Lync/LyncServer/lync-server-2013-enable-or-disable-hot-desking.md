---
title: 'Lync Server 2013: habilitar ou desabilitar o hot desk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb052f3a0743edac47ccfbe3786943820c59f78f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515538"
---
# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Habilitar ou desabilitar o hot desk no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-20_

Você pode configurar telefones de área comum como *telefones de mesa*. Com telefones de uma só mesa, os usuários podem fazer logon em sua própria conta de usuário e, depois de estarem conectados, usar os recursos do Lync Server e suas próprias configurações de perfil de usuário. O hot desk é gerenciado com o uso de políticas de cliente: para habilitar ou desabilitar o hot desk, você precisa modificar as políticas de cliente usadas por seus telefones de área comum. Para obter detalhes sobre como determinar as políticas de conferência que foram atribuídas a seus telefones de área comum, consulte [Exibir informações de telefone de área comum no Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).

Você usa o parâmetro EnableHotdesking do cmdlet **New-CSClientPolicy** ou o cmdlet **set-CSClientPolicy** para habilitar ou desabilitar o hot desk em um telefone, da seguinte maneira. Execute estes cmdlets do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>


<div>

## <a name="enabling-hot-desking"></a>Habilitando o hot desk

  - Para habilitar o hot desk para um telefone de área comum, você deve modificar a política de cliente que foi atribuída a esse telefone (ou a uma coleção de telefones).
    
    Depois de identificar a política que precisa ser modificada, a próxima etapa é usar o cmdlet **set-CsClientPolicy** para definir o parâmetro EnableHotdesking como true. Por exemplo:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - Como alternativa, você pode usar o cmdlet **New-CsClientPolicy** para criar uma nova política de cliente que habilita o hot desk. Por exemplo:
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> Após a criação da política, você deve atribuí-la aos telefones de área comum apropriados. Para obter detalhes, consulte <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">atribuir políticas no Lync Server 2013 a um telefone de área comum</A>.



</div>

<div>

## <a name="disabling-hot-desking"></a>Desabilitando o hot desk

  - Para desabilitar o hot desk para um telefone de área comum, redefina o parâmetro EnableHotdesking do cmdlet **set-CsClientPolicy** para o valor padrão false. Por exemplo:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

Para obter detalhes, consulte os tópicos de ajuda para o cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e o cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

