---
title: Configurar a caixa postal na nuvem
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Saiba como configurar o correio de voz na nuvem para seus usuários. '
ms.openlocfilehash: d747b86d50cf4e81398d53bbc3602bff9cc4351c
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349715"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="2d815-103">Configurar a caixa postal na nuvem</span><span class="sxs-lookup"><span data-stu-id="2d815-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="2d815-104">Este artigo é para o [administrador do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que deseja configurar o recurso de correio de voz na nuvem para todos os participantes da empresa.</span><span class="sxs-lookup"><span data-stu-id="2d815-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="2d815-105">O correio de voz na nuvem aceita o depósito de mensagens de correio de voz apenas em uma caixa de correio do Exchange e não é compatível com sistemas de email de terceiros.</span><span class="sxs-lookup"><span data-stu-id="2d815-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-cloud-psystem-users"></a><span data-ttu-id="2d815-106">Ambientes somente de nuvem: configurar o correio de voz na nuvem para usuários da nuvem psystem</span><span class="sxs-lookup"><span data-stu-id="2d815-106">Cloud-only environments: Set up Cloud Voicemail for Cloud Psystem Users</span></span>

<span data-ttu-id="2d815-107">Para os usuários do Skype for Business Online e dos planos de chamada, o correio de voz na nuvem é automaticamente configurado e provisionado para os usuários após a atribuição de uma licença do **sistema telefônico** e um número de telefone a ele.</span><span class="sxs-lookup"><span data-stu-id="2d815-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="2d815-108">Se o recurso do sistema de telefonia não estiver incluído no seu plano, talvez seja necessário comprar licenças complementares do **sistema telefônico** .</span><span class="sxs-lookup"><span data-stu-id="2d815-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="2d815-109">Você também pode precisar comprar uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2d815-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="2d815-110">Consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="2d815-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="2d815-111">[Atribuir ou remover licenças do Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), as [licenças de complemento atribuir Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)e as licenças do Exchange Online às pessoas de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="2d815-111">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="2d815-112">Depois disso, elas poderão receber mensagens de voz!</span><span class="sxs-lookup"><span data-stu-id="2d815-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="2d815-113">O suporte para a transcrição de correio de voz foi adicionado a partir de março de 2017 e é habilitado por padrão para todas as organizações e usuários.</span><span class="sxs-lookup"><span data-stu-id="2d815-113">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="2d815-114">Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="2d815-114">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="2d815-115">Configurar correio de voz na nuvem para usuários de caixa de correio do Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2d815-115">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="2d815-116">As informações a seguir tratam da configuração do correio de voz em nuvem para trabalhar com os usuários online para o sistema telefônico, mas têm sua caixa de correio no Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="2d815-116">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="2d815-117">Se o recurso do sistema de telefonia não estiver incluído no seu plano, talvez seja necessário comprar licenças complementares do **sistema telefônico** .</span><span class="sxs-lookup"><span data-stu-id="2d815-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="2d815-118">Consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="2d815-118">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="2d815-119">[Atribuir licenças de Complementos do Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md) às pessoas de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="2d815-119">[Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) to the people in your business.</span></span>
    
3. <span data-ttu-id="2d815-120">O suporte para a transcrição de correio de voz foi adicionado a partir de março de 2017 e é habilitado por padrão para todas as organizações e usuários.</span><span class="sxs-lookup"><span data-stu-id="2d815-120">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="2d815-121">Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="2d815-121">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

4. <span data-ttu-id="2d815-122">As mensagens de correio de voz são entregues à caixa de correio do Exchange do usuário via SMTP roteado por meio do Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="2d815-122">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="2d815-123">Para habilitar a entrega bem-sucedida dessas mensagens, certifique-se de que os conectores do Exchange estejam configurados corretamente entre seus servidores Exchange e a proteção do Exchange Online; [Usar conectores para configurar o fluxo de emails](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="2d815-123">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

6. <span data-ttu-id="2d815-124">Para habilitar recursos de correio de voz, como personalizar saudações e correio de voz visual nos clientes Skype for Business, é necessário conectividade do Office 365 para a caixa de correio do Exchange Server via Exchange Web Services.</span><span class="sxs-lookup"><span data-stu-id="2d815-124">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="2d815-125">Para habilitar essa conectividade, você deve configurar o novo protocolo de autenticação OAuth do Exchange descrito em [Configurar a autenticação OAuth entre as organizações Exchange e Exchange Online](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), ou executar o assistente híbrido do Exchange no Exchange 2013 CU5 ou superior.</span><span class="sxs-lookup"><span data-stu-id="2d815-125">To enable this connectivity you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="2d815-126">Além disso, você deve configurar a integração e o OAuth entre o Skype for Business Online e o Exchange Server descritos em [Configurar a integração e o OAuth entre o Skype for Business Online e o Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span><span class="sxs-lookup"><span data-stu-id="2d815-126">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="2d815-127">Configurar correio de voz na nuvem para usuários do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2d815-127">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="2d815-128">As informações a seguir tratam da configuração do correio de voz em nuvem para trabalhar com os usuários online do Exchange e no local para o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="2d815-128">The following information is about configuring Cloud Voicemail to work with users who are online for Exchange and on-premises for Skype for Business.</span></span> 
  
1. <span data-ttu-id="2d815-129">Talvez seja necessário comprar licenças do Exchange Online para as pessoas em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="2d815-129">You may need to purchase Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="2d815-130">Consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="2d815-130">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="2d815-131">[Atribuir ou remover licenças do Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) as licenças do Exchange Online para as pessoas em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="2d815-131">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="2d815-132">O suporte para a transcrição de correio de voz foi adicionado a partir de março de 2017 e é habilitado por padrão para todas as organizações e usuários.</span><span class="sxs-lookup"><span data-stu-id="2d815-132">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="2d815-133">Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="2d815-133">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

4. <span data-ttu-id="2d815-134">Para configurar usuários do Skype for Business Server para correio de voz na nuvem, consulte [planejar o serviço de correio de voz para usuários locais](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)</span><span class="sxs-lookup"><span data-stu-id="2d815-134">To configure Skype for Business server users for Cloud Voicemail please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)</span></span>


> [!NOTE]
> <span data-ttu-id="2d815-135">Quando um representante responde a uma chamada em nome de um delegador, as notificações não estão disponíveis no correio de voz na nuvem.</span><span class="sxs-lookup"><span data-stu-id="2d815-135">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="2d815-136">Os usuários podem receber notificações de chamadas perdidas.</span><span class="sxs-lookup"><span data-stu-id="2d815-136">Users can receive notifications for missed calls.</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="2d815-137">Configuração de políticas de caixa postal em sua organização</span><span class="sxs-lookup"><span data-stu-id="2d815-137">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="2d815-138">Para clientes do Skype for Business, desabilitar o correio de voz por meio de uma política de chamadas do Microsoft Teams também pode desabilitar o serviço de correio de voz para seus usuários do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="2d815-138">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="2d815-139">A transcrição do correio de voz é habilitada por padrão e o mascaramento de obscenidades está desativado por padrão para todas as organizações e usuários; no entanto, você pode controlá-los usando os cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="2d815-139">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="2d815-140">As mensagens de correio de voz recebidas pelos usuários em sua organização são transcritas na região em que a sua organização do Office 365 está hospedada.</span><span class="sxs-lookup"><span data-stu-id="2d815-140">Voicemail messages received by users in your organization are transcribed in the region where your Office 365 organization is hosted.</span></span> <span data-ttu-id="2d815-141">A região em que seu locatário está hospedado pode não ser a mesma região em que o usuário que está recebendo a mensagem de correio de voz está localizado.</span><span class="sxs-lookup"><span data-stu-id="2d815-141">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="2d815-142">Para exibir a região em que seu locatário está hospedado, vá para a página de [perfil da organização](https://go.microsoft.com/fwlink/p/?linkid=2067339) e clique em **Exibir detalhes** ao lado de **local de dados**.</span><span class="sxs-lookup"><span data-stu-id="2d815-142">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d815-143">Você não pode criar uma nova instância de política para transcrição e o mascaramento de obscenidades de transcrição usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não pode remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="2d815-143">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="2d815-144">Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="2d815-144">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="2d815-145">Para ver todas as instâncias de política de correio de voz disponíveis, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2d815-145">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="2d815-146">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="2d815-146">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="2d815-148">Desativação da transcrição para sua organização</span><span class="sxs-lookup"><span data-stu-id="2d815-148">Turning off transcription for your organization</span></span>

<span data-ttu-id="2d815-149">Como a configuração padrão para a transcrição está ativada para sua organização, talvez você queira desabilitá-la usando [set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="2d815-149">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="2d815-150">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="2d815-150">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="2d815-151">Ativação do mascaramento de obscenidades para sua organização</span><span class="sxs-lookup"><span data-stu-id="2d815-151">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="2d815-152">Mascaramento de obscenidades está desativado por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="2d815-152">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="2d815-153">Se houver um requisito de negócios para habilitá-lo, você pode habilitar o mascaramento de obscenidades usando [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="2d815-153">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="2d815-154">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="2d815-154">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="2d815-155">Desativação da transcrição para usuário</span><span class="sxs-lookup"><span data-stu-id="2d815-155">Turning off transcription for a user</span></span>

<span data-ttu-id="2d815-156">As políticas de usuário são avaliadas antes das configurações organizacionais padrão.</span><span class="sxs-lookup"><span data-stu-id="2d815-156">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="2d815-157">Por exemplo, se a transcrição de correio de voz estiver habilitada para todos os seus usuários, você poderá atribuir uma política para desabilitar a transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2d815-157">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="2d815-158">Para desabilitar a transcrição para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="2d815-158">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="2d815-159">Ativação do mascaramento de obscenidades para um usuário</span><span class="sxs-lookup"><span data-stu-id="2d815-159">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="2d815-160">Para habilitar o mascaramento de obscenidades para um usuário específico, você pode atribuir uma política para habilitar o mascaramento de obscenidades de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="2d815-160">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="2d815-161">Para habilitar o mascaramento de obscenidades para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="2d815-161">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="2d815-p116">[!IMPORTANTE] O serviço de caixa postal no Office 365 armazena em cache as políticas de caixa postal e atualiza o cache a cada 4 horas. Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas.</span><span class="sxs-lookup"><span data-stu-id="2d815-p116">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="2d815-164">Ajude seus usuários a aprender recursos de caixa postal do teams</span><span class="sxs-lookup"><span data-stu-id="2d815-164">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="2d815-165">Temos as seguintes informações para os usuários sobre como gerenciar suas configurações de correio de voz, bem como outros recursos de chamada no Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="2d815-165">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="2d815-166">[Gerenciar suas configurações de chamada no Microsoft Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span><span class="sxs-lookup"><span data-stu-id="2d815-166">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="2d815-167">Este artigo explica como gerenciar todos os recursos de chamada de equipe do usuário final.</span><span class="sxs-lookup"><span data-stu-id="2d815-167">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="2d815-168">Ajude os usuários a conhecer os recursos da caixa postal do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2d815-168">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="2d815-169">Temos informações e artigos de treinamento para ajudar seus usuários a ser bem-sucedidos com o correio de voz do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="2d815-169">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="2d815-170">Indique os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="2d815-170">Point them to the following articles:</span></span>

- <span data-ttu-id="2d815-171">[Verifique a caixa postal e as opções do Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Este artigo explica como ouvir o seu correio de voz no Skype for Business, alterar a saudação da sua caixa postal, mudar suas configurações de correio de voz e ouvir o seu correio de voz em diferentes velocidades.</span><span class="sxs-lookup"><span data-stu-id="2d815-171">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="2d815-172">Treinamento do Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="2d815-172">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="2d815-173">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2d815-173">Related topics</span></span>
[<span data-ttu-id="2d815-174">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2d815-174">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="2d815-175">Veja aqui o que você obtém com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="2d815-175">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="2d815-176">Plano de migração para o Skype for Business Server e Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2d815-176">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)

