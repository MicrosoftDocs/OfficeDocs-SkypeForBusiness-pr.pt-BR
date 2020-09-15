---
title: Habilitar usuários para roteamento direto
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
description: Saiba como habilitar o roteamento direto do sistema de usuários do Microsoft Phone System.
ms.openlocfilehash: f89133b5205dc77f8045c484b97d3049773c28e2
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814540"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="68957-103">Habilite os usuários para roteamento direto, voz e correio de voz</span><span class="sxs-lookup"><span data-stu-id="68957-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="68957-104">Este artigo descreve como habilitar usuários para o roteamento direto do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="68957-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="68957-105">Esta é a etapa 2 das seguintes etapas para configurar o roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="68957-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="68957-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="68957-106">Step 1.</span></span> [<span data-ttu-id="68957-107">Conectar o SBC com o sistema Microsoft Phone e validar a conexão</span><span class="sxs-lookup"><span data-stu-id="68957-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="68957-108">**Etapa 2. Habilite os usuários para roteamento direto, voz e correio de voz**   (este artigo)</span><span class="sxs-lookup"><span data-stu-id="68957-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="68957-109">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="68957-109">Step 3.</span></span> [<span data-ttu-id="68957-110">Configurar roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="68957-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="68957-111">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="68957-111">Step 4.</span></span> [<span data-ttu-id="68957-112">Converter números em um formato alternativo</span><span class="sxs-lookup"><span data-stu-id="68957-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="68957-113">Para obter informações sobre todas as etapas necessárias para configurar o roteamento direto, consulte [Configurar o roteamento direto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="68957-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="68957-114">Quando estiver pronto para habilitar os usuários para roteamento direto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="68957-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="68957-115">Crie um usuário no Microsoft 365 ou no Office 365 e atribua uma licença do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="68957-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="68957-116">Certifique-se de que o usuário esteja hospedado no Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="68957-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="68957-117">Configurar o número de telefone e habilitar o Enterprise Voice e correio de voz.</span><span class="sxs-lookup"><span data-stu-id="68957-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="68957-118">Atribuir o modo apenas Teams aos usuários.</span><span class="sxs-lookup"><span data-stu-id="68957-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="68957-119">Criar um usuário e atribuir a licença</span><span class="sxs-lookup"><span data-stu-id="68957-119">Create a user and assign the license</span></span> 

<span data-ttu-id="68957-120">Há duas opções para criar um novo usuário no Microsoft 365 ou no Office 365.</span><span class="sxs-lookup"><span data-stu-id="68957-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="68957-121">No entanto, a Microsoft recomenda que sua organização escolha uma opção para evitar problemas de roteamento:</span><span class="sxs-lookup"><span data-stu-id="68957-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="68957-122">Crie o usuário no Active Directory local e sincronize o usuário com a nuvem.</span><span class="sxs-lookup"><span data-stu-id="68957-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="68957-123">Confira [integrar seus diretórios locais com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="68957-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="68957-124">Crie o usuário diretamente no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="68957-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="68957-125">Consulte [Adicionar usuários individualmente ou em massa ao Microsoft 365 ou ao Office 365-ajuda para administradores](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="68957-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="68957-126">Se sua implantação do Skype for Business online existir com o Skype for Business 2015 ou o Lync 2010 ou 2013 local, a única opção com suporte é criar o usuário no Active Directory local e sincronizar o usuário com a nuvem (opção 1).</span><span class="sxs-lookup"><span data-stu-id="68957-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="68957-127">Para obter informações sobre os requisitos de licença, consulte [Licenciamento e outros requisitos](direct-routing-plan.md#licensing-and-other-requirements) no [Roteamento direto do plano](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="68957-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="68957-128">Certifique-se de que o usuário esteja hospedado online e o número de telefone não esteja sendo sincronizado no local (aplicável para usuários habilitados do Skype for Business Server Enterprise que estão sendo migrados para o roteamento direto do Teams)</span><span class="sxs-lookup"><span data-stu-id="68957-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="68957-129">O roteamento direto exige que o usuário seja hospedado online.</span><span class="sxs-lookup"><span data-stu-id="68957-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="68957-130">Você pode verificar a aparência do parâmetro RegistrarPool, que precisa ter um valor no domínio infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="68957-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="68957-131">O parâmetro OnPremLineUriManuallySet também deve ser definido como true.</span><span class="sxs-lookup"><span data-stu-id="68957-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="68957-132">Isso é conseguido Configurando o número de telefone e habilitando o correio de voz e o correio de voz corporativos usando o Skype for Business online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68957-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="68957-133">Conecte uma sessão do PowerShell do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="68957-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="68957-134">Execute o comando:</span><span class="sxs-lookup"><span data-stu-id="68957-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="68957-135">Em caso de OnPremLineUriManuallySet ser definido como false e LineUri for preenchido com um número de telefone <E. 164>, limpe os parâmetros usando o Shell de gerenciamento do Skype for Business local, antes de configurar o número de telefone usando o Skype for Business online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68957-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="68957-136">No Shell de gerenciamento do Skype for Business, execute o comando:</span><span class="sxs-lookup"><span data-stu-id="68957-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="68957-137">Depois que as alterações tiverem sido sincronizadas com o Office 365, a saída esperada `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` seria:</span><span class="sxs-lookup"><span data-stu-id="68957-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="68957-138">Configurar o número de telefone e habilitar o Enterprise Voice e correio de voz</span><span class="sxs-lookup"><span data-stu-id="68957-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="68957-139">Depois de criar o usuário e atribuir uma licença, a próxima etapa é configurar o número de telefone do usuário e o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="68957-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="68957-140">Para adicionar o número de telefone e habilitar o correio de voz:</span><span class="sxs-lookup"><span data-stu-id="68957-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="68957-141">Conecte uma sessão do PowerShell do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="68957-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="68957-142">Execute o comando:</span><span class="sxs-lookup"><span data-stu-id="68957-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```
    
    <span data-ttu-id="68957-143">Por exemplo, para adicionar um número de telefone para o usuário "Spencer baixo", digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="68957-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="68957-144">O número de telefone usado deve ser configurado como um número de telefone completo E. 164 com código de país.</span><span class="sxs-lookup"><span data-stu-id="68957-144">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="68957-145">Se o número de telefone do usuário for gerenciado localmente, use o Shell de gerenciamento do Skype for Business local ou o painel de controle para configurar o número de telefone do usuário.</span><span class="sxs-lookup"><span data-stu-id="68957-145">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="68957-146">Configurar o envio de chamadas diretamente para o correio de voz</span><span class="sxs-lookup"><span data-stu-id="68957-146">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="68957-147">O roteamento direto permite encerrar a chamada para um usuário e enviá-la diretamente ao correio de voz do usuário.</span><span class="sxs-lookup"><span data-stu-id="68957-147">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="68957-148">Se você quiser enviar a chamada diretamente para o correio de voz, anexe opaco = App: correio de voz ao cabeçalho URI da solicitação.</span><span class="sxs-lookup"><span data-stu-id="68957-148">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="68957-149">Por exemplo, "SIP: user@yourdomain. com; opaco = App: correio de voz".</span><span class="sxs-lookup"><span data-stu-id="68957-149">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="68957-150">Nesse caso, o usuário do Teams não receberá a notificação de chamada, a chamada será conectada diretamente ao correio de voz do usuário.</span><span class="sxs-lookup"><span data-stu-id="68957-150">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="68957-151">Atribuir o modo apenas Teams aos usuários para garantir chamadas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="68957-151">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="68957-152">O roteamento direto requer que os usuários estejam no modo somente Teams para garantir que as chamadas de entrada sejam feitas no cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="68957-152">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="68957-153">Para colocar usuários no modo somente Teams, atribua a eles a instância "UpgradeToTeams" de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="68957-153">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="68957-154">Para obter mais informações, consulte [diretrizes de atualização para administradores de ti](upgrade-to-teams-on-prem-overview.md).</span><span class="sxs-lookup"><span data-stu-id="68957-154">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="68957-155">Se sua organização usa o Skype for Business Server ou o Skype for Business Online, consulte o artigo a seguir para obter informações sobre interoperabilidade entre o Skype e o Teams: [migração e interoperabilidade com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="68957-155">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="68957-156">Confira também</span><span class="sxs-lookup"><span data-stu-id="68957-156">See also</span></span>

[<span data-ttu-id="68957-157">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="68957-157">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="68957-158">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="68957-158">Configure Direct Routing</span></span>](direct-routing-configure.md)
