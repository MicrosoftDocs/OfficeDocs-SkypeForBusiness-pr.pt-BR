---
title: Exemplo de como reunir seus requisitos para o controle de admissão de chamadas
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
ms.openlocfilehash: 345f5d7e41dd9da3e6d68c59ce9656d3052c57b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a>Exemplo: reunindo seus requisitos de controle de admissão de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Este exemplo mostra como planejar e implementar o CAC (controle de admissão de chamadas). Em um alto nível, isso consiste nas seguintes atividades:

1.  Identificar todos os hubs e backbones de rede (conhecidos como *regiões de rede*).

2.  Identifique o site central do Lync Server que irá gerenciar o CAC para cada região de rede.

3.  Identificar e definir os *locais de rede* conectados a cada região de rede.

4.  Para cada site de rede cuja conexão à WAN é restrita à largura de banda, descreva a capacidade de largura de banda da conexão WAN e os limites de largura de banda que o administrador de rede definiu para o tráfego de mídia do Lync Server, se aplicável. Não é necessário incluir locais cuja conexão com a WAN não tenha restrição de largura de banda.

5.  Associe cada sub-rede de sua rede a um local de rede.

6.  Mapeie os links entre as regiões de rede. Para cada link, descreva a capacidade da largura de banda e os limites que o administrador da rede colocou no tráfego de mídia do Lync Server.

7.  Defina uma rota entre cada par de regiões de rede.

<div>

## <a name="gather-the-required-information"></a>Colete as informações necessárias

Para se preparar para o controle de admissão de chamada, colete as informações descritas nas seguintes etapas:

1.  Identifique suas regiões de rede. Uma região de rede representa um backbone de rede ou um hub de rede.
    
    Um backbone de rede ou um hub de rede faz parte da infraestrutura de rede do computador que interconecta diversas partes da rede, fornecendo um caminho para a troca de informações entre LANs ou sub-redes diferentes. Um backbone pode unir redes distintas, de um pequeno local até uma ampla área geográfica. A capacidade do backbone é normalmente superior à da rede conectada a ele.
    
    Nosso exemplo de topologia têm três regiões de rede: América do Norte, EMEA e APAC. Uma região de rede contém uma coleção de locais de rede. Trabalhe com seu administrador de rede para definir as regiões de rede para sua empresa.

