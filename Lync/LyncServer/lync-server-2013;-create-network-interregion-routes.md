---
title: Lync Server 2013; Criar rotas entre regiões de rede
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 2890d903df512e2f7eef26e6d1c22fa5bc029839
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508527"
---
# <a name="create-network-interregion-routes-in-lync-server-2013"></a>Criar rotas entre regiões de rede no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-20_

Uma *rota entre regiões de rede* define a rota entre um par de regiões de rede. Cada par de regiões de rede em sua implantação do serviço de controle de admissão de chamadas exige uma rota entre regiões de rede. Isso permite que cada região da rede dentro da implantação acesse todas as demais regiões.

Enquanto os vínculos de região definem limitações de largura de banda nas conexões entre regiões, uma rota entre regiões de rede determina o caminho vinculado que a conexão percorrerá de uma região à outra.

Para obter detalhes sobre como trabalhar com rotas entre regiões de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

Na topologia de exemplo, as rotas entre regiões de rede devem ser definidas para cada um dos três pares de regiões: América do Norte/EMEA, EMEA/APAC e América do Norte/APAC.

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>Para criar rotas entre regiões de rede usando o Shell de gerenciamento do Lync Server

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

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
    > A rota entre regiões de rede América do Norte/APAC requer dois links de regiões de rede porque não há um link de região de rede direta entre elas.

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>Para criar rotas entre regiões de rede usando o painel de controle do Lync Server

1.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação esquerda, clique em **Configuração de Rede**.

3.  Clique no botão de navegações **Rota de Região**.

4.  Clique em **Novo**.

5.  Na página **Nova Rota de Região**, clique em **Nome** e digite um nome para a rota entre regiões de rede.

6.  Clique em **região de rede \# 1**e, em seguida, clique em uma região de rede na lista que você deseja rotear para a região de rede \# 2.

7.  Clique em **região de rede \# 2**e, em seguida, clique em uma região de rede na lista que você deseja rotear para a região de rede \# 1.

8.  Clique em **Adicionar** próximo ao campo **Links de Região de Rede**  e adicione um link de região de rede que será usado na rota entre regiões de rede.
    
    <div class=" ">
    

    > [!NOTE]  
    > Se você estiver criando uma rota para duas regiões de rede que não têm um link de região de rede direta de rede entre elas, deverá adicionar todos os links necessários para concluir a rota. Por exemplo, a rota entre regiões de rede América do Norte/APAC requer dois links de região de rede porque não há nenhum link de região de rede direta entre elas.

    
    </div>

9.  Clique em **Confirmar**.

10. Para concluir a criação de rotas entre regiões de rede para sua topologia de rede, repita as etapas 4 a 9 com configurações de outras rotas entre regiões de rede.

</div>

</div>

<span> </span>

</div>

</div>

</div>

