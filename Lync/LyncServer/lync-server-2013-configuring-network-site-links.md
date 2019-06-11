---
title: 'Lync Server 2013: Configurando links de sites de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0ddd5e28cd37cd31e28e5c6427b9b700b5a4c9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>Configurar links de sites de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Em uma configuração de controle de admissão de chamadas (CAC), você pode criar políticas entre sites de rede que definem as limitações de largura de banda entre sites vinculados diretamente. Quando os sites de rede compartilham um link direto, as limitações de largura de banda para conexões de áudio e vídeo podem ser definidas entre esses dois sites. Você não pode usar o painel de controle do Lync Server para configurar políticas de site de rede, isso pode ser feito somente usando cmdlets do Shell de gerenciamento do Lync Server. Você pode criar, modificar e remover um link de site de rede (também conhecido como política entre sites de rede) a partir do Shell de gerenciamento do Lync Server.

<div>

## <a name="to-create-a-network-site-link"></a>Para criar um link de site de rede

1.  Faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [permissões de configuração de representante no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  No prompt de comando, digite o comando a seguir, substituindo os valores válidos para a sua configuração:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    Este exemplo cria um novo link de site de rede\_chamado Reno Portland que define as limitações de largura de banda entre os sites de rede Reno e Portland. Os sites de rede e o perfil da política de largura de banda já devem existir antes de executar este comando.

Para obter descrições de parâmetros detalhadas, consulte [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) na documentação do Shell de gerenciamento do Lync Server. Para recuperar uma lista de perfis de política de largura de banda que podem ser aplicados ao link de site de rede, chame o cmdlet **Get-CsNetworkBandwidthPolicyProfile** . Para obter detalhes, consulte [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) na documentação do Shell de gerenciamento do Lync Server.

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>Para modificar um link de site de rede

1.  Faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [permissões de configuração de representante no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Use o cmdlet **set-CsNetworkInterSitePolicy** para modificar as propriedades de um determinado link de site de rede. Você pode modificar um (ou ambos) ou os sites conectados, e pode modificar o perfil da política de largura de banda associado ao link. Aqui está um exemplo de modificação do perfil da política de largura de banda de um\_link de site chamado Reno Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Para obter descrições de parâmetros detalhadas, consulte [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) na documentação do Shell de gerenciamento do Lync Server.

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>Para excluir um link de site de rede

1.  Faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [permissões de configuração de representante no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Use o cmdlet **Remove-CsNetworkInterSitePolicy** para remover um link de site de rede. O exemplo a seguir exclui o\_link de site de rede de Portland Reno:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Para obter descrições de parâmetros detalhadas, consulte [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) na documentação do Shell de gerenciamento do Lync Server.

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

