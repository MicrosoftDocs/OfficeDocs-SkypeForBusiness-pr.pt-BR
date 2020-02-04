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
ms.openlocfilehash: 7c56d7ae13be9afa3af7e4732242a86f4be4c458
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a>Habilitar ou desabilitar o hot desk no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-20_

Você pode configurar telefones de área comuns como *telefones de mesa ativa*. Com telefones de mesa ativa, os usuários podem fazer logon em sua própria conta de usuário e, depois de conectados, usar os recursos do Lync Server e suas próprias configurações de perfil de usuário. A divisão de acesso é gerenciada usando políticas de cliente: para habilitar ou desabilitar o uso de redes de mesa, você precisa modificar as políticas de cliente que são usadas pelos seus telefones comuns. Para obter detalhes sobre como determinar as políticas de conferência que foram atribuídas a seus telefones de área comuns, consulte [Exibir informações de telefone de área comum no Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).

Você usa o parâmetro EnableHotdesking do cmdlet **New-CSClientPolicy** ou o cmdlet **set-CSClientPolicy** para habilitar ou desabilitar o uso de uma mesa em um telefone, da seguinte maneira. Execute esses cmdlets a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>


<div>

## <a name="enabling-hot-desking"></a>Habilitando o acesso à mesa

  - Para habilitar o hot desk para um telefone de mesa comum, você deve modificar a política de cliente que foi atribuída a esse telefone (ou conjunto de telefones).
    
    Depois de ter identificado a política que precisa ser modificada, a próxima etapa é usar o cmdlet **set-CsClientPolicy** para definir o parâmetro EnableHotdesking como true. Por exemplo:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - Ou, se preferir, você pode usar o cmdlet **New-CsClientPolicy** para criar uma nova política de cliente que permite o uso de mesas de acesso. Por exemplo:
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> Após a criação da política, você deve atribuí-la aos telefones de área comuns apropriados. Para obter detalhes, consulte <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">atribuir políticas no Lync Server 2013 a um telefone de área comum</A>.



</div>

<div>

## <a name="disabling-hot-desking"></a>Desativando o hot desk

  - Para desativar o hot desk para um telefone de área comum, redefina o parâmetro EnableHotdesking do cmdlet **set-CsClientPolicy** como o valor padrão de false. Por exemplo:
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

Para obter detalhes, consulte os tópicos da ajuda para o cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e o cmdlet [set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

