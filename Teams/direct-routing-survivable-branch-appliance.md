---
title: SBA de Roteamento Direto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre o Roteamento Direto, como configuração, decisões de implantação principais necessárias e considerações de roteamento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fb8812fd025317eb9c6e3c67ce1f5fcea094978
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196485"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a><span data-ttu-id="e0626-103">SBA (Dispositivo de Ramificação Sobrevável) para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="e0626-103">Survivable Branch Appliance (SBA) for Direct Routing</span></span>


<span data-ttu-id="e0626-104">Ocasionalmente, um site do cliente que usa Roteamento Direto para se conectar ao Microsoft Phone System pode ter uma queda na Internet.</span><span class="sxs-lookup"><span data-stu-id="e0626-104">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="e0626-105">Suponha que o site do cliente, chamado de ramificação, temporariamente não possa se conectar à nuvem da Microsoft por meio do Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="e0626-105">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="e0626-106">No entanto, a intranet dentro da ramificação ainda é totalmente funcional e os usuários podem se conectar ao Controlador de Borda de Sessão (SBC) que fornece conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="e0626-106">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="e0626-107">Este artigo descreve como usar um SBA (Dispositivo de Ramificação Sobrevável) para permitir que o Microsoft Phone System continue a fazer e receber chamadas PSTN (Rede Telefônica Pública Comutado) no caso de uma paralisação.</span><span class="sxs-lookup"><span data-stu-id="e0626-107">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e0626-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e0626-108">Prerequisites</span></span>

<span data-ttu-id="e0626-109">O SBA é um código distribuível fornecido pela Microsoft para fornecedores SBC que, em seguida, insemitem código em seu firmware ou o distribuem separadamente para que o SBA seja executado em um VM ou hardware separado.</span><span class="sxs-lookup"><span data-stu-id="e0626-109">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="e0626-110">Para obter o firmware mais recente do Controlador de Borda de Sessão com o Dispositivo de Ramificação Sobrevável inserido, entre em contato com o fornecedor SBC.</span><span class="sxs-lookup"><span data-stu-id="e0626-110">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="e0626-111">Além disso, é necessário fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e0626-111">In addition, the following is required:</span></span>

- <span data-ttu-id="e0626-112">O SBC precisa ser configurado para o Bypass de Mídia para garantir que o cliente do Microsoft Teams no site de ramificação possa ter mídia fluindo diretamente com o SBC.</span><span class="sxs-lookup"><span data-stu-id="e0626-112">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="e0626-113">O TLS1.2 deve estar habilitado no sistema operacional VM SBA.</span><span class="sxs-lookup"><span data-stu-id="e0626-113">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="e0626-114">Clientes do Teams com suporte</span><span class="sxs-lookup"><span data-stu-id="e0626-114">Supported Teams clients</span></span>

<span data-ttu-id="e0626-115">O recurso SBA tem suporte nos seguintes clientes do Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="e0626-115">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="e0626-116">Área de trabalho do Microsoft Teams para Windows</span><span class="sxs-lookup"><span data-stu-id="e0626-116">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="e0626-117">Área de trabalho do Microsoft Teams macOS</span><span class="sxs-lookup"><span data-stu-id="e0626-117">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="e0626-118">Como funciona</span><span class="sxs-lookup"><span data-stu-id="e0626-118">How it works</span></span>

<span data-ttu-id="e0626-119">Durante uma interrupção na Internet, o cliente do Teams deve alternar para o SBA automaticamente e as chamadas em andamento devem continuar sem interrupções.</span><span class="sxs-lookup"><span data-stu-id="e0626-119">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="e0626-120">Nenhuma ação é necessária do usuário.</span><span class="sxs-lookup"><span data-stu-id="e0626-120">No action is required from the user.</span></span> <span data-ttu-id="e0626-121">Assim que o cliente do Teams detectar que a Internet está pronta e todas as chamadas de saída terminarem, o cliente voltará ao modo de operação normal e se conectará a outros serviços do Teams.</span><span class="sxs-lookup"><span data-stu-id="e0626-121">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="e0626-122">O SBA carregará registros de dados de chamada coletados na nuvem e o histórico de chamada será atualizado para que essas informações sejam disponibilizadas para revisão pelo administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="e0626-122">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="e0626-123">Quando o cliente do Microsoft Teams está no modo offline, a seguinte funcionalidade relacionada a chamada está disponível:</span><span class="sxs-lookup"><span data-stu-id="e0626-123">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="e0626-124">Fazer chamadas PSTN via SBA/SBC local com mídia fluindo pelo SBC.</span><span class="sxs-lookup"><span data-stu-id="e0626-124">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="e0626-125">Receber chamadas PSTN via SBA/SBC local com mídia fluindo pelo SBC.</span><span class="sxs-lookup"><span data-stu-id="e0626-125">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="e0626-126">Espera e Currículo de chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="e0626-126">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="e0626-127">Configuração</span><span class="sxs-lookup"><span data-stu-id="e0626-127">Configuration</span></span>

