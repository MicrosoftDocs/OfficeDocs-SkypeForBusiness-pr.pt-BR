---
title: 'Lync Server 2013: processo de implantação para retirada de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ff5eda01c5436240c0baca2b1711bba8e9c996
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="ce8eb-102">Processo de implantação para retirada de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce8eb-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce8eb-103">_**Tópico da última modificação:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="ce8eb-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="ce8eb-104">Esta seção fornece uma visão geral das etapas envolvidas na implantação da retirada de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="ce8eb-105">Você deve implantar a edição Enterprise ou Standard Edition com o Enterprise Voice antes de configurar o recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="ce8eb-106">Os componentes necessários para o recebimento de chamadas em grupo são instalados e habilitados durante a implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="ce8eb-107">Processo de implantação do Recebimento de chamada de grupo</span><span class="sxs-lookup"><span data-stu-id="ce8eb-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce8eb-108">Fase</span><span class="sxs-lookup"><span data-stu-id="ce8eb-108">Phase</span></span></th>
<th><span data-ttu-id="ce8eb-109">Etapas</span><span class="sxs-lookup"><span data-stu-id="ce8eb-109">Steps</span></span></th>
<th><span data-ttu-id="ce8eb-110">Grupos e funções necessários</span><span class="sxs-lookup"><span data-stu-id="ce8eb-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="ce8eb-111">Documentação de Implantação</span><span class="sxs-lookup"><span data-stu-id="ce8eb-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce8eb-112">Habilitar a ferramenta SEFAUtil Resource Kit na topologia</span><span class="sxs-lookup"><span data-stu-id="ce8eb-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="ce8eb-113">Use o cmdlet <strong>New-CsTrustedApplicationPool</strong> para criar um novo pool de aplicativo confiável.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="ce8eb-114">Use o cmdlet <strong>New-CsTrustedApplication</strong> para especificar a ferramenta SEFAUtil como aplicativo confiável.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="ce8eb-115">Execute o cmdlet <strong>Enable-CsTopology</strong> para ativar a topologia.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="ce8eb-116">Instale as ferramentas do Resource Kit em um servidor front-end que está no pool de aplicativos confiáveis criado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="ce8eb-117">Verifique se o SEFAUtil está executando corretamente ao executá-lo para exibir as configurações de encaminhamento de chamada de um usuário na implantação.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="ce8eb-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ce8eb-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="ce8eb-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce8eb-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce8eb-120">Configure os intervalos de número para recebimento de chamada na tabela de órbita de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="ce8eb-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="ce8eb-121">Use o cmdlet <strong>New-CSCallParkOrbit</strong> para criar intervalos de números de recebimento de chamadas na tabela órbitas do estacionamento de chamada e atribuir os intervalos de recebimento de chamada ao tipo GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="ce8eb-122">Você deve usar o Shell de gerenciamento do Lync Server para criar, modificar, remover e exibir os intervalos de números de retirada de chamadas em grupo na tabela órbita do estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="ce8eb-123">Os intervalos de números de retirada de chamadas em grupo não estão disponíveis no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="ce8eb-p103">Para uma integração perfeita aos planos de discagem existentes, os intervalos de número são normalmente configurados como um bloco de ramais virtuais. A atribuição dos números de Discagem Direta de Entrada (DID) como números de intervalos  na tabela de órbita de estacionamento de chamada não é suportada.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-p103">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="ce8eb-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="ce8eb-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="ce8eb-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="ce8eb-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="ce8eb-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="ce8eb-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="ce8eb-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="ce8eb-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="ce8eb-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configurar números de grupo de recebimento de chamadas no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce8eb-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce8eb-131">Atribuir um número de recebimento de chamadas aos usuários e habilitar o recebimento de chamadas em grupo para os usuários</span><span class="sxs-lookup"><span data-stu-id="ce8eb-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="ce8eb-132">Use o parâmetro/enablegrouppickup na ferramenta do kit de recursos do SEFAUtil para habilitar o recebimento de chamadas em grupo e atribuir um número de recebimento de chamadas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="ce8eb-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Habilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013 e atribuir um número de grupo</a></span><span class="sxs-lookup"><span data-stu-id="ce8eb-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce8eb-134">Notifique os usuários do número de recebimento de chamada atribuído e qualquer outro número de interesse</span><span class="sxs-lookup"><span data-stu-id="ce8eb-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="ce8eb-135">Como qualquer usuário pode recuperar uma chamada feita para um usuário de recebimento de chamada em grupo, os usuários podem querer monitorar mais de um grupo.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="ce8eb-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Comunicar as atribuições de recebimento de chamadas em grupo aos usuários no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce8eb-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce8eb-137">Verificar sua implantação de retirada de chamadas em grupo</span><span class="sxs-lookup"><span data-stu-id="ce8eb-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="ce8eb-138">Teste fazer e receber chamadas para garantir que a configuração funcione conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="ce8eb-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="ce8eb-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Adicionais Verificar a implantação da retirada de chamadas em grupo no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="ce8eb-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

