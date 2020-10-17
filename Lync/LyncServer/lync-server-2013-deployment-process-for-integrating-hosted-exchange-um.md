---
title: 'Lync Server 2013: processo de implantação para integração do UM do Exchange hospedado'
description: 'Lync Server 2013: processo de implantação para integração do UM do Exchange hospedado.'
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
ms.openlocfilehash: 83239c6534dfdaa65109c8880cc4cb4946bffab6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542607"
---
# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="fe075-103">Processo de implantação para integração do UM do Exchange hospedado com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe075-103">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe075-104">_**Última modificação do tópico:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="fe075-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="fe075-105">O planejamento eficaz da integração do Lync Server 2013 com a Unificação de mensagens (UM) do Exchange hospedado exige que você leve em consideração o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fe075-105">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="fe075-106">Pré-requisitos para a integração do Lync Server 2013 com o UM do Exchange hospedado</span><span class="sxs-lookup"><span data-stu-id="fe075-106">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="fe075-107">Etapas necessárias durante o processo de integração</span><span class="sxs-lookup"><span data-stu-id="fe075-107">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="fe075-108">Pré-requisitos de implantação para a integração com UM do Exchange hospedada</span><span class="sxs-lookup"><span data-stu-id="fe075-108">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="fe075-109">Antes de começar o processo de integração, você já deve ter implantado o Lync Server 2013 (no mínimo, um pool de front-end ou um servidor Standard Edition), um servidor de borda e os clientes do Lync 2013 ou Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="fe075-109">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="fe075-110">Processo de integração</span><span class="sxs-lookup"><span data-stu-id="fe075-110">Integration Process</span></span>

<span data-ttu-id="fe075-111">A tabela a seguir fornece uma visão geral do processo de integração da UM do Exchange hospedada.</span><span class="sxs-lookup"><span data-stu-id="fe075-111">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="fe075-112">Para obter detalhes sobre etapas de implantação, consulte [fornecer mensagens de voz do Lync Server 2013 Users no Hosted Exchange um](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="fe075-112">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe075-113">Fase</span><span class="sxs-lookup"><span data-stu-id="fe075-113">Phase</span></span></th>
<th><span data-ttu-id="fe075-114">Etapas</span><span class="sxs-lookup"><span data-stu-id="fe075-114">Steps</span></span></th>
<th><span data-ttu-id="fe075-115">Direitos e permissões</span><span class="sxs-lookup"><span data-stu-id="fe075-115">Rights and permissions</span></span></th>
<th><span data-ttu-id="fe075-116">Documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="fe075-116">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe075-117">Configuração do Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="fe075-117">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="fe075-118">Configure o Servidor de Borda para federação.</span><span class="sxs-lookup"><span data-stu-id="fe075-118">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="fe075-119">Replique manualmente os dados para o Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="fe075-119">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="fe075-120">Configure um provedor de hospedagem no Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="fe075-120">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="fe075-121">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="fe075-121">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="fe075-122"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configurar o servidor de borda para integração com o UM do Exchange hospedado</a></span><span class="sxs-lookup"><span data-stu-id="fe075-122"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe075-123">Configure a política de caixa postal hospedada.</span><span class="sxs-lookup"><span data-stu-id="fe075-123">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="fe075-124">Modifique a política global de caixa postal hospedada ou crie uma nova política de caixa postal hospedada com escopo de Site ou Por usuário.</span><span class="sxs-lookup"><span data-stu-id="fe075-124">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="fe075-125">Para políticas com o escopo Por usuário, atribua a política aos usuários ou grupos.</span><span class="sxs-lookup"><span data-stu-id="fe075-125">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="fe075-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="fe075-126">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="fe075-127"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Gerenciar políticas de caixa postal hospedada no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fe075-127"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe075-128">Habilite os usuários para caixa postal hospedada</span><span class="sxs-lookup"><span data-stu-id="fe075-128">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe075-129">Configure contas de usuário para usuário cujas caixas postais estão em um serviço do Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="fe075-129">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fe075-130">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="fe075-130">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="fe075-131"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Habilitar usuários para caixa postal hospedada no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fe075-131"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe075-132">Configure objetos de contato hospedados.</span><span class="sxs-lookup"><span data-stu-id="fe075-132">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="fe075-133">Crie objetos de contato Atendedor Automático para UM do Exchange hospedada.</span><span class="sxs-lookup"><span data-stu-id="fe075-133">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="fe075-134">Crie objetos de contato Acesso do Assinante para UM do Exchange hospedada.</span><span class="sxs-lookup"><span data-stu-id="fe075-134">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="fe075-135">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="fe075-135">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fe075-136">Para criar, modificar ou remover objetos de contato, o usuário que executa o cmdlet New-CsExUmContact, Set-CsExUmContact ou Remove-CsExUmContact precisa ter a permissão correta para a unidade organizacional Active Directory na qual os novos objetos de contato são armazenados.</span><span class="sxs-lookup"><span data-stu-id="fe075-136">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="fe075-137">Essa permissão pode ser atribuída por meio da execução do cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="fe075-137">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="fe075-138">Para obter detalhes, consulte a documentação do Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fe075-138">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="fe075-139"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Criar objetos de contato para a UM do Exchange hospedado no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fe075-139"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

