---
title: Habilitar usuários para Roteamento Direto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como habilitar os usuários Telefone Microsoft Roteamento Direto do Sistema.
ms.openlocfilehash: 86132778226702577068d9502ae46cba949667c6
ms.sourcegitcommit: 5df33e7fe912426e3e158b3be7334e05dc3803a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53345707"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="053b8-103">Habilitar usuários para Roteamento Direto, voz e caixa postal</span><span class="sxs-lookup"><span data-stu-id="053b8-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="053b8-104">Este artigo descreve como habilitar os usuários para Sistema de Telefonia Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="053b8-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="053b8-105">Esta é a etapa 2 das seguintes etapas para configurar o Roteamento Direto:</span><span class="sxs-lookup"><span data-stu-id="053b8-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="053b8-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="053b8-106">Step 1.</span></span> [<span data-ttu-id="053b8-107">Conexão SBC com Telefone Microsoft System e validar a conexão</span><span class="sxs-lookup"><span data-stu-id="053b8-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="053b8-108">**Etapa 2. Habilitar usuários para Roteamento Direto, voz e caixa postal**   (este artigo)</span><span class="sxs-lookup"><span data-stu-id="053b8-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="053b8-109">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="053b8-109">Step 3.</span></span> [<span data-ttu-id="053b8-110">Configurar roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="053b8-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="053b8-111">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="053b8-111">Step 4.</span></span> [<span data-ttu-id="053b8-112">Traduzir números para um formato alternativo</span><span class="sxs-lookup"><span data-stu-id="053b8-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="053b8-113">Para obter informações sobre todas as etapas necessárias para configurar o Roteamento Direto, consulte [Configure Direct Routing](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="053b8-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="053b8-114">Quando você estiver pronto para habilitar usuários para Roteamento Direto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="053b8-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="053b8-115">Crie um usuário no Microsoft 365 ou Office 365 e atribua uma Sistema de Telefonia de usuário.</span><span class="sxs-lookup"><span data-stu-id="053b8-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="053b8-116">Verifique se o usuário está no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="053b8-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="053b8-117">Configure o número de telefone e habilita a voz corporativa e a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="053b8-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="053b8-118">Atribua Teams modo Somente aos usuários.</span><span class="sxs-lookup"><span data-stu-id="053b8-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="053b8-119">Criar um usuário e atribuir a licença</span><span class="sxs-lookup"><span data-stu-id="053b8-119">Create a user and assign the license</span></span>

<span data-ttu-id="053b8-120">Há duas opções para criar um novo usuário no Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="053b8-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="053b8-121">No entanto, a Microsoft recomenda que sua organização escolha uma opção para evitar problemas de roteamento:</span><span class="sxs-lookup"><span data-stu-id="053b8-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="053b8-122">Crie o usuário no Active Directory local e sincronize o usuário com a nuvem.</span><span class="sxs-lookup"><span data-stu-id="053b8-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="053b8-123">Consulte [Integrar seus diretórios locais com Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="053b8-123">See [Integrate your on-premises directories with Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="053b8-124">Crie o usuário diretamente no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="053b8-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="053b8-125">Consulte [Adicionar usuários individualmente ou em massa a](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)Microsoft 365 ou Office 365 - Ajuda do administrador .</span><span class="sxs-lookup"><span data-stu-id="053b8-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="053b8-126">Se sua implantação do Skype for Business Online coexistir com o Skype for Business 2015 ou o Lync 2010 ou 2013 local, a única opção com suporte é criar o usuário no Active Directory local e sincronizar o usuário com a nuvem (Opção 1).</span><span class="sxs-lookup"><span data-stu-id="053b8-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="053b8-127">Para obter informações sobre os requisitos de licença, consulte [licenciamento e outros requisitos](direct-routing-plan.md#licensing-and-other-requirements) em [Plan Direct Routing](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="053b8-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online"></a><span data-ttu-id="053b8-128">Verifique se o usuário está em casa online</span><span class="sxs-lookup"><span data-stu-id="053b8-128">Ensure that the user is homed online</span></span> 

<span data-ttu-id="053b8-129">Esta etapa é aplicável Skype for Business Server Enterprise Voice usuários habilitados que estão sendo migrados para Teams Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="053b8-129">This step is applicable to Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing.</span></span>

<span data-ttu-id="053b8-130">O Roteamento Direto exige que o usuário seja 100% online.</span><span class="sxs-lookup"><span data-stu-id="053b8-130">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="053b8-131">Você pode verificar olhando para o parâmetro RegistrarPool, que precisa ter um valor no infra.lync.com domínio.</span><span class="sxs-lookup"><span data-stu-id="053b8-131">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="053b8-132">Também é recomendável, mas não necessário, alterar o gerenciamento do LineURI de local para online ao migrar usuários para Teams Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="053b8-132">It's also recommended, but not required, to change management of the LineURI from on-premises to online when migrating users to Teams Direct Routing.</span></span> 

1. <span data-ttu-id="053b8-133">Conexão uma sessão Skype for Business Do PowerShell Online.</span><span class="sxs-lookup"><span data-stu-id="053b8-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="053b8-134">Emitir o comando:</span><span class="sxs-lookup"><span data-stu-id="053b8-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="053b8-135">Caso OnPremLineUriManuallySet seja definido como False e LineUri for preenchido com um número de telefone do <E.164>, o número de telefone foi atribuído no local e sincronizado com o O365.</span><span class="sxs-lookup"><span data-stu-id="053b8-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, the phone number was assigned on-premises and synchronized to O365.</span></span> <span data-ttu-id="053b8-136">Se você quiser gerenciar o número de telefone online, limpe o parâmetro usando o Shell de Gerenciamento local Skype for Business e sincronizar com o O365, antes de configurar o número de telefone usando o Skype for Business Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="053b8-136">If you want manage the phone number online, clean the parameter using on-premises Skype for Business Management Shell and synchronize to O365, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="053b8-137">A partir Skype for Business Shell de Gerenciamento em questão o comando:</span><span class="sxs-lookup"><span data-stu-id="053b8-137">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > <span data-ttu-id="053b8-138">Não defina EnterpriseVoiceEnabled como False, pois não há nenhum requisito para fazer isso e isso pode levar a problemas de normalização do plano de discagem se os telefones Skype for Business herdados estão em uso e a configuração híbrida tenant é definida com UseOnPremDialPlan $True.</span><span class="sxs-lookup"><span data-stu-id="053b8-138">Do not set EnterpriseVoiceEnabled to False as there is no requirement to do so and this can lead to dial plan normalization issues if legacy Skype for Business phones are in use and the Tenant hybrid configuration is set with UseOnPremDialPlan $True.</span></span> 
    
   <span data-ttu-id="053b8-139">Depois que as alterações sincronizadas Office 365 a saída esperada `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` de seria:</span><span class="sxs-lookup"><span data-stu-id="053b8-139">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > <span data-ttu-id="053b8-140">Todos os atributos de telefone do usuário devem ser gerenciados online antes de você [decomissioná-lo Skype for Business ambiente local.](/skypeforbusiness/hybrid/decommission-on-prem-overview)</span><span class="sxs-lookup"><span data-stu-id="053b8-140">All user's phone attributes must be managed online before you [decomission your on-premises Skype for Business environment](/skypeforbusiness/hybrid/decommission-on-prem-overview).</span></span> 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online"></a><span data-ttu-id="053b8-141">Configurar o número de telefone e habilitar a voz corporativa e a caixa postal online</span><span class="sxs-lookup"><span data-stu-id="053b8-141">Configure the phone number and enable enterprise voice and voicemail online</span></span> 

<span data-ttu-id="053b8-142">Depois de ter criado o usuário e atribuído uma licença, a próxima etapa é configurar as configurações de telefone online do usuário.</span><span class="sxs-lookup"><span data-stu-id="053b8-142">After you have created the user and assigned a license, the next step is to configure the user's online phone settings.</span></span> 

 
1. <span data-ttu-id="053b8-143">Conexão uma sessão Skype for Business Do PowerShell Online.</span><span class="sxs-lookup"><span data-stu-id="053b8-143">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="053b8-144">Se o gerenciamento do número de telefone do usuário no local, emito o comando:</span><span class="sxs-lookup"><span data-stu-id="053b8-144">If managing the user's phone number on-premises, issue the command:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
3. <span data-ttu-id="053b8-145">Se o gerenciamento do número de telefone do usuário online, emito o comando:</span><span class="sxs-lookup"><span data-stu-id="053b8-145">If managing the user's phone number online, issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="053b8-146">Por exemplo, para adicionar um número de telefone para o usuário "Spencer Low", digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="053b8-146">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="053b8-147">Se os usuários "Spencer Low" e "Stacy Quinn" compartilharem o mesmo número base com extensões exclusivas, insira o seguinte</span><span class="sxs-lookup"><span data-stu-id="053b8-147">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1001" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1002" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="053b8-148">É recomendável, mas não obrigatório, que o número de telefone usado seja configurado como um número de telefone E.164 completo com código de país.</span><span class="sxs-lookup"><span data-stu-id="053b8-148">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="053b8-149">Há suporte para configurar números de telefone com extensões que serão usadas para procurar usuários quando a pesquisa em relação ao número base retornar mais de um resultado.</span><span class="sxs-lookup"><span data-stu-id="053b8-149">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="053b8-150">Isso permite que as empresas configurem números de telefone com o mesmo número base e extensões exclusivas.</span><span class="sxs-lookup"><span data-stu-id="053b8-150">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="053b8-151">Para que a pesquisa seja bem-sucedida, o convite deve incluir o número completo com extensão da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="053b8-151">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="053b8-152">Se o número de telefone do usuário for gerenciado no local, use o Shell de Gerenciamento local Skype for Business Shell de Gerenciamento ou Painel de Controle para configurar o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="053b8-152">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="053b8-153">Configurando o envio de chamadas diretamente para a caixa postal</span><span class="sxs-lookup"><span data-stu-id="053b8-153">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="053b8-154">O Roteamento Direto permite que você termine a chamada para um usuário e envie-a diretamente para a caixa postal do usuário.</span><span class="sxs-lookup"><span data-stu-id="053b8-154">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="053b8-155">Se você quiser enviar a chamada diretamente para a caixa postal, anexe opaque=app:voicemail ao header request URI.</span><span class="sxs-lookup"><span data-stu-id="053b8-155">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="053b8-156">Por exemplo, "sip:user@yourdomain.com;opaque=app:voicemail".</span><span class="sxs-lookup"><span data-stu-id="053b8-156">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="053b8-157">Nesse caso, o Teams usuário não receberá a notificação de chamada, a chamada será conectada diretamente à caixa postal do usuário.</span><span class="sxs-lookup"><span data-stu-id="053b8-157">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="053b8-158">Atribuir Teams modo Somente aos usuários para garantir que as chamadas aterrisem Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="053b8-158">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="053b8-159">O Roteamento Direto exige que os usuários Teams modo Somente para garantir que as chamadas de entrada chegam no Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="053b8-159">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="053b8-160">Para colocar os usuários Teams modo Somente, atribua a eles a instância "UpgradeToTeams" do TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="053b8-160">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="053b8-161">Para obter mais informações, [consulte Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md).</span><span class="sxs-lookup"><span data-stu-id="053b8-161">For more information, see [Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md).</span></span> <span data-ttu-id="053b8-162">Se sua organização usa Skype for Business Server ou Skype for Business Online, consulte o artigo a seguir para obter informações sobre interoperabilidade entre Skype e Teams: Migração e [interoperabilidade](migration-interop-guidance-for-teams-with-skype.md)com Skype for Business .</span><span class="sxs-lookup"><span data-stu-id="053b8-162">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="053b8-163">Confira também</span><span class="sxs-lookup"><span data-stu-id="053b8-163">See also</span></span>

[<span data-ttu-id="053b8-164">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="053b8-164">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="053b8-165">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="053b8-165">Configure Direct Routing</span></span>](direct-routing-configure.md)
