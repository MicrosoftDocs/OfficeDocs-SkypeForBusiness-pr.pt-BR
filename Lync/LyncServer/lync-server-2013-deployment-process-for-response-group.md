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

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="f5e73-102">Processo de implantação para grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5e73-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5e73-103">_**Última modificação do tópico:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="f5e73-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="f5e73-104">Esta seção fornece uma visão geral das fases e etapas envolvidas na implantação do aplicativo de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="f5e73-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="f5e73-105">Processo de implantação do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="f5e73-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5e73-106">Fase</span><span class="sxs-lookup"><span data-stu-id="f5e73-106">Phase</span></span></th>
<th><span data-ttu-id="f5e73-107">Etapas</span><span class="sxs-lookup"><span data-stu-id="f5e73-107">Steps</span></span></th>
<th><span data-ttu-id="f5e73-108">Permissões</span><span class="sxs-lookup"><span data-stu-id="f5e73-108">Permissions</span></span></th>
<th><span data-ttu-id="f5e73-109">Documentação de Implantação</span><span class="sxs-lookup"><span data-stu-id="f5e73-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5e73-110">Instalar o aplicativo grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="f5e73-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="f5e73-111">O aplicativo grupo de resposta é instalado e ativado por padrão ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f5e73-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="f5e73-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f5e73-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="f5e73-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Implantando o Enterprise Voice no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5e73-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5e73-114">Instalar componentes para o grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="f5e73-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="f5e73-115">Cmdlets do Lync Server, o painel de controle do Lync Server, a ferramenta de configuração do grupo de resposta, o console de entrada e saída dos agentes e o serviço Web do cliente do grupo de resposta são instalados como parte dos serviços Web.</span><span class="sxs-lookup"><span data-stu-id="f5e73-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="f5e73-116">O Web Services é instalado ao implantar um pool do Enterprise Edition ou um servidor do Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f5e73-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="f5e73-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f5e73-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="f5e73-118"><a href="lync-server-2013-deploying-lync-server.md">Implantando o Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5e73-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5e73-119">Habilitar usuários para o Lync 2013 e para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="f5e73-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="f5e73-120">Habilitar usuários que serão agentes para Lync Server e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f5e73-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="f5e73-121">Os usuários devem ser habilitados antes de adicioná-los a grupos de agente.</span><span class="sxs-lookup"><span data-stu-id="f5e73-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="f5e73-122">Normalmente, os usuários estão habilitados para o Lync Server durante a implantação do servidor Enterprise Edition ou Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f5e73-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="f5e73-123">Os usuários são habilitados para o Enterprise Voice durante a implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f5e73-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="f5e73-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f5e73-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="f5e73-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="f5e73-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="f5e73-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f5e73-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f5e73-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Desabilitar ou reabilitar a conta de usuário do Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5e73-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f5e73-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Habilitar usuários para o Enterprise Voice no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5e73-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5e73-129">Criar e configura grupos de resposta, que consistem de grupos de agentes, filas e fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="f5e73-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="f5e73-130">Use o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f5e73-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="f5e73-131">Criar e configurar grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="f5e73-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="f5e73-132">Criar e configurar filas.</span><span class="sxs-lookup"><span data-stu-id="f5e73-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="f5e73-133">Opcionalmente, use o Shell de gerenciamento do Lync Server para criar horários de negócios e feriados do grupo de resposta predefinidos.</span><span class="sxs-lookup"><span data-stu-id="f5e73-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="f5e73-134">Use a ferramenta de configuração de grupo de resposta ou o Shell de gerenciamento do Lync Server para criar fluxos de trabalho (fluxos de chamada de grupos de chamadas ou de resposta de voz interativa (IVR)), incluindo o horário comercial e feriados do grupo de resposta personalizado.</span><span class="sxs-lookup"><span data-stu-id="f5e73-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f5e73-135">Você pode acessar a ferramenta de configuração do grupo de resposta por meio do painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5e73-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="f5e73-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f5e73-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f5e73-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="f5e73-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="f5e73-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f5e73-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="f5e73-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f5e73-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f5e73-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f5e73-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="f5e73-141">À csresponsegroupmanager</span><span class="sxs-lookup"><span data-stu-id="f5e73-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="f5e73-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Criar grupos de agente de grupo de resposta Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5e73-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f5e73-143"><a href="lync-server-2013-create-response-group-queues.md">Criar filas de grupo de resposta no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5e73-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f5e73-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">Opcion Definir o horário comercial do grupo de resposta no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5e73-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f5e73-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Opcion Definir os conjuntos de feriados do grupo de resposta no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5e73-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="f5e73-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Criar ou modificar um fluxo de trabalho no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5e73-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5e73-147">(Opcional) Personalizar configurações a nível de aplicativo</span><span class="sxs-lookup"><span data-stu-id="f5e73-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="f5e73-148">Use o Shell de gerenciamento do Lync Server para personalizar a configuração de música em espera padrão, o arquivo de áudio padrão de música em espera, o período de cortesia de retorno de toque do agente e a configuração do contexto da chamada.</span><span class="sxs-lookup"><span data-stu-id="f5e73-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="f5e73-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f5e73-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f5e73-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="f5e73-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="f5e73-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f5e73-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="f5e73-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f5e73-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f5e73-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f5e73-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f5e73-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Gerenciando as configurações do grupo de resposta no nível do aplicativo no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5e73-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5e73-155">(Opcional) Delega o gerenciamento dos grupos de resposta</span><span class="sxs-lookup"><span data-stu-id="f5e73-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="f5e73-156">Atribuir aos usuários a função À csresponsegroupmanager para delegar a configuração de grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="f5e73-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="f5e73-157">Os gerentes do grupo de resposta podem configurar os grupos de resposta atribuídos a eles.</span><span class="sxs-lookup"><span data-stu-id="f5e73-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="f5e73-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f5e73-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="f5e73-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="f5e73-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="f5e73-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f5e73-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="f5e73-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f5e73-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="f5e73-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f5e73-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="f5e73-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planejando o controle de acesso baseado em função no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="f5e73-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5e73-164">Verificar a implantação do grupo de respostas</span><span class="sxs-lookup"><span data-stu-id="f5e73-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="f5e73-165">Teste responder chamadas para seu fluxo de trabalho de resposta de voz interativa e grupo coletivo para garantir que sua configuração funcione como esperado.</span><span class="sxs-lookup"><span data-stu-id="f5e73-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
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

