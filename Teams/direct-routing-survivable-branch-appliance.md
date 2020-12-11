---
title: Encaminhamento direto SBA
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
description: Saiba mais sobre roteamento direto, como configuração, decisões de implantação básica necessárias e considerações de roteamento de voz.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3204bc58b083f62feca3f878d2189558b69af6bd
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620720"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a><span data-ttu-id="66592-103">Aplicativo de ramificação sobreviventes (SBA) para roteamento direto-visualização pública</span><span class="sxs-lookup"><span data-stu-id="66592-103">Survivable Branch Appliance (SBA) for Direct Routing - Public Preview</span></span>


> [!NOTE]
> <span data-ttu-id="66592-104">Esta é uma versão de visualização pública.</span><span class="sxs-lookup"><span data-stu-id="66592-104">This is a public preview release.</span></span>

<span data-ttu-id="66592-105">Às vezes, um site do cliente que usa o roteamento direto para se conectar ao sistema telefônico da Microsoft pode sofrer uma falha na Internet.</span><span class="sxs-lookup"><span data-stu-id="66592-105">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="66592-106">Suponha que o site do cliente--chamado de ramificação--temporariamente não pode se conectar ao Microsoft Cloud por meio do roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="66592-106">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="66592-107">No entanto, a intranet dentro da ramificação ainda é totalmente funcional e os usuários podem se conectar ao controlador de borda de sessão (SBC) que está fornecendo conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="66592-107">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="66592-108">Este artigo descreve como usar um aparelho de ramificação sobreviventes (SBA) para permitir que o sistema de telefonia da Microsoft continue a fazer e receber chamadas de rede telefônica pública comutada (PSTN) no caso de uma paralisação.</span><span class="sxs-lookup"><span data-stu-id="66592-108">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66592-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="66592-109">Prerequisites</span></span>

<span data-ttu-id="66592-110">O SBA é um código distribuível fornecido pela Microsoft a fornecedores SBC que, em seguida, insere código em seu firmware ou distribui-lo separadamente para ter o SBA executado em uma VM ou em um hardware separado.</span><span class="sxs-lookup"><span data-stu-id="66592-110">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="66592-111">Para obter o firmware do controlador de borda de sessão mais recente com o aparelho de ramificação sobreviventes incorporado, entre em contato com o fornecedor do SBC.</span><span class="sxs-lookup"><span data-stu-id="66592-111">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="66592-112">Além disso, é necessário o seguinte:</span><span class="sxs-lookup"><span data-stu-id="66592-112">In addition, the following is required:</span></span>

- <span data-ttu-id="66592-113">O SBC precisa ser configurado para bypass de mídia para garantir que o cliente do Microsoft Teams no site de ramificação possa ter mídia que flui diretamente com o SBC.</span><span class="sxs-lookup"><span data-stu-id="66592-113">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="66592-114">O TLS 1.2 deve ser habilitado no sistema operacional VM SBA.</span><span class="sxs-lookup"><span data-stu-id="66592-114">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="66592-115">Clientes de equipes com suporte</span><span class="sxs-lookup"><span data-stu-id="66592-115">Supported Teams clients</span></span>

<span data-ttu-id="66592-116">O recurso SBA tem suporte nos seguintes clientes do Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="66592-116">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="66592-117">Microsoft Teams Windows Desktop</span><span class="sxs-lookup"><span data-stu-id="66592-117">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="66592-118">Área de trabalho do macOS do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66592-118">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="66592-119">Como funciona</span><span class="sxs-lookup"><span data-stu-id="66592-119">How it works</span></span>

