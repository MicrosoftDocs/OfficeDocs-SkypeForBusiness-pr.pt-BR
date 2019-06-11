---
title: 'Lync Server 2013: planejamento de capacidade para servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af60947a1132d26d5e8ba015d54cdbea80b8b54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Planejamento de capacidade para servidor de chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-05_

O servidor de chat persistente pode executar chats em tempo real de vários usuários que podem persistir para recuperação futura e pesquisa. Ao contrário das mensagens instantâneas em grupo (IM) salvas na caixa de correio de um usuário, se o histórico da conversa estiver configurado, uma sessão persistente do servidor de chat permanecerá aberta e o conteúdo será salvo em um servidor, juntamente com as mensagens, arquivos, URLs e outros dados que fazem parte de um conversa em andamento.

O planejamento de capacidade é uma parte importante da preparação para a implantação do servidor de chat persistente. Este tópico fornece detalhes sobre topologias persistentes de servidor de chat com suporte e tabelas de planejamento de capacidade que você pode usar para determinar a melhor configuração para a sua implantação. Ele também descreve como gerenciar melhor implantações persistentes do servidor de chat que exigem maior capacidade nos horários de pico.

Para baixar o servidor de chat persistente, consulte "servidor de chat persistente do Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)Server 13" em.

Para obter detalhes sobre como instalar o servidor de chat persistente, consulte Instalando o [servidor de chat persistente no Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) e Configurando o [servidor de chat persistente no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) na documentação de implantação.

Ferramentas de suporte, como o Lync Server Planning Tool, podem ajudá-lo ainda mais no planejamento da capacidade. Para obter detalhes sobre a ferramenta de planejamento, consulte [iniciando o processo de planejamento do Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) na documentação de planejamento.

<div>

## <a name="persistent-chat-server-supported-topologies"></a>Topologias compatíveis com o servidor de chat persistente

Você pode implantar um servidor de chat persistente em pools de servidor único ou de vários servidores e com topologia de pool único ou de vários pools.

Agora também é compatível com o servidor de chat persistente no servidor Standard Edition para novas implantações do Lync Server 2013. No entanto, o desempenho e a escala serão afetados, e como não há uma opção de alta disponibilidade para esta nova implantação, esperamos que você o use principalmente para fins de prova de conceito, avaliação e assim por diante.

<div>


> [!NOTE]  
> Para obter detalhes adicionais sobre ambas as topologias, consulte <A href="lync-server-2013-planning-for-persistent-chat-server.md">planejando o servidor de chat persistente no Lync server 2013</A> neste conjunto de documentação e implantando o <A href="lync-server-2013-deploying-persistent-chat-server.md">servidor de chat persistente no Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="single-server-topology"></a>Topologia de servidor único

A configuração mínima e a implantação mais simples para o servidor de chat persistente é uma única topologia de servidor front-end persistente do servidor de chat. Esta implantação requer um único servidor que executa o servidor de chat persistente (que, opcionalmente, executa o serviço de conformidade, se a conformidade estiver habilitada), um servidor que hospede o banco de dados do SQL Server e se a conformidade for necessária, o banco de dados do SQL Server para armazenar o dados de conformidade.

<div>


> [!IMPORTANT]  
> Você não pode adicionar mais servidores a um pool de servidores de chat persistente iniciado como uma implantação de servidor único no construtor de topologias. Recomendamos usar a topologia de pool de vários servidores, mesmo se você estiver usando um único servidor. Isso é possível para que você possa adicionar mais servidores mais tarde, se for necessário. 


</div>

A figura a seguir mostra todos os componentes obrigatórios e opcionais de uma topologia para um único servidor de front-end do servidor de chat persistente com conformidade.

**Único servidor de chat persistente**

