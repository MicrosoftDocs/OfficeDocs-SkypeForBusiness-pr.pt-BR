---
title: 'Lync Server 2013: processo de implantação para estacionamento de chamada'
description: 'Lync Server 2013: processo de implantação para estacionamento de chamada.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 149252d39ba3fc0c552900c87e453c60e1651a08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575707"
---
# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="e1bd6-103">Processo de implantação para estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1bd6-103">Deployment process for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1bd6-104">_**Última modificação do tópico:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="e1bd6-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="e1bd6-105">Esta seção fornece uma visão geral das etapas envolvidas na implantação do aplicativo de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-105">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="e1bd6-106">Você deve implantar o Enterprise Edition ou Standard Edition com o Enterprise Voice antes de configurar o estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-106">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="e1bd6-107">Os componentes exigidos pelo estacionamento de chamada são instalados e habilitados quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-107">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="e1bd6-108">Implantação do Processo de Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="e1bd6-108">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1bd6-109">Fase</span><span class="sxs-lookup"><span data-stu-id="e1bd6-109">Phase</span></span></th>
<th><span data-ttu-id="e1bd6-110">Etapas</span><span class="sxs-lookup"><span data-stu-id="e1bd6-110">Steps</span></span></th>
<th><span data-ttu-id="e1bd6-111">Grupos e funções exigidos</span><span class="sxs-lookup"><span data-stu-id="e1bd6-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="e1bd6-112">Documentação da implantação</span><span class="sxs-lookup"><span data-stu-id="e1bd6-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1bd6-113">Configure os intervalos de órbita de estacionamento de chamada na tabela de órbita</span><span class="sxs-lookup"><span data-stu-id="e1bd6-113">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="e1bd6-114">Use o painel de controle do Lync Server ou o cmdlet <strong>New-CSCallParkOrbit</strong> para criar os intervalos de órbita na tabela de órbitas do estacionamento de chamada e associá-los ao serviço de aplicativo que hospeda o aplicativo de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-114">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e1bd6-p102">Para uma integração perfeita aos planos de discagem existentes, os intervalos de órbitas são normalmente considerados como um bloco de ramais virtuais. A atribuição dos números DID (Discagem Direta de Entrada) como números de órbita na tabela de órbita de estacionamento de chamada não é suportada.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-p102">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="e1bd6-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e1bd6-117">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e1bd6-118">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-118">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e1bd6-119">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-119">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e1bd6-120">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-120">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e1bd6-121"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Criar ou modificar um intervalo de órbita de estacionamento de chamada no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e1bd6-121"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1bd6-122">Definir configurações de Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="e1bd6-122">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="e1bd6-123">Use o cmdlet <strong>set-CsCpsConfiguration</strong> para definir as configurações de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-123">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="e1bd6-124">No mínimo, recomendamos que você configure a opção <strong>OnTimeoutURI</strong> para configurar o destino de fallback a ser usado quando uma chamada estacionada expirar. Você também pode definir as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="e1bd6-124">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="e1bd6-125">(Opcional) <strong>EnableMusicOnHold</strong> para ativar ou desativar música em espera.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-125">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="e1bd6-126">(Opcional) <strong>MaxCallPickupAttempts</strong> para determinar o número de vezes que uma chamada estacionada toca novamente no telefone de atendimento, antes de ser encaminhada para o URI (Uniform Resource Identifier) de fallback.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-126">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="e1bd6-127">(Opcional) <strong>CallPickupTimeoutThreshold</strong> para determinar o tempo decorrido depois que a chamada foi estacionada, antes que toque novamente no telefone em que foi atendida.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-127">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="e1bd6-128">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e1bd6-128">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e1bd6-129">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-129">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e1bd6-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-130">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e1bd6-131">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-131">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e1bd6-132"><a href="lync-server-2013-configure-call-park-settings.md">Definir configurações de estacionamento de chamadas no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e1bd6-132"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1bd6-133">Opcionalmente, personalize a música em espera</span><span class="sxs-lookup"><span data-stu-id="e1bd6-133">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="e1bd6-134">Use o cmdlet <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> para personalizar e carregar um arquivo de áudio, se você não deseja usar a música em espera padrão.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-134">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="e1bd6-135">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e1bd6-135">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e1bd6-136">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-136">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e1bd6-137">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-137">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e1bd6-138">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-138">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e1bd6-139"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Personalizar o estacionamento de chamada música em espera no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e1bd6-139"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1bd6-140">Configurar a política de voz para habilitar o estacionamento de chamada para usuários</span><span class="sxs-lookup"><span data-stu-id="e1bd6-140">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="e1bd6-141">Use o painel de controle do Lync Server ou o cmdlet <strong>set-CSVoicePolicy</strong> com a opção <strong>EnableCallPark</strong> para habilitar o estacionamento de chamadas para usuários na política de voz.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-141">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="e1bd6-142">Por padrão, o estacionamento de chamadas está desabilitado para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-142">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="e1bd6-143">Se você tiver diversas políticas de voz, veja se a propriedade EnableCallPark está configurada para cada política, não somente para a padrão.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-143">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="e1bd6-144">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e1bd6-144">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e1bd6-145">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-145">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e1bd6-146">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-146">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="e1bd6-147">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-147">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e1bd6-148"><a href="lync-server-2013-enable-call-park-for-users.md">Habilitar estacionamento de chamada para usuários no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e1bd6-148"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1bd6-149">Verificar regras de normalização para o Estacionamento de Chamada</span><span class="sxs-lookup"><span data-stu-id="e1bd6-149">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="e1bd6-p104">Órbitas de estacionamento de chamadas não devem ser normalizadas. Verifique se suas regras de normalização não incluem nenhum intervalo de órbita. Se necessário, crie regras adicionais de normalização para evitar órbitas normalizadas.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-p104">Call park orbits must not be normalized. Verify that your normalization rules do not include any of your orbit ranges. If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="e1bd6-153">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="e1bd6-153">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="e1bd6-154">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-154">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="e1bd6-155">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-155">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="e1bd6-156">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="e1bd6-156">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="e1bd6-157"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verificar regras de normalização para estacionamento de chamada no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e1bd6-157"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1bd6-158">Verificar a implantação do estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="e1bd6-158">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="e1bd6-159">Teste o estacionamento e a recuperação de chamadas para garantir que a configuração funcione conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="e1bd6-159">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="e1bd6-160"><a href="lync-server-2013-optional-verify-call-park-deployment.md">Opcion Verificar a implantação do estacionamento de chamada no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="e1bd6-160"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

