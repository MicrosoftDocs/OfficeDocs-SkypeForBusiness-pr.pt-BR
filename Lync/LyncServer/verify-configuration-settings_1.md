---
title: Verifique as configurações
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9871d16c3e5b0af894653ac5d60c4614201e8e24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="74d7a-102">Verifique as configurações</span><span class="sxs-lookup"><span data-stu-id="74d7a-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74d7a-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="74d7a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="74d7a-104">Após mesclar a topologia e executar o cmdlet **Import-CsLegacyConfiguration** , verifique se as políticas e configurações do Office Communications Server 2007 R2 foram importadas para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74d7a-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="74d7a-105">A tabela a seguir lista as políticas e configurações que você deve verificar.</span><span class="sxs-lookup"><span data-stu-id="74d7a-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="74d7a-106">Políticas e configurações para verificar após a migração</span><span class="sxs-lookup"><span data-stu-id="74d7a-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74d7a-107">Se você usar esta carga de trabalho:</span><span class="sxs-lookup"><span data-stu-id="74d7a-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="74d7a-108">Verifique estas políticas e configurações:</span><span class="sxs-lookup"><span data-stu-id="74d7a-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74d7a-109">IM (mensagens instantâneas) e conferências</span><span class="sxs-lookup"><span data-stu-id="74d7a-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="74d7a-110">Política de presença</span><span class="sxs-lookup"><span data-stu-id="74d7a-110">Presence policy</span></span></p>
<p><span data-ttu-id="74d7a-111">Política de conferência</span><span class="sxs-lookup"><span data-stu-id="74d7a-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74d7a-112">Conferência Discada</span><span class="sxs-lookup"><span data-stu-id="74d7a-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="74d7a-113">Números de acesso de discagem</span><span class="sxs-lookup"><span data-stu-id="74d7a-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="74d7a-114">Planos de discagem</span><span class="sxs-lookup"><span data-stu-id="74d7a-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74d7a-115">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="74d7a-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="74d7a-116">Política de voz</span><span class="sxs-lookup"><span data-stu-id="74d7a-116">Voice policy</span></span></p>
<p><span data-ttu-id="74d7a-117">Roteamentos de voz</span><span class="sxs-lookup"><span data-stu-id="74d7a-117">Voice routes</span></span></p>
<p><span data-ttu-id="74d7a-118">Planos de discagem</span><span class="sxs-lookup"><span data-stu-id="74d7a-118">Dial plans</span></span></p>
<p><span data-ttu-id="74d7a-119">Configurações de uso do PSTN</span><span class="sxs-lookup"><span data-stu-id="74d7a-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74d7a-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="74d7a-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="74d7a-121">URLs simples</span><span class="sxs-lookup"><span data-stu-id="74d7a-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74d7a-122">Usuários externos</span><span class="sxs-lookup"><span data-stu-id="74d7a-122">External users</span></span></p></td>
<td><p><span data-ttu-id="74d7a-123">Políticas externas de acesso</span><span class="sxs-lookup"><span data-stu-id="74d7a-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74d7a-124">Arquivamento</span><span class="sxs-lookup"><span data-stu-id="74d7a-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="74d7a-125">Política de arquivamento</span><span class="sxs-lookup"><span data-stu-id="74d7a-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="74d7a-126">Para verificar as políticas e configurações</span><span class="sxs-lookup"><span data-stu-id="74d7a-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="74d7a-127">No ambiente do Office Communications Server 2007 R2, anote os nomes dos planos de discagem (anteriormente conhecidos como perfis de local), números de acesso de discagem (números de telefone e regiões de acesso de atendedor de conferência), rotas de voz e as políticas listadas na tabela anterior, além das URLs usadas para o Communicator Web Access.</span><span class="sxs-lookup"><span data-stu-id="74d7a-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="74d7a-128">No servidor front-end do Lync Server 2013, abra o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74d7a-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="74d7a-129">Para verificar as políticas de conferência importadas, no painel esquerdo, clique em **conferência**, em **política de conferência**e verifique se todas as políticas de conferência no seu ambiente do Office Communications Server 2007 R2 estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="74d7a-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74d7a-130">A política de <STRONG>reunião</STRONG> de versões anteriores do Office Communications Server agora é conhecida como a política de conferência no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74d7a-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="74d7a-131">Além disso, a configuração <STRONG>particpants anônima</STRONG> de versões anteriores do Office Communications Server agora é uma configuração na política de conferência do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74d7a-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74d7a-132">No Office Communications Server 2007 R2, se a política de conferência não estiver definida para <STRONG>uso por usuário</STRONG>, somente as configurações de política global serão importadas.</span><span class="sxs-lookup"><span data-stu-id="74d7a-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="74d7a-133">Nenhuma outra política de conferência é importada nessa situação.</span><span class="sxs-lookup"><span data-stu-id="74d7a-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74d7a-134">Se <STRONG>os participantes anônimos</STRONG> estiverem configurados para <STRONG>impor por usuário</STRONG> em sua política de conferência do Office Communications Server 2007 R2, duas políticas de conferência são criadas durante a migração: uma com <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> definido como <STRONG>true</STRONG> e uma com <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> definido como <STRONG>false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="74d7a-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="74d7a-135">Para verificar planos importados, clique em **Roteamento de voz**, clique em **Plano de discagem** e, então, verifique se todos os planos de discagem no seu ambiente Office Communicator 2007 R2 estão incluídos na lista.</span><span class="sxs-lookup"><span data-stu-id="74d7a-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74d7a-136">No Lync Server 2013, os <STRONG>perfis de local</STRONG> agora são chamados de planos de <STRONG>discagem</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="74d7a-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="74d7a-137">Para verificar políticas de voz importadas, clique em **Roteamento de voz**, clique em **Política de voz** e, então, verifique se todas as suas políticas de voz do ambiente Office Communicator 2007 R2 estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="74d7a-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74d7a-138">Se a política de voz não estiver configurada para <STRONG>uso por usuário</STRONG> no seu ambiente do Office Communications Server 2007 R2, somente as configurações de política global serão importadas.</span><span class="sxs-lookup"><span data-stu-id="74d7a-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="74d7a-139">Nenhuma outra política de voz é importada nesta situação.</span><span class="sxs-lookup"><span data-stu-id="74d7a-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="74d7a-140">Para verificar rotas de voz importadas, clique em **Rota de voz**, clique em **Rota** e, então, verifique se todas as rotas de voz no seu ambiente Office Communicator 2007 R2 estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="74d7a-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="74d7a-141">Para verificar configurações de uso do PSTN, clique em **Roteamento de voz**, clique em **Uso do PSTN** e, então, verifique se as configurações de Uso do PSTN do seu ambiente Office Communicator 2007 R2 foram incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="74d7a-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="74d7a-142">Para verificar políticas de acesso externo importadas, clique em **Federação e acesso externo**, clique em **Política de acesso externo** e, então, verifique se todas as políticas de acesso externo no seu ambiente Office Communicator 2007 R2 estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="74d7a-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="74d7a-143">Para verificar as políticas de arquivamento, clique em **monitoramento e arquivamento**, em **política de arquivamento**e verifique se todas as políticas de arquivamento no seu ambiente do Office Communications Server 2007 R2 estão incluídas na lista.</span><span class="sxs-lookup"><span data-stu-id="74d7a-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="74d7a-144">Abra o Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74d7a-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="74d7a-145">Para verificar as políticas de presença, na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="74d7a-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="74d7a-146">Olhando o nome no parâmetro **Identity** , verifique se todas as políticas de presença no ambiente do Office Communications Server 2007 R2 foram importadas.</span><span class="sxs-lookup"><span data-stu-id="74d7a-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="74d7a-147">Para verificar as políticas e configurações usando cmdlets</span><span class="sxs-lookup"><span data-stu-id="74d7a-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="74d7a-148">Abra o Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74d7a-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="74d7a-149">Execute os cmdlets na tabela a seguir para verificar as políticas e configurações.</span><span class="sxs-lookup"><span data-stu-id="74d7a-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="74d7a-150">A sintaxe desses cmdlets é como o exemplo abaixo:</span><span class="sxs-lookup"><span data-stu-id="74d7a-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="74d7a-151">Para detalhes sobre esses cmdlets, execute:</span><span class="sxs-lookup"><span data-stu-id="74d7a-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74d7a-152">Para essa política ou configuração:</span><span class="sxs-lookup"><span data-stu-id="74d7a-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="74d7a-153">Utilize este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="74d7a-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74d7a-154">Política de presença</span><span class="sxs-lookup"><span data-stu-id="74d7a-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="74d7a-155"><strong>Get-CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="74d7a-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74d7a-156">Política de conferência</span><span class="sxs-lookup"><span data-stu-id="74d7a-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="74d7a-157"><strong>Get-CsConferencingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="74d7a-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74d7a-158">Números de acesso de discagem</span><span class="sxs-lookup"><span data-stu-id="74d7a-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="74d7a-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span><span class="sxs-lookup"><span data-stu-id="74d7a-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74d7a-160">Planos de discagem</span><span class="sxs-lookup"><span data-stu-id="74d7a-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="74d7a-161"><strong>Get-CsDialPlan</strong></span><span class="sxs-lookup"><span data-stu-id="74d7a-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74d7a-162">Política de voz</span><span class="sxs-lookup"><span data-stu-id="74d7a-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="74d7a-163"><strong>Get-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="74d7a-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74d7a-164">Rotas de voz</span><span class="sxs-lookup"><span data-stu-id="74d7a-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="74d7a-165"><strong>Get-CsVoiceRoute</strong></span><span class="sxs-lookup"><span data-stu-id="74d7a-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74d7a-166">Uso de PSTN</span><span class="sxs-lookup"><span data-stu-id="74d7a-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="74d7a-167"><strong>Get-CsPstnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="74d7a-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74d7a-168">URLs</span><span class="sxs-lookup"><span data-stu-id="74d7a-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="74d7a-169"><strong>Get-CsSimpleUrlConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="74d7a-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74d7a-170">Políticas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="74d7a-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="74d7a-171"><strong>Get-CsExternalAccessPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="74d7a-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74d7a-172">Política de arquivamento</span><span class="sxs-lookup"><span data-stu-id="74d7a-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="74d7a-173"><strong>Get-CsArchivingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="74d7a-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

