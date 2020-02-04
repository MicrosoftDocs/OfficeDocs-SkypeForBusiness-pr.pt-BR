---
title: 'Lync Server 2013: Processo de implantação para integrar o Exchange UM hospedado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b314ea3bd7a88264a72c804c7c67ed3baa819972
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="69523-102">Processo de implantação para integrar o Exchange UM hospedado ao Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69523-102">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69523-103">_**Tópico da última modificação:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="69523-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="69523-104">O planejamento efetivo para a integração do Lync Server 2013 com a Unificação de mensagens do Exchange hospedada requer que você leve em conta o seguinte:</span><span class="sxs-lookup"><span data-stu-id="69523-104">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="69523-105">Pré-requisitos para a integração do Lync Server 2013 com o Exchange UM hospedado</span><span class="sxs-lookup"><span data-stu-id="69523-105">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="69523-106">Etapas necessárias durante o processo de integração</span><span class="sxs-lookup"><span data-stu-id="69523-106">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="69523-107">Pré-requisitos de implantação para integração com o Exchange UM hospedado</span><span class="sxs-lookup"><span data-stu-id="69523-107">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="69523-108">Antes de começar o processo de integração, você já deve ter implantado o Lync Server 2013 (no mínimo, um pool de front-end ou um servidor Standard Edition), um servidor de borda e clientes Lync 2013 ou Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="69523-108">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="69523-109">Processo de integração</span><span class="sxs-lookup"><span data-stu-id="69523-109">Integration Process</span></span>

<span data-ttu-id="69523-110">A tabela a seguir fornece uma visão geral do processo de integração do Exchange UM hospedado.</span><span class="sxs-lookup"><span data-stu-id="69523-110">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="69523-111">Para obter detalhes sobre etapas de implantação, consulte [fornecendo aos usuários do Lync Server 2013 a caixa postal no Exchange um hospedado](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="69523-111">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69523-112">Fase</span><span class="sxs-lookup"><span data-stu-id="69523-112">Phase</span></span></th>
<th><span data-ttu-id="69523-113">Etapas</span><span class="sxs-lookup"><span data-stu-id="69523-113">Steps</span></span></th>
<th><span data-ttu-id="69523-114">Direitos e permissões</span><span class="sxs-lookup"><span data-stu-id="69523-114">Rights and permissions</span></span></th>
<th><span data-ttu-id="69523-115">Documentação de Implantação</span><span class="sxs-lookup"><span data-stu-id="69523-115">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69523-116">Configurar o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="69523-116">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="69523-117">Configure o Servidor de Borda para federação.</span><span class="sxs-lookup"><span data-stu-id="69523-117">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="69523-118">Replique manualmente os dados para o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="69523-118">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="69523-119">Configurar o provedor de hospedagem no servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="69523-119">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="69523-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="69523-120">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="69523-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configurar Servidor de Borda para integração com o Exchange UM hospedado</a></span><span class="sxs-lookup"><span data-stu-id="69523-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69523-122">Configurar a política de caixa postal hospedada.</span><span class="sxs-lookup"><span data-stu-id="69523-122">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="69523-123">Modifique a política de caixa de correio de voz hospedada global ou crie uma nova política de caixa postal hospedada com o site ou o escopo por usuário.</span><span class="sxs-lookup"><span data-stu-id="69523-123">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="69523-124">Para políticas com escopo por usuário, atribua a política a usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="69523-124">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="69523-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="69523-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="69523-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Gerenciar políticas de caixa postal hospedada no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="69523-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69523-127">Habilite os usuários para a caixa postal hospedada.</span><span class="sxs-lookup"><span data-stu-id="69523-127">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="69523-128">Configure contas de usuário para os usuários cujas caixas de correio estão em um serviço hospedado do Exchange.</span><span class="sxs-lookup"><span data-stu-id="69523-128">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="69523-129">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="69523-129">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="69523-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Habilitar usuários para correio de voz hospedado no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="69523-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69523-131">Configurar objetos de contato hospedados.</span><span class="sxs-lookup"><span data-stu-id="69523-131">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="69523-132">Crie objetos de contato do atendente automático para UM Exchange UM hospedado.</span><span class="sxs-lookup"><span data-stu-id="69523-132">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="69523-133">Crie objetos de contato do acesso do assinante para o Exchange UM hospedado.</span><span class="sxs-lookup"><span data-stu-id="69523-133">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="69523-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="69523-134">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="69523-135">Para criar, modificar ou remover objetos de contato, o usuário que executa o cmdlet New-CsExUmContact, Set-CsExUmContact ou remove-CsExUmContact deve ter a permissão correta para a unidade organizacional do Active Directory na qual os novos objetos de contato são armazenados.</span><span class="sxs-lookup"><span data-stu-id="69523-135">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="69523-136">Esta permissão pode ser concedida executando-se o cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="69523-136">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="69523-137">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69523-137">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="69523-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Criar objetos de contato para Exchange UM hospedado no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="69523-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

