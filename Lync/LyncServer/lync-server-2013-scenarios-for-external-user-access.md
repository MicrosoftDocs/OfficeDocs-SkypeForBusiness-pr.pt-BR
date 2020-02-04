---
title: 'Lync Server 2013: Cenários de acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eab8323744615dc3f5d0b68f4325fbfb85bf911e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Cenários de acesso de usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

O acesso de usuários externos para o Lync Server 2013 exige que você implante pelo menos um servidor de borda e um proxy reverso na sua rede de perímetro. Opcionalmente, você pode implantar um diretor ou um pool de diretor em sua rede interna.

Se você precisar de maior capacidade do que um único servidor de borda pode fornecer ou se precisar de alta disponibilidade para a implantação do servidor de borda, você pode configurar o balanceamento de carga e implantar vários servidores de borda em um pool de carga balanceada. Se a sua organização tiver vários data centers, você poderá ter implantações de servidor de borda ou de pool de bordas em mais de um local. No entanto, apenas uma das implantações de servidor de borda pode ser designada como a rota de Federação.

Esta seção define os cenários para implantações do servidor de borda e mapeia as seções de planejamento para os cenários possíveis. Por exemplo, se a sua implantação requer alta disponibilidade, Federação com contatos de presença e mensagens extensível (XMPP) e Lync Mobility, selecione as entradas correspondentes na tabela a seguir que atenderiam a esses requisitos e usar o seções de planejamento referenciadas para definir sua implantação, conforme ilustrado no fluxograma a seguir.

**Processo de seleção do cenário de implantação do servidor de borda**

