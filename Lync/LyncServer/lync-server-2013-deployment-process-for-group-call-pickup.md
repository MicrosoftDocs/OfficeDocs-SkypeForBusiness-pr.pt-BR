---
title: 'Lync Server 2013: processo de implantação para recebimento de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52f7646010e4048d135e11c98d06a651f923d633
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522608"
---
# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="3fecd-102">Processo de implantação do recebimento de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fecd-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fecd-103">_**Última modificação do tópico:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="3fecd-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="3fecd-104">Esta seção fornece uma visão geral das etapas envolvidas na implantação do recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="3fecd-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="3fecd-105">Você deve implantar o Enterprise Edition ou Standard Edition com o Enterprise Voice antes de configurar o recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="3fecd-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="3fecd-106">Os componentes necessários para o recebimento de chamadas em grupo são instalados e habilitados quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3fecd-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="3fecd-107">Processo de implantação de recebimento de chamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="3fecd-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fecd-108">Fase</span><span class="sxs-lookup"><span data-stu-id="3fecd-108">Phase</span></span></th>
<th><span data-ttu-id="3fecd-109">Etapas</span><span class="sxs-lookup"><span data-stu-id="3fecd-109">Steps</span></span></th>
<th><span data-ttu-id="3fecd-110">Grupos e funções exigidos</span><span class="sxs-lookup"><span data-stu-id="3fecd-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="3fecd-111">Documentação da implantação</span><span class="sxs-lookup"><span data-stu-id="3fecd-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fecd-112">Habilitar a ferramenta SEFAUtil Resource Kit na topologia</span><span class="sxs-lookup"><span data-stu-id="3fecd-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="3fecd-113">Use o cmdlet <strong>New-CsTrustedApplicationPool</strong> para criar um novo pool de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="3fecd-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="3fecd-114">Use o cmdlet <strong>New-CsTrustedApplication</strong> para especificar a ferramenta SEFAUtil como aplicativo confiável.</span><span class="sxs-lookup"><span data-stu-id="3fecd-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="3fecd-115">Execute o cmdlet <strong>Enable-CsTopology</strong> para habilitar a topologia.</span><span class="sxs-lookup"><span data-stu-id="3fecd-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="3fecd-116">Instale as ferramentas do kit de recursos em um servidor front-end que esteja no pool de aplicativos confiáveis criado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="3fecd-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="3fecd-117">Verifique se o SEFAUtil está funcionando corretamente executando-o para exibir as configurações de encaminhamento de chamadas de um usuário na implantação.</span><span class="sxs-lookup"><span data-stu-id="3fecd-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="3fecd-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3fecd-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="3fecd-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Implantar a ferramenta SEFAUtil no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3fecd-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fecd-120">Configurar intervalos de números de recebimento de chamada na tabela de órbita de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="3fecd-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="3fecd-121">Use o cmdlet <strong>New-CSCallParkOrbit</strong> para criar intervalos de números de recebimento de chamadas na tabela de órbitas do estacionamento de chamadas e atribua ao tipo de chamada os intervalos de GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="3fecd-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="3fecd-122">Você deve usar o Shell de gerenciamento do Lync Server para criar, modificar, remover e exibir intervalos de números de recebimento de chamadas em grupo na tabela de órbita de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="3fecd-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="3fecd-123">Os intervalos de números de recebimento de chamadas de grupo não estão disponíveis no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3fecd-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="3fecd-124">Para uma integração perfeita com planos de discagem existentes, os intervalos de números geralmente são configurados como um bloco de extensões virtuais.</span><span class="sxs-lookup"><span data-stu-id="3fecd-124">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="3fecd-125">A atribuição de números DID (discagem direta interna) como números de intervalo na tabela de órbita de estacionamento de chamada não é suportada.</span><span class="sxs-lookup"><span data-stu-id="3fecd-125">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="3fecd-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3fecd-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="3fecd-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="3fecd-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="3fecd-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="3fecd-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="3fecd-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="3fecd-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="3fecd-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurar números de grupos de recebimento de chamadas no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3fecd-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fecd-131">Atribuir um número de recebimento de chamada aos usuários e habilitar o recebimento de chamadas em grupo para os usuários</span><span class="sxs-lookup"><span data-stu-id="3fecd-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="3fecd-132">Use o parâmetro/enablegrouppickup na ferramenta do kit de recursos do SEFAUtil para habilitar o recebimento de chamadas em grupo e atribuir um número de recebimento de chamada para os usuários.</span><span class="sxs-lookup"><span data-stu-id="3fecd-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3fecd-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Habilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013 e atribuir um número de grupo</a></span><span class="sxs-lookup"><span data-stu-id="3fecd-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fecd-134">Notificar os usuários sobre o número de recebimento de chamadas atribuído e qualquer outro número de interesse</span><span class="sxs-lookup"><span data-stu-id="3fecd-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="3fecd-135">Como qualquer usuário pode recuperar uma chamada feita para um usuário de recebimento de chamada em grupo, os usuários podem querer monitorar mais de um grupo.</span><span class="sxs-lookup"><span data-stu-id="3fecd-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3fecd-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Comunicar as atribuições de recebimento de chamadas de grupo aos usuários no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3fecd-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fecd-137">Verificar a implantação do recebimento de chamadas em grupo</span><span class="sxs-lookup"><span data-stu-id="3fecd-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="3fecd-138">Teste a colocação e recuperação de chamadas para garantir que a configuração funcione conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="3fecd-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="3fecd-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Opcion Verificar a implantação do recebimento de chamadas em grupo no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3fecd-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

