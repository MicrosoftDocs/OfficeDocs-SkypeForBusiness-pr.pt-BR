---
title: 'Lync Server 2013: criar políticas entre sites de rede'
description: 'Lync Server 2013: criar políticas entre sites de rede.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9666efcb9c6da459a8e50eeae66cd1a513b46f65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562267"
---
# <a name="create-network-intersite-policies-in-lync-server-2013"></a>Criar políticas entre sites de rede no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Uma *política entre sites de rede* define limitações de largura de banda entre sites com links de WAN diretos entre eles.

Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> Uma política entre sites de rede é obrigatória <EM>somente</EM> se houver um link cruzado direto entre dois sites de rede.



</div>

Na região América do Norte da topologia de exemplo, existe um link direto entre os sites Reno e Albuquerque. Esses dois sites exigem uma política entre sites que aplique um perfil de política de largura de banda adequado. O exemplo a seguir aplica o perfil de link de 20 MB \_ .

<div>

## <a name="to-create-a-network-intersite-policy"></a>Para criar uma política entre sites da rede

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o cmdlet New-CsNetworkInterSitePolicy para criar política entre sites de rede e aplicar um perfil de política de largura de banda apropriado para dois sites que possuem um link cruzado direto. Por exemplo, execute:
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  Repita a etapa 2 conforme o necessário para criar políticas entre sites de rede para todos os pares de sites da rede que possuírem um link cruzado direto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

