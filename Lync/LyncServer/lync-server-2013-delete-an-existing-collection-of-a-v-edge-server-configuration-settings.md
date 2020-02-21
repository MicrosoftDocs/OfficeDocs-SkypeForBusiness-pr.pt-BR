---
title: Excluir um conjunto existente de definições de configuração do servidor de borda A/V
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
ms.openlocfilehash: 7043b2ce5fd35e36615b7b92d1561d725a86cc92
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a>Excluir um conjunto existente de definições de configuração de servidor de borda A/V no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

O serviço de Borda A/V fornece uma forma para seus usuários internos (usuários que não estão logados na sua rede organizacional) a compartilhar áudio e vídeo com usuários externos (usuários que não estão logados na sua rede organizacional). O serviço de Borda A/V é primariamente gerenciado utilizando definições de configuração de Borda A/V, configuração que pode ser definida no escopo do local ou no escopo do serviço (isto é, pode ser configurado para um serviço de Borda A/V individual.

Quando você instala o Lync Server, uma coleção global de definições de configuração de borda A/V é criada para você. Esta coleção global não pode ser excluída. No entanto, você pode usar o Windows PowerShell e o cmdlet Remove-CsAVEdgeConfiguration para "redefinir" a coleção global; Isso simplesmente significa que todos os valores de propriedade na coleção global serão redefinidos para o valor padrão. Por exemplo, se você tiver definido a propriedade MaxTokenLifetime para 16 horas, essa propriedade será redefinida com o valor padrão de 8 horas.

No entanto, as coleções de configurações personalizadas que você criou no escopo do site ou no escopo do serviço podem ser excluídas usando o cmdlet Remove-CsAVEdgeConfiguration. Se você excluir as configurações do site, os servidores de borda A/V desse site serão gerenciados pelas configurações globais. Se você excluir as configurações de escopo de serviço, esse servidor será gerenciado por suas configurações de site, se existirem, ou pelas configurações globais, se nenhuma configuração de site estiver disponível.

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) .

<div>

## <a name="to-reset-the-global-collection"></a>Para redefinir a coleção global

  - O comando a seguir redefine o conjunto global de definições de configuração de borda A/V:
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a>Para remover uma coleção do escopo do site

  - Este comando remove as definições de configuração de borda A/V aplicadas ao site Redmond:
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a>Para remover uma coleção do escopo do serviço

  - Este comando remove as configurações aplicadas ao servidor de borda A/V atl-edge-001.litwareinc.com:
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>Confira também


[Retornar as informações de configuração do servidor de borda A/V no Lync Server 2013](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Criar ou modificar uma coleção de definições de configuração de servidor de borda A/V no Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[Servidores de borda de áudio/vídeo (A/V) no Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

