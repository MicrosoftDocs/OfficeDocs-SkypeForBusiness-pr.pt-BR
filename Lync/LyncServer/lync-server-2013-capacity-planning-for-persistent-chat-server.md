---
title: 'Lync Server 2013: planejamento de capacidade para servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0cd27f961d3b4857cf13d5786897bd29a657851
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Planejamento de capacidade para servidor de chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-05_

O servidor de chat persistente pode executar chat em tempo real de vários usuários que pode persistir em futuras recuperações e pesquisa. Ao contrário de mensagens instantâneas de grupo (IM) salvas na caixa de correio de um usuário, se o histórico de conversa estiver configurado, uma sessão de servidor de chat persistente permanecerá aberta e o conteúdo será salvo em um servidor, junto com as mensagens, arquivos, URLs e outros dados que fazem parte de um conversa em andamento.

O planejamento de capacidade é uma parte importante da preparação para implantar o servidor de chat persistente. Este tópico fornece detalhes sobre topologias de servidor de chat persistente compatíveis e tabelas de planejamento de capacidade que você pode usar para determinar a melhor configuração para sua implantação. Também descreve como gerenciar melhor as implantações de servidor de chat persistente que exigem mais capacidade em horários de pico.

Para baixar o servidor de chat persistente, consulte "Microsoft Lync Server 13 persistent chat Server [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539)" em.

Para obter detalhes sobre como instalar o servidor de chat persistente, consulte [instalando o servidor de chat persistente no Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) e [Configurando o servidor de chat persistente no Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) na documentação de implantação.

As ferramentas de suporte, como a ferramenta de planejamento do Lync Server, podem ajudá-lo ainda mais no planejamento da capacidade. Para obter detalhes sobre a ferramenta de planejamento, consulte [iniciando o processo de planejamento do Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) na documentação de planejamento.

<div>

## <a name="persistent-chat-server-supported-topologies"></a>Topologias compatíveis com o servidor de chat persistente

Você pode implantar o servidor de chat persistente em pools de servidor único ou de vários servidores, com uma topologia de pool único ou de vários pools.

Agora também há suporte para o servidor de chat persistente no servidor Standard Edition para novas implantações do Lync Server 2013. No entanto, o desempenho e a escala serão afetados, e como não há uma opção de alta disponibilidade para essa nova implantação, esperamos que você use isso principalmente para fins de verificação de conceito, avaliação e assim por diante.

<div>


> [!NOTE]  
> Para obter detalhes adicionais sobre ambas as topologias, consulte <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for persistent chat Server in Lync server 2013</A> , neste conjunto de documentação, e <A href="lync-server-2013-deploying-persistent-chat-server.md">implantando o servidor de chat persistente no Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="single-server-topology"></a>Topologia de servidor único

A configuração mínima e a implantação mais simples para o servidor de chat persistente é uma topologia de servidor front-end de servidor de chat persistente única. Esta implantação requer um único servidor que executa o servidor de chat persistente (que, opcionalmente, executa o serviço de conformidade, se a conformidade estiver habilitada), um servidor que hospeda o banco de dados do SQL Server e, se a conformidade for necessária, o banco de dados do SQL Server para armazenar o dados de conformidade.

<div>


> [!IMPORTANT]  
> Não é possível adicionar mais servidores a um pool de servidores de chat persistente iniciado como uma implantação de servidor único no construtor de topologias. É recomendável usar a topologia de pool de vários servidores, mesmo que você esteja usando um único servidor. Isso é possível para que você possa adicionar mais servidores posteriormente, se necessário. 


</div>

A figura a seguir mostra todos os componentes obrigatórios e opcionais de uma topologia para um único servidor de front-end do servidor de chat persistente com conformidade.

**Servidor de Chat Persistente único**

