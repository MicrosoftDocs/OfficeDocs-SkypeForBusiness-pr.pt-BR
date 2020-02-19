---
title: 'Lync Server 2013: exibindo informações de rota de região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb8d163dadafaf8824307bd784bea4670757cd87
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a>Exibindo informações de rota de região de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Cada região de um configuração de CAC (controle de admissão de chamadas) deve ter alguma forma de acessar todas as outras regiões. Enquanto os links da região definem limitações nas conexões entre regiões e representam também os links físicos, uma rota determina o caminho vinculado que a conexão percorrerá de uma região a outra. Use os procedimentos a seguir para exibir as rotas de região de rede existentes no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server 2013. Para obter detalhes sobre como criar ou modificar as rotas de região de rede, consulte [criando ou modificando rotas de região de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a>Para exibir informações de rota de região de rede no painel de controle do Lync Server

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Configuração da Rede** e clique em **Rota de Região**.

4.  Na página **Rota de Região**, clique na rota de região que deseja exibir.
    
    <div>
    

    > [!NOTE]  
    > É possível ver apenas uma rota de região por vez.

    
    </div>

5.  No menu **Editar**, clique em **Mostrar detalhes**.

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de rota de região de rede usando cmdlets do Windows PowerShell

As informações de rota de região de rede podem ser visualizadas usando o Windows PowerShell e o cmdlet Get-CsNetworkInterRegionRoute. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-view-network-region-route-information"></a>Para exibir informações de rota de região de rede

  - Para exibir informações sobre todas as suas rotas de região de rede, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsNetworkInterRegionRoute
    
    Isto retorna informações semelhantes à seguinte:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

Para obter mais informações, consulte o tópico de ajuda do cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute).

</div>

<div>

## <a name="see-also"></a>Confira também


[Criando ou modificando rotas de região de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[Excluindo rotas de região de rede existentes no Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

