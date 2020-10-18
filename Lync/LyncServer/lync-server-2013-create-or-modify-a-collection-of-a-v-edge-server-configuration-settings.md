---
title: Criar ou modificar uma coleção de definições de configuração do servidor de borda A/V
description: Criar ou modificar uma coleção de definições de configuração de servidor de borda A/V.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cdf7dca19446f4eac584564eed776f7fde47bfe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578337"
---
# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Criar ou modificar uma coleção de definições de configuração de servidor de borda A/V no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

O serviço de Borda A/V fornece uma forma para seus usuários internos (usuários que não estão logados na sua rede organizacional) a compartilhar áudio e vídeo com usuários externos (usuários que não estão logados na sua rede organizacional). O serviço de Borda A/V é primariamente gerenciado utilizando definições de configuração de Borda A/V, configuração que pode ser definida no escopo do local ou no escopo do serviço (isto é, pode ser configurado para um serviço de Borda A/V individual.

Quando você instala o Lync Server, uma coleção global de definições de configuração de borda A/V é criada para você. Além disso, você pode usar o Windows PowerShell e o cmdlet New-CsAVEdgeConfiguration para criar novas configurações no escopo do site ou no escopo do serviço (ou seja, para um servidor de borda A/V individual). Se você criar novas configurações, tenha em mente que:

  - As definições configuradas no escopo de serviço (isto é, em um servidor individual ) têm prioridade sobre tudo.

  - As definições configuradas no escopo do site têm prioridade sobre as definições configuradas no escopo global. No entanto, as definições de escopo de serviço também substituem as configurações de escopo do site.

  - As configurações no escopo global serão usadas somente se não há definições de serviço configuradas no servidor individual e se não há configurações de site para o site onde o servidor está localizado.

Qualquer configuração pode ser modificada utilizando o cmdlet Set-CsAVEdgeConfiguration. Para obter mais informações, consulte os tópicos de ajuda para os cmdlets [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) e [set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) .

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>Para criar novas definições de configuração de borda a/V no escopo do site

  - O comando a seguir criar uma nova coleção de definições de configuração de Borda A/V para o site Redmond:
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>Para criar definições de configuração de borda A/V personalizadas no escopo do site

  - Por não haver parâmetros adicionais incluídos, essas novas configurações utilizarão os valores padrão para o serviço de Borda A/V. De forma alternativa, você pode adicionar parâmetros e valores de parâmetros para criar uma coleção personalizada. Por exemplo, este comando define a propriedade MaxTokenLifetime para 4 horas (04 horas : 00 minutos : 00 segundos):
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>Para criar definições de configuração de borda A/V personalizada no escopo do serviço

  - Este comando cria um conjunto similar aplicado ao servidor de Borda A/V atl-edge-001.litwareinc.com:
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>Para modificar as definições de configuração de borda A/V existentes

  - Neste exemplo, o cmdlet Set-CsAVEdgeConfiguration é utilizado para alterar o tempo de vida máximo do token para o site Redmond para 12 horas:
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>Confira também


[Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Excluir um conjunto existente de definições de configuração de servidor de borda A/V no Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))  
[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

