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
description: Saiba mais sobre Roteamento Direto, como configuração, decisões de implantação principais necessárias e considerações de roteamento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d6342f41b3cd4bfad690794c0b6474ca45e78c8
ms.sourcegitcommit: bdd9901db1fc741aaec9c7ddcf5ee1caaca4d777
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52589235"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a><span data-ttu-id="8c590-103">Aparelho de Filial Desavivável (SBA) para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="8c590-103">Survivable Branch Appliance (SBA) for Direct Routing</span></span>


<span data-ttu-id="8c590-104">Ocasionalmente, um site do cliente que usa Roteamento Direto para se conectar ao Telefone Microsoft System pode ter uma paralisação na Internet.</span><span class="sxs-lookup"><span data-stu-id="8c590-104">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="8c590-105">Suponha que o site do cliente , chamado de filial, temporariamente não possa se conectar à nuvem da Microsoft por meio do Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="8c590-105">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="8c590-106">No entanto, a intranet dentro da filial ainda está totalmente funcional e os usuários podem se conectar ao Controlador de Borda de Sessão (SBC) que está fornecendo conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="8c590-106">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="8c590-107">Este artigo descreve como usar um Aparelho de Filial Desavivável (SBA) para permitir que o sistema Telefone Microsoft continue a fazer e receber chamadas PSTN (Rede Telefônica Pública Comutado) no caso de uma paralisação.</span><span class="sxs-lookup"><span data-stu-id="8c590-107">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c590-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8c590-108">Prerequisites</span></span>

<span data-ttu-id="8c590-109">O SBA é um código distribuível fornecido pela Microsoft para fornecedores SBC que, em seguida, incorporam código em seu firmware ou o distribuem separadamente para que o SBA seja executado em uma VM ou hardware separado.</span><span class="sxs-lookup"><span data-stu-id="8c590-109">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="8c590-110">Para obter o firmware mais recente do Controlador de Borda de Sessão com o Aparelho de Filial Suportável incorporado, entre em contato com o fornecedor SBC.</span><span class="sxs-lookup"><span data-stu-id="8c590-110">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="8c590-111">Além disso, o seguinte é necessário:</span><span class="sxs-lookup"><span data-stu-id="8c590-111">In addition, the following is required:</span></span>

- <span data-ttu-id="8c590-112">O SBC precisa ser configurado para Bypass de Mídia para garantir que o cliente Microsoft Teams no site de filial possa ter a mídia fluindo diretamente com o SBC.</span><span class="sxs-lookup"><span data-stu-id="8c590-112">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="8c590-113">O TLS1.2 deve estar habilitado no sistema operacional VM do SBA.</span><span class="sxs-lookup"><span data-stu-id="8c590-113">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="8c590-114">Clientes Teams com suporte</span><span class="sxs-lookup"><span data-stu-id="8c590-114">Supported Teams clients</span></span>

<span data-ttu-id="8c590-115">O recurso SBA é suportado nos seguintes clientes Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="8c590-115">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="8c590-116">Microsoft Teams Windows desktop</span><span class="sxs-lookup"><span data-stu-id="8c590-116">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="8c590-117">Microsoft Teams macOS desktop</span><span class="sxs-lookup"><span data-stu-id="8c590-117">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="8c590-118">Como funciona</span><span class="sxs-lookup"><span data-stu-id="8c590-118">How it works</span></span>

