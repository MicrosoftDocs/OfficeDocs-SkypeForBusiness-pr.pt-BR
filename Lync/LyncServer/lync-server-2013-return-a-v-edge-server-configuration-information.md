---
title: 'Lync Server 2013: retornar informações de configuração do servidor de borda A/V'
description: 'Lync Server 2013: retornar informações de configuração do servidor de borda A/V.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f72fccfe51b946dc0dc285aee12a07e59c844b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575437"
---
# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a>Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

O serviço de Borda A/V fornece uma forma para seus usuários internos (usuários que não estão logados na sua rede organizacional) a compartilhar áudio e vídeo com usuários externos (usuários que não estão logados na sua rede organizacional). O serviço de Borda A/V é primariamente gerenciado utilizando definições de configuração de Borda A/V, configuração que pode ser definida no escopo do local ou no escopo do serviço (isto é, pode ser configurado para um serviço de Borda A/V individual.

Para retornar informações sobre as definições de configuração de borda A/V em uso na sua organização, você deve usar o Windows PowerShell e o cmdlet Get-CsAVEdgeConfiguration. Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .

As informações retornadas pelo cmdlet Get-CsAVEdgeConfiguration terão uma aparência semelhante a esta:

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a>Para retornar informações de todas as suas definições de configuração de borda A/V

  - O comando a seguir retorna informações sobre todas as definições de configuração de borda A/V atualmente em uso na sua organização:
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a>Para retornar informações para definições de configuração de borda A/V com escopo de site

  - Para retornar informações sobre uma coleção específica de definições de configuração de borda A/V, especifique a identidade dessa coleção ao executar o cmdlet Get-CsAVEdgeConfiguration. Por exemplo, este comando retorna informações somente para as configurações aplicadas ao site Redmond:
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a>Para retornar informações para definições de configuração de borda de A/V de escopo de serviço

  - E este comando retorna informações somente para as configurações aplicadas a um servidor de borda A/V específico:
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar ou modificar uma coleção de definições de configuração de servidor de borda A/V no Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Excluir um conjunto existente de definições de configuração de servidor de borda A/V no Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