<span data-ttu-id="e0626-128">Para que o recurso SBA funcione, o cliente do Teams precisa saber quais SBAs estão disponíveis em cada site de ramificação e quais SBAs são atribuídos aos usuários nesse site.</span><span class="sxs-lookup"><span data-stu-id="e0626-128">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="e0626-129">As etapas de configuração são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="e0626-129">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="e0626-130">Crie os SBAs.</span><span class="sxs-lookup"><span data-stu-id="e0626-130">Create the SBAs.</span></span>
2. <span data-ttu-id="e0626-131">Crie a política de sobreabilidade de ramificação do Teams.</span><span class="sxs-lookup"><span data-stu-id="e0626-131">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="e0626-132">Atribua a política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="e0626-132">Assign the policy to users.</span></span>
4. <span data-ttu-id="e0626-133">Registre um aplicativo para o SBA com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e0626-133">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="e0626-134">Toda a configuração é feita usando cmdlets do PowerShell do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="e0626-134">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="e0626-135">(O Centro de administração do Teams ainda não dá suporte ao recurso SBA de Roteamento Direto.)</span><span class="sxs-lookup"><span data-stu-id="e0626-135">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="e0626-136">(Para obter informações sobre como configurar o SBC, com links para a documentação do fornecedor SBC, consulte a configuração do Controlador de Borda de Sessão no final deste artigo.)</span><span class="sxs-lookup"><span data-stu-id="e0626-136">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="e0626-137">Criar os SBAs</span><span class="sxs-lookup"><span data-stu-id="e0626-137">Create the SBAs</span></span>

<span data-ttu-id="e0626-138">Para criar os SBAs, você usará o cmdlet New-CsTeamsSurvivableBranchAppliance dados.</span><span class="sxs-lookup"><span data-stu-id="e0626-138">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="e0626-139">Este cmdlet tem os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="e0626-139">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="e0626-140">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="e0626-140">Parameter</span></span>| <span data-ttu-id="e0626-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="e0626-141">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="e0626-142">Identidade</span><span class="sxs-lookup"><span data-stu-id="e0626-142">Identity</span></span>  | <span data-ttu-id="e0626-143">A identidade do SBA</span><span class="sxs-lookup"><span data-stu-id="e0626-143">The identity of the SBA</span></span>  |
| <span data-ttu-id="e0626-144">Fqdn</span><span class="sxs-lookup"><span data-stu-id="e0626-144">Fqdn</span></span> | <span data-ttu-id="e0626-145">O FQDN do SBA</span><span class="sxs-lookup"><span data-stu-id="e0626-145">The FQDN of the SBA</span></span> |
| <span data-ttu-id="e0626-146">Site</span><span class="sxs-lookup"><span data-stu-id="e0626-146">Site</span></span> | <span data-ttu-id="e0626-147">O TenantNetworkSite onde o SBA está localizado</span><span class="sxs-lookup"><span data-stu-id="e0626-147">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="e0626-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="e0626-148">Description</span></span> | <span data-ttu-id="e0626-149">Formatar texto gratuito</span><span class="sxs-lookup"><span data-stu-id="e0626-149">Free format text</span></span> |
|||

