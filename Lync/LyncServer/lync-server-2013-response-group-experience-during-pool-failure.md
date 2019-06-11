---
title: 'Lync Server 2013: Experiência do grupo de resposta durante falha no pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90911bebc7c3e60847f5b3fcb8f69523697af0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a>Experiência do grupo de resposta no Lync Server 2013 durante falha no pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-30_

Esta seção descreve detalhadamente como a atividade do grupo de resposta é afetada nos seguintes estágios:

  - Ocorre uma paralisação no pool primário, mas o failover ainda não foi iniciado.

  - O serviço falha no pool de backup.

  - O serviço de volta ao pool primário.

<div>

## <a name="user-experience-when-outage-occurs"></a>Experiência do usuário quando ocorre uma falha

Quando ocorre uma falha de pool ou site, mas o administrador ainda não iniciou o failover, a atividade do grupo de resposta é manipulada conforme descrito na tabela a seguir.

<div>


> [!NOTE]  
> Durante a recuperação de desastres, as chamadas se comportam de forma diferente dependendo se os grupos de resposta do pool primário foram importados para o pool de backup durante a recuperação Na tabela a seguir, as referências a grupos de resposta importados significam que os grupos de resposta de pool primário foram importados para o pool de backup durante o modo de recuperação de desastre.



</div>

### <a name="outage-occurs"></a>Ocorre uma falha

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de ação do usuário ou chamada</th>
<th>Durante a interrupção</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas conectadas a um agente</p></td>
<td><ul>
<li><p>As chamadas normais permanecem conectadas.</p></li>
<li><p>As chamadas anônimas são desconectadas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chamadas em andamento ainda não conectadas a um agente</p></td>
<td><p>As chamadas são desconectadas.</p></td>
</tr>
<tr class="odd">
<td><p>Novas chamadas</p></td>
<td><ul>
<li><p>As chamadas são desconectadas.</p></li>
<li><p>Se os grupos de resposta foram importados, as chamadas conectam-se ao pool de backup, mas os agentes hospedados no pool primário são inacessíveis.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chamadas de agente em nome do grupo de resposta</p></td>
<td><p>O recurso está desativado durante este estágio.</p></td>
</tr>
<tr class="odd">
<td><p>Informações de entrada e agente do agente</p></td>
<td><ul>
<li><p>Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente, mas os agentes não podem entrar.</p></li>
<li><p>Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</p></li>
<li><p>Os grupos de agente importados não são exibidos no console do agente.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuração do grupo de resposta</p></td>
<td><ul>
<li><p>Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</p></li>
<li><p>Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</p></li>
<li><p>Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a>Experiência do usuário durante o failover

Quando um administrador invoca o failover para um pool de backup, a atividade do grupo de resposta é manipulada durante e após o failover conforme descrito na tabela a seguir. A primeira coluna descreve o tipo de atividade que pode estar ocorrendo. A coluna do meio descreve como cada atividade é manipulada durante o tempo curto necessário para failover para o pool de backup. A última coluna descreve como a atividade é manipulada pela duração, após o término do processo de failover e o pool de backup se posicionar para o pool primário.

<div>


> [!NOTE]  
> Durante a recuperação de desastres, as chamadas se comportam de forma diferente dependendo se os grupos de resposta do pool primário foram importados para o pool de backup durante a recuperação Na tabela a seguir, as referências a grupos de resposta importados significam que os grupos de resposta de pool primário foram importados para o pool de backup durante o modo de recuperação de desastre.



</div>

