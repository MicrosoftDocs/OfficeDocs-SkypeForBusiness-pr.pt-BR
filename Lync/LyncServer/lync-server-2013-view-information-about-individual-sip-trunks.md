---
title: 'Lync Server 2013: exibir informações sobre troncos SIP individuais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c7d29c7318c8fb6d1cd08775853eb46b1c898d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>Exibir informações sobre troncos SIP individuais no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Os troncos SIP são usados para conectar a rede de telefone IP do Lync Server 2013 com a rede telefônica comutada pública. Na versão anterior do produto, os troncos foram usados para rotear chamadas de saída de um Servidor de Mediação para um gateway PSTN e cada gateway estava limitado a um único tronco. Como resultado, um gateway PSTN e um tronco SIP eram essencialmente idênticos. Para os administradores, isso significava que seria possível exibir informações sobre um tronco SIP individual simplesmente exibindo informações sobre o gateway PSTN associado.

No Lync Server 2013, no entanto, vários troncos agora podem ser atribuídos a um único gateway PSTN; Isso significa que os gateways e troncos não são mais um e iguais. Por outro lado, isso significa que os administradores devem usar o novo cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) para exibir informações sobre um tronco SIP individual.

O cmdlet Get-CsTrunk pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>Para visualizar as informações de todos os seus troncos SIP

  - O seguinte comando retorna informações sobre todos os troncos SIP usados em sua organização:
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>Para visualizar as informações de um tronco SIP específico

  - Este comando retorna informações somente para o tronco SIP com a Identidade PstnGateway:192.168.0.240:
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Exibir informações de todos os troncos SIP atribuídos a um pool

  - Neste exemplo, as informações são retornadas para todos os troncos SIP atribuídos ao pool atl-cs-001.litwareinc.com:
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

