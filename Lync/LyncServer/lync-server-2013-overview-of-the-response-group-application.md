---
title: 'Lync Server 2013: visão geral do aplicativo grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b523a05509b0043effb8cb2b761d7ee06fd36751
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Visão geral do aplicativo grupo de resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-11_

Quando um chamador chama um grupo de resposta, a chamada é roteada para um agente com base em um grupo de busca ou nas respostas do chamador às perguntas de IVR (resposta de voz interativa). O aplicativo grupo de resposta usa métodos de roteamento de grupo de resposta padrão para direcionar a chamada para o próximo agente disponível. Os métodos de roteamento de chamadas incluem serial, Idle mais longo, paralelo, rodízio e roteamento de atendedor (ou seja, todos os agentes são chamados ao mesmo tempo para cada chamada de entrada, independentemente da presença atual). Se nenhum agente estiver disponível, a chamada será mantida em uma fila até que um agente esteja disponível. Enquanto estiver na fila, o chamador ouvirá música até que um agente disponível aceite a chamada. Se a fila estiver cheia ou se a chamada expirar durante a fila, o chamador pode ouvir uma mensagem e, em seguida, desconectado ou transferido para um destino diferente. Quando um agente aceita a chamada, o chamador pode ou não ver a identidade do agente, dependendo de como o administrador configura o grupo de resposta. Os agentes podem ser formais, o que significa que devem entrar no grupo antes de aceitarem chamadas encaminhadas para o grupo, ou informal, o que significa que eles não entram e saem do grupo para aceitar chamadas.

<div>


> [!NOTE]  
> Somente os usuários no local podem ser agentes. Se um agente for movido do local para o online, as chamadas em grupo de resposta não serão roteadas para esse agente.



</div>

<div>


> [!NOTE]  
> O aplicativo grupo de resposta usa um serviço interno, chamado fazer correspondência, para enfileirar chamadas e localizar agentes disponíveis. Cada computador que executa o aplicativo do grupo de resposta executa o serviço fazer correspondência, mas apenas um serviço de correspondência por pool do Lync Server fica ativo por vez--os outros são passivos. Se a correspondência ativa que faz o serviço ficar indisponível durante uma interrupção não planejada, um dos serviços de correspondência passiva será ativado. O aplicativo grupo de resposta faz o melhor possível para garantir que o encaminhamento de chamadas e o enfileiramento continuem ininterruptos. No entanto, quando ocorre uma correspondência fazendo a transição do serviço, todas as chamadas que estão sendo transferidas no momento são perdidas. Por exemplo, se a transição for devida ao servidor de front-end, todas as chamadas atualmente manipuladas pela correspondência ativa que está fazendo o serviço nesse servidor front-end também serão perdidas.



</div>

No Lync Server 2013, duas funções de gerenciamento estão disponíveis para o gerenciamento de grupos de resposta: gerente de grupo de resposta e administrador de grupo de resposta. Os administradores de grupo de resposta podem gerenciar qualquer aspecto de qualquer grupo de resposta. Os gerentes de grupo de resposta podem gerenciar apenas determinados aspectos e somente para os grupos de resposta que eles possuem. A nova função gerente pode ajudar a reduzir os custos de administração, pois você pode delegar responsabilidades limitadas para grupos de resposta específicos para qualquer usuário habilitado para o Enterprise Voice.

Para acomodar a nova função gerente, o aplicativo do grupo de resposta do Lync Server 2013 introduz um **tipo de fluxo de trabalho** gerenciado ou não gerenciado. A tabela a seguir descreve os grupos de resposta gerenciados e não gerenciados.

### <a name="managed-and-unmanaged-response-groups"></a>Grupos de resposta gerenciados e não gerenciados

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de grupo de resposta</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Não gerenciado</p></td>
<td><ul>
<li><p>Os grupos de resposta não gerenciados não têm gerentes atribuídos. Somente o administrador do grupo de resposta pode configurar esses grupos de resposta.</p></li>
<li><p>Vários grupos de resposta não gerenciados podem compartilhar uma fila ou um grupo de agente.</p></li>
<li><p>Quando você migra grupos de resposta de uma versão anterior para o Lync Server 2013, o tipo é definido como não gerenciado.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Gerenciado</p></td>
<td><ul>
<li><p>Os administradores de grupo de resposta podem configurar qualquer aspecto de grupos de resposta gerenciado.</p></li>
<li><p>Os gerentes de grupo de resposta não podem exibir ou modificar os grupos de resposta que não foram atribuídos explicitamente a eles.</p></li>
<li><p>Os gerentes de grupo de resposta podem configurar apenas algumas configurações para os grupos de resposta atribuídos explicitamente a eles.</p></li>
<li><p>Grupos de resposta gerenciada não podem compartilhar filas ou grupos de agente com qualquer outro grupo de resposta, gerenciado ou não gerenciado.</p></li>
</ul></td>
</tr>
</tbody>
</table>


A tabela a seguir descreve as ações que os gerentes de grupo de resposta podem e não podem realizar para os grupos de resposta atribuídos a eles.

### <a name="response-group-manager-capabilities"></a>Funcionalidades do Gerenciador de grupo de resposta

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Pode configurar:</th>
<th>Pode criar, excluir ou configurar:</th>
<th>Consegue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>Agentes</p></li>
<li><p>Mensagem de boas-vindas</p></li>
<li><p>Nome do grupo de resposta</p></li>
<li><p>Descrição</p></li>
<li><p>Número para exibição</p></li>
<li><p>Horário comercial</p></li>
<li><p>Música de espera</p></li>
<li><p>Status (ativo/inativo)</p></li>
<li><p>Fluxos de trabalho de grupo de busca ou de reação de voz interativa (IVR)</p></li>
</ul></td>
<td><ul>
<li><p>Grupos de agente</p></li>
<li><p>Filas</p></li>
<li><p>Conjuntos de feriados</p></li>
</ul></td>
<td><ul>
<li><p>Criar ou excluir qualquer tipo de fluxo de trabalho</p></li>
<li><p>Modifique as configurações do grupo de respostas principais, como: <strong>URI SIP</strong>, <strong>número de telefone</strong>ou <strong>tipo de fluxo de trabalho</strong>.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Os gerentes de grupo de resposta podem usar as seguintes ferramentas para gerenciar os grupos de resposta designados.

  - Painel de Controle do Lync Server
    
    <div>
    

    > [!NOTE]  
    > Os gerentes de grupo de resposta só podem gerenciar as configurações de grupo de resposta com essa ferramenta. Outras configurações do Lync Server não estão disponíveis para gerentes.

    
    </div>

  - Ferramenta de Configuração de Grupo de Resposta

  - Shell de Gerenciamento do Lync Server

Grupo de resposta dimensionável bem para ambientes de departamento ou de grupo de trabalho (para obter detalhes, consulte [planejamento de capacidade para o grupo de resposta no Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) e pode ser implantado em instalações de telefonia totalmente novas. Ele é compatível com chamadas de implantação do Enterprise Voice e da rede da operadora local. Os agentes podem usar o Lync 2013, o Lync 2010, o Lync 2010 Attendant ou o Lync Phone Edition para fazer as chamadas serem roteadas para eles.

O aplicativo grupo de resposta é um componente do Enterprise Voice. Ao implantar o Enterprise Voice, o aplicativo grupo de resposta é instalado e ativado automaticamente.

</div>

<span> </span>

</div>

</div>

</div>

