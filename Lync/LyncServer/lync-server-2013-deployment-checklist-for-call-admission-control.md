---
title: 'Lync Server 2013: lista de verificação de implantação para controle de admissão de chamadas'
description: 'Lync Server 2013: lista de verificação de implantação para controle de admissão de chamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for call admission control
ms:assetid: 7e56a169-3e63-44ab-bf28-1fdeb52381c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398631(v=OCS.15)
ms:contentKeyID: 48184621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea5b16d41228faf01637e7e0d78f5ce56f950a19
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557687"
---
# <a name="deployment-checklist-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="dbc41-103">Lista de verificação de implantação para controle de admissão de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc41-103">Deployment checklist for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbc41-104">_**Última modificação do tópico:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="dbc41-104">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="dbc41-105">Para planejar efetivamente o controle de admissão de chamadas (CAC), você deve levar em consideração o seguinte:</span><span class="sxs-lookup"><span data-stu-id="dbc41-105">To plan effectively for call admission control (CAC), you need to consider the following:</span></span>

  - <span data-ttu-id="dbc41-106">Pré-requisitos para implantação do CAC.</span><span class="sxs-lookup"><span data-stu-id="dbc41-106">Prerequisites for deploying CAC.</span></span>

  - <span data-ttu-id="dbc41-107">Informações necessárias para decisões de CAC e de configuração que você deve tomar antes de começar a implantação</span><span class="sxs-lookup"><span data-stu-id="dbc41-107">Information required for CAC and configuration decisions that you must make in advance of deployment.</span></span>

<div>

## <a name="deployment-prerequisites-for-call-admission-control"></a><span data-ttu-id="dbc41-108">Pré-requisitos de implantação do controle de admissão de chamada</span><span class="sxs-lookup"><span data-stu-id="dbc41-108">Deployment Prerequisites for Call Admission Control</span></span>

<span data-ttu-id="dbc41-109">Antes de implantar o controle de admissão de chamadas, você já deve ter implantado seus servidores internos do Lync Server 2013, incluindo um pool de front-ends ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="dbc41-109">Before you deploy call admission control, you must already have deployed your Lync Server 2013 internal servers, including either a Front End pool or a Standard Edition server.</span></span>

</div>

<div>

## <a name="information-requirements-for-call-admission-control"></a><span data-ttu-id="dbc41-110">Requisitos de informações para o controle de admissão de chamada</span><span class="sxs-lookup"><span data-stu-id="dbc41-110">Information Requirements for Call Admission Control</span></span>

<span data-ttu-id="dbc41-111">A tabela a seguir resume as informações exigidas para implantar o controle de admissão de chamada.</span><span class="sxs-lookup"><span data-stu-id="dbc41-111">The following table summarizes the required information for deploying call admission control.</span></span>

