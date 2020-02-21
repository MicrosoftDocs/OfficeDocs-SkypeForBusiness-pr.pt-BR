---
title: 'Lync Server 2013: cenários para acesso de usuário externo'
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
ms.openlocfilehash: 3e9a2f60b2273cf8d43833226ede66a2a90478a6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a>Cenários para acesso de usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

Fornecer acesso de usuário externo para o Lync Server 2013 requer que você implante pelo menos um servidor de borda e um proxy reverso na sua rede de perímetro. Opcionalmente, você pode implantar um diretor ou pool de diretor em sua rede interna.

Se você precisar de capacidade maior do que um servidor de borda único pode fornecer, ou se você precisar de alta disponibilidade para a implantação do servidor de borda, você pode configurar o balanceamento de carga e implantar vários servidores de borda em um pool com balanceamento de carga. Se sua organização tiver vários data centers, você pode ter implantações de servidor de borda ou de pool de borda em mais de um local. No entanto, apenas uma das implantações do servidor de borda pode ser designada como a rota de Federação.

Esta seção define os cenários de implantações do servidor de borda e mapeia as seções de planejamento para os cenários possíveis. Por exemplo, se sua implantação requer alta disponibilidade, Federação com contatos extensível de mensagens e presença (XMPP) e Lync Mobility, selecione as entradas correspondentes na seguinte tabela que atendam a esses requisitos e use o seções de planejamento referenciadas para definir sua implantação, conforme ilustrado no fluxograma a seguir.

**Processo de seleção do cenário de implantação do Servidor de Borda**

