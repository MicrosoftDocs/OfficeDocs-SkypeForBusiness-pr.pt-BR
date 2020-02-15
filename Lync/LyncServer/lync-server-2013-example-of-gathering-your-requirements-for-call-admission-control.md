---
title: Exemplo de coleta de seus requisitos para controle de admissão de chamadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 204339161cf5af83f0d9e393a0a4db981c0e8445
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a>Exemplo: coletando seus requisitos para controle de admissão de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Este exemplo mostra como planejar e implementar o CAC (controle de admissão de chamadas). Em um alto nível, isso consiste nas seguintes atividades:

1.  Identificar todos os seus hubs e backbones de rede (conhecidos como *regiões de rede*).

2.  Identifique o site central do Lync Server que gerenciará o CAC para cada região de rede.

3.  Identificar e definir os *sites de rede* conectados a cada região de rede.

4.  Para cada local de rede cuja conexão com a WAN é restrita à largura de banda, descreva a capacidade de largura de banda da conexão WAN e os limites de largura de banda que para o administrador de rede definiu para o tráfego de mídia do Lync Server, se aplicável. Não é necessário incluir sites cuja conexão com a WAN não sofra restrições de largura de banda.

5.  Associe cada sub-rede em sua rede a um site de rede.

6.  Mapeie os links entre as regiões de rede. Para cada link, descreva sua capacidade de largura de banda e quaisquer limites que o administrador de rede colocou no tráfego de mídia do Lync Server.

7.  Defina uma rota entre cada par de regiões de rede.

<div>

## <a name="gather-the-required-information"></a>Colete as informações necessárias

Para se preparar para o controle de admissão de chamada, colete as informações descritas nas seguintes etapas:

1.  Identifique suas regiões de rede. Uma região de rede representa um backbone de rede ou um hub de rede.
    
    Um backbone de rede ou um hub de rede faz parte da infraestrutura de rede do computador que interconecta diversas peças da rede, fornecendo um caminho para a troca de informações entre LANs ou sub-redes diferentes. Um backbone pode unir diversas redes, de um pequeno local até uma área geográfica ampla. A capacidade do backbone é normalmente superior a da rede conectada a ele.
    
    Nosso exemplo de topologia têm três regiões de rede: América do Norte, EMEA e APAC. Uma região de rede contém uma coleção de sites de rede. Trabalhe com seu administrador de rede para definir as regiões de rede para sua empresa.

