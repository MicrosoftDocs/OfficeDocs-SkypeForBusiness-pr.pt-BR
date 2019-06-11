---
title: 'Lync Server 2013: atribuir políticas a um telefone comum de área'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b792d6ae14ee13fd1d95761d2a0d6b0af7bbdfae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844998"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a>Atribuir políticas no Lync Server 2013 a um telefone de área comum

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-20_

Depois de criar sua política para telefones comuns (para obter detalhes, consulte [criar uma política de voz e configurar registros de uso PSTN no Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), você pode atribuir a política a um telefone comum usando o Windows PowerShell e a **concessão-cs apropriada **cmdlet. Esses cmdlets podem ser executados no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a>Atribuir uma política a um único telefone de área comum

  - O comando a seguir atribui a política de voz por usuário RedmondVoice para o telefone de área comum que tem a identidade prédio 14 lobby.
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a>Atribuir uma política a vários telefones comuns de área

  - Neste exemplo, a política de voz por usuário RedmondVoice é atribuída a todos os telefones de área comuns configurados para uso na organização.
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

Para obter detalhes, consulte os tópicos da ajuda para o [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).

</div>

<div>

## <a name="see-also"></a>Confira também


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