<span data-ttu-id="8c590-119">Durante uma interrupção na Internet, Teams cliente deve alternar para o SBA automaticamente e as chamadas em andamento devem continuar sem interrupções.</span><span class="sxs-lookup"><span data-stu-id="8c590-119">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="8c590-120">Nenhuma ação é necessária do usuário.</span><span class="sxs-lookup"><span data-stu-id="8c590-120">No action is required from the user.</span></span> <span data-ttu-id="8c590-121">Assim que o cliente Teams detectar que a Internet está em funcionamento e todas as chamadas de saída são concluídas, o cliente retornará ao modo de operação normal e se conectará a outros serviços Teams serviços.</span><span class="sxs-lookup"><span data-stu-id="8c590-121">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="8c590-122">O SBA carregará registros de dados de chamada coletados na nuvem e o histórico de chamada será atualizado para que essas informações sejam disponibilizadas para revisão pelo administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="8c590-122">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="8c590-123">Quando o Microsoft Teams cliente está no modo offline, a seguinte funcionalidade relacionada a chamada está disponível:</span><span class="sxs-lookup"><span data-stu-id="8c590-123">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="8c590-124">Fazendo chamadas PSTN via SBA/SBC local com a mídia fluindo através do SBC.</span><span class="sxs-lookup"><span data-stu-id="8c590-124">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="8c590-125">Receber chamadas PSTN por meio de SBA/SBC local com mídia fluindo pelo SBC.</span><span class="sxs-lookup"><span data-stu-id="8c590-125">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="8c590-126">Espera e retomada de chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="8c590-126">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="8c590-127">Configuração</span><span class="sxs-lookup"><span data-stu-id="8c590-127">Configuration</span></span>

<span data-ttu-id="8c590-128">Para que o recurso SBA funcione, o cliente Teams precisa saber quais SBAs estão disponíveis em cada site de filial e quais SBAs são atribuídos aos usuários nesse site.</span><span class="sxs-lookup"><span data-stu-id="8c590-128">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="8c590-129">As etapas de configuração são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="8c590-129">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="8c590-130">Crie os SBAs.</span><span class="sxs-lookup"><span data-stu-id="8c590-130">Create the SBAs.</span></span>
2. <span data-ttu-id="8c590-131">Crie a Teams de sobrevivência de filial.</span><span class="sxs-lookup"><span data-stu-id="8c590-131">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="8c590-132">Atribua a política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="8c590-132">Assign the policy to users.</span></span>
4. <span data-ttu-id="8c590-133">Registre um aplicativo para o SBA com Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8c590-133">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="8c590-134">Toda a configuração é feita usando Skype for Business cmdlets do PowerShell Online.</span><span class="sxs-lookup"><span data-stu-id="8c590-134">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="8c590-135">(O Teams de administração do Teams ainda não dá suporte ao recurso SBA de Roteamento Direto.)</span><span class="sxs-lookup"><span data-stu-id="8c590-135">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="8c590-136">(Para obter informações sobre como configurar o SBC, com links para a documentação do fornecedor SBC, consulte Session Border Controller configuration at the end of this article.)</span><span class="sxs-lookup"><span data-stu-id="8c590-136">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="8c590-137">Criar os SBAs</span><span class="sxs-lookup"><span data-stu-id="8c590-137">Create the SBAs</span></span>

<span data-ttu-id="8c590-138">Para criar os SBAs, você usará o cmdlet New-CsTeamsSurvivableBranchAppliance.</span><span class="sxs-lookup"><span data-stu-id="8c590-138">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="8c590-139">Este cmdlet tem os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="8c590-139">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="8c590-140">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="8c590-140">Parameter</span></span>| <span data-ttu-id="8c590-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="8c590-141">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="8c590-142">Identidade</span><span class="sxs-lookup"><span data-stu-id="8c590-142">Identity</span></span>  | <span data-ttu-id="8c590-143">A identidade do SBA</span><span class="sxs-lookup"><span data-stu-id="8c590-143">The identity of the SBA</span></span>  |
| <span data-ttu-id="8c590-144">Fqdn</span><span class="sxs-lookup"><span data-stu-id="8c590-144">Fqdn</span></span> | <span data-ttu-id="8c590-145">O FQDN do SBA</span><span class="sxs-lookup"><span data-stu-id="8c590-145">The FQDN of the SBA</span></span> |
| <span data-ttu-id="8c590-146">Site</span><span class="sxs-lookup"><span data-stu-id="8c590-146">Site</span></span> | <span data-ttu-id="8c590-147">TenantNetworkSite onde o SBA está localizado</span><span class="sxs-lookup"><span data-stu-id="8c590-147">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="8c590-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="8c590-148">Description</span></span> | <span data-ttu-id="8c590-149">Texto de formato livre</span><span class="sxs-lookup"><span data-stu-id="8c590-149">Free format text</span></span> |
|||

