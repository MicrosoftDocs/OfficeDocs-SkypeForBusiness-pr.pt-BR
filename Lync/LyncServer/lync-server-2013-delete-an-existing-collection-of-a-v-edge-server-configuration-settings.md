---
title: Excluir uma coleção existente de definições de configuração de um servidor de borda A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cc085cd6ac39c4712647795c5baf06eaa68f77a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Excluir uma coleção existente de configurações de servidor de borda A/V no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

O serviço de borda A/V fornece uma maneira para seus usuários internos (usuários que estão conectados à sua rede organizacional) para compartilhar áudio e vídeo com usuários externos (usuários que não estão conectados à sua rede organizacional). O serviço de borda A/V é gerenciado principalmente pelo uso de configurações de borda A/V, a configuração que pode ser configurada no escopo do site ou no escopo do serviço (ou seja, pode ser configurada para um servidor de borda A/V individual).

Quando você instala o Lync Server, uma coleção global de definições de configuração de borda A/V é criada para você. Esta coleção global não pode ser excluída. No entanto, você pode usar o Windows PowerShell e o cmdlet Remove-CsAVEdgeConfiguration para "redefinir" a coleção global; Isso simplesmente significa que todos os valores de propriedade na coleção global serão redefinidos para o valor padrão. Por exemplo, se você tiver definido a propriedade MaxTokenLifetime para 16 horas, essa propriedade será redefinida para o valor padrão de 8 horas.

No entanto, as coleções de configurações personalizadas que você criou em um escopo de site ou o escopo do serviço podem ser excluídas usando o cmdlet Remove-CsAVEdgeConfiguration. Se você excluir configurações de site, os servidores de borda A/V nesse site serão gerenciados pelas configurações globais. Se você excluir as configurações de escopo de serviço, esse servidor será gerenciado por suas configurações de site, se existirem, ou pelas configurações globais, se nenhuma configuração de site estiver disponível.

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15)) .

<div>

## <a name="to-reset-the-global-collection"></a>Para redefinir a coleção global

  - O comando a seguir redefine a coleção global de definições de configuração de borda A/V:
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>Para remover uma coleção do escopo do site

  - Este comando remove as configurações de borda a/V aplicadas ao site Redmond:
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>Para remover uma coleção do escopo do serviço

  - Este comando remove as configurações aplicadas à atl-edge-001.litwareinc.com do servidor de borda a/V:
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Confira também


[Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Criar ou modificar um conjunto de configurações de servidor de borda A/V no Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

