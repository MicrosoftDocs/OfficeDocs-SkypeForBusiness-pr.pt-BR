---
title: 'Lync Server 2013: exibindo informações de link de região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d69040594a04d71f07d004826e4207c0b23612f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535688"
---
# <a name="viewing-network-region-link-information-in-lync-server-2013"></a>Exibindo informações de link de região de rede no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Você pode visualizar os links entre duas regiões de redes como parte do controle de admissão de chamadas (CAC). Regiões dentro de uma rede são vinculadas por conectividade de WAN física. Você pode usar o painel de controle do Lync Server para exibir um link existente entre duas regiões de rede. Para obter detalhes sobre como criar ou modificar um link de região de rede, confira [Configurando links de região de rede no Lync Server 2013](lync-server-2013-configuring-network-region-links.md).

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a>Para exibir um link de região de rede no painel de controle do Lync Server

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Configuração da rede** e em **Link da região**.

4.  Na página **Link da região**, clique no link da região que você deseja ver.
    
    <div>
    

    > [!NOTE]  
    > Você pode ver informações somente sobre um link da região por vez.

    
    </div>

5.  No menu**Editar**, selecione **Mostras detalhes**.

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de link de região de rede usando cmdlets do Windows PowerShell

Você pode exibir os links de região de rede usando o Windows PowerShell e o cmdlet **Get-CsNetworkRegionLink** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-network-region-link-information"></a>Para ver informações do link de região de rede

  - Para exibir informações sobre todos os seus links de região de rede, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsNetworkRegionLink
    
    Esse comando retornará informações parecidas com:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

Para detalhes, consulte [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando links de site de rede no Lync Server 2013](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