### <a name="failover-is-initiated"></a>O failover é iniciado

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de ação do usuário ou chamada</th>
<th>Durante o failover</th>
<th>Após a conclusão do failover</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas conectadas a um agente</p></td>
<td><ul>
<li><p>As chamadas normais permanecem conectadas.</p></li>
<li><p>As chamadas anônimas são desconectadas.</p></li>
</ul></td>
<td><ul>
<li><p>As chamadas normais permanecem conectadas.</p></li>
<li><p>Para grupos de resposta importados, chamadas anônimas que atingiram o pool de backup permanecerão conectadas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chamadas em andamento ainda não conectadas a um agente</p></td>
<td><p>As chamadas são desconectadas.</p></td>
<td><ul>
<li><p>Se os grupos de resposta não foram importados, nenhuma chamada está nesse status.</p></li>
<li><p>Para os grupos de resposta importados, as chamadas que atingiram o pool de backup permanecerão conectadas.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Novas chamadas</p></td>
<td><ul>
<li><p>As chamadas são desconectadas.</p></li>
<li><p>Para grupos de resposta importados, chamadas conectam-se ao pool de backup, mas os agentes hospedados no pool primário não são acessíveis.</p></li>
</ul></td>
<td><ul>
<li><p>Se os grupos de resposta não foram importados, as chamadas serão desconectadas.</p></li>
<li><p>Para grupos de resposta importados, chamadas conectam-se ao pool de backup.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chamadas de agente em nome do grupo de resposta</p></td>
<td><p>O recurso está desativado durante este estágio</p></td>
<td><ul>
<li><p>Se os grupos de resposta não foram importados, as chamadas falharão.</p></li>
<li><p>Para os grupos de resposta importados, as chamadas são bem-sucedidas.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Informações de entrada e agente do agente</p></td>
<td><ul>
<li><p>Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente, mas os agentes não podem entrar.</p></li>
<li><p>Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</p></li>
<li><p>Grupos de agente importados são exibidos no console do agente e os agentes podem entrar.</p></li>
</ul></td>
<td><ul>
<li><p>Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente, mas os agentes não podem entrar.</p></li>
<li><p>Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</p></li>
<li><p>Grupos de agente importados são exibidos no console do agente e os agentes podem entrar.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuração do grupo de resposta</p></td>
<td><ul>
<li><p>Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</p></li>
<li><p>Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</p></li>
<li><p>Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</p></li>
</ul></td>
<td><ul>
<li><p>Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end, mas não podem ser modificados.</p></li>
<li><p>Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</p></li>
<li><p>Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a>Experiência do usuário durante o failback

Quando um administrador invoca o failback para o pool primário, a atividade do grupo de resposta é manipulada durante e após o failback, conforme descrito na tabela a seguir.

<div>


> [!NOTE]  
> Durante a recuperação de desastres, as chamadas se comportam de forma diferente dependendo se os grupos de resposta do pool primário foram importados para o pool de backup durante a recuperação Na tabela a seguir, as referências a grupos de resposta importados significam que os grupos de resposta de pool primário foram importados para o pool de backup durante o modo de recuperação de desastre.



</div>

### <a name="call-handling-in-failback"></a>Tratamento de chamadas em failback

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de ação do usuário ou chamada</th>
<th>Durante o failback</th>
<th>Após a conclusão do failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas conectadas a um agente</p></td>
<td><ul>
<li><p>As chamadas normais permanecem conectadas.</p></li>
<li><p>Se os grupos de resposta não foram importados, não há chamadas anônimas nesse status.</p></li>
<li><p>Para grupos de resposta importados, as chamadas anônimas permanecem conectadas.</p></li>
</ul></td>
<td><ul>
<li><p>As chamadas normais permanecem conectadas.</p></li>
<li><p>Se os grupos de resposta não foram importados, não há chamadas anônimas nesse status.</p></li>
<li><p>Para grupos de resposta importados, as chamadas anônimas permanecem conectadas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chamadas em andamento ainda não conectadas a um agente</p></td>
<td><ul>
<li><p>Se os grupos de resposta não foram importados, nenhuma chamada está nesse status.</p></li>
<li><p>Para os grupos de resposta importados, as chamadas serão desconectadas.</p></li>
</ul></td>
<td><ul>
<li><p>Se os grupos de resposta não foram importados, nenhuma chamada está nesse status.</p></li>
<li><p>Para os grupos de resposta importados, as chamadas serão desconectadas.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Novas chamadas</p></td>
<td><p>Chamadas conectadas ao pool primário, mas os agentes hospedados no pool primário não são acessíveis.</p></td>
<td><p>Chamadas conectadas ao pool primário.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas de agente em nome do grupo de resposta</p></td>
<td><p>O recurso está desativado durante este estágio.</p></td>
<td><p>Chamadas com êxito.</p></td>
</tr>
<tr class="odd">
<td><p>Informações de entrada e agente do agente</p></td>
<td><ul>
<li><p>Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente, mas os agentes não podem entrar.</p></li>
<li><p>Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</p></li>
<li><p>Grupos de agente importados são exibidos no console do agente e os agentes podem entrar.</p></li>
</ul></td>
<td><ul>
<li><p>Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente e os agentes podem entrar.</p></li>
<li><p>Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</p></li>
<li><p>Os grupos de agente importados não são exibidos no console do agente.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuração do grupo de resposta</p></td>
<td><ul>
<li><p>Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</p></li>
<li><p>Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</p></li>
<li><p>Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</p></li>
</ul></td>
<td><ul>
<li><p>Os grupos de resposta pertencentes ao pool primário podem ser exibidos e modificados.</p></li>
<li><p>Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</p></li>
<li><p>Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

