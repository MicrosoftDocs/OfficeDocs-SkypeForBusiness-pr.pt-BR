---
title: Lync Server 2013; Criar rotas interregions de rede
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 3909c41328e18302ef1104ac05d9a7c7987f57d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>Criar rotas de interregião de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-20_

Uma *rota interregião de rede* define a rota entre um par de regiões de rede. Cada par de regiões de rede em sua implantação de controle de admissão de chamadas requer uma rota interregion de rede. Isso permite que cada região da rede dentro da implantação acesse todas as demais regiões.

Embora os links de região definam as limitações de largura de banda nas conexões entre regiões, uma rota entre regiões determina qual caminho vinculado a conexão passará de uma região para outra.

Para obter detalhes sobre como trabalhar com rotas de interregião de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

Na topologia de exemplo, as rotas interregion de rede devem ser definidas para cada um dos três pares de regiões: América do Norte/EMEA, EMEA/Ásia e América do Norte/Ásia-Pacífico.

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>Para criar rotas de interregião de rede usando o Shell de gerenciamento do Lync Server

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o cmdlet **New-CsNetworkInterRegionRoute** para definir as rotas necessárias. Por exemplo, execute:
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > A rota interregião da rede América do Norte/Ásia requer dois links de região de rede porque não há um link de região de rede direto entre eles.

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>Para criar rotas de interregião de rede usando o painel de controle do Lync Server

1.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação esquerda, clique em **Configuração de rede**.

3.  Clique no botão de navegações **Rota de Região**.

4.  Clique em **Novo**.

5.  Na página **nova rota de região** , clique em **nome** e digite um nome para a rota interregião de rede.

6.  Clique na **região \#de rede 1**e, em seguida, clique em uma região de rede na lista que você deseja \#direcionar para a região de rede 2.

7.  Clique em **rede \#2**e, em seguida, clique em uma região de rede na lista que você deseja direcionar \#para a região de rede 1.

8.  Clique em **Adicionar** ao lado do campo de **links de região de rede** e, em seguida, adicione um link de região de rede que será usado na rota interregião de rede.
    
    <div class=" ">
    

    > [!NOTE]  
    > Se você estiver criando uma rota para duas regiões de rede que não têm um link de região de rede direta de rede entre elas, deverá adicionar todos os links necessários para concluir a rota. Por exemplo, a rota de interregião da rede América do Norte/Ásia requer dois links de região de rede porque não há um link de região de rede direto entre eles.

    
    </div>

9.  Clique em **Confirmar**.

10. Para concluir a criação de rotas interregions de rede para a sua topologia, repita as etapas de 4 a 9 com configurações para outras rotas interregions de rede.

</div>

</div>

<span> </span>

</div>

</div>

</div>