![Exemplo de fluxograma de implantação](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Exemplo de fluxograma de implantação")

Ao usar esse processo, você pode planejar e documentar a configuração de todos os recursos possíveis que pretende implantar para seus usuários. No entanto, é possível adicionar serviços de Federação e mobilidade após a implantação do servidor de borda e confirmar a operação correta antes de adicionar outros recursos. O processo de adicionar recursos a uma implantação de servidor de borda existente é abordado na seção implantação. Para obter detalhes sobre a implantação, consulte [implantando o acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) , incluindo o planejamento desses recursos durante o processo de planejamento inicial, você pode se preparar para os requisitos de DNS, firewall e certificado para os recursos adicionais, que permitem que você adquira os certificados e configure os requisitos de DNS e de porta/protocolo com antecedência.

<div>


> [!TIP]  
> Se você estiver planejando instalar os servidores de borda e o proxy reverso e adicionar recursos mais tarde (por exemplo, Federação e mobilidade), determine quais certificados você precisará para todos os serviços após a implantação. Planejar e adquirir os certificados para todos os recursos de antemão, implantados inicialmente ou não, poupa a necessidade de solicitar novos certificados para satisfazer os requisitos de Federação (ou seja, nos servidores de borda) ou o proxy reverso (ou seja, para mobilidade serviços).



</div>

<div>


> [!NOTE]  
> Todos os serviços de borda são executados em cada servidor de borda. Os serviços não podem ser divididos entre dois servidores de borda diferentes. Se você implantar um pool de bordas para escalabilidade, todos os serviços de borda serão implantados em cada servidor de borda no pool. A Federação do XMPP, o Office Communications Server e a Federação do Lync Server, a conectividade de mensagens de chat públicas e a mobilidade do cliente são serviços adicionais que podem ser implantados após a implantação do seu primeiro servidor de borda ou do pool de borda. Serviços de mobilidade é um recurso que usa o proxy reverso. A instalação dos serviços de mobilidade não adicionará recursos aos seus servidores de borda, mas exigirá a reconfiguração do seu proxy reverso. A coluna de <STRONG>metas de instalação</STRONG> que lista esses recursos fornece orientação de planejamento na coluna associada em seções de planejamento do <STRONG>servidor de borda ou seções</STRONG> para planejar simultaneamente esses recursos a serem implantados quando os servidores de borda estiverem instalados e configurados.



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>Identificar e mapear seus objetivos de implantação


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Objetivo de instalação</th>
<th>Documentação de planejamento do servidor de borda</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Você decidiu que um único servidor é suficiente para serviços de Edge na sua infraestrutura. Você também pretende usar endereços IP particulares para as interfaces externas do servidor de borda com NAT para a Internet.</p>
<p>Use esta seção de planejamento se você estiver implantando um servidor de borda único em seu perímetro. Você vai implantar um servidor de borda com endereços IP privados atribuídos ao servidor de borda e usar o NAT para fornecer os endereços IP públicos para os usuários externos na Internet.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Única borda consolidada com endereços IP privados e NAT no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Você decidiu que um único servidor é suficiente para serviços de Edge na sua infraestrutura. Você também pretende usar endereços IP públicos para as interfaces externas do servidor de borda para a Internet.</p>
<p>Use esta seção de planejamento se você estiver implantando um servidor de borda único em seu perímetro. Você vai implantar um servidor de borda com endereços IP públicos atribuídos ao servidor de borda. Em vez de NAT, você usará o roteamento nesse cenário. O endereço IP público real do servidor de borda é disponibilizado para conexões de usuários externos.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Única borda consolidada com endereços IP públicos no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Você decidiu que a alta disponibilidade dos serviços de borda é importante para seus usuários e irá implantar dois ou mais servidores de borda neste pool. Você também pretende usar endereços IP particulares para as interfaces externas do servidor de borda com NAT para a Internet.</p>
<p>Use esta seção de planejamento se você estiver implantando um pool de servidores de borda em seu perímetro. Você implantará os servidores de borda com endereços IP privados atribuídos ao servidor de borda usando o balanceamento de carga de DNS para distribuir a comunicação entre o pool. Você usará o NAT para fornecer os endereços IP públicos para os usuários externos na Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Você decidiu que a alta disponibilidade dos serviços de borda é importante para seus usuários e irá implantar dois ou mais servidores de borda neste pool. Você também pretende usar endereços IP públicos para as interfaces externas do servidor de borda para a Internet.</p>
<p>Use esta seção de planejamento se você estiver implantando um pool de servidores de borda em seu perímetro. Você implantará os servidores de borda com endereços IP públicos atribuídos ao servidor de borda usando o balanceamento de carga de DNS para distribuir a comunicação entre o pool. Em vez de NAT, você usará o roteamento para fornecer os endereços IP públicos para os usuários externos na Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Você decidiu que a alta disponibilidade dos serviços de borda é importante para seus usuários e irá implantar dois ou mais servidores de borda nesse pool usando um balanceador de carga de hardware.</p>
<p>Use esta seção de planejamento se você estiver implantando um pool de servidores de borda em seu perímetro. Você implantará os servidores de borda com endereços IP públicos atribuídos ao servidor de borda usando balanceadores de carga de hardware para distribuir a comunicação em todo o pool. Em vez de NAT, você usará o roteamento para fornecer os endereços IP públicos para os usuários externos na Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Os cenários de Federação permitem que você planeje o recurso que estenderá os tipos de parceiros com os quais os usuários podem se comunicar.</p>
<ul>
<li><p>Federação do Lync Server</p></li>
<li><p>Federação do Office Communications Server</p></li>
<li><p>Conectividade de mensagem de chat Pública</p></li>
<li><p>Federação do XMPP</p></li>
</ul></td>
<td><p>Planejando cenários de Federação</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planejando a Federação do Lync Server 2013 e do Office Communications Server</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planejando a conectividade de mensagens instantâneas públicas no Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Como planejar a Federação do protocolo de presença e de mensagens extensíveis (XMPP) no Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Os serviços de mobilidade são oferecidos por meio do proxy reverso. Os serviços que permitem a mobilidade para usuários externos são implantados no servidor front-end ou no pool de front-end. Você cria ou modifica regras de publicação existentes no proxy reverso para habilitar serviços de mobilidade para seus usuários externos.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Planejamento para mobilidade no Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> Nas seções de cenários a seguir estão as arquiteturas de referência, o exemplo de DNS, as definições de porta/protocolo e os requisitos de certificado. Também estão incluídos diagramas para suas definições de DNS, porta/protocolo e necessidades de certificado. Os diagramas fornecerão um modelo para você preencher e distribuir para outras equipes (por exemplo, a equipe de rede da sua organização, a equipe da infraestrutura de chave pública e a equipe de implantação do servidor). A meta dos diagramas é melhorar a comunicação e garantir o sucesso ao comunicar os elementos de configuração do servidor de borda necessárias para as pessoas que farão o trabalho de configuração real. Recomendamos que você use os diagramas e as arquiteturas de referência associadas para planejar a implantação.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