<span data-ttu-id="66592-120">Durante uma falha na Internet, o cliente da equipe deve alternar para o SBA automaticamente, e as chamadas contínuas devem continuar sem interrupções.</span><span class="sxs-lookup"><span data-stu-id="66592-120">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="66592-121">Nenhuma ação é necessária do usuário.</span><span class="sxs-lookup"><span data-stu-id="66592-121">No action is required from the user.</span></span> <span data-ttu-id="66592-122">Assim que o cliente do teams detectar que a Internet está ativa e todas as chamadas feitas terminarem, o cliente retornará ao modo de operação normal e se conectará a outros serviços do teams.</span><span class="sxs-lookup"><span data-stu-id="66592-122">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="66592-123">O SBA carregará os registros de dados de chamadas coletados para a nuvem e o histórico de chamadas será atualizado para que essas informações estejam disponíveis para análise pelo administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="66592-123">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="66592-124">Quando o cliente do Microsoft Teams está no modo offline, a seguinte funcionalidade relacionada a chamadas está disponível:</span><span class="sxs-lookup"><span data-stu-id="66592-124">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="66592-125">Realização de chamadas PSTN via SBA/SBC locais com mídia fluindo pelo SBC.</span><span class="sxs-lookup"><span data-stu-id="66592-125">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="66592-126">Recebimento de chamadas PSTN via SBA/SBC locais com mídia fluindo pelo SBC.</span><span class="sxs-lookup"><span data-stu-id="66592-126">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="66592-127">Espera e retomada de chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="66592-127">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="66592-128">Configuração</span><span class="sxs-lookup"><span data-stu-id="66592-128">Configuration</span></span>

<span data-ttu-id="66592-129">Para que o recurso SBA funcione, o cliente das equipes precisa saber quais SBAs estão disponíveis em cada site de filial e quais SBAs são atribuídos aos usuários desse site.</span><span class="sxs-lookup"><span data-stu-id="66592-129">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="66592-130">As etapas de configuração são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="66592-130">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="66592-131">Crie o SBAs.</span><span class="sxs-lookup"><span data-stu-id="66592-131">Create the SBAs.</span></span>
2. <span data-ttu-id="66592-132">Criar a política de sustentabilidade da ramificação do teams.</span><span class="sxs-lookup"><span data-stu-id="66592-132">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="66592-133">Atribua a política aos usuários.</span><span class="sxs-lookup"><span data-stu-id="66592-133">Assign the policy to users.</span></span>
4. <span data-ttu-id="66592-134">Registre um aplicativo para o SBA com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="66592-134">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="66592-135">Todas as configurações são feitas usando cmdlets do PowerShell do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="66592-135">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="66592-136">(O centro de administração do teams ainda não é compatível com o recurso de roteamento direto SBA.)</span><span class="sxs-lookup"><span data-stu-id="66592-136">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="66592-137">(Para obter informações sobre como configurar o SBC, com links para a documentação do fornecedor do SBC, consulte configuração do controlador de borda de sessão no final deste artigo.)</span><span class="sxs-lookup"><span data-stu-id="66592-137">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="66592-138">Criar a SBAs</span><span class="sxs-lookup"><span data-stu-id="66592-138">Create the SBAs</span></span>

<span data-ttu-id="66592-139">Para criar o SBAs, você vai usar o cmdlet New-CsTeamsSurvivableBranchAppliance.</span><span class="sxs-lookup"><span data-stu-id="66592-139">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="66592-140">Este cmdlet tem os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="66592-140">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="66592-141">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="66592-141">Parameter</span></span>| <span data-ttu-id="66592-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="66592-142">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="66592-143">Identidade</span><span class="sxs-lookup"><span data-stu-id="66592-143">Identity</span></span>  | <span data-ttu-id="66592-144">A identidade do SBA</span><span class="sxs-lookup"><span data-stu-id="66592-144">The identity of the SBA</span></span>  |
| <span data-ttu-id="66592-145">Fqdn</span><span class="sxs-lookup"><span data-stu-id="66592-145">Fqdn</span></span> | <span data-ttu-id="66592-146">O FQDN do SBA</span><span class="sxs-lookup"><span data-stu-id="66592-146">The FQDN of the SBA</span></span> |
| <span data-ttu-id="66592-147">Site</span><span class="sxs-lookup"><span data-stu-id="66592-147">Site</span></span> | <span data-ttu-id="66592-148">O TenantNetworkSite em que o SBA está localizado</span><span class="sxs-lookup"><span data-stu-id="66592-148">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="66592-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="66592-149">Description</span></span> | <span data-ttu-id="66592-150">Texto em formato livre</span><span class="sxs-lookup"><span data-stu-id="66592-150">Free format text</span></span> |
|||