<span data-ttu-id="8c590-150">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8c590-150">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="8c590-151">Criar a política Teams de sobrevivência de filial</span><span class="sxs-lookup"><span data-stu-id="8c590-151">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="8c590-152">Para criar uma política, use o cmdlet New-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="8c590-152">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="8c590-153">Este cmdlet tem os seguintes parâmetros.</span><span class="sxs-lookup"><span data-stu-id="8c590-153">This cmdlet has the following parameters.</span></span> <span data-ttu-id="8c590-154">Observe que a política pode conter um ou mais SBAs.</span><span class="sxs-lookup"><span data-stu-id="8c590-154">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="8c590-155">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="8c590-155">Parameter</span></span>| <span data-ttu-id="8c590-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="8c590-156">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="8c590-157">Identidade</span><span class="sxs-lookup"><span data-stu-id="8c590-157">Identity</span></span> | <span data-ttu-id="8c590-158">A identidade da política</span><span class="sxs-lookup"><span data-stu-id="8c590-158">The identity of the policy</span></span> |
| <span data-ttu-id="8c590-159">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="8c590-159">BranchApplianceFqdns</span></span>  | <span data-ttu-id="8c590-160">O FQDN dos SBA(s) no site</span><span class="sxs-lookup"><span data-stu-id="8c590-160">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="8c590-161">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8c590-161">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="8c590-162">Você pode adicionar ou remover SBAs de uma política usando o cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="8c590-162">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="8c590-163">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8c590-163">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="8c590-164">Atribuir uma política a um usuário</span><span class="sxs-lookup"><span data-stu-id="8c590-164">Assign a policy to a user</span></span>

<span data-ttu-id="8c590-165">Para atribuir a política a usuários individuais, você usará o cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy usuário.</span><span class="sxs-lookup"><span data-stu-id="8c590-165">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="8c590-166">Este cmdlet tem os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="8c590-166">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="8c590-167">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="8c590-167">Parameter</span></span>| <span data-ttu-id="8c590-168">Descrição</span><span class="sxs-lookup"><span data-stu-id="8c590-168">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="8c590-169">Identidade</span><span class="sxs-lookup"><span data-stu-id="8c590-169">Identity</span></span> | <span data-ttu-id="8c590-170">A identidade do usuário</span><span class="sxs-lookup"><span data-stu-id="8c590-170">The identity of the user</span></span> |
| <span data-ttu-id="8c590-171">PolicyName</span><span class="sxs-lookup"><span data-stu-id="8c590-171">PolicyName</span></span> | <span data-ttu-id="8c590-172">A identidade da política</span><span class="sxs-lookup"><span data-stu-id="8c590-172">The identity of the policy</span></span> |
||

<span data-ttu-id="8c590-173">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8c590-173">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="8c590-174">Você pode remover uma política de um usuário concedendo a política de $Null conforme mostrado no próximo exemplo:</span><span class="sxs-lookup"><span data-stu-id="8c590-174">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="8c590-175">Registrar um aplicativo para o SBA com Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8c590-175">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="8c590-176">Para permitir que diferentes SBAs usados em seu locatário leiam os dados necessários do Microsoft 365, você precisa registrar um aplicativo para o SBA com Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8c590-176">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="8c590-177">Para obter mais informações sobre o registro do aplicativo, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8c590-177">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="8c590-178">Desenvolver aplicativos de linha de negócios para Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8c590-178">Develop line-of-business apps for Azure Active Directory</span></span>](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="8c590-179">[Registre um aplicativo com o plataforma de identidade da Microsoft](/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="8c590-179">[Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="8c590-180">Você só precisa registrar um aplicativo para uso por todos os SBAs em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="8c590-180">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="8c590-181">Para o registro do SBA, você precisa dos seguintes valores criados pelo registro:</span><span class="sxs-lookup"><span data-stu-id="8c590-181">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="8c590-182">ID do aplicativo (cliente)</span><span class="sxs-lookup"><span data-stu-id="8c590-182">Application (client) ID</span></span> 
- <span data-ttu-id="8c590-183">Segredo do cliente</span><span class="sxs-lookup"><span data-stu-id="8c590-183">Client secret</span></span> 

