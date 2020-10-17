---
title: Lync Server 2013 lista de verificação de implantação para conferência discada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a81a4baee7062936144d0a6d066d59cf0a8ef1e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522788"
---
# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="563f1-102">Lista de verificação de implantação para conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="563f1-102">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="563f1-103">_**Última modificação do tópico:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="563f1-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="563f1-104">Os componentes necessários para conferência discada são implantados quando a carga de trabalho de conferência é implantada.</span><span class="sxs-lookup"><span data-stu-id="563f1-104">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="563f1-105">Antes de poder configurar a conferência discada, você precisa implantar o Enterprise Voice ou um servidor de mediação e um gateway PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="563f1-105">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="563f1-106">Todas as etapas na tabela a seguir devem ser executadas antes que os usuários possam discar a partir do PSTN para entrar em uma conferência de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="563f1-106">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="563f1-107">Se você estiver migrando do Office Communications Server 2007 R2, deverá aplicar as atualizações mais recentes para o ambiente do Office Communications Server 2007 R2 antes de implantar a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="563f1-107">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="563f1-108">Processo de implantação da conferência discada</span><span class="sxs-lookup"><span data-stu-id="563f1-108">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="563f1-109">Fase</span><span class="sxs-lookup"><span data-stu-id="563f1-109">Phase</span></span></th>
<th><span data-ttu-id="563f1-110">Etapas</span><span class="sxs-lookup"><span data-stu-id="563f1-110">Steps</span></span></th>
<th><span data-ttu-id="563f1-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="563f1-111">Permissions</span></span></th>
<th><span data-ttu-id="563f1-112">Documentação de Implantação</span><span class="sxs-lookup"><span data-stu-id="563f1-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="563f1-113"><strong>Crie uma topologia que inclua a carga de trabalho de conferência, incluindo um servidor de mediação e um gateway PSTN, e implante o pool de front-ends ou o servidor Standard Edition</strong></span><span class="sxs-lookup"><span data-stu-id="563f1-113"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="563f1-114">Execute o construtor de topologias para configurar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="563f1-114">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="563f1-115">Enquanto a configuração da topologia é executada, selecione a opção de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="563f1-115">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="563f1-116">Publique a topologia e implante o pool de front-ends ou o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="563f1-116">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="563f1-117">Se necessário, crie um servidor de mediação autônomo e associe-o a um gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="563f1-117">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="563f1-118">Esta etapa é necessária somente se você não implantar o Enterprise Voice e não colocar o servidor de mediação com o servidor final do Enterprise EditionFront ou o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="563f1-118">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="563f1-119">Se você implantar o Enterprise Voice, instale e configure os servidores de mediação e os gateways PSTN como parte da implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="563f1-119">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="563f1-120">Se você colocar o servidor de mediação, instale e configure o servidor de mediação como parte da implantação do pool de front-ends ou do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="563f1-120">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="563f1-121">Admins. do Domínio</span><span class="sxs-lookup"><span data-stu-id="563f1-121">Domain Admins</span></span></p>
<p><span data-ttu-id="563f1-122">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="563f1-122">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="563f1-123">Administrador</span><span class="sxs-lookup"><span data-stu-id="563f1-123">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="563f1-124"><a href="lync-server-2013-deploying-lync-server.md">Implantando o Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="563f1-124"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="563f1-125">Para criar um pool de servidor de mediação autônomo: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">implantando servidores de mediação e definindo pares no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="563f1-125">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="563f1-126"><strong>Configure planos de discagem</strong></span><span class="sxs-lookup"><span data-stu-id="563f1-126"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="563f1-127">Um plano de discagem é um conjunto de regras de normalização de número de telefone que traduzem números discados de um local específico para um padrão de formato único (E.164), para fins de autorização do telefone e roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="563f1-127">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="563f1-128">O mesmo número de telefone discado a partir de locais diferentes pode, com base nos respectivos planos de discagem, resolver para diferentes números E.164, conforme o que for mais adequado para cada local.</span><span class="sxs-lookup"><span data-stu-id="563f1-128">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="563f1-129">Se você implantar o Enterprise Voice, configure os planos de discagem como parte dessa implantação e você precisará certificar-se de que os planos de discagem também acomodem a conferência discada.</span><span class="sxs-lookup"><span data-stu-id="563f1-129">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="563f1-130">Se você não implantar o Enterprise Voice, precisará configurar planos de discagem para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="563f1-130">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="563f1-131">Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para configurar planos de discagem da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="563f1-131">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="563f1-132">Crie um ou mais planos de discagem para rotear números de telefone de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="563f1-132">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="563f1-p105">Atribua um plano de discagem padrão para cada pool. Defina a <strong>Região da conferência discada</strong> à localização geográfica à qual o plano de discagem se aplica. A região associa o plano de discagem aos números de acesso discado.</span><span class="sxs-lookup"><span data-stu-id="563f1-p105">Assign a default dial plan to each pool. Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies. The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="563f1-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="563f1-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="563f1-137">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-137">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="563f1-138">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-138">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="563f1-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="563f1-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configurar planos de discagem para conferência discada no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="563f1-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="563f1-141"><strong>Verifique se os planos de discagem são atribuídos às regiões</strong></span><span class="sxs-lookup"><span data-stu-id="563f1-141"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="563f1-142">Execute os cmdlets <strong>Get-CsDialPlan</strong> e <strong>set-CsDialPlan</strong> para verificar se todos os planos de discagem têm uma região atribuída.</span><span class="sxs-lookup"><span data-stu-id="563f1-142">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="563f1-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="563f1-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="563f1-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="563f1-145">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-145">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="563f1-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="563f1-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Verifique se os planos de discagem Lync Server 2013 possuem regiões atribuídas</a></span><span class="sxs-lookup"><span data-stu-id="563f1-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="563f1-148"><strong>(Opcional) Verifique ou modifique os requisitos do número de identificação pessoal (PIN) do usuário.</strong></span><span class="sxs-lookup"><span data-stu-id="563f1-148"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="563f1-149">Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para exibir ou modificar a <strong>política de PIN</strong>de conferência.</span><span class="sxs-lookup"><span data-stu-id="563f1-149">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="563f1-150">Você pode especificar o comprimento mínimo do PIN, o número máximo de tentativas de logon, a expiração do PIN e se padrões comuns são permissíveis.</span><span class="sxs-lookup"><span data-stu-id="563f1-150">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="563f1-151">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="563f1-151">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="563f1-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="563f1-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="563f1-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">Opcion Verificar as configurações de política de PIN no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="563f1-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="563f1-155"><strong>Configure a política de conferência para suportar conferências discadas.</strong></span><span class="sxs-lookup"><span data-stu-id="563f1-155"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="563f1-156">Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para definir as configurações de <strong>política de conferência</strong> .</span><span class="sxs-lookup"><span data-stu-id="563f1-156">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="563f1-157">Especifique se:</span><span class="sxs-lookup"><span data-stu-id="563f1-157">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="563f1-158">A discagem de conferência PSTN está habilitada.</span><span class="sxs-lookup"><span data-stu-id="563f1-158">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="563f1-159">Usuários podem convidar participantes anônimos.</span><span class="sxs-lookup"><span data-stu-id="563f1-159">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="563f1-p108">Usuários não autenticados podem participar de uma conferência usando discagem de saída. Com a discagem de saída, o servidor de conferência faz uma chamada para o usuário e o usuário atende o telefone para entrar na conferência.</span><span class="sxs-lookup"><span data-stu-id="563f1-p108">Unauthenticated users can join a conference by using dial-out phoning. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="563f1-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="563f1-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="563f1-163">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-163">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="563f1-164">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-164">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="563f1-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configurar a política de conferência para discagem no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="563f1-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="563f1-166"><strong>Configure números de acesso de discagem</strong></span><span class="sxs-lookup"><span data-stu-id="563f1-166"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="563f1-167">Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para configurar números de acesso de discagem que os usuários chamam para discar para uma conferência e especifique as regiões que associam o número de acesso com os planos de discagem apropriados.</span><span class="sxs-lookup"><span data-stu-id="563f1-167">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="563f1-168">Os três primeiros números de acesso para a região especificada pelo plano de discagem do organizador são incluídos no convite da conferência.</span><span class="sxs-lookup"><span data-stu-id="563f1-168">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="563f1-169">Todos os números de acesso estão disponíveis na página Configurações de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="563f1-169">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="563f1-170">Após criar números de acesso de discagem, você pode usar o cmdlet <STRONG>set-CsDialInConferencingAccessNumber</STRONG> para modificar o nome de exibição dos objetos de contato do Active Directory de modo que os usuários possam identificar mais facilmente o número de acesso correto.</span><span class="sxs-lookup"><span data-stu-id="563f1-170">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="563f1-171">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="563f1-171">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="563f1-172">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-172">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="563f1-173">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-173">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="563f1-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configurar números de acesso de conferência discada no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="563f1-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="563f1-175"><strong>(Opcional) Verifique as configurações da conferência discada</strong></span><span class="sxs-lookup"><span data-stu-id="563f1-175"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="563f1-176">Use o cmdlet <strong>Get-CsDialinConferencingAccessNumber</strong> para pesquisar planos de discagem que tenham uma região de conferência discada que não seja usada por qualquer número de acesso e números de acesso que não possuam região atribuída.</span><span class="sxs-lookup"><span data-stu-id="563f1-176">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="563f1-177">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="563f1-177">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="563f1-178">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-178">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="563f1-179">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-179">CsAdministrator</span></span></p>
<p><span data-ttu-id="563f1-180">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-180">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="563f1-181">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="563f1-181">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="563f1-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">Opcion Verificar as configurações de conferência discada no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="563f1-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="563f1-183"><strong>(Opcional) Modifique o mapeamento de teclas dos comandos DTMF</strong></span><span class="sxs-lookup"><span data-stu-id="563f1-183"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="563f1-184">Use o cmdlet <strong>Set-CsDialinConferencingDtmfConfiguration</strong> para modificar as teclas usadas para comandos DTMF que os participantes podem usar para controlar as configurações da conferência (como silenciar e ativar ou travar e destravar).</span><span class="sxs-lookup"><span data-stu-id="563f1-184">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="563f1-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="563f1-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="563f1-186">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-186">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="563f1-187">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-187">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="563f1-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">Opcion Modificar o mapeamento de teclas para comandos DTMF no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="563f1-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="563f1-189"><strong>(Opcional) Modifique o comportamento do anúncio de entrada e saída da conferência</strong></span><span class="sxs-lookup"><span data-stu-id="563f1-189"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="563f1-190">Use o cmdlet <strong>Set-CsDialinConferencingConfiguration</strong> para alterar como os anúncios funcionam quando participantes entram e saem das conferências.</span><span class="sxs-lookup"><span data-stu-id="563f1-190">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="563f1-191">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="563f1-191">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="563f1-192">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-192">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="563f1-193">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-193">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="563f1-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">Opcion Habilitar e desabilitar comunicados de ingresso e saída de conferência no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="563f1-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="563f1-195"><strong>(Opcional) Verifique a conferência discada</strong></span><span class="sxs-lookup"><span data-stu-id="563f1-195"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="563f1-196">Use o cmdlet <strong>Test-CsDialInConferencing</strong> para testar se os números de acesso para o pool especificado estão funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="563f1-196">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="563f1-197">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="563f1-197">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="563f1-198">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-198">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="563f1-199">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-199">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="563f1-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">Opcion Verificar a conferência discada no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="563f1-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="563f1-201"><strong>Implantar o suplemento reunião online para Lync 2013</strong></span><span class="sxs-lookup"><span data-stu-id="563f1-201"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="563f1-202">Implante o suplemento reunião online do Lync 2013 para que os usuários possam agendar conferências que suportam conferência discada.</span><span class="sxs-lookup"><span data-stu-id="563f1-202">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="563f1-203">O suplemento de reunião online para Lync 2013 é instalado automaticamente quando você instala o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="563f1-203">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="563f1-204">Administradores</span><span class="sxs-lookup"><span data-stu-id="563f1-204">Administrators</span></span></p></td>
<td><p><span data-ttu-id="563f1-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Implantar o suplemento reunião online para Lync 2013</a></span><span class="sxs-lookup"><span data-stu-id="563f1-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="563f1-206"><strong>Defina as configurações da conta do usuário</strong></span><span class="sxs-lookup"><span data-stu-id="563f1-206"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="563f1-207">Use o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server para configurar o <strong>URI da linha</strong> de telefonia como um número de telefone normalizado exclusivo (por exemplo, Tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="563f1-207">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="563f1-208">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="563f1-208">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="563f1-209">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-209">CsAdministrator</span></span></p>
<p><span data-ttu-id="563f1-210">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="563f1-210">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="563f1-211"><a href="lync-server-2013-configure-user-account-settings.md">Definir configurações de conta de usuário no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="563f1-211"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="563f1-212">Recomenda Configurar diretórios de conferência</span><span class="sxs-lookup"><span data-stu-id="563f1-212">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="563f1-213">Use o cmdlet <strong>New-CsConferenceDirectory</strong> para criar um diretório de conferência para cada 999 usuários no pool.</span><span class="sxs-lookup"><span data-stu-id="563f1-213">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="563f1-214">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="563f1-214">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="563f1-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Requisitos de conferência discada no Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(recomendado) criar diretórios de conferência</a></span><span class="sxs-lookup"><span data-stu-id="563f1-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="563f1-216"><strong>(Opcional) Receba os usuários em conferências discadas e defina o PIN inicial</strong></span><span class="sxs-lookup"><span data-stu-id="563f1-216"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="563f1-217">Use o script <strong>set-CsPinSendCAWelcomeMail</strong> para definir os Pins iniciais dos usuários e enviar um email de boas-vindas que contém o PIN inicial e um link para a página Configurações de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="563f1-217">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="563f1-218">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="563f1-218">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="563f1-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">Opcion Usuários de boas-vindas para conferência discada no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="563f1-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

