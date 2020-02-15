---
title: 'Lync Server 2013: visão geral do aplicativo grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d63f13442588a84039fee6e1147a9c29e821e14a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Visão geral do aplicativo grupo de resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-11_

Quando um chamador chama um grupo de resposta, a chamada é roteada para um agente com base em um grupo de busca ou mas respostas do chamador para as perguntas de IVR (resposta de voz interativa). O aplicativo grupo de resposta usa métodos de roteamento de grupo de resposta padrão para rotear a chamada para o próximo agente disponível. Os métodos de roteamento de chamada incluem serial, ocioso por mais tempo, paralelo, round robin, e encaminhamento de Atendente (ou seja, todos os agentes são chamados ao mesmo tempo a cada chamada de entrada, independentemente de sua presença atual). Se não houverem agentes disponíveis, a chamada será mantida em uma fila até que um agente esteja disponível. Enquanto está na fila, o chamador ouve música até um agente disponível aceitar a chamada. Se a fila estiver cheia ou se a chamada expirar enquanto estiver na fila, o chamador poderá ouvir uma mensagem e está desconectado ou transferido para um destino diferente. Quando um agente aceita a chamada, o chamador pode ou não ser capaz de ver a identidade do agente, dependendo de como o administrador configura o grupo de resposta. Os agentes podem ser formais, o que significa que eles devem entrar no grupo antes de aceitar chamadas encaminhadas para o grupo, ou informais, que significa que eles não precisam entrar no grupo para aceitar chamadas.

<div>


> [!NOTE]  
> Apenas os usuários locais podem ser operadores. Se um operador for movido de local para online, a chamada do grupo de resposta não será mais roteada para ele.



</div>

<div>


> [!NOTE]  
> O aplicativo grupo de resposta usa um serviço interno, chamado fazer correspondência, para enfileirar chamadas e localizar agentes disponíveis. Cada computador que executa o aplicativo grupo de resposta executa o serviço de correspondência, mas apenas um serviço de correspondência por pool do Lync Server está ativo por vez – os outros são passivos. Se o serviço Correspondência ativo ficar indisponível durante uma paralisação não planejada, um dos serviços Correspondência passivos ficará ativo. O aplicativo grupo de resposta faz o melhor para garantir que o roteamento de chamadas e o enfileiramento continuem sem interrupção. No entanto, quando ocorre uma transição do serviço Correspondência, todas as chamadas em transferência no momento são perdidas. Por exemplo, se a transição for devido ao servidor de front-end ser desativado, todas as chamadas que estão sendo tratadas no momento pela correspondência ativa, fazendo o serviço nesse servidor de front-end também serão perdidas.



</div>

No Lync Server 2013, duas funções de gerenciamento estão disponíveis para gerenciar grupos de resposta: gerente de grupo de resposta e administrador de grupo de resposta. Os administradores do grupo de resposta podem gerenciar qualquer aspecto de qualquer grupo de resposta. Os gerentes do grupo de resposta podem gerenciar apenas determinados aspectos e apenas os grupos de resposta que eles possuem. A nova função de gerente pode ajudar a reduzir os custos de administração, pois você pode delegar responsabilidades limitadas para grupos de resposta específicos para qualquer usuário habilitado para o Enterprise Voice.

Para acomodar a nova função gerente, o aplicativo de grupo de resposta do Lync Server 2013 introduz um **tipo de fluxo de trabalho** gerenciado ou não gerenciado. A tabela a seguir descreve os grupos de respostas Gerenciado ou Não gerenciado.

### <a name="managed-and-unmanaged-response-groups"></a>Grupos de respostas Gerenciado ou Não gerenciado

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de grupo de respostas</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Não gerenciados</p></td>
<td><ul>
<li><p>Os grupos de respostas não gerenciados não têm gerentes atribuídos. Somente o administrador do grupo de resposta pode configurar esses grupos de resposta.</p></li>
<li><p>Vários grupos de respostas não gerenciados podem compartilhar uma fila ou grupo de agentes.</p></li>
<li><p>Ao migrar grupos de resposta de uma versão anterior para o Lync Server 2013, o tipo é definido como não gerenciado.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Gerenciados</p></td>
<td><ul>
<li><p>Os administradores do grupo de resposta podem configurar qualquer aspecto de grupos de respostas gerenciados.</p></li>
<li><p>Os gerentes do grupo de resposta não podem exibir nem modificar grupos de respostas que não sejam explicitamente atribuídos a eles.</p></li>
<li><p>Os gerentes do grupo de resposta podem definir apenas algumas configurações dos grupos de resposta atribuídos explicitamente a eles.</p></li>
<li><p>Os grupos de respostas gerenciados não podem compartilhas filas nem grupos de agentes com outros grupos de respostas, sejam gerenciados ou não gerenciados.</p></li>
</ul></td>
</tr>
</tbody>
</table>


A tabela a seguir descreve as ações que os gerentes de grupo de resposta podem ou não executar para os grupos de resposta atribuídos a eles.

### <a name="response-group-manager-capabilities"></a>Recursos do gerente do grupo de respostas

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
<th>Conseguir</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>SNMP</p></li>
<li><p>Mensagem de boas-vindas</p></li>
<li><p>Nome do grupo de resposta</p></li>
<li><p>Descrição</p></li>
<li><p>Número de exibição</p></li>
<li><p>Horário comercial</p></li>
<li><p>Música de espera</p></li>
<li><p>Status (ativo/inativo)</p></li>
<li><p>Fluxos de trabalho de grupo de busca ou fluxos de trabalho de IVR (reposta interativa de voz)</p></li>
</ul></td>
<td><ul>
<li><p>Grupos de agentes</p></li>
<li><p>Filas</p></li>
<li><p>Conjuntos de feriados</p></li>
</ul></td>
<td><ul>
<li><p>Criar ou excluir qualquer tipo de fluxo de trabalho</p></li>
<li><p>Modificar configurações centrais do grupo de respostas, como: <strong>URI do SIP</strong>, <strong>Número de Telefone</strong> ou <strong>Tipo de Fluxo de Trabalho</strong>.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Os gerentes do grupo de resposta podem usar as ferramentas a seguir para gerenciar os grupos de resposta designados.

  - Painel de controle do Lync Server
    
    <div>
    

    > [!NOTE]  
    > Os gerentes do grupo de resposta podem gerenciar apenas as configurações do grupo de resposta com essa ferramenta. Outras configurações do Lync Server não estão disponíveis para gerentes.

    
    </div>

  - Ferramenta de configuração do grupo de resposta

  - Shell de Gerenciamento do Lync Server

O grupo de resposta é dimensionado bem para ambientes de departamento ou de grupo de trabalho (para obter detalhes, consulte [planejamento de capacidade para grupo de resposta no Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) e pode ser implantado em instalações de telefonia totalmente novas. Ele oferece suporte a chamadas de entrada da implantação do Enterprise Voice e da rede da operadora local. Os agentes podem usar o Lync 2013, o Lync 2010, o Lync 2010 Attendant ou o Lync Phone Edition para fazer as chamadas roteadas para eles.

O aplicativo grupo de resposta é um componente do Enterprise Voice. Quando você implanta o Enterprise Voice, o aplicativo grupo de resposta é instalado e ativado automaticamente.

</div>

<span> </span>

</div>

</div>

</div>

