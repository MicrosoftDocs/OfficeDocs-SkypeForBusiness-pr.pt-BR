---
title: 'Lync Server 2013: Configurando links de site de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50457100f1ba476fd3ddfa923b73acd6bfe6d843
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>Configurando links de site de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Em uma configuração de controle de admissão de chamada, você pode criar políticas entre locais de rede que definem as limitações de largura de banda entre os locais que estejam diretamente vinculados. Quando os locais de uma rede compartilham um link direto, é possível definir limitações de largura de banda às conexões audiovisuais entre esses dois locais. Você não pode usar o painel de controle do Lync Server para configurar as políticas de site de rede, isso só pode ser feito usando cmdlets do Shell de gerenciamento do Lync Server. Você pode criar, modificar e remover um link de site de rede (também conhecido como política entre sites de rede) do Shell de gerenciamento do Lync Server.

<div>

## <a name="to-create-a-network-site-link"></a>Para criar um link de site de rede

1.  Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  No prompt de comando, digite o seguinte comando, substituindo os valores que são válidos para a sua configuração:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Este exemplo cria um novo link de site de rede\_chamado Reno Portland que define as limitações de largura de banda entre os sites de rede Reno e Portland. Os sites de rede e o perfil da política de largura de banda já devem existir antes de executar este comando.

Para obter descrições detalhadas de parâmetros, consulte [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) na documentação do Shell de gerenciamento do Lync Server. Para recuperar uma lista de perfis de políticas de largura de banda que podem ser aplicada ao link de site de rede, chame o cmdlet de **Get-CsNetworkBandwidthPolicyProfile**. Para obter detalhes, consulte [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) na documentação do Shell de gerenciamento do Lync Server.

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>Para modificar um link de site de rede

1.  Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Use o cmdlet **Set-CsNetworkInterSitePolicy** para modificar as propriedades de um link de site de rede fornecido. Você pode modificar um (ou ambos) dos sites conectados e modificar o perfil da política de largura de banda associado ao link. Veja um exemplo de como modificar o perfil de política de largura de banda de um\_link de site chamado Reno Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Para obter descrições detalhadas de parâmetros, consulte [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) na documentação do Shell de gerenciamento do Lync Server.

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>Para excluir um link de site de rede

1.  Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Use o cmdlet **Remove-CsNetworkInterSitePolicy** para remover um link de site de rede. O exemplo a seguir exclui o\_link de site de rede de Portland Reno:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Para obter descrições detalhadas de parâmetros, consulte [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) na documentação do Shell de gerenciamento do Lync Server.

</div>

<div>

## <a name="see-also"></a>Confira também


[Cmdlets do controle de admissão de chamadas no Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)  


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

