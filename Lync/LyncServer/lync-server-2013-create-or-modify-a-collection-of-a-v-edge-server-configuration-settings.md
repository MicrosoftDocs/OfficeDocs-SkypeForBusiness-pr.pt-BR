---
title: Criar ou modificar um conjunto de configurações de servidor de borda A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4010c209e1231c47c328d616f686f55fc89008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Criar ou modificar um conjunto de configurações de servidor de borda A/V no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

O serviço de borda A/V fornece uma maneira para seus usuários internos (usuários que estão conectados à sua rede organizacional) para compartilhar áudio e vídeo com usuários externos (usuários que não estão conectados à sua rede organizacional). O serviço de borda A/V é gerenciado principalmente pelo uso de configurações de borda A/V, a configuração que pode ser configurada no escopo do site ou no escopo do serviço (ou seja, pode ser configurada para um servidor de borda A/V individual).

Quando você instala o Lync Server, uma coleção global de definições de configuração de borda A/V é criada para você. Além disso, você pode usar o Windows PowerShell e o cmdlet New-CsAVEdgeConfiguration para criar novas configurações no escopo do site ou no escopo do serviço (ou seja, para um servidor de borda A/V individual). Se você criar novas configurações, lembre-se de que:

  - As configurações definidas no escopo do serviço (ou seja, em um servidor individual) têm prioridade sobre tudo.

  - As configurações definidas no escopo do site têm prioridade sobre as configurações definidas no escopo global. No entanto, as configurações de escopo do serviço também substituirão as configurações de escopo do site.

  - As configurações no escopo global serão usadas apenas se não houver configurações de serviço configuradas no servidor individual e se não houver configurações de site para o site em que o servidor está localizado.

Qualquer uma de suas configurações pode ser modificada usando o cmdlet Set-CsAVEdgeConfiguration. Para obter mais informações, consulte os tópicos da ajuda para os cmdlets [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) e [set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) .

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a>Para criar novas configurações de borda a/V no escopo do site

  - O comando a seguir cria uma nova coleção de configurações de borda a/V para o site Redmond:
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a>Para criar configurações personalizadas de borda A/V no escopo do site

  - Como nenhum parâmetro adicional foi incluído, essas novas configurações usarão os valores padrão para o serviço de borda A/V. Você também pode adicionar parâmetros e valores de parâmetro adicionais para criar uma coleção personalizada. Por exemplo, esse comando define a propriedade MaxTokenLifetime como 4 horas (04 horas: 00 minutos: 00 segundos):
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a>Para criar configurações personalizadas de borda a/V no escopo do serviço

  - Esse comando cria uma coleção semelhante aplicada à atl-edge-001.litwareinc.com do servidor de borda a/V:
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a>Para modificar as definições de configuração de borda A/V existentes

  - Neste exemplo, o cmdlet Set-CsAVEdgeConfiguration é usado para alterar o tempo de vida máximo do token para o site Redmond para 12 horas:
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a>Confira também


[Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Excluir uma coleção existente de configurações de servidor de borda A/V no Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))  
[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

