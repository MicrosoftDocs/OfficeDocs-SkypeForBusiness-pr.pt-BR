---
title: 'Lync Server 2013: exibir informações sobre troncos SIP individuais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d01a56ca0365c041ae9469dee2d328f81acd3e65
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523578"
---
# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>Exibir informações sobre troncos SIP individuais no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Os troncos SIP são usados para conectar a rede de telefone de voz sobre IP do Lync Server 2013 com a rede telefônica pública comutada. Na versão anterior do produto, os troncos foram usados para rotear chamadas de saída de um servidor de mediação para um gateway PSTN, e cada gateway estava limitado a um único tronco. Como resultado, um gateway PSTN e um tronco SIP eram essencialmente idênticos. Para administradores, isso significava que poderia exibir informações sobre um tronco SIP individual simplesmente exibindo informações sobre o gateway PSTN associado.

No Lync Server 2013, no entanto, vários troncos agora podem ser atribuídos a um único gateway PSTN; Isso significa que os gateways e troncos não são mais um e o mesmo. Por sua vez, isso significa que os administradores devem usar o novo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) para exibir informações sobre um tronco SIP individual.

O cmdlet Get-CsTrunk pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>Para exibir informações de todos os troncos SIP

  - O seguinte comando retorna informações sobre todos os troncos SIP em uso na sua organização:
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>Para exibir informações de um tronco SIP específico

  - Este comando retorna informações somente para o tronco SIP com a identidade PstnGateway: 192.168.0.240:
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Exibindo informações de todos os troncos SIP atribuídos a um pool

  - Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