<span data-ttu-id="e0626-150">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e0626-150">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="e0626-151">Criar a Política de Surviabilidade de Ramificação do Teams</span><span class="sxs-lookup"><span data-stu-id="e0626-151">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="e0626-152">Para criar uma política, use o cmdlet New-CsTeamsSurvivableBranchAppliancePolicy dados.</span><span class="sxs-lookup"><span data-stu-id="e0626-152">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="e0626-153">Este cmdlet tem os seguintes parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e0626-153">This cmdlet has the following parameters.</span></span> <span data-ttu-id="e0626-154">Observe que a política pode conter um ou mais SBAs.</span><span class="sxs-lookup"><span data-stu-id="e0626-154">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="e0626-155">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="e0626-155">Parameter</span></span>| <span data-ttu-id="e0626-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="e0626-156">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="e0626-157">Identidade</span><span class="sxs-lookup"><span data-stu-id="e0626-157">Identity</span></span> | <span data-ttu-id="e0626-158">A identidade da política</span><span class="sxs-lookup"><span data-stu-id="e0626-158">The identity of the policy</span></span> |
| <span data-ttu-id="e0626-159">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="e0626-159">BranchApplianceFqdns</span></span>  | <span data-ttu-id="e0626-160">O FQDN dos SBA(s) no site</span><span class="sxs-lookup"><span data-stu-id="e0626-160">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="e0626-161">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e0626-161">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="e0626-162">Você pode adicionar ou remover SBAs de uma política usando o cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy dados.</span><span class="sxs-lookup"><span data-stu-id="e0626-162">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="e0626-163">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e0626-163">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="e0626-164">Atribuir uma política a um usuário</span><span class="sxs-lookup"><span data-stu-id="e0626-164">Assign a policy to a user</span></span>

<span data-ttu-id="e0626-165">Para atribuir a política a usuários individuais, você usará o cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy usuário.</span><span class="sxs-lookup"><span data-stu-id="e0626-165">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="e0626-166">Este cmdlet tem os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="e0626-166">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="e0626-167">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="e0626-167">Parameter</span></span>| <span data-ttu-id="e0626-168">Descrição</span><span class="sxs-lookup"><span data-stu-id="e0626-168">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="e0626-169">Identidade</span><span class="sxs-lookup"><span data-stu-id="e0626-169">Identity</span></span> | <span data-ttu-id="e0626-170">A identidade do usuário</span><span class="sxs-lookup"><span data-stu-id="e0626-170">The identity of the user</span></span> |
| <span data-ttu-id="e0626-171">Policyname</span><span class="sxs-lookup"><span data-stu-id="e0626-171">PolicyName</span></span> | <span data-ttu-id="e0626-172">A identidade da política</span><span class="sxs-lookup"><span data-stu-id="e0626-172">The identity of the policy</span></span> |
||

<span data-ttu-id="e0626-173">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e0626-173">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="e0626-174">Você pode remover uma política de um usuário concedendo a política de $Null conforme mostrado no próximo exemplo:</span><span class="sxs-lookup"><span data-stu-id="e0626-174">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="e0626-175">Registrar um aplicativo para o SBA com o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e0626-175">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="e0626-176">Para permitir que diferentes SBAs usados em seu locatário leiam os dados necessários do Microsoft 365, você precisa registrar um aplicativo para o SBA com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e0626-176">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="e0626-177">Para obter mais informações sobre o registro do aplicativo, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e0626-177">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="e0626-178">Desenvolver aplicativos de linha de negócios para o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e0626-178">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="e0626-179">[Registre um aplicativo com a plataforma de identidade da Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)</span><span class="sxs-lookup"><span data-stu-id="e0626-179">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="e0626-180">Você só precisa registrar um aplicativo para uso por todos os SBAs em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="e0626-180">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="e0626-181">Para o registro do SBA, você precisa dos seguintes valores criados pelo registro:</span><span class="sxs-lookup"><span data-stu-id="e0626-181">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="e0626-182">ID do aplicativo (cliente)</span><span class="sxs-lookup"><span data-stu-id="e0626-182">Application (client) ID</span></span> 
- <span data-ttu-id="e0626-183">Segredo do cliente</span><span class="sxs-lookup"><span data-stu-id="e0626-183">Client secret</span></span> 