2.  Identifique o local central associado a cada região de rede. Um site central contém pelo menos um servidor front-end e é a implantação do Lync Server que gerenciará o CAC para todo o tráfego de mídia que passar pela conexão WAN da região de rede.
    
    **Um exemplo de rede de empresa dividida em três regiões de rede**
    
    ![Exemplo de topologia de rede com 3 regiões de rede](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Exemplo de topologia de rede com 3 regiões de rede")  
    
    <div>
    

    > [!NOTE]
    > Uma rede MPLS deve ser representada como uma região de rede na qual cada local geográfico tem um local de rede correspondente. Para obter detalhes, consulte o tópico "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">controle de admissão de chamadas em uma rede MPLS com o Lync Server 2013</A>" na documentação de planejamento.

    
    </div>
    
    Na topologia de rede de exemplo anterior, há três regiões de rede, cada uma com um site central do Lync Server que gerencia o CAC. O local central apropriado para uma região de rede é escolhido pela proximidade geográfica. Como o tráfego de mídia será o mais intenso nas regiões de rede, a propriedade por proximidade geográfica o tornará autocontido e continuará funcionando mesmo que outros locais centrais fiquem indisponíveis.
    
    Neste exemplo, uma implantação do Lync Server chamada Chicago é o site central da região da América do Norte.
    
    Todos os usuários do Lync na América do Norte são hospedados em servidores na implantação de Chicago. A tabela a seguir mostra os locais centrais de todas as três regiões de rede.
    
    ### <a name="network-regions-and-their-associated-central-sites"></a>Regiões de rede e locais centrais associados
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Região de rede</th>
    <th>Local central</th>
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
    > Dependendo da topologia do Lync Server, o mesmo site central pode ser atribuído a várias regiões de rede.

    
    </div>

3.  Para cada região de rede, identifique todos os locais de rede (escritórios ou locais) cujas conexões WAN não sofrem restrições de largura de banda. Como esses locais não sofrem restrições de largura de banda, não é necessário aplicar as políticas de largura de banda de CAC a eles.
    
    No exemplo exibido na tabela abaixo, três locais de rede não têm links WAN com restrição de largura de banda: Nova York, Chicago e Detroit.
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a>Locais de rede sem restrições de largura de banda de WAN
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Local de rede</th>
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


4.  Para cada região de rede, identifique todos os locais de rede que se conectam à região de rede por meio de links WAN com restrição de largura de banda.
    
    Para garantir a qualidade de áudio e vídeo, é recomendável que esses locais de rede com restrição de largura de banda tenham as WANs monitoradas e tenham políticas de largura de banda de CAC que limitem o tráfego de mídia (voz ou vídeo) de e para a região de rede.
    
    No exemplo exibido na tabela abaixo, há três locais de rede com restrição de largura de banda de WAN: Portland, Reno e Albuquerque.
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a>Locais de rede com restrições de largura de banda de WAN
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Local de rede</th>
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
    
    ![Exemplo de sites de rede restritos pela largura de banda WAN](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Exemplo de sites de rede restritos pela largura de banda WAN")  

5.  Para cada link de WAN com restrição de largura de banda, determine o seguinte:
    
      - Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas. Se uma nova sessão de áudio fará com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.
    
      - Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.
    
      - Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas. Se uma nova sessão de vídeo fará com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.
    
      - Limite de largura de banda que você deseja definir para cada sessão de vídeo individual. O limite padrão de largura de banda de CAC é de 700 kbps, mas o administrador pode modificá-lo.
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a>Locais de rede com informações sobre restrição de largura de banda de WAN (largura de banda em kbps)
    
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
    <th>Local de rede</th>
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
    <td><p>2.000</p></td>
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


6.  Para cada sub-rede em sua rede, especifique seu local de rede associado.
    
    <div>
    

    > [!IMPORTANT]
    > Cada sub-rede em sua rede precisa estar associada a um local de rede, mesmo se o local de rede não sofrer restrição de largura de banda. Isso é devido ao controle de admissão de chamada usar as informações da sub-rede para determinar em qual local de rede um ponto de extremidade está localizado. Quando os locais de ambas as partes na sessão são determinados, o controle de admissão de chamada pode determinar se há largura de banda suficiente para estabelecer uma chamada. Quando uma sessão é estabelecida sobre um link que não possui limites de largura de banda, um alerta é gerado.<BR>Se você implantar Servidores de Borda de Áudio/Vídeo, os endereços IP públicos de cada Servidor de Borda deverão ser associados ao local externo no qual o Servidor de Borda está implantado. Cada endereço IP público do Servidor de Borda A/V deve ser adicionado aos seus parâmetros de configuração de rede como uma sub-rede com uma máscara de sub-rede 32. Por exemplo, se você implantar Servidores de Borda A/V em Chicago, para cada endereço IP externo desses servidores, crie uma sub-rede com uma máscara de sub-rede 32 e associe o local de rede Chicago a essas sub-redes. Para obter detalhes sobre endereços IP públicos, consulte <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determinar requisitos de firewall e porta externo A/V para o Lync Server 2013</A> na documentação de planejamento.

    
    </div>
    
    <div>
    

    > [!NOTE]
    > Um alerta KHI (Key Health Indicator) é acionado, especificando uma lista de endereços IP presentes em sua rede, mas que não estão associados a uma sub-rede, ou a sub-rede que inclui os endereços IP não está associada a um local de rede. Esse alerta não será acionado novamente durante um período de oito horas. Veja a seguir as informações relevantes do alerta e um exemplo:<BR><STRONG>Fonte:</STRONG> Serviço de política de largura de banda do CS (básico)<BR><STRONG>Número do evento:</STRONG> 36034<BR><STRONG>Nível:</STRONG> 2<BR><STRONG>Descrição:</STRONG> As sub-redes para os seguintes endereços IP: &lt;a lista de endereços&gt; IP não estão configurados ou as sub-redes não estão associadas a um site de rede.<BR><STRONG>Causa:</STRONG> As sub-redes dos endereços IP correspondentes estão ausentes nas configurações de configuração de rede ou as sub-redes não estão associadas a um site de rede.<BR><STRONG>Resolução:</STRONG> Adicione sub-redes correspondentes à lista anterior de endereços IP nas configurações de configuração de rede e associe cada sub-rede a um site de rede.<BR>Por exemplo, a lista de endereços IP do alerta especifica 10.121.248.226 e 10.121.249.20. Esses dois endereços IP não estão associados a uma sub-rede, ou a sub-rede à qual eles estão associados não pertence a um local de rede. Se 10.121.248.0/24 e 10.121.249.0/24 forem as sub-redes correspondentes desses endereços, será possível resolver esse problema da seguinte maneira: 
    > <OL>
    > <LI>
    > <P>Certifique-se de que o endereço IP 10.121.248.226 está associado à sub-rede 10.121.248.0/24 e que o endereço IP 10.121.249.20 está associado à sub-rede 10.121.249.0/24.</P>
    > <LI>
    > <P>Certifique-se de que ambas as sub-redes 10.121.248.0/24 e 10.121.249.0/24 estejam associadas a um local de rede.</P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a>Locais de rede e sub-redes associadas (largura de banda em kbps)
    
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
    <th>Local de rede</th>
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
    <td><p>2.000</p></td>
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


7.  No controle de admissão de chamadas do Lync Server, as conexões entre regiões de rede são chamadas de *links de região*. Para cada link de região, determine o seguinte, da mesma forma que fez para os locais de rede:
    
      - Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas. Se uma nova sessão de áudio fará com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.
    
      - Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.
    
      - Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas. Se uma nova sessão de vídeo fará com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.
    
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
    <td><p>LINK-NA-EMEA</p></td>
    <td><p>América do Norte</p></td>
    <td><p>EMEA</p></td>
    <td><p>50.000</p></td>
    <td><p>20.000</p></td>
    <td><p>175</p></td>
    <td><p>14.000</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>LINK-EMEA-APAC</p></td>
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
    <td><p>ROTA-NA-EMEA</p></td>
    <td><p>América do Norte</p></td>
    <td><p>EMEA</p></td>
    <td><p>LINK-NA-EMEA</p></td>
    </tr>
    <tr class="even">
    <td><p>ROTA-EMEA-APAC</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>LINK-EMEA-APAC</p></td>
    </tr>
    <tr class="odd">
    <td><p>ROTA-NA-APAC</p></td>
    <td><p>América do Norte</p></td>
    <td><p>APAC</p></td>
    <td><p>LINK-NA-EMEA, LINK-EMEA-APAC</p></td>
    </tr>
    </tbody>
    </table>


9.  Para cada par de locais de rede conectados diretamente por um único link (chamado de link *entre locais*), determine o seguinte:
    
      - Limite de largura de banda geral que você deseja definir para todas as sessões de áudio simultâneas. Se uma nova sessão de áudio fará com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.
    
      - Limite de largura de banda que você deseja definir para cada sessão de áudio individual. O limite padrão de largura de banda de CAC é de 175 kbps, mas o administrador pode modificá-lo.
    
      - Limite de largura de banda geral que você deseja definir para todas as sessões de vídeo simultâneas. Se uma nova sessão de vídeo fará com que esse limite seja excedido, o Lync Server não permitirá que a sessão seja iniciada.
    
      - Limite de largura de banda que você deseja definir para cada sessão de vídeo individual. O limite padrão de largura de banda de CAC é de 700 kbps, mas o administrador pode modificá-lo.
    
    **Região da rede CAC América do Norte mostrando as capacidades de largura de banda e limites de largura de banda para o link entre sites entre Reno e Albuquerque**
    
    ![Sites de rede restritos pelo exemplo de largura de banda de WAN](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Sites de rede restritos pelo exemplo de largura de banda de WAN")  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a>Informações de largura de banda para link entre locais entre dois locais de rede (largura de banda em kbps)
    
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
    <th>Nome do link entre locais</th>
    <th>Primeiro local</th>
    <th>Segundo local</th>
    <th>Limite de BW</th>
    <th>Limite de áudio</th>
    <th>Limite de sessão de áudio</th>
    <th>Limite de vídeo</th>
    <th>Limite de sessão de vídeo</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Link-entre-locais-Reno-Albu</p></td>
    <td><p>Reno</p></td>
    <td><p>Albuquerque</p></td>
    <td><p>20.000</p></td>
    <td><p>12.000</p></td>
    <td><p>175</p></td>
    <td><p>5.000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a>Próximas etapas

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