<span data-ttu-id="66592-151">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="66592-151">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="66592-152">Criar a política de sustentabilidade da ramificação do teams</span><span class="sxs-lookup"><span data-stu-id="66592-152">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="66592-153">Para criar uma política, use o cmdlet New-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="66592-153">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="66592-154">Esse cmdlet tem os parâmetros a seguir.</span><span class="sxs-lookup"><span data-stu-id="66592-154">This cmdlet has the following parameters.</span></span> <span data-ttu-id="66592-155">Observe que a política pode conter um ou mais SBAs.</span><span class="sxs-lookup"><span data-stu-id="66592-155">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="66592-156">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="66592-156">Parameter</span></span>| <span data-ttu-id="66592-157">Descrição</span><span class="sxs-lookup"><span data-stu-id="66592-157">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="66592-158">Identidade</span><span class="sxs-lookup"><span data-stu-id="66592-158">Identity</span></span> | <span data-ttu-id="66592-159">A identidade da política</span><span class="sxs-lookup"><span data-stu-id="66592-159">The identity of the policy</span></span> |
| <span data-ttu-id="66592-160">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="66592-160">BranchApplianceFqdns</span></span>  | <span data-ttu-id="66592-161">O FQDN do (s) SBA (s) no site</span><span class="sxs-lookup"><span data-stu-id="66592-161">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="66592-162">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="66592-162">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="66592-163">Você pode adicionar ou remover SBAs de uma política usando o cmdlet Set-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="66592-163">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="66592-164">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="66592-164">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="66592-165">Atribuir uma política a um usuário</span><span class="sxs-lookup"><span data-stu-id="66592-165">Assign a policy to a user</span></span>

<span data-ttu-id="66592-166">Para atribuir a política a usuários individuais, você vai usar o cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="66592-166">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="66592-167">Esse cmdlet tem os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="66592-167">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="66592-168">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="66592-168">Parameter</span></span>| <span data-ttu-id="66592-169">Descrição</span><span class="sxs-lookup"><span data-stu-id="66592-169">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="66592-170">Identidade</span><span class="sxs-lookup"><span data-stu-id="66592-170">Identity</span></span> | <span data-ttu-id="66592-171">A identidade do usuário</span><span class="sxs-lookup"><span data-stu-id="66592-171">The identity of the user</span></span> |
| <span data-ttu-id="66592-172">PolicyName</span><span class="sxs-lookup"><span data-stu-id="66592-172">PolicyName</span></span> | <span data-ttu-id="66592-173">A identidade da política</span><span class="sxs-lookup"><span data-stu-id="66592-173">The identity of the policy</span></span> |
||

