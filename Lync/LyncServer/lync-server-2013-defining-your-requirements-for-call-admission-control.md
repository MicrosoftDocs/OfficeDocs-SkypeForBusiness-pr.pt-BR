---
title: 'Lync Server 2013: Definindo seus requisitos de controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba23e34099ed75f61f8025711189c60d36ca18f0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a>Definindo seus requisitos de controle de admissão de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-28_

O planejamento de controle de admissão de chamadas (CAC) requer informações detalhadas sobre a topologia de rede corporativa. Para ajudar a planejar suas políticas de controle de admissão de chamadas, siga estas etapas.

1.  Identifique os hubs/backbones (chamados de *regiões de rede*) dentro da sua rede corporativa.

2.  Identifique os escritórios ou locais (chamados de *sites de rede*) em cada região de rede.

3.  Determine a rota de rede entre todos os pares de regiões de rede.

4.  Determine os limites de largura de banda para cada link de WAN.
    
    <div>
    

    > [!NOTE]  
    > Os limites de largura de banda referem-se à quantidade de largura de banda de um link de WAN atribuída ao tráfego de voz e áudio/vídeo da empresa. Quando um link de WAN é descrito como "largura de banda restringida", o link de WAN tem um limite de largura de banda menor do que o tráfego de pico esperado no link.

    
    </div>

5.  Identifique as sub-redes IP atribuídas a cada site de rede.

Para explicar esses conceitos, usaremos a topologia de rede de exemplo mostrada na figura a seguir.

**Exemplo de topologia para controle de admissão de chamadas**

