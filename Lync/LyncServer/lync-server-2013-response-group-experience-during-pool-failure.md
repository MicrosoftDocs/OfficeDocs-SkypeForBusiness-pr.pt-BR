---
title: Lync Server 2013 experiência do grupo de resposta durante falha do pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2beb0a914fe5a2880926872ed1cab365fac988f0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a>Experiência do grupo de resposta no Lync Server 2013 durante falha do pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-30_

Essa seção descreve em detalhes como a atividade do grupo de resposta é afetada nos seguintes estágios:

  - Uma interrupção ocorre no pool primário, mas o failover ainda não foi iniciado.

  - O serviço realizou um failover ao pool de backup.

  - O serviço realizou um failback ao pool primário.

<div>

## <a name="user-experience-when-outage-occurs"></a>Experiência do usuário quando ocorre interrupção

Quando ocorre uma interrupção de um pool ou site, mas o administrador ainda não iniciou o failover, a atividade do grupo de resposta é manipulada como descrito na seguinte tabela.

<div>


> [!NOTE]  
> Durante a recuperação de desastre, as chamadas se comportam de forma diferente se os grupos de resposta do pool primário forem importados ao pool de backup durante a recuperação. Na tabela seguinte, as referências aos grupos de resposta importados significam que os grupos de resposta do pool primário foram importados ao pool de backup durante o modo de recuperação de desastre.



</div>

### <a name="outage-occurs"></a>Ocorre a interrupção

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de chamada ou ação do usuário</th>
<th>Durante a interrupção</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas conectadas ao agente</p></td>
<td><ul>
<li><p>Chamadas normais permanecem conectadas.</p></li>
<li><p>Chamadas anônimas são desconectadas.</p></li>
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
<li><p>Se um grupo de resposta for importado, as chamadas serão conectadas ao pool de backup, mas os agentes hospedados no pool primário serão inacessíveis.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Os agente fazem chamadas em nome do grupo de resposta</p></td>
<td><p>O recurso é desabilitado durante esse estágio.</p></td>
</tr>
<tr class="odd">
<td><p>Entrada do agente e informações do agente</p></td>
<td><ul>
<li><p>Os grupos de agente pertencentes ao pool primário podem ser exibidos no console do agente, mas os agentes não podem entrar.</p></li>
<li><p>Os grupos de agentes pertencentes ao pool de backup podem ser exibido no console do agente e os agentes podem entrar.</p></li>
<li><p>Os grupos de agentes importados não são exibidos no console do agente.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuração do grupo de resposta</p></td>
<td><ul>
<li><p>Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</p></li>
<li><p>Os grupos de respostas pertencentes ao pool de backup podem ser exibidos e modificados.</p></li>
<li><p>Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a>Experiência do usuário durante o failover

Quando um administrador chama um failover para um pool de backup, a atividade do grupo de resposta é manipulada durante e depois do failover, conforme descrito na tabela seguinte. A primeira coluna descreve o tipo de atividade que pode estar ocorrendo. A coluna do meio descreve como cada atividade é manipulada durante o breve período necessário para enviar o failover ao pool de backup. A última coluna descreve como a atividade é manipulada durante todo o período, após o processo de failover ser concluído e o pool de backup estar disponível para o pool primário.

<div>


> [!NOTE]  
> Durante a recuperação de desastre, as chamadas se comportam de maneiras diferentes se os grupos de respostas do pool primário forem importados ao pool de backup durante a recuperação. Na seguinte tabela, as referências aos grupos de resposta importados significam que os grupos de respostas do pool primário foram importados ao pool de backup durante o modo de recuperação de desastre.



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
<th>Tipo de chamada ou ação do usuário</th>
<th>Durante o failover</th>
<th>Após a conclusão do failover</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas conectadas a um agente</p></td>
<td><ul>
<li><p>Chamadas normais permanecem conectadas.</p></li>
<li><p>Chamadas anônimas são desconectadas.</p></li>
</ul></td>
<td><ul>
<li><p>Chamadas normais permanecem conectadas.</p></li>
<li><p>Para grupos de respostas importados, as chamadas anônimas que alcançaram o pool de backup permanecem conectadas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chamadas em andamento ainda não conectadas a um agente</p></td>
<td><p>As chamadas são desconectadas.</p></td>
<td><ul>
<li><p>Se os grupos de respostas não forem importados, não haverá chamadas nesse status.</p></li>
<li><p>Para grupos de chamadas importados, as chamadas que alcançaram o pool de backup permanecem conectadas.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Novas chamadas</p></td>
<td><ul>
<li><p>As chamadas são desconectadas.</p></li>
<li><p>Para grupos de respostas importados, as chamadas se conectam ao pool de backup, mas os agentes hospedados no pool primário são inalcançáveis.</p></li>
</ul></td>
<td><ul>
<li><p>Se os grupos de resposta não forem importados, as chamadas serão desconectadas.</p></li>
<li><p>Para grupos de respostas importados, as chamadas são conectadas ao pool de backup.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>O agente chama em nome do grupo de resposta</p></td>
<td><p>O recurso é desabilitado durante esse estágio</p></td>
<td><ul>
<li><p>Se os grupos de resposta não forem importados, as chamadas falham.</p></li>
<li><p>Para grupos de resposta importados, as chamadas são bem-sucedidas.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Entrada do agente e informação do agente</p></td>
<td><ul>
<li><p>Os grupos de agente pertencentes ao pool primário podem ser exibidos no console do agente, mas os agentes não podem entrar.</p></li>
<li><p>Os grupos de agentes pertencentes ao pool de backup podem ser exibido no console do agente e os agentes podem entrar.</p></li>
<li><p>Os grupos de agentes importados são exibidos no console do agente e os agentes podem entrar.</p></li>
</ul></td>
<td><ul>
<li><p>Os grupos de agentes pertencentes ao pool primário podem ser exibidos no console do agente, mas os agentes não podem entrar.</p></li>
<li><p>Os grupos de agentes pertencentes ao pool de backup podem ser exibido no console do agente e os agentes podem entrar.</p></li>
<li><p>Os grupos de agentes importados são exibidos no console do agente e os agentes podem entrar.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuração do grupo de resposta</p></td>
<td><ul>
<li><p>Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</p></li>
<li><p>Os grupos de respostas pertencentes ao pool de backup podem ser exibidos e modificados.</p></li>
<li><p>Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</p></li>
</ul></td>
<td><ul>
<li><p>Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back end, mas não podem ser modificados.</p></li>
<li><p>Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</p></li>
<li><p>Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a>Experiência do usuário durante o failback