<span data-ttu-id="66592-174">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="66592-174">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="66592-175">Você pode remover uma política de um usuário concedendo a política de $Null conforme mostrado no próximo exemplo:</span><span class="sxs-lookup"><span data-stu-id="66592-175">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="66592-176">Registrar um aplicativo para o SBA com o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="66592-176">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="66592-177">Para permitir que diferentes SBAs usadas dentro do seu locatário leiam os dados necessários do Microsoft 365, você precisa registrar um aplicativo para o SBA com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="66592-177">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="66592-178">Para obter mais informações sobre o registro do aplicativo, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="66592-178">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="66592-179">Desenvolver aplicativos de linha de negócios para o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="66592-179">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="66592-180">[Registre um aplicativo com a plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="66592-180">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="66592-181">Você só precisa registrar um aplicativo para uso por todos os SBAs em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="66592-181">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="66592-182">Para o registro SBA, você precisa dos seguintes valores criados pelo registro:</span><span class="sxs-lookup"><span data-stu-id="66592-182">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="66592-183">ID do aplicativo (cliente)</span><span class="sxs-lookup"><span data-stu-id="66592-183">Application (client) ID</span></span> 
- <span data-ttu-id="66592-184">Segredo do cliente</span><span class="sxs-lookup"><span data-stu-id="66592-184">Client secret</span></span> 

<span data-ttu-id="66592-185">Para o aplicativo SBA, tenha em mente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="66592-185">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="66592-186">O nome pode ser qualquer coisa que você decidir.</span><span class="sxs-lookup"><span data-stu-id="66592-186">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="66592-187">Tipos de conta com suporte = conta neste diretório organizacional apenas.</span><span class="sxs-lookup"><span data-stu-id="66592-187">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="66592-188">O URI de redirecionamento da Web = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="66592-188">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="66592-189">Símbolos de concessão implícito = tokens de acesso e tokens de identificação.</span><span class="sxs-lookup"><span data-stu-id="66592-189">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="66592-190">Permissões de API = acesso de administrador de locatários do Skype e do teams-> permissões de aplicativo-> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="66592-190">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="66592-191">Segredo do cliente: você pode usar qualquer descrição e expiração.</span><span class="sxs-lookup"><span data-stu-id="66592-191">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="66592-192">Lembre-se de copiar o segredo do cliente imediatamente após criá-lo.</span><span class="sxs-lookup"><span data-stu-id="66592-192">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="66592-193">A ID do aplicativo (cliente) é mostrada na guia Visão geral.</span><span class="sxs-lookup"><span data-stu-id="66592-193">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="66592-194">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="66592-194">Then follow these steps:</span></span>

1. <span data-ttu-id="66592-195">Registre o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="66592-195">Register the application.</span></span>
2. <span data-ttu-id="66592-196">Defina os tokens de concessão implícito.</span><span class="sxs-lookup"><span data-stu-id="66592-196">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="66592-197">Defina as permissões da API.</span><span class="sxs-lookup"><span data-stu-id="66592-197">Set the API permissions.</span></span>
4. <span data-ttu-id="66592-198">Crie o segredo do cliente.</span><span class="sxs-lookup"><span data-stu-id="66592-198">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="66592-199">Configuração de controlador de borda de sessão</span><span class="sxs-lookup"><span data-stu-id="66592-199">Session Border Controller configuration</span></span> 

<span data-ttu-id="66592-200">Para obter uma orientação passo a passo sobre como configurar o controlador de borda de sessão com o dispositivo de ramificação sobreviventes incorporado, consulte a documentação fornecida pelo seu fornecedor de SBC:</span><span class="sxs-lookup"><span data-stu-id="66592-200">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="66592-201">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="66592-201">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="66592-202">Faixa</span><span class="sxs-lookup"><span data-stu-id="66592-202">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="66592-203">Oracle</span><span class="sxs-lookup"><span data-stu-id="66592-203">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="66592-204">SMS-Systems</span><span class="sxs-lookup"><span data-stu-id="66592-204">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="66592-205">Relatar problemas</span><span class="sxs-lookup"><span data-stu-id="66592-205">Reporting issues</span></span>

<span data-ttu-id="66592-206">Relatar problemas à organização de suporte de seu fornecedor de SBC.</span><span class="sxs-lookup"><span data-stu-id="66592-206">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="66592-207">Ao relatar o problema, indique que você tem um aparelho de ramificação sobreviventes configurado.</span><span class="sxs-lookup"><span data-stu-id="66592-207">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="66592-208">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="66592-208">Known issues</span></span>

- <span data-ttu-id="66592-209">Ao adicionar novos aparelhos de ramificação sobreviventes, pode levar algum tempo até que você possa usá-los em políticas de aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="66592-209">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="66592-210">Ao atribuir uma política de aparelho de ramificação sobreviventes a um usuário, pode levar algum tempo até que o SBA seja mostrado na saída de Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="66592-210">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="66592-211">A pesquisa de número reverso nos contatos do Azure AD não é realizada.</span><span class="sxs-lookup"><span data-stu-id="66592-211">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="66592-212">O SBA não é compatível com as configurações de encaminhamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="66592-212">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="66592-213">Não há suporte para fazer uma chamada de emergência para um número de emergência configurado para chamadas de emergência dinâmicas (E911).</span><span class="sxs-lookup"><span data-stu-id="66592-213">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="66592-214">A saída de Get-CsOnlineUser mostra TeamsBranchSurvivabilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="66592-214">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