### <a name="information-requirements-for-call-admission-control-deployment"></a><span data-ttu-id="dbc41-112">Requisitos de informações para a implantação do controle de admissão de chamada</span><span class="sxs-lookup"><span data-stu-id="dbc41-112">Information Requirements for Call Admission Control Deployment</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbc41-113">Informações</span><span class="sxs-lookup"><span data-stu-id="dbc41-113">Information</span></span></th>
<th><span data-ttu-id="dbc41-114">Resumo das informações necessárias</span><span class="sxs-lookup"><span data-stu-id="dbc41-114">Summary of Information Required</span></span></th>
<th><span data-ttu-id="dbc41-115">Documentação</span><span class="sxs-lookup"><span data-stu-id="dbc41-115">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbc41-116">Recursos do Lync Server exigidos pela sua organização</span><span class="sxs-lookup"><span data-stu-id="dbc41-116">Lync Server capabilities required by your organization</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbc41-117">Recursos a ser suportados pela organização</span><span class="sxs-lookup"><span data-stu-id="dbc41-117">Capabilities to be supported by your organization</span></span></p></li>
<li><p><span data-ttu-id="dbc41-118">Recursos a ser ativados para os usuários individuais</span><span class="sxs-lookup"><span data-stu-id="dbc41-118">Capabilities to be enabled for individual users</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dbc41-119"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definindo seus requisitos de controle de admissão de chamadas no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dbc41-119"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbc41-120">Topologias e componentes a serem implantados</span><span class="sxs-lookup"><span data-stu-id="dbc41-120">Topologies and components to be deployed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbc41-121">Os componentes relacionados ao CAC são instalados automaticamente como parte do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc41-121">CAC related components are automatically installed as part of Lync Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dbc41-122"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definindo seus requisitos de controle de admissão de chamadas no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dbc41-122"><a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Defining your requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbc41-123">Requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="dbc41-123">System requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbc41-124">Requisitos de hardware</span><span class="sxs-lookup"><span data-stu-id="dbc41-124">Hardware requirements</span></span></p></li>
<li><p><span data-ttu-id="dbc41-125">Requisitos de software</span><span class="sxs-lookup"><span data-stu-id="dbc41-125">Software requirements</span></span></p></li>
<li><p><span data-ttu-id="dbc41-126">Requisitos de colocação</span><span class="sxs-lookup"><span data-stu-id="dbc41-126">Collocation requirements</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dbc41-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determinando os requisitos do sistema para o Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dbc41-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbc41-128">Requisitos de infra-estrutura</span><span class="sxs-lookup"><span data-stu-id="dbc41-128">Infrastructure requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbc41-129">Nenhum requisito de infraestrutura específica é necessário para CAC</span><span class="sxs-lookup"><span data-stu-id="dbc41-129">No specific infrastructure requirements are necessary for CAC</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dbc41-130"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Requisitos de infraestrutura para controle de admissão de chamadas no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dbc41-130"><a href="lync-server-2013-infrastructure-requirements-for-call-admission-control.md">Infrastructure requirements for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbc41-131">Requisitos de interface de rede</span><span class="sxs-lookup"><span data-stu-id="dbc41-131">Network interface requirements</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbc41-132">Informações sobre as interfaces interna e externa</span><span class="sxs-lookup"><span data-stu-id="dbc41-132">Internal and external interface information</span></span></p></li>
<li><p><span data-ttu-id="dbc41-133">Informações de roteamento (incluindo informações sobre o blog do NextHop em <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a> , canal de resposta do cliente da equipe do Microsoft Lync Server)</span><span class="sxs-lookup"><span data-stu-id="dbc41-133">Routing information (including information on the NextHop blog at <a href="https://go.microsoft.com/fwlink/p/?linkid=203149">https://go.microsoft.com/fwlink/p/?LinkId=203149</a>, Microsoft Lync Server team’s customer response channel)</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dbc41-134"><a href="lync-server-2013-deploying-external-user-access.md">Implantando o acesso de usuário externo no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dbc41-134"><a href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbc41-135">Estratégia de implantação</span><span class="sxs-lookup"><span data-stu-id="dbc41-135">Deployment strategy</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbc41-136">Sequência de implantação</span><span class="sxs-lookup"><span data-stu-id="dbc41-136">Deployment sequence</span></span></p></li>
<li><p><span data-ttu-id="dbc41-137">Grupo de trabalho ou domínio</span><span class="sxs-lookup"><span data-stu-id="dbc41-137">Workgroup or domain</span></span></p></li>
<li><p><span data-ttu-id="dbc41-138">Segurança</span><span class="sxs-lookup"><span data-stu-id="dbc41-138">Security</span></span></p></li>
<li><p><span data-ttu-id="dbc41-139">Monitoramento e auditoria</span><span class="sxs-lookup"><span data-stu-id="dbc41-139">Monitoring and auditing</span></span></p></li>
<li><p><span data-ttu-id="dbc41-140">Considerações de hardware</span><span class="sxs-lookup"><span data-stu-id="dbc41-140">Hardware considerations</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dbc41-141"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Práticas recomendadas para controle de admissão de chamadas no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dbc41-141"><a href="lync-server-2013-best-practices-for-call-admission-control.md">Best practices for call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbc41-142">Processo de implantação</span><span class="sxs-lookup"><span data-stu-id="dbc41-142">Deployment process</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbc41-143">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="dbc41-143">Prerequisites</span></span></p></li>
<li><p><span data-ttu-id="dbc41-144">Requisitos de informações</span><span class="sxs-lookup"><span data-stu-id="dbc41-144">Information requirements</span></span></p></li>
<li><p><span data-ttu-id="dbc41-145">Processo e procedimentos</span><span class="sxs-lookup"><span data-stu-id="dbc41-145">Process and procedures</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="dbc41-146"><a href="lync-server-2013-configure-call-admission-control.md">Configurar o controle de admissão de chamadas no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="dbc41-146"><a href="lync-server-2013-configure-call-admission-control.md">Configure call admission control in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

