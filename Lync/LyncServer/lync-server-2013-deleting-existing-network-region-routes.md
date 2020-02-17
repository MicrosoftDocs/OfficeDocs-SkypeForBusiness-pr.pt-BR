---
title: 'Lync Server 2013: excluindo rotas de região de rede existentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 030980ca18e21915f514435a8682ec8ddcf78286
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a>Excluindo rotas de região de rede existentes no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Cada região de um configuração de CAC (controle de admissão de chamadas) deve ter alguma forma de acessar todas as outras regiões. Enquanto os links da região definem limitações nas conexões entre regiões e representam também os links físicos, uma rota determina o caminho vinculado que a conexão percorrerá de uma região a outra. Você pode usar o painel de controle do Lync Server para configurar rotas de região de rede. No painel de controle do Lync Server, você pode criar, modificar ou excluir uma rota de região de rede. Use este tópico para excluir rotas de região de rede existentes. Para obter detalhes sobre como criar ou modificar as rotas de região de rede, consulte [criando ou modificando rotas de região de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).

<div>

## <a name="to-delete-a-network-region-route"></a>Para excluir uma rota de região de rede

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Configuração de Rede** e depois em **Rota de Região**.

4.  Na página **Rota de Região**, clique na rota de região que deseja excluir.
    
    <div>
    

    > [!NOTE]  
    > Você pode excluir mais de uma rota de região por vez. Para fazer isso, pressione CTRL e selecione várias rotas de região mantendo pressionada a tecla CTRL. Para selecionar todas as rotas da região, clique em <STRONG>Selecionar tudo</STRONG> no menu <STRONG>Editar</STRONG>.

    
    </div>

5.  No menu **Editar**, clique em **Excluir**.

6.  Clique em **OK**.

</div>

<div>

## <a name="see-also"></a>Confira Também


[Criando ou modificando rotas de região de rede no Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md)  


[Configurar uma Rota de Região de Rede](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))  


[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

