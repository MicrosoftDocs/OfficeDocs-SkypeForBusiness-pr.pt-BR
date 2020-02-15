---
title: 'Lync Server 2013: importar regras de atualização de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import Device Update rules
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994056(v=OCS.15)
ms:contentKeyID: 51803967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7c0700606966713d9828f538d37600a718dcd43
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-device-update-rules-in-lync-server-2013"></a>Importar regras de atualização de dispositivo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

As regras de atualização de dispositivo podem ser importadas apenas usando o Windows PowerShell e o cmdlet **Import-CsDeviceUpdate** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 using Remote PowerShell" em.



</div>

<div>


<div>

## <a name="to-import-device-update-rules-to-a-single-web-server"></a>Para importar regras de atualização de dispositivo para um único servidor Web

  - O seguinte comando importa as regras de atualização de dispositivo para o servidor Web atl-cs-001.litwareinc.com:
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

</div>

<div>

## <a name="to-import-device-update-rules-to-all-your-web-servers"></a>Para importar regras de atualização de dispositivo para todos os seus servidores Web

  - Neste exemplo, as regras de atualização de dispositivo são importadas para todos os servidores Web implantados em sua organização. Para que esse comando funcione, as atualizações \\ \\da\\pasta ATL-FS-001.litwareinc.com devem ser compartilhadas e disponíveis para todos os servidores Web.
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

</div>

Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Exibir informações sobre as regras de atualização de dispositivos no Lync Server 2013](lync-server-2013-view-information-about-device-update-rules.md)  
[Aprovar uma regra de atualização de dispositivo no Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