<span data-ttu-id="8c590-184">Para o aplicativo SBA, lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="8c590-184">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="8c590-185">O nome pode ser o que você decidir.</span><span class="sxs-lookup"><span data-stu-id="8c590-185">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="8c590-186">Tipos de conta com suporte = Conta somente neste diretório organizacional.</span><span class="sxs-lookup"><span data-stu-id="8c590-186">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="8c590-187">O Uri de Redirecionamento da Web = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="8c590-187">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="8c590-188">Tokens de concessão implícitos = tokens de acesso e tokens de ID.</span><span class="sxs-lookup"><span data-stu-id="8c590-188">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="8c590-189">Permissões de API = Skype e Teams acesso de administrador de locatário -> Permissões de aplicativo -> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="8c590-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="8c590-190">Segredo do cliente: você pode usar qualquer descrição e expiração.</span><span class="sxs-lookup"><span data-stu-id="8c590-190">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="8c590-191">Lembre-se de copiar o segredo do cliente imediatamente após a criação.</span><span class="sxs-lookup"><span data-stu-id="8c590-191">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="8c590-192">A ID do aplicativo (cliente) é mostrada na guia Visão geral.</span><span class="sxs-lookup"><span data-stu-id="8c590-192">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="8c590-193">Em seguida, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="8c590-193">Then follow these steps:</span></span>

1. <span data-ttu-id="8c590-194">Registre o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8c590-194">Register the application.</span></span>
2. <span data-ttu-id="8c590-195">De definir os tokens de concessão implícitos.</span><span class="sxs-lookup"><span data-stu-id="8c590-195">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="8c590-196">De definir as permissões da API.</span><span class="sxs-lookup"><span data-stu-id="8c590-196">Set the API permissions.</span></span>
4. <span data-ttu-id="8c590-197">Crie o segredo do cliente.</span><span class="sxs-lookup"><span data-stu-id="8c590-197">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="8c590-198">Configuração do Controlador de Borda de Sessão</span><span class="sxs-lookup"><span data-stu-id="8c590-198">Session Border Controller configuration</span></span> 

<span data-ttu-id="8c590-199">Para obter orientações passo a passo sobre como configurar o Controlador de Borda de Sessão com o Aparelho de Filial Suportável incorporado, consulte a documentação fornecida pelo fornecedor SBC:</span><span class="sxs-lookup"><span data-stu-id="8c590-199">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="8c590-200">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="8c590-200">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="8c590-201">Faixa de Opções</span><span class="sxs-lookup"><span data-stu-id="8c590-201">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="8c590-202">Oracle</span><span class="sxs-lookup"><span data-stu-id="8c590-202">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="8c590-203">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="8c590-203">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="8c590-204">Problemas de relatórios</span><span class="sxs-lookup"><span data-stu-id="8c590-204">Reporting issues</span></span>

<span data-ttu-id="8c590-205">Reporte quaisquer problemas à organização de suporte do fornecedor SBC.</span><span class="sxs-lookup"><span data-stu-id="8c590-205">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="8c590-206">Ao relatar o problema, indique que você tem um Aparelho de Filial Desavivável configurado.</span><span class="sxs-lookup"><span data-stu-id="8c590-206">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="8c590-207">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="8c590-207">Known issues</span></span>

- <span data-ttu-id="8c590-208">Quando você adiciona novos Aparelhos de Filial Desavisáveis, pode levar algum tempo até que você possa usá-los em políticas de Aparelho de Filial Suportável.</span><span class="sxs-lookup"><span data-stu-id="8c590-208">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="8c590-209">Quando você atribui uma política de Aparelho de Filial Desavivável a um usuário, pode levar algum tempo até que o SBA seja mostrado na saída de Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="8c590-209">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="8c590-210">A inversão de número em contatos do Azure AD não é realizada.</span><span class="sxs-lookup"><span data-stu-id="8c590-210">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="8c590-211">O SBA não dá suporte às configurações de encaminhamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="8c590-211">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="8c590-212">Não há suporte para fazer uma chamada de emergência para um número de emergência configurado para chamada de emergência dinâmica (E911).</span><span class="sxs-lookup"><span data-stu-id="8c590-212">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>