![Litware Inc. exemplo de topologia de rede](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. exemplo de topologia de rede")

<div>


> [!NOTE]  
> Todos os sites de rede estão associados a uma região de rede. Por exemplo, Portland, Reno e Albuquerque estão incluídos na região da América do Norte. Nesta figura, somente links WAN que têm políticas de CAC aplicadas são mostrados, com limites de largura de banda. Os sites de rede de Chicago, Nova York e Detroit são exibidos dentro da elipse da América do Norte, pois eles não são restringidos por largura de banda e, portanto, não exigem políticas do CAC.



</div>

Os componentes deste exemplo de topologia são explicados nas seções a seguir. Para obter detalhes sobre como essa topologia era planejada, incluindo os limites de largura de banda, consulte [exemplo: reunir seus requisitos para o controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).

<div>

## <a name="identify-network-regions"></a>Identificar regiões de rede

Uma região de rede representa um backbone de rede ou um hub de rede.

Um backbone ou Hub de rede é uma parte da infraestrutura de rede de computador que interconecta partes diferentes da rede, fornecendo um caminho para a troca de informações entre diferentes LANs ou sub-redes. Um backbone pode unir várias redes diferentes de um local pequeno para uma ampla área geográfica. A capacidade do backbone normalmente é maior do que a das redes conectadas a ele.

Nosso exemplo de topologia têm três regiões de rede: América do Norte, EMEA e APAC. Uma região de rede contém um conjunto de sites de rede (consulte a definição de sites de rede mais adiante neste tópico). Trabalhe com sua equipe de operações de rede para identificar suas regiões de rede.

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a>Associando um site central a cada região de rede

O CAC requer que um site central do Lync Server seja definido para cada região de rede. O site central é selecionado com a melhor conectividade de rede e largura de banda mais alta para todos os outros sites na região da rede. O exemplo anterior da topologia de rede mostra três regiões de rede, cada uma com um site central que gerencia decisões do CAC. No exemplo anterior, a associação apropriada é mostrada na tabela a seguir.

<div>


> [!NOTE]  
> Os sites centrais não correspondem necessariamente a sites de rede. Nos exemplos desta documentação, alguns sites centrais (Chicago, Londres e Pequim) compartilham o mesmo nome dos sites de rede. No entanto, mesmo se um site central e um site de rede compartilharem o mesmo nome, o site central será um elemento da topologia do Lync Server, enquanto o site de rede faz parte da rede geral na qual a topologia do Lync Server reside.



</div>

### <a name="network-regions-central-sites-and-network-sites"></a>Regiões de rede, sites centrais e sites de rede

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Região de rede</th>
<th>Local central</th>
<th>Sites de rede</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>América do Norte</p></td>
<td><p>Chicago</p></td>
<td><p>Chicago</p>
<p>Nova York</p>
<p>Detroit</p>
<p>Portland</p>
<p>Reno</p>
<p>Albuquerque</p></td>
</tr>
<tr class="even">
<td><p>EMEA</p></td>
<td><p>Londres</p></td>
<td><p>Londres</p>
<p>Cologne</p></td>
</tr>
<tr class="odd">
<td><p>APAC</p></td>
<td><p>Pequim</p></td>
<td><p>Pequim</p>
<p>Manila</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a>Identificar sites de rede

Um site de rede representa um local onde sua organização tem um local físico, por exemplo, escritórios, um conjunto de prédios ou um campus. Um local físico com uma LAN e com conectividade de WAN a outros sites é considerado um site de rede. Comece inventariando todos os escritórios da sua organização. Na nossa topologia de exemplo, a região de rede da América do Norte consiste nos seguintes sites de rede: New York, Chicago, Detroit, Portland, Reno e Albuquerque.

Você deve associar todos os sites de rede a uma região de rede. Dependendo se o site de rede tem um link de WAN restrito, uma política de largura de banda é associada ao site de rede. Para obter detalhes sobre as políticas do CAC e a largura de banda que você atribuir usando-as, consulte "definir políticas de largura de banda" mais adiante neste tópico. Para configurar o CAC, associe sites de rede com regiões de rede e, em seguida, crie políticas de alocação de largura de banda para aplicar às conexões restritas de largura de banda entre um determinado site ou região e as conexões WAN entre os sites e regiões.

</div>

<div>

## <a name="identify-network-links"></a>Identificar links de rede

Links de rede representam conexões para a WAN física que vincula diferentes áreas e sites. Na nossa topologia de exemplo, há dois links de rede regionais, cinco links de rede entre regiões e sites e um link de rede entre dois sites.

Os dois links regionais estão entre a América do Norte e a EMEA, representados como NA-EMEA-LINK e entre a Ásia e a EMEA, representados como EMEA-Ásia-LINK.

Os links de site são indicados pelas linhas que conectam a Portland, Reno e Albuquerque à região da América do Norte, Manila à região da Ásia e Cologne à região da EMEA. A linha entre Reno e Albuquerque mostra um link de rede direto entre esses dois sites.

</div>

<div>

## <a name="define-bandwidth-policies"></a>Definir políticas de largura de banda

Trabalhe com sua equipe de operações de rede para determinar Quanta largura de banda de WAN está disponível para tráfego de áudio e vídeo em tempo real nos links WAN de sua organização. Geralmente, as políticas de largura de banda são aplicadas ao WAN links se o uso da largura de banda for restrito; ou seja, se ela deveria ser maior que a largura de banda que pode ser alocada para modalidades de áudio e vídeo.

*Políticas de largura de banda* do CAC definem a largura de banda máxima que pode ser reservada para modalidades de áudio e vídeo em tempo real. Como o CAC não limita a largura de banda de outro tráfego, ele não pode evitar outros tráfegos de dados, como uma transferência de arquivo grande, fluxo de música, desde o uso de toda a largura de banda da rede.

As políticas de largura de banda do CAC podem definir qualquer um dos seguintes itens:

  - Largura de banda total máxima atribuída para áudio.

  - Largura de banda total máxima alocada para vídeo.

  - Largura de banda máxima alocada para uma única chamada de áudio (sessão).

  - Largura de banda máxima alocada para uma única chamada de vídeo (sessão).

<div>


> [!NOTE]  
> Todos os valores de largura de banda do CAC representam os limites de largura de banda <EM>unidirecionais</EM>



</div>

<div>


> [!NOTE]  
> Os recursos da política de voz do Lync Server 2013 fornecem a capacidade de substituir verificações de política de largura de banda para chamadas recebidas para o usuário (não para chamadas feitas pelo usuário). Depois que a sessão for estabelecida, o consumo de largura de banda será considerado com precisão. Esta configuração deve ser usada com moderação. Para obter detalhes, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">criar uma política de voz e configurar registros de uso de PSTN no Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar uma política de voz e configurar registros de uso PSTN no Lync Server 2013</A> na documentação de implantação.



</div>

Para otimizar a utilização da largura de banda com base em cada sessão, considere o tipo de codecs de áudio e vídeo que será usado. Em particular, evite alocar largura de banda insuficiente para um codec que você espera que seja usado com frequência. Por outro lado, se você quiser impedir que a mídia use um codec que exija mais largura de banda, deve definir a largura de banda máxima por sessão, o suficiente para desencorajar tal uso. Para áudio, nem todos os codecs estão disponíveis para todos os cenários. Por exemplo:

  - As chamadas de áudio ponto a ponto entre os pontos de extremidade do Lync usarão RTAudio (8kHz) ou RTAudio (16kHz) quando você fatorar a largura de banda e a priorização de codecs.

  - As chamadas em conferência entre os pontos de extremidade do Lync e o serviço de conferência A/V usarão G. 722 ou sirene.

  - As chamadas para a rede telefônica pública comutada (PSTN) para ou a partir de pontos de extremidade do Lync usarão G. 711 ou RTAudio (8kHz).

Use a tabela a seguir para ajudar a otimizar as configurações de largura de banda máxima por sessão.

### <a name="bandwidth-utilization-by-codecs"></a>Utilização de largura de banda por codecs

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Codec</th>
<th>Requisitos de largura de banda sem correção de erro antecipado (FEC)</th>
<th>Requisitos de largura de banda com a correção de erro antecipada (FEC)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio (8kHz)</p></td>
<td><p>49,8 kbps</p></td>
<td><p>61,6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTAudio (16kHz)</p></td>
<td><p>67 kbps</p></td>
<td><p>96 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Siren</p></td>
<td><p>57,6 kbps</p></td>
<td><p>73,6 kbps</p></td>
</tr>
<tr class="even">
<td><p>G.711</p></td>
<td><p>102 kbps</p></td>
<td><p>166 kbps</p></td>
</tr>
<tr class="odd">
<td><p>G.722</p></td>
<td><p>105,6 kbps</p></td>
<td><p>169,6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTVideo (CIF 15 fps)</p></td>
<td><p>260 kbps</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="odd">
<td><p>RTVideo (VGA de 30 fps)</p></td>
<td><p>610 kbps</p></td>
<td><p>Não aplicável</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Os requisitos de largura de banda levam em conta a sobrecarga para o seguinte: Ethernet II, IP, protocolo de datagrama de usuário (UDP), RTP (protocolo de transporte em tempo real) e SRTP (Secure real-time Transport Protocol). Eles também incluem 10 kbps para a sobrecarga RTCP.



</div>

Os codecs G. 722.1 e sirene são semelhantes, mas oferecem tarifas de bit diferentes.

O G. 722, o codec padrão para a conferência do Lync Server, é completamente diferente dos codecs G. 722.1 e sirene.

O codec sirene é usado no Lync Server nas seguintes situações:

  - Se a política de largura de banda estiver definida como muito baixa para G. 722 a ser usada.

  - Se um cliente do Communications Server 2007 ou Communications Server 2007 R2 se conectar a um serviço de conferência do Lync Server (pois esses clientes não dão suporte para o codec G. 722).

### <a name="bandwidth-utilization-by-scenario"></a>Utilização da largura de banda por cenário

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cenário</th>
<th>Requisitos de largura de banda otimizados para quantidade (Kbps)</th>
<th>Requisitos de largura de banda para o modo balanceado (Kbps)</th>
<th>Requisitos de largura de banda otimizados para qualidade (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas de áudio ponto a ponto</p></td>
<td><p>45 kbps</p></td>
<td><p>62 kbps</p></td>
<td><p>91 kbps</p></td>
</tr>
<tr class="even">
<td><p>Chamadas em conferência</p></td>
<td><p>53 kbps</p></td>
<td><p>101 kbps</p></td>
<td><p>165 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas PSTN (entre o Lync 2013 e o gateway PSTN com bypass de mídia)</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>Chamadas PSTN (entre o Lync 2013 e o servidor de mediação, sem bypass de mídia)</p></td>
<td><p>45 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Chamadas PSTN (entre o servidor de mediação e o gateway PSTN sem bypass de mídia)</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>Chamadas do Lync Polycom</p></td>
<td><p>101 kbps</p></td>
<td><p>101 kbps</p></td>
<td><p>101 kbps</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a>Identifique as subredes IP

Para cada site de rede, você precisará trabalhar com o administrador da rede para determinar quais sub-redes IP serão atribuídas a cada site de rede. Se seu administrador de rede já organizou as subredes IP em regiões de rede e sites de rede, seu trabalho fica muito mais simples.

Em nosso exemplo, o site de Nova York na região da América do Norte recebe as seguintes sub-redes de IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suponha que o Bob geralmente funcione no Detroit, vá para o escritório de Nova York para treinamento. Quando ele ligar o computador e se conectar à rede, o computador receberá um endereço IP em um dos quatro intervalos reservados para Nova York, por exemplo, 172.29.80.103.

<div>


> [!WARNING]  
> As sub-redes IP especificadas durante a configuração de rede no servidor devem corresponder ao formato fornecido pelos computadores cliente para serem usadas corretamente para o bypass de mídia. Um cliente do Lync assume seu endereço IP local e mascara o endereço IP com a máscara de sub-rede associada. Ao determinar a ID de bypass associada a cada cliente, o registrador irá comparar a lista de sub-redes IP associadas a cada site de rede em relação à sub-rede fornecida pelo cliente para uma correspondência exata. Por este motivo, é importante que as subredes inseridas durante a configuração de rede no servidor sejam subredes reais ao invés de subredes virtuais. (Se você implantar o controle de admissão de chamada, mas não o bypass de mídia, o controle de admissão de chamada funcionará mesmo se você configurar as subredes virtuais.)<BR>Por exemplo, se um cliente entrar em um computador com um endereço IP de 172.29.81.57 com uma máscara de sub-rede IP de 255.255.255.0, o Lync 2013 solicitará a ID de bypass associada à 172.29.81.0 de sub-rede. Se a subrede for definida como 172.29.0.0/16, embora o cliente pertença à subrede virtual, o Registrador não irá considerar uma correspondência porque ele está procurando especificamente pela subrede 172.29.81.0. Portanto, é importante que o administrador insira sub-redes exatamente conforme fornecido pelos clientes do Lync (que são provisionados com sub-redes durante a configuração de rede, de forma estática ou por DHCP.)



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

