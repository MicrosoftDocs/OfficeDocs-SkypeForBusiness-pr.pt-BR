---
title: 'Lync Server 2013: processo de implantação para grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c87519c26a0804ad6c9f275d2e12c4a26988d29
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Processo de implantação para grupo de resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-27_

Esta seção fornece uma visão geral das fases e etapas envolvidas na implantação do aplicativo de grupo de resposta.

### <a name="response-group-deployment-process"></a>Processo de implantação do grupo de resposta

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Etapas</th>
<th>Permissões</th>
<th>Documentação de Implantação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Instalar o aplicativo grupo de resposta</p></td>
<td><p>O aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">Implantando o Enterprise Voice no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Instalar componentes para o grupo de resposta</p></td>
<td><p>Cmdlets do Lync Server, o painel de controle do Lync Server, a ferramenta de configuração do grupo de resposta, o console de entrada e saída dos agentes e o serviço Web do cliente do grupo de resposta são instalados como parte dos serviços Web. O Web Services é instalado ao implantar um pool do Enterprise Edition ou um servidor do Standard Edition.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">Implantando o Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Habilitar usuários para o Lync 2013 e para o Enterprise Voice</p></td>
<td><p>Habilitar usuários que serão agentes para Lync Server e Enterprise Voice. Os usuários devem ser habilitados antes de adicioná-los a grupos de agente. Normalmente, os usuários estão habilitados para o Lync Server durante a implantação do servidor Enterprise Edition ou Standard Edition. Os usuários são habilitados para o Enterprise Voice durante a implantação do Enterprise Voice.</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Desabilitar ou reabilitar a conta de usuário do Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Habilitar usuários para o Enterprise Voice no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Criar e configura grupos de resposta, que consistem de grupos de agentes, filas e fluxos de trabalho</p></td>
<td><ol>
<li><p>Use o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server para fazer o seguinte:</p>
<ol>
<li><p>Criar e configurar grupos de agentes.</p></li>
<li><p>Criar e configurar filas.</p></li>
</ol></li>
<li><p>Opcionalmente, use o Shell de gerenciamento do Lync Server para criar horários de negócios e feriados do grupo de resposta predefinidos.</p></li>
<li><p>Use a ferramenta de configuração de grupo de resposta ou o Shell de gerenciamento do Lync Server para criar fluxos de trabalho (fluxos de chamada de grupos de chamadas ou de resposta de voz interativa (IVR)), incluindo o horário comercial e feriados do grupo de resposta personalizado.</p>
<div>

> [!NOTE]  
> Você pode acessar a ferramenta de configuração do grupo de resposta por meio do painel de controle do Lync Server.


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>À csresponsegroupmanager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">Criar grupos de agente de grupo de resposta Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">Criar filas de grupo de resposta no Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">Opcion Definir o horário comercial do grupo de resposta no Lync Server 2013</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Opcion Definir os conjuntos de feriados do grupo de resposta no Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">Criar ou modificar um fluxo de trabalho no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Opcional) Personalizar configurações a nível de aplicativo</p></td>
<td><p>Use o Shell de gerenciamento do Lync Server para personalizar a configuração de música em espera padrão, o arquivo de áudio padrão de música em espera, o período de cortesia de retorno de toque do agente e a configuração do contexto da chamada.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">Gerenciando as configurações do grupo de resposta no nível do aplicativo no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>(Opcional) Delega o gerenciamento dos grupos de resposta</p></td>
<td><p>Atribuir aos usuários a função À csresponsegroupmanager para delegar a configuração de grupos de resposta. Os gerentes do grupo de resposta podem configurar os grupos de resposta atribuídos a eles.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">Planejando o controle de acesso baseado em função no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Verificar a implantação do grupo de respostas</p></td>
<td><p>Teste responder chamadas para seu fluxo de trabalho de resposta de voz interativa e grupo coletivo para garantir que sua configuração funcione como esperado.</p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

