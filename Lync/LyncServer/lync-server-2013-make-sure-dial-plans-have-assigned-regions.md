---
title: 'Lync Server 2013: Certifique-se de que os planos de discagem têm opções atribuídas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75c5aa91470accf0f25478b9233e1efb90357251
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>Verifique se os planos de discagem do Lync Server 2013 atribuiram regiões

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2010-11-02_

Os planos de discagem que são usados para conferência discada precisam ter uma **região de conferência discada** especificada para associar números de acesso à conferência discada com o plano de discagem apropriado. Ao configurar um plano de discagem, você especifica a região de conferência discada que se aplica ao plano de discagem. Em seguida, ao criar o número de acesso de discagem, selecione as regiões que associam o número de acesso com os planos de discagem apropriados.

Como é importante especificar uma região para todos os planos de discagem, recomendamos que você use este procedimento para verificar se todos os planos de discagem têm regiões. Esta etapa é opcional.

Use o cmdlet **Get-CsDialPlan** para verificar se a região está definida para todos os planos de discagem de conferência discada. Se a região não existir nos planos de discagem, você poderá usar o cmdlet **Set-CsDialPlan** para defini-la. Você também pode usar o painel de controle do Lync Server para atualizar a região em planos de discagem existentes. Para obter detalhes sobre como usar o painel de controle do Lync Server, consulte [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Para verificar se os planos de discagem têm a propriedade de região definida

1.  Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**ou **CsAdministrator**.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Execute o seguinte no prompt de comando:
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    Por exemplo:
    
        Get-CsDialPlan
    
    Neste exemplo, todos os planos de discagem configurados para sua organização são retornados.

4.  Revise os planos de discagem retornados para identificar todos que estão faltando na região da conferência discada. Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server.

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>Para definir a propriedade de região de um plano de discagem

1.  Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**ou **CsAdministrator**.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Para todos os planos de discagem que não têm a região de conferência discada, execute:
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    Por exemplo:
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    Neste exemplo, o plano de discagem com Identidade de Redmond é modificado para definir a propriedade DialinConferencingRegion como "Costa Leste dos EUA". Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

