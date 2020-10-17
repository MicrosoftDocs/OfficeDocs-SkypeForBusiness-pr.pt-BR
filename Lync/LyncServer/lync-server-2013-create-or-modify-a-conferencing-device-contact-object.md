---
title: 'Lync Server 2013: criar ou modificar um objeto de contato do dispositivo de conferência'
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
ms.openlocfilehash: 8ff0a3dbc50b48994752e48ea8889508f2376068
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506168"
---
# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a>Criar ou modificar um objeto de contato de dispositivo de conferência no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-02_

Para criar um objeto de sala de conferência, primeiro crie uma conta de usuário do Active Directory para representar o dispositivo. Em seguida, use o cmdlet **Enable-CsMeetingRoom** para permitir que essa conta funcione como um dispositivo de conferência. Se você precisar alterar as propriedades de um dispositivo de conferência existente, use o cmdlet **set-CsMeetingRoom** .

Esses cmdlets podem ser executados a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a>Criando um dispositivo de conferência

  - Depois de criar a conta de usuário do Active Directory que representa o novo dispositivo de conferência, habilite-o usando o cmdlet **Enable-CsMeetingRoom** . Certifique-se de incluir uma, a identidade do dispositivo de conferência, b) o pool de registradores onde a conta da sala será hospedada e c) o endereço SIP a ser atribuído a essa conta. Por exemplo:
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a>Modificando um dispositivo de conferência

  - Para modificar os valores de propriedade de um dispositivo de conferência existente, use o cmdlet **set-CsMeetingRoom** . Por exemplo, o seguinte comando atualiza o número de telefone (LineUri) associado a um dispositivo de conferência:
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

Para obter detalhes, consulte os tópicos de ajuda para o cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) e o cmdlet [set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