![Topologia de servidor único com serviço de conformidade] (images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologia de servidor único com serviço de conformidade")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologia de vários servidores

Para fornecer maior capacidade e confiabilidade, você pode implantar uma topologia de vários servidores, conforme descrito em [planejamento para servidor de chat persistente no Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). A topologia de vários servidores pode incluir até quatro computadores ativos que executam o servidor de chat persistente (as configurações de alta disponibilidade e recuperação de desastres permitirão até oito, mas apenas quatro podem estar ativas e as quatro restantes em standby). Cada servidor pode oferecer suporte a quantos usuários simultâneos do 20.000, para um total de 80.000 usuários simultâneos conectados a um pool de servidores de chat persistente com quatro servidores. Uma topologia de vários servidores é a mesma que a topologia de servidor único, exceto que vários servidores hospedam o servidor de chat persistente e podem ser dimensionados para maior. Vários computadores que executam o servidor de chat persistente devem residir no mesmo domínio dos serviços de domínio Active Directory do Lync Server e no serviço de conformidade.

A figura a seguir mostra todos os componentes de uma topologia de vários servidores com vários computadores que executam o servidor de chat persistente, o serviço de conformidade opcional e um banco de dados de conformidade separado.

**Vários servidores de chat persistentes**

![Topologia de vários servidores] (images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologia de vários servidores")

Em uma implantação de servidor de chat persistente de quatro servidores, em que os usuários do 80.000 podem ser conectados simultaneamente e usar chats persistentes, a carga é distribuída uniformemente em 20.000 usuários por servidor. Se um servidor ficar indisponível, os usuários que estiverem conectados a esse servidor perderão o acesso ao servidor de chat persistente. Os usuários desconectados serão automaticamente transferidos para os servidores remanescentes até que o servidor indisponível seja restaurado. Dependendo da quantidade de tráfego de chat persistente na rede, esta transferência pode demorar alguns minutos ou mais. Como cada um dos servidores restantes pode estar hospedando tantos quanto os usuários do 30.000, recomendamos que você restaure o servidor indisponível o mais rápido possível para evitar problemas de desempenho. Caso contrário, você pode disponibilizar outro servidor de chat persistente usando o construtor de topologias ou o cmdlet do Windows PowerShell, **set-CsPersistentChatActiveServer**.

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>Planejamento da capacidade do servidor de chat persistente

As tabelas a seguir podem ajudá-lo com o planejamento da capacidade para o servidor de chat persistente. Eles modelam como alterar várias configurações de servidor de chat persistente afetam os recursos de capacidade.

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>Planejando a capacidade máxima para o servidor de chat persistente

Use a seguinte tabela de exemplo para determinar o número de usuários que você será capaz de suportar.

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>Exemplo de capacidade máxima do pool do servidor de chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Instâncias ativas do serviço de chat persistente</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>Instâncias do serviço de chat persistente</p></td>
<td><p><em>8 (4 deve estar inativo; somente um máximo de 4 pode estar ativo)</em></p></td>
</tr>
<tr class="odd">
<td><p>Usuários ativos conectados</p></td>
<td><p><em>80,000</em></p></td>
</tr>
<tr class="even">
<td><p>Total de usuários provisionados</p></td>
<td><p>150,000</p></td>
</tr>
<tr class="odd">
<td><p>Número de pontos de extremidade</p></td>
<td><p>120,000</p></td>
</tr>
</tbody>
</table>


No exemplo anterior, o plano é compatível com o número máximo de usuários que o chat do servidor de chat persistente permite: quatro servidores/instâncias do serviço de chat persistente (pode ter quatro servidores passivos executando o chat persistente para alta disponibilidade e recuperação de desastres) e usuários do 20.000 por servidor, para um total de 80.000 usuários ativos.

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>Planejamento de capacidade para gerenciar o acesso persistente à sala de chat

A tabela de exemplo a seguir pode ajudá-lo a planejar o gerenciamento de acesso à sala de chat persistente em um pool de servidores de chat persistente.

### <a name="managing-chat-room-access-sample"></a>Como gerenciar o exemplo de acesso à sala de chat

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Salas de chat pequenas</th>
<th>Salas de chat médias</th>
<th>Salas de chat grandes</th>
<th>Total</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tamanho das salas de chat (número de usuários conectados)</p></td>
<td><p>30 por sala</p></td>
<td><p>150 por sala</p></td>
<td><p>16.000 por sala</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salas de chat</p></td>
<td><p>32,000</p></td>
<td><p>1,067</p></td>
<td><p>254</p></td>
<td><p>33,077</p></td>
</tr>
<tr class="odd">
<td><p>% de salas que são auditórios</p></td>
<td><p>1%</p></td>
<td><p>1%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>% de salas abertas</p></td>
<td><p>3%</p></td>
<td><p>3%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salas abertas (para associação explícita)</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>Salas não abertas (salas normais com associação explícita)</p></td>
<td><p>31,040</p></td>
<td><p>1.035</p></td>
<td><p>5</p></td>
<td><p>32,080</p></td>
</tr>
<tr class="odd">
<td><p>Salas de auditório (ingresso de apresentadores adicionais)</p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salas gerenciadas pro associação direta</p></td>
<td><p>50%</p></td>
<td><p>10%</p></td>
<td><p>0%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salas gerenciadas por grupos de usuários</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Grupos de usuários na lista de associação de cada sala de chat para salas abertas (sem especificação explícita)</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuários na lista de associação de cada sala de chat para salas não abertas</p></td>
<td><p>30</p></td>
<td><p>150</p></td>
<td><p>16,000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Grupos de usuários na lista de associação de cada sala de chat para salas não abertas</p></td>
<td><p>3</p></td>
<td><p>5</p></td>
<td><p>254</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuários e grupos de usuários na lista de gerentes de cada sala de chat (para salas abertas e não abertas)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Usuários e grupos de usuários na lista de apresentadores de cada sala de chat (para salas abertas e não abertas)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entidades de associação com base em usuário em todas as salas não abertas</p></td>
<td><p>465,600</p></td>
<td><p>15,520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entidades de associação com base em grupo usuários em todas as salas não abertas</p></td>
<td><p>46,560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entidades de usuários e grupos de usuários em todas as salas de chat de auditório</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entidades de gerente com base em usuários e grupos de usuários em todas as listas de gerentes das salas de chat</p></td>
<td><p>192,000</p></td>
<td><p>6,400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuários ativos por sala de chat</p></td>
<td><p><em>30</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16,000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salas de chat por usuário</p></td>
<td><p><em>12</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>16</em></p></td>
</tr>
<tr class="odd">
<td><p>Grupos de usuário na lista de membros de cada sala de chat</p></td>
<td><p><em>254</em></p></td>
<td><p><em>254</em></p></td>
<td><p><em>15</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salas gerenciadas por grupos de usuários</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entidades de participação baseadas em grupos de usuário em todas as salas de chat</p></td>
<td><p>155,200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entidades de participação baseadas em usuários em todas as salas de chat</p></td>
<td><p>465,600</p></td>
<td><p>77,600</p></td>
<td><p>72,000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuários e grupos de usuários no gerenciador de cada sala de chat, apresentador e listas de escopo</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Usuários e grupos de usuários em todas as listas de escopo, gerentes e apresentadores das salas de chat</p></td>
<td><p>192,000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entradas de controle de acesso</p></td>
<td><p>704,160</p></td>
<td><p>26,768</p></td>
<td><p>160</p></td>
<td><p>731,088</p></td>
</tr>
<tr class="even">
<td><p>Entradas de controle de máximo acesso</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2,000,000</p></td>
</tr>
</tbody>
</table>


No exemplo anterior, quando você implanta os servidores de chat persistente de acordo com as diretrizes recomendadas, eles podem manipular até 80.000 usuários ativos em um pool de quatro servidores com conformidade habilitada.

Este exemplo mostra como salas de chat são categorizadas como pequenas (30 usuários ativos a qualquer momento), médias (150 usuários ativos) e grandes (16.000 usuários ativos). O número de salas de chat de um determinado tamanho é calculado com base no número total de:

  - Usuários ativos no sistema

  - Usuários ativos em salas de chat de determinado tamanho

  - Salas de chat de um tamanho determinado onde ingressa um único usuário

Para cada sala de chat, a tabela de planejamento de capacidade anterior especifica o número de entradas de controle de acesso que estão associados com a sala de chat, incluindo entradas que são atribuídos diretamente para a sala de chat. Você pode controlar o acesso a salas de chat individuais usando listas de controle de acesso (ACLs). Você também pode controlar o acesso no nível de categoria. Em uma ACL, uma entrada de controle de acesso individual pode ser um grupo de usuários (por exemplo, um grupo de segurança, uma lista de distribuição) ou um único usuário. Você pode definir as entradas de controle de acesso aos membros, aos apresentadores e aos gerentes de sala de chat.

<div>


> [!IMPORTANT]  
> No planejamento da estratégia de gerenciamento de salas de chat, tenha em mente que o número total de entradas de controle de acesso permitido é de dois milhões. Se as entradas de controle de acesso calculado excederem dois milhões, o desempenho do servidor pode degradar significativamente. Para evitar esse problema, sempre que possível, verifique se as entradas de controle de acesso são grupos de usuários em vez de usuários individuais.



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>Planejamento de capacidade para gerenciar o acesso à sala de chat por convite

Você pode usar a tabela de planejamento de capacidade a seguir para compreender o número de convites que o servidor de chat persistente cria e armazena no banco de dados de chat persistente quando ele está configurado para enviar convites. Você gerencia os convites na categoria usando a página de **configurações de categoria da sala de chat** no painel de controle do Lync Server, ou usando o cmdlet do Windows PowerShell, **set-csPersistentChatCategory**. Você pode gerenciar convites em uma sala de chat (em linha com o que a categoria permite) usando a página de **Gerenciamento de salas** iniciada do cliente do Lync ou usando um cmdlet do Windows PowerShell, **set-csPersistentChatRoom**.

Os dados de exemplo na tabela a seguir pressupõem que, na página de  **configurações de sala de chat** para 50% de todas as salas de chat, a opção de  **convites** está definida como  **Sim**.

<div>


> [!IMPORTANT]  
> Se o valor calculado para o número de convites gerado pelo servidor exceder 1 milhão, o desempenho do servidor pode degradar significativamente. Para evitar esse problema, certifique-se de minimizar o número de salas de chat que estão configuradas para enviar convites ou restringir o número de usuários que podem participar de salas de chat que foram configurados para enviar convites.



</div>

### <a name="chat-room-access-by-invitation-sample"></a>Exemplo de acesso à sala de chat por convite

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Salas de chat pequenas</th>
<th>Salas de chat médias</th>
<th>Salas de chat grandes</th>
<th>Total</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Usuários que podem acessar a sala de chat</p></td>
<td><p>30 por sala</p></td>
<td><p>150 por sala</p></td>
<td><p>16.000 por sala</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Porcentagem de salas com convites</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salas de chat configuradas para enviar convites</p></td>
<td><p><em>16,000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Usuários que podem acessar a sala de chat</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16,000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Convites gerados pelo servidor de chat persistente</p></td>
<td><p>960,000</p></td>
<td><p>120,000</p></td>
<td><p>80,000</p></td>
<td><p>1,160,000</p></td>
</tr>
<tr class="even">
<td><p>Número de convites máximo permitido</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2,000,000</p></td>
</tr>
<tr class="odd">
<td><p>Modelo 1 - Iniciar com o número esperado de mensagens por sala/dia</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Taxa de chat por sala (por dia)</p></td>
<td><p>50</p></td>
<td><p>500</p></td>
<td><p>100</p></td>
<td><p>650</p></td>
</tr>
<tr class="odd">
<td><p>Taxa de chat (por segundo) em todas as salas</p></td>
<td><p>55.56</p></td>
<td><p>18.52</p></td>
<td><p>0.03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>Modelo 2 - Iniciar com um número de mensagens publicadas por usuário/dia</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Taxa de chat por usuário/dia</p></td>
<td><p>15</p></td>
<td><p>5</p></td>
<td><p>0.1</p></td>
<td><p>cedido</p></td>
</tr>
<tr class="even">
<td><p>Taxa de chat por sala (por dia)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1,213</p></td>
</tr>
<tr class="odd">
<td><p>Taxa de chat (por segundo) em todas as salas</p></td>
<td><p>41.67</p></td>
<td><p>13.89</p></td>
<td><p>0.28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>Modelo de usuário de desempenho persistente do servidor de chat

A tabela a seguir descreve o modelo de usuário para o servidor de chat persistente. Ela fornece a base para requisitos de planejamento de capacidade e representa uma organização típica com 80.000 usuários simultâneos em quatro servidores.

### <a name="persistent-chat-server-performance-user-model"></a>Modelo de usuário de desempenho persistente do servidor de chat

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Número de usuários ativos conectados</p></td>
<td><p>80,000</p></td>
</tr>
<tr class="even">
<td><p>Número de instâncias de serviço do servidor de chat persistente</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>Tamanho de salas de chat pequenas</p></td>
<td><p>30 usuários</p></td>
</tr>
<tr class="even">
<td><p>Tamanho médio de salas de chat</p></td>
<td><p>150 usuários</p></td>
</tr>
<tr class="odd">
<td><p>Tamanho grande de salas de chat</p></td>
<td><p>16.000 usuários</p></td>
</tr>
<tr class="even">
<td><p>Número total de salas de chat</p></td>
<td><p>33,077</p></td>
</tr>
<tr class="odd">
<td><p>Número de salas de chat pequenas</p></td>
<td><p>32,000</p></td>
</tr>
<tr class="even">
<td><p>Número de salas de chat médias</p></td>
<td><p>1,067</p></td>
</tr>
<tr class="odd">
<td><p>Número de salas de chat grandes</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>Número total de salas de chat por usuário</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>Número de salas de chat pequenas por usuário</p></td>
<td><p>12</p></td>
</tr>
<tr class="even">
<td><p>Número de salas de chat médias por usuário</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>Número de salas de chat grandes por usuário</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Número de salas com ingresso por usuário</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>Taxa de pico de associação</p></td>
<td><p>10/segundo</p></td>
</tr>
<tr class="even">
<td><p>Taxa de chat total</p></td>
<td><p>24/segundo</p></td>
</tr>
<tr class="odd">
<td><p>Taxa de chat para pequenas salas de chat</p></td>
<td><p>22.22/second</p></td>
</tr>
<tr class="even">
<td><p>Taxa de chat para salas de chat médias</p></td>
<td><p>1.67/second</p></td>
</tr>
<tr class="odd">
<td><p>Taxa de chat para salas de chat grandes</p></td>
<td><p>~0.15/second</p></td>
</tr>
<tr class="even">
<td><p>Porcentagem de salas de chat configuradas para convites</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Porcentagem de participação direta em</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>Porcentagem de membros em grupo</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Número médio de afiliações ancestrais nos serviços de domínio Active Directory</p></td>
<td><p>100 - 200</p></td>
</tr>
<tr class="even">
<td><p>Número de contatos inscritos por usuário</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>Número médio de pontos de extremidade por usuário</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="even">
<td><p>Número médio de salas de chat visíveis por ponto de extremidade</p></td>
<td><p>1.5</p></td>
</tr>
<tr class="odd">
<td><p>Número médio de salas de chat visíveis por usuário</p></td>
<td><p>2,25 (50% para uma sala e 50% para duas salas); até seis salas abertas, uma por monitor</p></td>
</tr>
<tr class="even">
<td><p>Número de participantes sondados por intervalo</p></td>
<td><p>25 por sala de chat visível</p></td>
</tr>
<tr class="odd">
<td><p>Duração do intervalo de sondagem</p></td>
<td><p>5 minutos</p></td>
</tr>
<tr class="even">
<td><p>Número de participantes sondados por segundo</p></td>
<td><p>15,000</p></td>
</tr>
<tr class="odd">
<td><p>Número de alterações de presença por hora por usuário</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>Número de alterações de presença por segundo</p></td>
<td><p>133.33</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