2.  Identifique o site central associado a cada região de rede. Um site central contém pelo menos um servidor front-end e é a implantação do Lync Server que gerenciará o CAC para todo o tráfego de mídia que passar pela conexão WAN da região de rede.
    
    **Um exemplo de rede de empresa dividida em três regiões de rede**
    
    ![Exemplo de topologia de rede com 3 regiões de rede](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Exemplo de topologia de rede com 3 regiões de rede")  
    
    <div>
    

    > [!NOTE]
    > Uma rede MPLS (Multiprotocol Label Switching) deve ser representada como uma região de rede na qual cada local geográfico tem um site de rede correspondente. Para obter detalhes, consulte o tópico "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">controle de admissão de chamadas em uma rede MPLS com Lync Server 2013</A>" na documentação de planejamento.

    
    </div>
    
    Na topologia de rede de exemplo anterior, há três regiões de rede, cada uma com um site central do Lync Server que gerencia o CAC. O site central apropriado para uma região de rede é escolhido pela proximidade geográfica. Como o tráfego de mídia será o mais intenso nas regiões de rede, a propriedade por proximidade geográfica o tornará autocontido e continuará funcionando mesmo se outros sites centrais ficarem indisponíveis.
    
    Neste exemplo, uma implantação do Lync Server chamada Chicago é o site central da região da América do Norte.
    
    Todos os usuários do Lync na América do Norte estão hospedados em servidores da implantação de Chicago. A tabela a seguir mostra os sites centrais de todas as três regiões de rede.
    
    ### <a name="network-regions-and-their-associated-central-sites"></a>Regiões de rede e seus sites centrais associados
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Região de rede</th>
    <th>Site central</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>América do Norte</p></td>
    <td><p>Chicago</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA</p></td>
    <td><p>Londres</p></td>
    </tr>
    <tr class="odd">
    <td><p>APAC</p></td>
    <td><p>Pequim</p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > Dependendo da sua topologia do Lync Server, o mesmo site central pode ser atribuído a várias regiões de rede.

    
    </div>

3.  Para cada região de rede, identifique todos os sites de rede (escritórios ou locais) cujas conexões WAN não sofrem restrições de largura de banda. Como esses sites não sofrem restrições de largura de banda, não é necessário aplicar as políticas de largura de banda de CAC neles.
    
    No exemplo exibido na tabela abaixo, três sites de rede não têm links de WAN com restrição de largura de banda: Nova York, Chicago e Detroit.
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a>Sites de rede sem restrições de largura de banda de WAN
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Site de rede</th>
    <th>Região de rede</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Nova York</p></td>
    <td><p>América do Norte</p></td>
    </tr>
    <tr class="even">
    <td><p>Chicago</p></td>
    <td><p>América do Norte</p></td>
    </tr>
    <tr class="odd">
    <td><p>Detroit</p></td>
    <td><p>América do Norte</p></td>
    </tr>
    </tbody>
    </table>


4.  Para cada região de rede, identifique todos os sites de rede que se conectam à região de rede por meio de links de WAN com restrição de largura de banda.
    
    Para garantir a qualidade de áudio e vídeo, é recomendável que esses locais de rede com restrição de largura de banda tenham as WANs monitoradas e tenham políticas de largura de banda de CAC que limitem o tráfego de mídia (voz ou vídeo) de e para a região de rede.
    
    No exemplo exibido na tabela abaixo, há três sites de rede com restrição de largura de banda de WAN: Portland, Reno e Albuquerque.
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a>Sites de rede com restrições de largura de banda de WAN
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Site de rede</th>
    <th>Região de rede</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>América do Norte</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>América do Norte</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>América do Norte</p></td>
    </tr>
    </tbody>
    </table>
    
    **Região de rede de CAC América do Norte com três sites de rede sem restrição de largura de banda (Chicago, Nova York e Detroit) e três sites de rede com restrição de largura de banda de WAN (Portland, Reno e Albuquerque)**
    
    ![Exemplo de sites de rede restritos pela largura de banda de WAN](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Exemplo de sites de rede restritos pela largura de banda de WAN")  

5.  Para cada link de WAN com restrição de largura de banda, determine o seguinte:
    
      - Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas. Se uma nova sessão de áudio fizer com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.
    
      - Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.
    
      - Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas. Se uma nova sessão de vídeo fizer com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.
    
      - Limite de largura de banda que você deseja definir para cada sessão de vídeo individual. O limite padrão de largura de banda de CAC é de 700 kbps, mas o administrador pode modificá-lo.
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a>Sites de rede com informações sobre restrição de largura de banda de WAN (largura de banda em kbps)
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Site de rede</th>
    <th>Região de rede</th>
    <th>Limite de BW</th>
    <th>Limite de áudio</th>
    <th>Limite de sessão de áudio</th>
    <th>Limite de vídeo</th>
    <th>Limite de sessão de vídeo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>América do Norte</p></td>
    <td><p>5.000</p></td>
    <td><p>2,000</p></td>
    <td><p>175</p></td>
    <td><p>1.400</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>América do Norte</p></td>
    <td><p>10.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>América do Norte</p></td>
    <td><p>5.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>Nova York</p></td>
    <td><p>América do Norte</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    </tr>
    <tr class="odd">
    <td><p>Chicago</p></td>
    <td><p>América do Norte</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    </tr>
    <tr class="even">
    <td><p>Detroit</p></td>
    <td><p>América do Norte</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    </tr>
    </tbody>
    </table>


6.  Para cada sub-rede em sua rede, especifique seu site de rede associado.
    
    <div>
    

    > [!IMPORTANT]
    > Cada sub-rede em sua rede precisa estar associada a um site de rede, mesmo se o site de rede não sofrer restrição de largura de banda. Isso é devido ao controle de admissão de chamada usar as informações da sub-rede para determinar em qual site de rede um ponto de extremidade está localizado. Quando os locais de ambas as partes na sessão são determinados, o controle de admissão de chamada pode determinar se há largura de banda suficiente para estabelecer uma chamada. Quando uma sessão é estabelecida sobre um link que não possui limites de largura de banda, um alerta é gerado.<BR>Se você implantar os Servidores de Borda de Áudio/Vídeo, os endereços IP públicos de cada Servidor de Borda deverão ser associados ao site externo no qual o Servidor de Borda está implantado. Cada endereço IP público do Servidor de Borda A/V precisa ser adicionado às suas configurações de rede como uma sub-rede com a máscara de sub-rede de 32. Por exemplo, se você implantar os Servidores de Borda A/V em Chicago, para cada endereço IP externo desses servidores, crie uma sub-rede com uma máscara de sub-rede de 32 e associe o site de rede Chicago a essas sub-redes. Para obter detalhes sobre endereços IP públicos, consulte <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determine external A/V Firewall and Port Requirements for Lync Server 2013</A> na documentação de planejamento.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Um alerta de KHI (Key Health Indicator) é acionado, especificando uma lista de endereços IP presentes em sua rede, mas que não estão associados a uma sub-rede ou a sub-rede que inclui os endereços IP não está associada a um site de rede. Esse alerta não será acionado novamente durante um período de oito horas. Veja a seguir as informações relevantes do alerta e um exemplo:<BR><STRONG>Fonte:</STRONG> Serviço de política de largura de banda CS (núcleo)<BR><STRONG>Número do evento:</STRONG> 36034<BR><STRONG>Nível:</STRONG> 2<BR><STRONG>Descrição:</STRONG> As sub-redes para os seguintes endereços IP: &lt;a lista de endereços&gt; IP não estão configuradas ou as sub-redes não estão associadas a um site de rede.<BR><STRONG>Causa:</STRONG> As sub-redes dos endereços IP correspondentes estão ausentes nas definições de configuração de rede ou as sub-redes não estão associadas a um site de rede.<BR><STRONG>Resolução:</STRONG> Adicione sub-redes correspondentes à lista anterior de endereços IP nas definições de configuração de rede e associe todas as sub-redes a um site de rede.<BR>Por exemplo, a lista de endereços IP do alerta especifica 10.121.248.226 e 10.121.249.20. Esses dois endereços IP não estão associados a uma sub-rede ou a sub-rede a qual eles estão associados não pertence a um site de rede. Se 10.121.248.0/24 e 10.121.249.0/24 forem as sub-redes correspondentes desses endereços, será possível resolver esse problema da seguinte maneira: 
    > <OL>
    > <LI>
    > <P>Certifique-se de que o endereço IP 10.121.248.226 esteja associado à sub-rede 10.121.248.0/24 e o endereço IP 10.121.249.20 esteja associado à sub-rede 10.121.249.0/24.</P>
    > <LI>
    > <P>Certifique-se de que cada uma das sub-redes 10.121.248.0/24 e 10.121.249.0/24 esteja associada a um site de rede.</P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a>Sites de rede e sub-redes associadas (largura de banda em kbps)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Site de rede</th>
    <th>Região de rede</th>
    <th>Limite de BW</th>
    <th>Limite de áudio</th>
    <th>Limite de sessão de áudio</th>
    <th>Limite de vídeo</th>
    <th>Limite de sessão de vídeo</th>
    <th>Sub-redes</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Albuquerque</p></td>
    <td><p>América do Norte</p></td>
    <td><p>5.000</p></td>
    <td><p>2,000</p></td>
    <td><p>175</p></td>
    <td><p>1.400</p></td>
    <td><p>700</p></td>
    <td><p>172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</p></td>
    </tr>
    <tr class="even">
    <td><p>Reno</p></td>
    <td><p>América do Norte</p></td>
    <td><p>10.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    <td><p>157.57.210.0/23, 172.28.151.128/25</p></td>
    </tr>
    <tr class="odd">
    <td><p>Portland</p></td>
    <td><p>América do Norte</p></td>
    <td><p>5.000</p></td>
    <td><p>4.000</p></td>
    <td><p>175</p></td>
    <td><p>2.800</p></td>
    <td><p>700</p></td>
    <td><p>172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</p></td>
    </tr>
    <tr class="even">
    <td><p>Nova York</p></td>
    <td><p>América do Norte</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</p></td>
    </tr>
    <tr class="odd">
    <td><p>Chicago</p></td>
    <td><p>América do Norte</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>157.57.211.0/23, 172.28.152.128/25</p></td>
    </tr>
    <tr class="even">
    <td><p>Detroit</p></td>
    <td><p>América do Norte</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>(sem limite)</p></td>
    <td><p>172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</p></td>
    </tr>
    </tbody>
    </table>


7.  No Lync Server Call Admission Control, as conexões entre as regiões de rede são chamadas de *links de região*. Para cada link de região, determine o seguinte, da mesma forma que fez para os sites de rede:
    
      - Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas. Se uma nova sessão de áudio fizer com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.
    
      - Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.
    
      - Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas. Se uma nova sessão de vídeo fizer com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.
    
      - Limite de largura de banda que você deseja definir para cada sessão de vídeo individual. O limite padrão de largura de banda de CAC é de 700 kbps, mas o administrador pode modificá-lo.
    
    **Links de região de rede com limites de largura de banda associados**
    
    ![Exemplo de limitações entre 3 regiões](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Exemplo de limitações entre 3 regiões")  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a>Informações de largura de banda de link de região (largura de banda em kbps)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nome do link de região</th>
    <th>Primeira região</th>
    <th>Segunda região</th>
    <th>Limite de BW</th>
    <th>Limite de áudio</th>
    <th>Limite de sessão de áudio</th>
    <th>Limite de vídeo</th>
    <th>Limite de sessão de vídeo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-LINK</p></td>
    <td><p>América do Norte</p></td>
    <td><p>EMEA</p></td>
    <td><p>50.000</p></td>
    <td><p>20,000</p></td>
    <td><p>175</p></td>
    <td><p>14.000</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-O LINK</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>25.000</p></td>
    <td><p>10.000</p></td>
    <td><p>175</p></td>
    <td><p>7.000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


8.  Defina uma rota entre cada par de regiões de rede.
    
    <div>
    

    > [!NOTE]
    > Dois links são necessários para a rota entre as regiões América do Norte e APAC, pois não há um link de região que as conecte diretamente.

    
    </div>
    
    ### <a name="region-routes"></a>Rotas de região
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nome da rota de região</th>
    <th>Primeira região</th>
    <th>Segunda região</th>
    <th>Links de região</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-ROUTE</p></td>
    <td><p>América do Norte</p></td>
    <td><p>EMEA</p></td>
    <td><p>NA-EMEA-LINK</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-DIREÇÃO DA ROTA</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>EMEA-O LINK</p></td>
    </tr>
    <tr class="odd">
    <td><p>NA-CHEROKEE-ROUTE</p></td>
    <td><p>América do Norte</p></td>
    <td><p>APAC</p></td>
    <td><p>LINK-NA-EMEA, LINK-EMEA-APAC</p></td>
    </tr>
    </tbody>
    </table>


9.  Para cada par de sites de rede conectados diretamente por um único link (chamado de link *entre sites*), determine o seguinte:
    
      - Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas. Se uma nova sessão de áudio fizer com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.
    
      - Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.
    
      - Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas. Se uma nova sessão de vídeo fizer com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.
    
      - Limite de largura de banda que você deseja definir para cada sessão de vídeo individual. O limite padrão de largura de banda de CAC é de 700 kbps, mas o administrador pode modificá-lo.
    
    **Região da rede CAC América do Norte mostrando as capacidades de largura de banda e limites de largura de banda para o link entre sites entre Reno e Albuquerque**
    
    ![Sites de rede restritos por exemplo de largura de banda de WAN](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Sites de rede restritos por exemplo de largura de banda de WAN")  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a>Informações de largura de banda para link entre sites entre dois sites de rede (largura de banda em kbps)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nome do link entre sites</th>
    <th>Primeiro site</th>
    <th>Segundo site</th>
    <th>Limite de BW</th>
    <th>Limite de áudio</th>
    <th>Limite de sessão de áudio</th>
    <th>Limite de vídeo</th>
    <th>Limite de sessão de vídeo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Reno-Albu-entre sites-link</p></td>
    <td><p>Reno</p></td>
    <td><p>Albuquerque</p></td>
    <td><p>20,000</p></td>
    <td><p>12.000</p></td>
    <td><p>175</p></td>
    <td><p>5.000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a>Próximas Etapas

Depois de coletar as informações necessárias, você pode executar a implantação do CAC usando o Shell de gerenciamento do Lync Server ou o painel de controle do Lync Server.

<div>


> [!NOTE]
> Embora seja possível executar a maioria das tarefas de configuração de rede usando o painel de controle do Lync Server, para criar sub-redes e links entre sites, você deve usar o Shell de gerenciamento do Lync Server. Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server para o cmdlet <STRONG>New-CsNetworkSubnet</STRONG> e o cmdlet <STRONG>New-CsNetworkIntersitePolicy</STRONG> .



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