![Exemplo de fluxograma de implantação](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Exemplo de fluxograma de implantação")

Usando este processo, é possível planejar e documentar a configuração de todos os recursos em potencial que você pretende implantar para seus usuários. No entanto, você pode adicionar serviços de Federação e mobilidade depois de implantar o servidor de borda e ter confirmado a operação correta antes de adicionar outros recursos. O processo de adição de recursos a uma implantação de servidor de borda existente é abordado na seção implantação. Para obter detalhes sobre a implantação, consulte [implantando o acesso de usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) incluindo o planejamento desses recursos durante o processo de planejamento inicial, você pode se preparar para os requisitos de DNS, firewall e certificado para os recursos adicionados, o que permite que você adquira os certificados e configure os requisitos de DNS e de porta/protocolo com antecedência.

<div>


> [!TIP]  
> Se você estiver planejando instalar os servidores de borda e o proxy reverso e adicionar recursos posteriormente (por exemplo, Federação e mobilidade), determine quais certificados você precisará para todos os serviços após a implantação. O planejamento e a aquisição dos certificados para todos os recursos de antemão, implantados inicialmente ou não, evita que você precise solicitar novos certificados para atender aos requisitos de Federação (ou seja, nos servidores de borda) ou no proxy reverso (ou seja, para mobilidade serviços).



</div>

<div>


> [!NOTE]  
> Todos os serviços de borda são executados em cada servidor de borda. Os serviços não podem ser divididos entre dois servidores de borda diferentes. Se você implantar um pool de borda para escalabilidade, todos os serviços de borda serão implantados em cada servidor de borda no pool. XMPP Federation, Office Communications Server e Lync Server Federation, conectividade pública de IM e mobilidade de cliente são serviços adicionais que podem ser implantados após a implantação do seu primeiro pool de borda ou servidor de borda. Serviços de mobilidade é o recurso que usa proxy inverso. A instalação dos serviços de mobilidade não adicionará recursos aos servidores de borda, mas exigirá a reconfiguração de seu proxy reverso. A coluna <STRONG>objetivo de instalação</STRONG> que lista esses recursos fornece diretrizes de planejamento na coluna associada na <STRONG>seção planejamento do servidor de borda ou seções</STRONG> para planejar simultaneamente que esses recursos sejam implantados quando os servidores de borda são instalados e configurados.



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a>Identificando e mapeando suas metas de implantação


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Objetivo de instalação</th>
<th>Documentação de planejamento do Servidor de Borda</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Você decidiu que um único servidor é suficiente para serviços de Borda em sua infraestrutura. Você também pretende usar endereços IP privados para interfaces externas do servidor de Borda com NAT para a Internet.</p>
<p>Use esta seção de planejamento se você estiver implantando um único servidor de borda em seu perímetro. Você implantará um servidor de borda com endereços IP privados atribuídos ao servidor de borda e usará o NAT para fornecer os endereços IP públicos para os usuários externos na Internet.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Única borda consolidada com endereços IP privados e NAT no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Você decidiu que um único servidor é suficiente para serviços de Borda em sua infraestrutura. Você também pretende usar endereços IP públicos para interfaces externas do servidor de Borda para a Internet.</p>
<p>Use esta seção de planejamento se você estiver implantando um único servidor de borda em seu perímetro. Você implantará um servidor de borda com endereços IP públicos atribuídos ao servidor de borda. Ao invés do NAT, você usará o roteamento neste cenário. O endereço IP público real do servidor de borda é disponibilizado para conexões de usuário externo.</p></td>
<td><p><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Única borda consolidada com endereços IP públicos no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Você decidiu que alta disponibilidade dos serviços de Borda é importante para seus usuários e irá implantar dois ou mais Servidores de Borda neste pool. Você também pretende usar endereços IP privados para as interfaces externas do Servidor de Borda com NAT para a Internet.</p>
<p>Use esta seção de planejamento se você estiver implantando um pool de servidores de borda em seu perímetro. Você implantará os servidores de borda com endereços IP privados atribuídos ao servidor de borda, usando o balanceamento de carga DNS para distribuir a comunicação entre o pool. Você usará NAT para oferecer endereços IP públicos para usuários externos na Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Você decidiu que alta disponibilidade dos serviços de Borda é importante para seus usuários e irá implantar dois ou mais Servidores de Borda neste pool. Você também pretende usar endereços IP públicos para as interfaces externas do servidor de borda para a Internet.</p>
<p>Use esta seção de planejamento se você estiver implantando um pool de servidores de borda em seu perímetro. Você implantará os servidores de borda com endereços IP públicos atribuídos ao servidor de borda, usando o balanceamento de carga DNS para distribuir a comunicação entre o pool. Ao invés do NAT, você usará o roteamento para oferecer endereços IP públicos para usuários externos na Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Você decidiu que a alta disponibilidade dos serviços de borda é importante para seus usuários e implantar dois ou mais servidores de borda nesse pool usando um balanceador de carga de hardware.</p>
<p>Use esta seção de planejamento se você estiver implantando um pool de servidores de borda em seu perímetro. Você implantará os servidores de borda com endereços IP públicos atribuídos ao servidor de borda, usando balanceadores de carga de hardware para distribuir a comunicação entre o pool. Ao invés do NAT, você usará o roteamento para oferecer endereços IP públicos para usuários externos na Internet.</p></td>
<td><p><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Os cenários de federação permite planejar o recurso que irá estender os tipos de parceiros que os usuários podem se comunicar.</p>
<ul>
<li><p>Federação do Lync Server</p></li>
<li><p>Federação do Office Communications Server</p></li>
<li><p>Conectividade a redes públicas de mensagens instantâneas</p></li>
<li><p>Federação XMPP</p></li>
</ul></td>
<td><p>Planejamento para cenários de federação</p>
<ul>
<li><p><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planejamento para Federação do Lync Server 2013 e Office Communications Server</a></p></li>
<li><p><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planejando a conectividade de mensagens instantâneas públicas no Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planejando a Federação do protocolo XMPP (Extensible Messaging and Presence Protocol) no Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Serviços de mobilidade são oferecidos através do proxy inverso. Os serviços que permitem a mobilidade para usuários externos são implantados no servidor front-end ou no pool de front-ends. Você cria ou modifica regras de publicação existentes no proxy inverso para habilitar os serviços de mobilidade para seus usuários externos.</p></td>
<td><p><a href="lync-server-2013-planning-for-mobility.md">Planejamento de mobilidade no Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> Nas seguintes seções Cenários existem arquiteturas de referência, DNS de exemplo, definições de porta/protocolo e requisitos de certificado. Também inclui diagramas para seu DNS, definições de porta/protocolo e necessidades de certificado. Os diagramas oferecerão um modelo para você preencher e distribuir para outras equipes (por exemplo, a Equipe de Rede da sua organização, Equipe de Infraestrutura de Chave Pública e Equipe de Implantação do Servidor). O objetivo dos diagramas é aprimorar a comunicação e garantir o sucesso ao comunicar os elementos de configuração necessários do servidor de borda às pessoas que farão o trabalho de configuração real. Recomendamos que você use os diagramas e as arquiteturas de referência associados para planejar sua implantação.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

