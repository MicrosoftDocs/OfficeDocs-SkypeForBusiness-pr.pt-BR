---
title: 'Lync Server 2013: Criar ou modificar um site da rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1afb986f88af11ee2020b760e0a6d65aabed838c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a>Criar ou modificar um site da rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-24_

O controle de admissão de chamadas (CAC), o E9-1-1 e as implantações de bypass de mídia dependem da configuração dos *sites de rede* que são definidos dentro e sempre associados a uma região de rede. Um site de rede representa uma localização de filial, um conjunto de edifícios ou um campus. Os sites de rede representam coleções de sub-redes com largura de banda semelhante.

Use os procedimentos a seguir para criar ou modificar sites de rede. Por exemplo, se você já tiver criado sites de rede para um recurso de voz, não precisará criar novos sites de rede; outros recursos de voz usarão esses mesmos sites. Você pode, porém, precisar modificar uma definição de site da rede existente para aplicar configurações específicas do recurso. Por exemplo, se você criou um site da rede para o E9-1-1, você precisa modificar o site da rede durante a implantação do serviço de controle de admissão de chamadas para aplicar um perfil de política de largura de banda.

<div>


> [!NOTE]  
> Onde elas existem, você pode encontrar exemplos e requisitos específicos para sites de rede à medida que eles pertencem a um recurso de voz avançado na documentação de implantação para cada recurso: 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">Configurar sites de rede para o CAC no Lync Server 2013</A></P></LI></UL>



</div>

Para obter detalhes sobre como trabalhar com sites de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a>Criar um site de rede

Crie uma região de rede que possa ser usada pelo controle de admissão de chamadas, E9-1-1 ou bypass de mídia.

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a>Para criar um site de rede usando o Shell de gerenciamento

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o cmdlet do New-CsNetworkSite para criar sites da rede:
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    Por exemplo:
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    Neste exemplo, você criou um site da rede chamado “Chicago” que está na região da rede “NorthAmerica”.
    
    <div>
    

    > [!NOTE]  
    > A região da rede NorthAmerica já deve existir para que esse comando seja executado com sucesso.

    
    </div>

3.  Para concluir a criação de sites da rede para a sua topologia, repita a etapa 2 com as configurações de outros sites.

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a>Para criar um site de rede usando o painel de controle do Lync Server

1.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação esquerda, clique em **Configuração de rede**.

3.  Clique no botão de navegação **Site**.

4.  Clique em **Novo**.

5.  Na página **Novo Site**, clique em **Nome** e depois digite um nome para o site da rede.

6.  Clique em **Região**, e depois clique em uma região na lista.

7.  De modo opcional, clique em **Política de largura de banda**, e depois clique em uma das larguras de banda da lista.
    
    <div>
    

    > [!NOTE]  
    > A política de largura de banda é solicitada apenas se você implantar o serviço de controle de admissão de chamadas no site.

    
    </div>

8.  De modo opcional, clique em **Política de Local**, depois clique em uma política de local na lista.
    
    <div>
    

    > [!NOTE]  
    > A política de local é solicitada se você implantar E9-1-1 no site.

    
    </div>

9.  Como opção, clique em **Descrição**, em seguida, digite as informações adicionais para descrever esse site da rede.

10. Clique em **Confirmar**.

11. Para concluir a criação de sites da rede para a sua topologia, repita as etapas 4 a 10 com as configurações de outros sites.

</div>

</div>

<div>

## <a name="modify-a-network-site"></a>Modificar um site de rede

Modifique uma região de rede que possa ser usada pelo controle de admissão de chamadas, E9-1-1 ou bypass de mídia.

<div>

## <a name="to-modify-a-network-site"></a>Para modificar um site de rede

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o cmdlet Set-CsNetworkSite para modificar os sites da rede:
    
        Set-CsNetworkSite -Identity <string>
    
    Por exemplo:
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    Neste exemplo, o site chamado “Albuquerque” é movido para a região “NorthAmerica”. Para modificar a configuração do site da rede para implantar o serviço de controle de admissão de chamadas, o E9-1-1 ou desvio de mídia, modifique o site da rede executando o cmdlet Set-CsNetworkSite com os parâmetros do BWPolicyProfileID ou LocationPolicy, respectivamente.
    
    <div>
    

    > [!NOTE]  
    > Embora o parâmetro do BypassID exista para o desvio de mídia, recomendamos que você não sobreponha IDs de desvio geradas automaticamente. Você não precisa especificar parâmetros adicionais para configurar um site da rede para o desvio de mídia.

    
    </div>

3.  Para concluir a modificação dos sites da rede para sua topologia, repita a etapa 2 com as configurações de outros sites.

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a>Para modificar um site de rede usando o painel de controle do Lync Server

1.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação esquerda, clique em **Configuração de rede**.

3.  Clique no botão de navegação **Site**.

4.  Na tabela, clique no site da rede que você quer modificar.

5.  Clique em **Editar**e, em seguida, clique em **Mostrar detalhes…**.

6.  Na página **Editar Site**, mude os valores dessas configurações de site da rede conforme apropriado.

7.  Clique em **Confirmar**.

8.  Para concluir a modificação de sites da rede, repita as etapas de 4 a 7 com configurações de outros sites.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