<span data-ttu-id="e0626-184">Para o aplicativo SBA, lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="e0626-184">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="e0626-185">O nome pode ser o que você decidir.</span><span class="sxs-lookup"><span data-stu-id="e0626-185">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="e0626-186">Tipos de conta com suporte = Conta somente neste diretório organizacional.</span><span class="sxs-lookup"><span data-stu-id="e0626-186">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="e0626-187">O Uri de Redirecionamento da Web = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="e0626-187">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="e0626-188">Tokens de concessão implícitos = tokens do Access e tokens de ID.</span><span class="sxs-lookup"><span data-stu-id="e0626-188">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="e0626-189">Permissões de API = Acesso de Administrador de Locatários do Skype e do Teams > permissões de aplicativo -> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="e0626-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="e0626-190">Segredo do cliente: você pode usar qualquer descrição e expiração.</span><span class="sxs-lookup"><span data-stu-id="e0626-190">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="e0626-191">Lembre-se de copiar o segredo do cliente imediatamente após a criação.</span><span class="sxs-lookup"><span data-stu-id="e0626-191">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="e0626-192">A ID do Aplicativo (cliente) é mostrada na guia Visão Geral.</span><span class="sxs-lookup"><span data-stu-id="e0626-192">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="e0626-193">Em seguida, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e0626-193">Then follow these steps:</span></span>

1. <span data-ttu-id="e0626-194">Registre o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e0626-194">Register the application.</span></span>
2. <span data-ttu-id="e0626-195">De definir os tokens implícitos de concessão.</span><span class="sxs-lookup"><span data-stu-id="e0626-195">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="e0626-196">Definir as permissões da API.</span><span class="sxs-lookup"><span data-stu-id="e0626-196">Set the API permissions.</span></span>
4. <span data-ttu-id="e0626-197">Crie o segredo do cliente.</span><span class="sxs-lookup"><span data-stu-id="e0626-197">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="e0626-198">Configuração do Controlador de Borda de Sessão</span><span class="sxs-lookup"><span data-stu-id="e0626-198">Session Border Controller configuration</span></span> 

<span data-ttu-id="e0626-199">Para obter orientações passo a passo sobre como configurar o Controlador de Borda de Sessão com o Dispositivo de Ramificação Sobrevável inserido, consulte a documentação fornecida pelo fornecedor SBC:</span><span class="sxs-lookup"><span data-stu-id="e0626-199">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="e0626-200">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="e0626-200">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="e0626-201">Fita</span><span class="sxs-lookup"><span data-stu-id="e0626-201">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="e0626-202">Oracle</span><span class="sxs-lookup"><span data-stu-id="e0626-202">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="e0626-203">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="e0626-203">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="e0626-204">Relatar problemas</span><span class="sxs-lookup"><span data-stu-id="e0626-204">Reporting issues</span></span>

<span data-ttu-id="e0626-205">Relatar problemas à organização de suporte do fornecedor SBC.</span><span class="sxs-lookup"><span data-stu-id="e0626-205">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="e0626-206">Ao relatar o problema, indique que você configurou um Dispositivo de Ramificação Sobrevável.</span><span class="sxs-lookup"><span data-stu-id="e0626-206">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="e0626-207">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="e0626-207">Known issues</span></span>

- <span data-ttu-id="e0626-208">Quando você adiciona novos Dispositivos de Ramificação Sobreváveis, pode levar algum tempo até que você possa usá-los nas políticas do Dispositivo de Ramificação Sobrevável.</span><span class="sxs-lookup"><span data-stu-id="e0626-208">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="e0626-209">Quando você atribui uma política de Dispositivo de Ramificação Sobrevável a um usuário, pode levar algum tempo até que o SBA seja mostrado na saída do Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="e0626-209">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="e0626-210">A operação de inversão de número em Contatos do Azure AD não é executada.</span><span class="sxs-lookup"><span data-stu-id="e0626-210">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="e0626-211">O SBA não dá suporte às configurações de encaminhamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="e0626-211">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="e0626-212">Não há suporte para fazer uma chamada de emergência para um número de emergência configurado para chamada de emergência dinâmica (E911).</span><span class="sxs-lookup"><span data-stu-id="e0626-212">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="e0626-213">A saída do Get-CsOnlineUser mostra TeamsBranchSuráveisPolicy.</span><span class="sxs-lookup"><span data-stu-id="e0626-213">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
