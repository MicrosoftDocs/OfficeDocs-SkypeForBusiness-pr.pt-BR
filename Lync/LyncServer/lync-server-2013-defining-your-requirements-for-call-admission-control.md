---
title: 'Lync Server 2013: definindo seus requisitos de controle de admissão de chamadas'
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
ms.openlocfilehash: 13a06cfc55481fcfada5782fcbedbac52e6a7660
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504418"
---
# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a>Definindo seus requisitos de controle de admissão de chamadas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-28_

O planejamento do CAC (serviço de controle de admissão de chamadas) requer informações detalhadas sobre a topologia da rede da empresa. Para ajudar a planejar suas políticas do serviço de controle de admissão de chamadas, execute as etapas a seguir.

1.  Identifique os hubs/backbones (chamados de *regiões de rede*) dentro de sua rede corporativa.

2.  Identifique os escritórios ou locais (chamados *sites de rede*) dentro de cada região de rede.

3.  Determine a rota de rede entre cada par de regiões de rede.

4.  Determine os limites de largura de banda para cada link WAN.
    
    <div>
    

    > [!NOTE]  
    > Os limites de largura de banda referem-se à quantidade de largura de banda em um link de WAN alocada para o tráfego de áudio/vídeo do Enterprise Voice. Quando um link WAN é descrito como "largura de banda restrita", o link WAN tem um limite de largura de banda menor do que os picos de tráfego esperados pelo link.

    
    </div>

5.  Identifique as subredes de IP que são atribuídas a cada site de rede.

Para explicar esses conceitos, usaremos a topologia de rede de exemplo mostrada na figura a seguir.

**Exemplo de topologia para o controle de admissão de chamada**

