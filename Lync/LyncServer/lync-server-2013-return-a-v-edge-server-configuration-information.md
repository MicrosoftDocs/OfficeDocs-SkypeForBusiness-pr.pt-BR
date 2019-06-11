---
title: 'Lync Server 2013: retornar informações de configuração do servidor de borda A/V'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15096099184525890328dbe1c89d891487b46d87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

O serviço de borda A/V fornece uma maneira para seus usuários internos (usuários que estão conectados à sua rede organizacional) para compartilhar áudio e vídeo com usuários externos (usuários que não estão conectados à sua rede organizacional). O serviço de borda A/V é gerenciado principalmente pelo uso de configurações de borda A/V, a configuração que pode ser configurada no escopo do site ou no escopo do serviço (ou seja, pode ser configurada para um servidor de borda A/V individual).

Para retornar informações sobre as configurações de borda a/V em uso em sua organização, você deve usar o Windows PowerShell e o cmdlet Get-CsAVEdgeConfiguration. Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .

As informações retornadas pelo cmdlet Get-CsAVEdgeConfiguration terão uma aparência semelhante a esta:

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>Para retornar informações de todas as suas configurações de borda A/V

  - O comando a seguir retorna informações sobre todas as configurações de borda a/V em uso no momento em sua organização:
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>Para retornar informações para configurações de borda com escopo de site A/V

  - Para retornar informações sobre uma coleção específica de definições de configuração de borda A/V, especifique a identidade dessa coleção ao executar o cmdlet Get-CsAVEdgeConfiguration. Por exemplo, esse comando retorna informações somente para as configurações aplicadas ao site Redmond:
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>Para retornar informações para configurações de borda de A/V com escopo de serviço

  - E esse comando retorna informações somente para configurações aplicadas a um servidor de borda A/V específico:
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar ou modificar um conjunto de configurações de servidor de borda A/V no Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Excluir uma coleção existente de configurações de servidor de borda A/V no Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

