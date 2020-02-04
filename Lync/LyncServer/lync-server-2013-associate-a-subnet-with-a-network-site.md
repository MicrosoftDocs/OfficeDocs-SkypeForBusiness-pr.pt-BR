---
title: 'Lync Server 2013: Associar uma subrede a um site de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f54ba8be2be6ae042633e519c5d7d27bde834162
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a>Associar uma subrede a um site de rede no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Todas as sub-redes da sua rede devem ser associadas a um site da rede específico, pois as informações da sub-rede são usadas para determinar o site da rede em que um ponto de extremidade se encontra quando uma nova sessão é iniciada. Quando o local de cada participante de uma sessão é conhecido, recursos avançados do Enterprise Voice podem aplicar essas informações para determinar como manipular a configuração ou o roteamento de chamadas.

<div>


> [!IMPORTANT]  
> Todos os endereços IP públicos configurados dos Servidores de Borda de Áudio/Vídeo em sua implantação devem ser adicionados às suas definições de configuração da rede. Estes endereços IP são adicionados como sub-redes com uma máscara de 32. O site da rede associado deve corresponder ao site da rede configurado adequado. Por exemplo, o endereço IP público que corresponde ao servidor de borda A/V no site central de Chicago seria NetworkSiteID Chicago. Para obter detalhes sobre endereços IP públicos, consulte <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determinar requisitos de firewall e porta externo A/V para o Lync Server 2013</A> na documentação de planejamento.



</div>

<div>


> [!NOTE]  
> Um alerta Key Health Indicator (KHI) é disparado, especificando uma lista de endereços IP presentes em sua rede, mas que não estão associados a uma sub-rede ou à sub-rede que inclui os endereços IP não está associada a um site da rede. Este alerta não será disparado mais de uma vez dentro de um período de 8 horas. A informação de alerta relevante e um exemplo são como segue:<BR><STRONG>Fonte:</STRONG> Serviço de política de largura de banda do CS (básico)<BR><STRONG>Número do evento:</STRONG> 36034<BR><STRONG>Nível:</STRONG> 2<BR><STRONG>Descrição:</STRONG> As sub-redes para os seguintes endereços IP: &lt;a lista de endereços&gt; IP não estão configurados ou as sub-redes não estão associadas a um site de rede.<BR><STRONG>Causa:</STRONG> As sub-redes dos endereços IP correspondentes estão ausentes nas configurações de configuração de rede ou as sub-redes não estão associadas a um site de rede.<BR><STRONG>Resolução:</STRONG> Adicione sub-redes correspondentes à lista de endereços IP nas configurações de configuração de rede e associe cada sub-rede a um site de rede.<BR>Por exemplo, se a lista de endereços IP no alerta especifica 10.121.248.226 e 10.121.249.20, ou estes endereços IP não estão associados a uma sub-rede ou a sub-rede à qual estão associados não pertence a um site da rede. Se 10.121.248.0/24 e 10.121.249.0/24 forem as sub-redes correspondentes para estes endereços, você pode resolver o problema da seguinte forma: 
> <OL>
> <LI>
> <P>Certifique-se de que o endereço IP 10.121.248.226 está associado à sub-rede 10.121.248.0/24 e que o endereço IP 10.121.249.20 está associado à sub-rede 10.121.249.0/24.</P>
> <LI>
> <P>Certifique-se de que ambas as sub-redes 10.121.248.0/24 e 10.121.249.0/24 estejam associadas a um site da rede.</P></LI></OL>



</div>

Para obter detalhes sobre como trabalhar com sub-redes de rede, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [Set-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [Remove-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> Se você estiver trabalhando com um grande número de sub-redes, recomendamos o uso de um arquivo de valores separados por vírgula (CSV) para associar as sub-redes a sites. O arquivo CSV deve ter as quatro colunas: <STRONG>IPAddress</STRONG>, <STRONG>máscara</STRONG>, <STRONG>Descrição</STRONG>e <STRONG>NetworkSiteID</STRONG>a seguir.



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a>Para associar uma sub-rede a um site de rede usando o Shell de gerenciamento

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Execute o cmdlet  **New-CsNetworkSubnet** para associar uma sub-rede a um site da rede:
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    Por exemplo:
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    Neste exemplo, você criou uma associação entre a sub-rede 172.11.12.13 e o site da rede “Chicago”.

3.  Repita a etapa 2 para todas as sub-redes em sua topologia.

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a>Para associar sub-redes a sites da rede importando um arquivo CSV

1.  Crie um arquivo CSV que inclui todas as sub-redes que deseja adicionar. Por exemplo, crie um arquivo chamado **subnet.csv** como o seguinte conteúdo:
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Execute o cmdlet a seguir para importar o **subnet. csv**e, em seguida, armazenar seu conteúdo na loja de gerenciamento do Lync Server:
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a>Para associar uma sub-rede a um site de rede usando o painel de controle do Lync Server

1.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação esquerda, clique em **Configuração de rede**.

3.  Clique no botão de navegação **Sub-rede**.

4.  Clique em **Novo**.

5.  Na página **Nova Sub-rede**, clique em **ID da Sub-rede** e digite o primeiro endereço do intervalo de endereços IP definido pela sub-rede que deseja associar a um site da rede.

6.  Clique em **Máscara** e digite o bitmask a ser aplicado à sub-rede.

7.  Clique em **ID do site da rede** e selecione o ID do site para o qual está adicionando esta sub-rede.
    
    <div>
    

    > [!NOTE]  
    > Se os sites da rede ainda não estiverem criados, a lista estará vazia. Para obter detalhes sobre o procedimento, consulte <A href="lync-server-2013-create-or-modify-a-network-site.md">criar ou modificar um site de rede no Lync Server 2013</A>. Você também pode recuperar as IDs do site para sua implantação executando o cmdlet <STRONG>Get-CsNetworkSite</STRONG>. Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server.

    
    </div>

8.  Opcionalmente, clique em  **Descrição** e digite informações adicionais para descrever esta sub-rede.

9.  Clique em **Confirmar**.

Repita estas etapas para adicionar outras sub-redes a um site da rede.

</div>

</div>

<span> </span>

</div>

</div>

</div>