Quando um administrador chama o failback para o pool primário, a atividade do grupo de resposta é manipulada durante e após o failback, conforme descritos na tabela seguinte.

<div>


> [!NOTE]  
> Durante a recuperação de desastre, as chamadas se comportam de forma diferente dependendo se os grupos de resposta do pool primário foram importados ao pool de backup durante a recuperação. Na tabela seguinte, as referências dos grupos de respostas importados significam que os grupos de respostas do pool primário foram importados ao pool de backup durante o modo de recuperação de desastre.



</div>

### <a name="call-handling-in-failback"></a>Administração de chamada no Failback

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de chamada ou ação do usuário</th>
<th>Durante o failback</th>
<th>Após a conclusão do failback</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chamadas conectadas a um agente</p></td>
<td><ul>
<li><p>Chamadas normais permanecem conectadas.</p></li>
<li><p>Se os grupos de respostas não forem importados, nenhuma chamada anônima estará nesse status.</p></li>
<li><p>Para grupos de resposta importados, as chamadas anônimas permanecem conectadas.</p></li>
</ul></td>
<td><ul>
<li><p>Chamadas normais permanecem conectadas.</p></li>
<li><p>Se os grupos de respostas não forem importados, nenhuma chamada anônima estará nesse status.</p></li>
<li><p>Para grupos de resposta importados, as chamadas anônimas permanecem conectadas.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Chamadas em andamento ainda não conectadas a um agente</p></td>
<td><ul>
<li><p>Se os grupos de respostas não forem importados, nenhuma chamada estará nesse status.</p></li>
<li><p>Para grupos de respostas importados, as chamadas serão desconectadas.</p></li>
</ul></td>
<td><ul>
<li><p>Se os grupos de respostas não forem importados, nenhuma chamada estará nesse status.</p></li>
<li><p>Para grupos de respostas importados, as chamadas serão desconectadas.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Novas chamadas</p></td>
<td><p>Chamadas conectadas ao pool primário, mas os agentes hospedados no pool primário são inacessíveis.</p></td>
<td><p>Chamadas conectadas ao pool primário.</p></td>
</tr>
<tr class="even">
<td><p>Chamadas de agentes em nome do grupo de resposta</p></td>
<td><p>Recurso desabilitado durante esse estágio.</p></td>
<td><p>Chamadas bem-sucedidas.</p></td>
</tr>
<tr class="odd">
<td><p>Entrada do agente e informações do agente</p></td>
<td><ul>
<li><p>Os grupos de agente pertencentes ao pool primário podem ser exibidos no console do agente, mas os agentes não podem entrar.</p></li>
<li><p>Os grupos de agentes pertencentes ao pool de backup podem ser exibido no console do agente e os agentes podem entrar.</p></li>
<li><p>Os grupos de agentes importados são exibidos no console do agente e os agentes podem entrar.</p></li>
</ul></td>
<td><ul>
<li><p>Os grupos de agente pertencentes ao pool primário podem ser exibidos no console do agente e os agentes podem entrar.</p></li>
<li><p>Os grupos de agentes pertencentes ao pool de backup podem ser exibidos no console do agente e os agentes podem entrar.</p></li>
<li><p>Os grupos de agentes importados não são exibidos no console do agente.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuração do grupo de resposta</p></td>
<td><ul>
<li><p>Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</p></li>
<li><p>Os grupos de respostas pertencentes ao pool de backup podem ser exibidos e modificados.</p></li>
<li><p>Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</p></li>
</ul></td>
<td><ul>
<li><p>Os grupos de respostas pertencentes ao pool primário podem ser exibidos e modificados.</p></li>
<li><p>Os grupos de respostas pertencentes ao pool de backup podem ser exibidos e modificados.</p></li>
<li><p>Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</p></li>
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

