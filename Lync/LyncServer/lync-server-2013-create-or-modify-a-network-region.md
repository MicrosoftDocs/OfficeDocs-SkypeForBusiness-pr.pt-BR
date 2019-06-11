---
title: 'Lync Server 2013: criar ou modificar uma região de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a9b7a8adbb4ca4c0853aa7013662433701201d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>Criar ou modificar uma região de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

*Regiões de rede* são os hubs de rede ou backbones usados na configuração de controle de admissão de chamadas, E9-1-1 e bypass de mídia. Use os procedimentos a seguir para criar ou modificar regiões de rede. Por exemplo, se você já tiver criado regiões de rede para um recurso de voz, não precisará criar novas regiões de rede; outros recursos avançados do Enterprise Voice usarão essas mesmas regiões de rede. No entanto, pode ser necessário modificar uma definição de região da rede existente para aplicar as configurações específicas do recurso. Por exemplo, se você cria regiões da rede para o E9-1-1 (que não exige um local central associado) e depois implanta o serviço de controle de admissão de chamadas, precisará modificar as definições de região da rede para especificar um local central. Para obter detalhes, consulte [configurar regiões de rede para o CAC no Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).

<div>


> [!NOTE]  
> Qualquer requisito específico de recurso para definições de região de rede está documentado nos tópicos de implantação do recurso.



</div>

Para obter detalhes sobre como trabalhar com regiões de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>Criar uma região de rede

Crie uma região de rede que possa ser usada pelo controle de admissão de chamadas, E9-1-1 ou bypass de mídia.

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>Para criar uma região de rede usando o Shell de gerenciamento do Lync Server

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o cmdlet New-CsNetworkRegion para criar regiões da rede:
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Por exemplo:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    Neste exemplo, você criou uma região da rede chamada “NorthAmerica” que é associada a um site central com o ID de site CHICAGO.

3.  Para concluir a criação das regiões de rede para sua topologia, repita a etapa 2 com as configurações para cada região da rede.

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>Para criar uma região de rede usando o painel de controle do Lync Server

1.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação esquerda, clique em **Configuração de rede**.

3.  Clique em **Região**.

4.  Clique em **Novo**.

5.  Na página **Nova Região**, clique em **Nome** e digite um nome para a região da rede.

6.  Clique em **Site central** e, em seguida, clique em um site central na lista.

7.  Como opção, clique em **Descrição** e digite as informações adicionais para descrever esse site da rede.

8.  Clique em **Confirmar**.

9.  Para concluir a criação das regiões da rede para sua topologia, repita as etapas 4 a 8 com as configurações de outras regiões.

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>Modificar uma região de rede

Modifique as configurações de uma região de rede existente para acomodar alterações nas informações básicas de região ou alterações necessárias para um novo recurso.

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>Para modificar uma região de rede usando o Shell de gerenciamento do Lync Server

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o cmdlet Set-CsNetworkRegion para modificar uma região da rede existente:
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Por exemplo:
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    Neste exemplo, você modificou uma região da rede existente chamada “NorthAmerica” (criada usando os procedimentos acima neste tópico) alterando a descrição. Se houver uma descrição para a região “NorthAmerica”, esse comando a substituirá por esse valor; se não houver uma descrição, esse comando a definirá.

3.  Para modificar outras regiões da rede, repita a etapa 2 com as configurações de outras regiões.

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>Para modificar uma região de rede usando o painel de controle do Lync Server

1.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação esquerda, clique em **Configuração de rede**.

3.  Clique no botão de navegação **Região**.

4.  Na tabela, clique na região da rede que você deseja modificar.

5.  Clique em **Editar** e, em seguida, clique em **Mostrar detalhes…**.

6.  Na página  **Editar Região**, altere os valores das configurações dessa região da rede conforme apropriado.

7.  Clique em **Confirmar**.

8.  Para concluir a modificação das regiões da rede, repita as etapas 4 a 7 com as configurações de outras regiões.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