![Exemplo de topologia de rede Litware Inc.](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Exemplo de topologia de rede Litware Inc.")

<div>


> [!NOTE]  
> Todos os sites de rede estão associados a uma região de rede. Por exemplo, Portland, Reno e Albuquerque estão incluídos na região da América do Norte. Nessa figura, são mostrados apenas links WAN que têm políticas de CAC aplicadas, com limites de largura de banda. Os sites de rede de Chicago, Nova York e Detroit são mostrados dentro da região oval da América do Norte, porque eles não estão com restrições largura de banda e não exigem políticas de CAC.



</div>

Os componentes da topologia neste exemplo são explicados nas seções a seguir. Para obter detalhes sobre como essa topologia foi planejada, incluindo os limites de largura de banda, consulte [exemplo: reunindo seus requisitos para controle de admissão de chamadas no Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).

<div>

## <a name="identify-network-regions"></a>Identifique as regiões de rede

Uma região de rede representa um backbone de rede ou um hub da rede.

Um backbone ou hub de rede é uma parte da infraestrutura de rede do computador que interconecta diferentes partes da rede, fornecendo um caminho para a troca de informações entre diferentes LANs ou subredes. Um backbone pode interligar diversas redes de um pequeno local para uma área geográfica ampla. A capacidade do backbone é normalmente maior do que as redes que se conectam a ele.

Nossa topologia de exemplo tem três regiões de rede: América do Norte, EMEA e APAC. Uma região de rede contém um conjunto de sites de rede (consulte a definição de sites de rede posteriormente neste tópico). Trabalhe com sua equipe de operações de rede para identificar as regiões de rede.

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a>Associando um site central de cada região de rede

O CAC requer que um site central do Lync Server seja definido para cada região de rede. O site central é selecionado com a melhor conectividade de rede e maior largura de banda para todos os outros sites nessa região de rede. O exemplo anterior da topologia de rede mostra três regiões de rede, cada uma com um site central que gerencia decisões do CAC. A partir do exemplo anterior, a associação apropriada é exibida na tabela a seguir.

<div>


> [!NOTE]  
> Os sites centrais não correspondem necessariamente aos sites de rede. Nos exemplos nesta documentação, alguns sites centrais (Chicago, Londres e Pequim) compartilham os mesmos nomes que os sites de rede. No entanto, mesmo que um site central e um site de rede compartilhem o mesmo nome, o site central é um elemento da topologia do Lync Server, enquanto o local da rede é parte da rede geral na qual a topologia do Lync Server reside.



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
<th>Site central</th>
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
<p>Colônia</p></td>
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

## <a name="identify-network-sites"></a>Identifique os sites de rede

Um site de rede representa um local onde a sua organização tem um espaço físico, por exemplo, um escritórios, um conjunto de edifícios ou um campus. Um espaço físico com uma LAN e conectividade WAN para outros sites é considerado um site de rede. Inicie o levantamento de todos os escritórios da organização. Em nosso exemplo de topologia, a região de rede da América do Norte consiste nos seguintes sites de rede: Nova York, Chicago, Detroit, Portland, Reno e Albuquerque.

Você deve associar cada site de rede a uma região de rede. Dependendo se o site de rede tem um link WAN restrito, uma política de largura de banda é associada ao site de rede. Para obter detalhes sobre políticas de CAC e a largura de banda que você alocar ao usá-las, consulte "Defina as políticas de largura de banda", posteriormente neste tópico. Para configurar o CAC, você deve associar os sites de rede às regiões de rede e criar políticas de alocação de largura de banda para aplicar às conexões de largura de banda restrita entre um determinado site ou região e conexões WAN entre locais e regiões.

</div>

<div>

## <a name="identify-network-links"></a>Identifique os links de rede

Os links de rede as representam conexões WAN físicas que vinculam sites e regiões diferentes. Em nosso exemplo de topologia, há dois links de rede regionais, cinco links de rede entre locais e regiões e um link de rede entre dois sites.

Os dois links regionais estão entre América do Norte e EMEA, representado como NA-EMEA-LINK, e entre APAC e EMEA, representado como EMEA-APAC-LINK.

Os links de site são indicados por linhas que conectam Portland, Reno e Albuquerque à região da América do Norte, Manila à região APAC e Colônia à região EMEA. A linha entre Reno e Albuquerque mostra um link de rede direta entre esses dois sites.

</div>

<div>

## <a name="define-bandwidth-policies"></a>Defina as políticas de largura de banda

Trabalhe com sua equipe de operações de rede para determinar a quantidade de largura de banda WAN que está disponível para o tráfego de vídeo e áudio em tempo real entre os links WAN na organização. As políticas de largura de banda são geralmente aplicadas aos links WAN quando o uso de largura de banda é restrito, isso é, espera-se que ele seja maior do que a largura de banda que pode ser alocada para as modalidades de áudio e vídeo.

CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities. Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.

As políticas de largura de banda do CAC podem definir o seguinte:

  - Largura de banda total máxima alocada para áudio.

  - Largura de banda total máxima alocada para vídeo.

  - Largura de banda máxima alocada para uma única chamada de áudio (sessão).

  - Largura de banda máxima alocada para uma única chamada de vídeo (sessão).

<div>


> [!NOTE]  
> Todos os valores de largura de banda do CAC representam os limites máximos de largura de banda <EM>unidirecional</EM>.



</div>

<div>


> [!NOTE]  
> Os recursos de política de voz do Lync Server 2013 oferecem a capacidade de substituir as verificações de política de largura de banda para chamadas de entrada para o usuário (não para chamadas de saída que são colocadas pelo usuário). Depois da sessão ser estabelecida, o consumo de largura de banda será contabilizado com precisão. Essa configuração deve ser usada com moderação. Para obter detalhes, consulte <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">criar uma política de voz e configurar registros de uso de PSTN no Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013</A> na documentação de implantação.



</div>

Para otimizar a utilização de largura de banda com base por sessão, considere o tipo de codec de áudio e vídeo que será usado. Mais especificamente, evite alocar menos largura de banda para um codec que você espera que seja usado com frequência. Por outro lado, se você deseja impedir que a mídia use um codec que exija mais largura de banda, deverá definir a largura de banda máxima por sessão menor o suficiente para desencorajar tal uso. Para o áudio, nem todos os codecs estão disponíveis para cada cenário. Por exemplo:

  - As chamadas de áudio ponto a ponto entre os pontos de extremidade do Lync usarão RTAudio (8 kHz) ou RTAudio (16 kHz) quando você fatorar a largura de banda e a priorização de codecs.

  - As chamadas de conferência entre os pontos de extremidade do Lync e o serviço de conferência A/V usarão G. 722 ou Siren.

  - Chamadas para a rede telefônica pública comutada (PSTN) para ou a partir de pontos de extremidade do Lync usarão G. 711 ou RTAudio (8 kHz).

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
<th>Requisito de largura de banda sem nenhuma FEC (correção de erro antecipada)</th>
<th>Requisito de largura de banda com FEC (correção de erro antecipada)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio (8 kHz)</p></td>
<td><p>49,8 kbps</p></td>
<td><p>61,6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTAudio (16 kHz)</p></td>
<td><p>67 kbps</p></td>
<td><p>96 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Siren</p></td>
<td><p>57,6 kbps</p></td>
<td><p>73,6 kbps</p></td>
</tr>
<tr class="even">
<td><p>G. 711</p></td>
<td><p>102 kbps</p></td>
<td><p>166 kbps</p></td>
</tr>
<tr class="odd">
<td><p>G. 722</p></td>
<td><p>105,6 kbps</p></td>
<td><p>169,6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTVideo (CIF 15 fps)</p></td>
<td><p>260 kbps</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="odd">
<td><p>RTVideo (VGA 30 fps)</p></td>
<td><p>610 kbps</p></td>
<td><p>Não aplicável</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Os requisitos de largura de banda consideram a sobrecarga de conta para o seguinte: Ethernet II, IP, protocolo de datagrama de usuário (UDP), RTP (protocolo de transporte em tempo rea) e SRTP (protoco de controle de transporte em tempo real). Eles também incluem 10 kbps para sobrecarga RTCP.



</div>

Os codecs G.722.1 e Siren são semelhantes, mas oferecem diferentes taxas de bits.

G. 722, o codec padrão para a conferência do Lync Server, é completamente diferente dos codecs G. 722.1 e Siren.

O codec Siren é usado no Lync Server nas seguintes situações:

  - Quando a política de largura de banda está definida para que o G.722 seja usado.

  - Se um cliente do Communications Server 2007 ou Communications Server 2007 R2 se conectar a um serviço de conferência do Lync Server (porque esses clientes não dão suporte ao codec G. 722).

### <a name="bandwidth-utilization-by-scenario"></a>Utilização de largura de banda por cenário

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
<th>Requisito de largura de banda otimizado por quantidade (kbps)</th>
<th>Requisito de largura de banda para modo balanceado (kbps)</th>
<th>Requisito de largura de banda otimizado por qualidade (kbps)</th>
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
<td><p>Chamadas PSTN (entre o Lync 2013 e gateway PSTN, com bypass de mídia)</p></td>
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
<td><p>Chamadas PSTN (entre o servidor de mediação e o gateway PSTN, sem bypass de mídia)</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>Chamadas do Lync-Polycom</p></td>
<td><p>101 kbps</p></td>
<td><p>101 kbps</p></td>
<td><p>101 kbps</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a>Identifique as subredes IP

Para cada site de rede, você precisará trabalhar com seu administrador de rede para determinar quais subredes IP são atribuídas para cada site de rede. Se seu administrador de rede já organizou as subredes IP em regiões de rede e sites de rede, seu trabalho é significantemente simplificado.

Em nosso exemplo, o site de Nova York na região da América do Norte é atribuído às seguintes subredes IP: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Vamos supor que Bob, que geralmente trabalha em Detroit, viaja para o escritório de Nova York para treinamento. Quando ele liga o computador e se conecta à rede, o computador obterá um endereço IP em um dos quatro intervalos reservados para Nova York, por exemplo, 172.29.80.103.

<div>


> [!WARNING]  
> As subredes IP especificadas durante a configuração de rede no servidor devem corresponder o formato oferecido por computadores clientes para poder ser usado adequadamente pelo bypass de mídia. Um cliente do Lync usa seu endereço IP local e mascara o endereço IP com a máscara de sub-rede associada. Ao determinar o ID de bypass associado com cada cliente, o Registrador irá comprar a lista de subredes IP associadas com cada local de rede na subrede oferecida pelo cliente para uma correspondência exata. Por este motivo, é importante que as subredes inseridas durante a configuração de rede no servidor sejam subredes reais ao invés de subredes virtuais. (Se você implantar o controle de admissão de chamada, mas não o bypass de mídia, o controle de admissão de chamada funcionará mesmo se você configurar as subredes virtuais.)<BR>Por exemplo, se um cliente entrar em um computador com um endereço IP de 172.29.81.57 com uma máscara de sub-rede IP 255.255.255.0, o Lync 2013 solicitará a ID de bypass associada à sub-rede 172.29.81.0. Se a subrede é definida como 172.29.0.0/16, embora o cliente pertença à subrede virtual, o Registrador não irá considerar uma correspondência porque ele está procurando especificamente pela subrede 172.29.81.0. Portanto, é importante que o administrador insira as sub-redes exatamente conforme fornecido pelos clientes do Lync (que são provisionados com sub-redes durante a configuração de rede, de forma estática ou por DHCP).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