![Topologia de servidor único com serviço de conformidade](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologia de servidor único com serviço de conformidade")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologia de vários servidores

Para fornecer maior capacidade e confiabilidade, você pode implantar uma topologia de vários servidores, conforme descrito em [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). A topologia de vários servidores pode incluir até quatro computadores ativos que executam o servidor de chat persistente (as configurações de alta disponibilidade e recuperação de desastre permitirão até oito, mas apenas quatro podem estar ativas e as quatro restantes em espera). Cada servidor pode suportar até 20.000 usuários simultâneos, para um total de 80.000 usuários simultâneos conectados a um pool de servidores de chat persistente com quatro servidores. Uma topologia de vários servidores é o mesmo que a topologia de servidor único, exceto pelo fato de que vários servidores hospedam o servidor de chat persistente e podem ser dimensionados de forma mais alta. Vários computadores que executam o servidor de chat persistente devem residir no mesmo domínio de serviços de domínio do Active Directory do Lync Server e no serviço de conformidade.

A figura a seguir mostra todos os componentes de uma topologia de vários servidores com vários computadores que executam o servidor de chat persistente, o serviço de conformidade opcional e um banco de dados de conformidade separado.

**Vários Servidores de Chat Persistente**

![Topologia de vários servidores](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologia de vários servidores")

Em uma implantação de servidor de chat persistente de quatro servidores, em que 80.000 os usuários podem estar conectados simultaneamente e usando o chat persistente, a carga é distribuída igualmente em 20.000 usuários por servidor. Se um servidor ficar indisponível, os usuários que estiverem conectados a esse servidor perderão o acesso ao servidor de chat persistente. Os usuários desconectados serão automaticamente transferidos para os servidores restantes até que o servidor disponível seja restaurado. Dependendo da quantidade de tráfego de chat persistente na rede, essa transferência pode levar alguns minutos ou mais. Como cada um dos servidores restantes pode hospedar até 30.000 usuários, recomendamos que você restaure o servidor indisponível o mais rápido possível para evitar problemas de desempenho. Caso contrário, você pode tornar outro servidor de chat persistente disponível usando o construtor de topologias ou o cmdlet do Windows PowerShell, **set-CsPersistentChatActiveServer**.

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>Planejamento da capacidade do servidor de chat persistente

As tabelas a seguir podem ajudá-lo com o planejamento de capacidade para o servidor de chat persistente. Eles modelam como alterar várias configurações de servidor de chat persistente afetam os recursos de capacidade.

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>Planejar sua capacidade máxima para o servidor de chat persistente

Use a seguinte tabela de exemplo para determinar o número de usuários que você será capaz de suportar.

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>Exemplo de capacidade máxima do pool de servidores de chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Instâncias ativas do serviço de chat persistente</p></td>
<td><p><em>quatro</em></p></td>
</tr>
<tr class="even">
<td><p>Instâncias do serviço de chat persistente</p></td>
<td><p><em>8 (4 deve estar inativo; somente um máximo de 4 pode ser ativo)</em></p></td>
</tr>
<tr class="odd">
<td><p>Usuários ativos conectados</p></td>
<td><p><em>80.000</em></p></td>
</tr>
<tr class="even">
<td><p>Total de usuários provisionados</p></td>
<td><p>150.000</p></td>
</tr>
<tr class="odd">
<td><p>Número de pontos de extremidade</p></td>
<td><p>120.000</p></td>
</tr>
</tbody>
</table>


No exemplo anterior, o plano é suportar o número máximo de usuários que o servidor de chat persistente permite: quatro servidores/instâncias do serviço de chat persistente (pode ter quatro mais servidores passivos executando o servidor de chat persistente para alta disponibilidade e recuperação de desastres) e 20.000 usuários por servidor, para um total de 80.000 usuários ativos.

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>Planejamento de capacidade para gerenciar o acesso de salas de chat persistente

A tabela de exemplo a seguir pode ajudá-lo a planejar o gerenciamento do acesso à sala de chat persistente em um pool de servidor de chat persistente.

### <a name="managing-chat-room-access-sample"></a>Gerenciando o exemplo de acesso da sala de chat

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
<td><p>Tamanho de salas de chat (número de usuários conectados)</p></td>
<td><p>30 por sala</p></td>
<td><p>150 por sala</p></td>
<td><p>16.000 por sala</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salas de chat</p></td>
<td><p>32.000</p></td>
<td><p>1.067</p></td>
<td><p>10 </p></td>
<td><p>33.077</p></td>
</tr>
<tr class="odd">
<td><p>% de salas que são auditório</p></td>
<td><p>1</p></td>
<td><p>1</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>% de salas abertas</p></td>
<td><p>3D</p></td>
<td><p>3D</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salas abertas (sem Associação explícita)</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>0,5</p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>Salas não abertas (salas regulares com associação explícita)</p></td>
<td><p>31.040</p></td>
<td><p>1, 35</p></td>
<td><p>0,5</p></td>
<td><p>32.080</p></td>
</tr>
<tr class="odd">
<td><p>Salas do auditório (entrada de apresentadores adicionais)</p></td>
<td><p>,0</p></td>
<td><p>32</p></td>
<td><p>0,5</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salas gerenciadas por associação direta</p></td>
<td><p>50%</p></td>
<td><p>254</p></td>
<td><p>0%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salas gerenciados por grupos de usuários</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Grupos de usuários na lista de associação de cada sala de chat para salas abertas (não especificado explicitamente)</p></td>
<td><p>,0</p></td>
<td><p>,0</p></td>
<td><p>,0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuários na lista de associação de cada sala de chat para salas não abertas</p></td>
<td><p>até</p></td>
<td><p>150</p></td>
<td><p>16.000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Grupos de usuários na lista de associação de cada sala de chat para salas não abertas</p></td>
<td><p>3D</p></td>
<td><p>0,5</p></td>
<td><p>10 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuários e grupos de usuários na lista de gerentes de cada sala de chat (para salas abertas e não abertas)</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Usuários e grupos de usuários em cada lista de apresentadores da sala de chat do auditório (para salas abertas e não abertas)</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entidades de associação com base no usuário em todas as salas não abertas</p></td>
<td><p>465.600</p></td>
<td><p>15.520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entidades de associação com base em grupo de usuário em todas as salas não abertas</p></td>
<td><p>46.560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entidades de usuários e grupos de usuários em todas as salas de chat do auditório</p></td>
<td><p>,0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entidades de usuários e grupos de usuários com base em todas as listas de gerentes de salas de chat</p></td>
<td><p>192.000</p></td>
<td><p>6.400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuários ativos por sala de chat</p></td>
<td><p><em>até</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16.000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salas de chat por usuário</p></td>
<td><p><em>3,6</em></p></td>
<td><p><em>duas</em></p></td>
<td><p><em>duas</em></p></td>
<td><p><em>dezesseis</em></p></td>
</tr>
<tr class="odd">
<td><p>Grupos de usuário na lista de membros de cada sala de chat</p></td>
<td><p><em>254</em></p></td>
<td><p><em>254</em></p></td>
<td><p><em>15</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Salas gerenciados por grupos de usuários</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entidades de participação baseadas em grupos de usuário em todas as salas de chat</p></td>
<td><p>155.200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entidades de participação baseadas em usuários em todas as salas de chat</p></td>
<td><p>465.600</p></td>
<td><p>77.600</p></td>
<td><p>72.000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Usuários e grupos de usuários no gerenciador de cada sala de chat, apresentador e listas de escopo</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Usuários e grupos de usuários em todas as listas de escopos, apresentador e Gerenciador de salas de chat</p></td>
<td><p>192.000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entradas de controle de acesso</p></td>
<td><p>704.160</p></td>
<td><p>26.768</p></td>
<td><p>160</p></td>
<td><p>731.088</p></td>
</tr>
<tr class="even">
<td><p>Entradas de controle de máximo acesso</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2 milhões</p></td>
</tr>
</tbody>
</table>


No exemplo anterior, quando você implanta os servidores de chat persistente de acordo com as diretrizes recomendadas, eles podem lidar com até 80.000 usuários ativos em um pool de quatro servidores com conformidade habilitada.

Este exemplo mostra as salas de chat categorizadas como pequenas (30 usuários ativos a qualquer momento), média (150 usuários ativos) e grandes (16.000 usuários ativos). O número de salas de chat de um determinado tamanho é calculado com base no número total de:

  - Usuários ativos no sistema

  - Usuários ativos em salas de chat de determinado tamanho

  - Salas de chat de um tamanho determinado onde ingressa um único usuário

Para cada sala de chat, a tabela de planejamento de capacidade anterior especifica o número de entradas de controle de acesso associadas à sala de chat, incluindo entradas atribuídas diretamente à sala de chat. Você pode controlar o acesso a salas de chat individuais usando listas de controle de acesso (ACLs). Você também pode controlar o acesso no nível de categoria. Em uma ACL, uma entrada de controle de acesso individual pode ser um grupo de usuários — por exemplo, um grupo de segurança, uma lista de distribuição ou um único usuário. Você pode definir as entradas de controle de acesso aos membros, aos apresentadores e aos gerentes de sala de chat.

<div>


> [!IMPORTANT]  
> Ao planejar sua estratégia de gerenciamento de salas de chat, tenha em mente que o número total de entradas de controle de acesso permitido é 2 milhões. Se as entradas de controle de acesso calculadas excederem 2 milhões, o desempenho do servidor pode degradar significativamente. Para evitar esse problema, sempre que possível, certifique-se de que suas entradas de controle de acesso sejam grupos de usuários, em vez de usuários individuais.



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>Planejamento de capacidade para gerenciar o acesso de sala de chat por convite

Você pode usar a seguinte tabela de planejamento de capacidade para entender o número de convites que o servidor de chat persistente cria e armazena no banco de dados de chat persistente quando ele é configurado para enviar convites. Você gerencia convites na categoria usando a página **configurações de categoria de sala de chat** no painel de controle do Lync Server ou usando o cmdlet do Windows PowerShell, **set-csPersistentChatCategory**. Você pode gerenciar convites em uma sala de chat (em linha com o que a categoria permite) usando a página de **Gerenciamento de sala** iniciada pelo cliente do Lync ou usando um cmdlet do Windows PowerShell, **set-csPersistentChatRoom**.

Os dados de exemplo na tabela a seguir pressupõem que, na página de **configurações de sala de chat** de 50% de todas as salas de chat, a opção de **convites** está definida como **Sim**.

<div>


> [!IMPORTANT]  
> Se o valor calculado para o número de convites gerados pelo servidor exceder 1 milhão, o desempenho do servidor pode degradar significativamente. Para evitar esse problema, certifique-se de minimizar o número de salas de chat que estão configuradas para enviar convites ou restringir o número de usuários que podem participar de salas de chat que foram configuradas para enviar convites.



</div>

### <a name="chat-room-access-by-invitation-sample"></a>Acesso à sala de chat por amostra de convite

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
<td><p>Porcentagem de salas que têm convites</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Salas de chat configuradas para enviar convites</p></td>
<td><p><em>16.000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>0,5</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Usuários que podem acessar a sala de chat</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16.000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Convites gerados pelo servidor de chat persistente</p></td>
<td><p>960.000</p></td>
<td><p>120.000</p></td>
<td><p>80.000</p></td>
<td><p>1.160.000</p></td>
</tr>
<tr class="even">
<td><p>Número de convites máximo permitido</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2 milhões</p></td>
</tr>
<tr class="odd">
<td><p>Modelo 1-iniciar com o número esperado de mensagens por sala por dia</p></td>
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
<td><p>55,56</p></td>
<td><p>18,52</p></td>
<td><p>0, 3</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>Modelo 2-iniciar com o número de mensagens postadas por usuário por dia</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Taxa de chat por usuário por dia</p></td>
<td><p>15 </p></td>
<td><p>0,5</p></td>
<td><p>0,1</p></td>
<td><p>508</p></td>
</tr>
<tr class="even">
<td><p>Taxa de chat por sala (por dia)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1.213</p></td>
</tr>
<tr class="odd">
<td><p>Taxa de chat (por segundo) em todas as salas</p></td>
<td><p>41,67</p></td>
<td><p>13,89</p></td>
<td><p>0,28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>Modelo de usuário de desempenho do servidor de chat persistente

A tabela a seguir descreve o modelo de usuário para o servidor de chat persistente. Ele fornece a base para os requisitos de planejamento de capacidade e representa uma organização típica com 80.000 usuários simultâneos em quatro servidores.

### <a name="persistent-chat-server-performance-user-model"></a>Modelo de usuário de desempenho do servidor de chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Número de usuários ativos conectados</p></td>
<td><p>80.000</p></td>
</tr>
<tr class="even">
<td><p>Número de instâncias do serviço do servidor de chat persistente</p></td>
<td><p>quatro</p></td>
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
<td><p>33.077</p></td>
</tr>
<tr class="odd">
<td><p>Número de salas de chat pequenas</p></td>
<td><p>32.000</p></td>
</tr>
<tr class="even">
<td><p>Número de salas de chat médias</p></td>
<td><p>1.067</p></td>
</tr>
<tr class="odd">
<td><p>Número de salas de chat grandes</p></td>
<td><p>10 </p></td>
</tr>
<tr class="even">
<td><p>Número total de salas de chat por usuário</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>Número de salas de chat pequenas por usuário</p></td>
<td><p>12</p></td>
</tr>
<tr class="even">
<td><p>Número de salas de chat médias por usuário</p></td>
<td><p>duas</p></td>
</tr>
<tr class="odd">
<td><p>Número de salas de chat grandes por usuário</p></td>
<td><p>duas</p></td>
</tr>
<tr class="even">
<td><p>Número de salas Unidas por usuário</p></td>
<td><p>dia</p></td>
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
<td><p>22.22/segundo</p></td>
</tr>
<tr class="even">
<td><p>Taxa de chat para salas de chat médias</p></td>
<td><p>1.67/segundo</p></td>
</tr>
<tr class="odd">
<td><p>Taxa de chat para salas de chat grandes</p></td>
<td><p>~ 0,15/segundo</p></td>
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
<td><p>Número médio de afiliações ancestrais nos serviços de domínio do Active Directory</p></td>
<td><p>100 - 200</p></td>
</tr>
<tr class="even">
<td><p>Número de contatos inscritos por usuário</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>Número médio de pontos de extremidade por usuário</p></td>
<td><p>1,5</p></td>
</tr>
<tr class="even">
<td><p>Número médio de salas de chat visíveis por ponto de extremidade</p></td>
<td><p>1,5</p></td>
</tr>
<tr class="odd">
<td><p>Número médio de salas de chat visíveis por usuário</p></td>
<td><p>2,25 (50% por 1 sala e 50% para 2 salas); Até seis salas abertas, uma por monitor</p></td>
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
<td><p>15.000</p></td>
</tr>
<tr class="odd">
<td><p>Número de alterações de presença por hora por usuário</p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>Número de alterações de presença por segundo</p></td>
<td><p>133,33</p></td>
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

