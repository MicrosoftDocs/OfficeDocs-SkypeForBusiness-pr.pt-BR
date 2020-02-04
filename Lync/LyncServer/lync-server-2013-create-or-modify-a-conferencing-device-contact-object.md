---
title: 'Lync Server 2013: criar ou modificar um objeto de contato de dispositivo de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56d594f0bf6e393545f4a7c29785b5f66b328bdc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a>Criar ou modificar um objeto de contato de dispositivo de conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-02_

Para criar um objeto de sala de conferência, primeiro crie uma conta de usuário do Active Directory para representar o dispositivo. Em seguida, use o cmdlet **Enable-CsMeetingRoom** para habilitar essa conta para funcionar como um dispositivo de conferência. Se você precisar alterar as propriedades de um dispositivo de conferência existente, use o cmdlet **set-CsMeetingRoom** .

Esses cmdlets podem ser executados no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Microsoft Lync Server 2010 usando o PowerShell remoto" em.



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a>Criando um dispositivo de conferência

  - Depois de criar a conta de usuário do Active Directory que representa o novo dispositivo de conferência, habilite-o usando o cmdlet **Enable-CsMeetingRoom** . Não se esqueça de incluir uma) a identidade do dispositivo de conferência, b) o pool de registrador onde a conta da sala será hospedada, e c) o endereço SIP a ser atribuído a essa conta. Por exemplo:
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a>Modificando um dispositivo de conferência

  - Para modificar os valores de propriedade de um dispositivo de conferência existente, use o cmdlet **set-CsMeetingRoom** . Por exemplo, o comando a seguir atualiza o número de telefone (LineUri) associado a um dispositivo de conferência:
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

Para obter detalhes, consulte os tópicos da ajuda para o cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) e o cmdlet [set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

