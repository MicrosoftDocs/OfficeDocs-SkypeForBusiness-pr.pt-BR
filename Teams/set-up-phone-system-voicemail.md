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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba como configurar o correio de voz na nuvem para seus usuários. '
ms.openlocfilehash: 49f64f4b4cda9830bc189310efc26f39859009af
ms.sourcegitcommit: 1764aa53441b9de5a8cfa37be344657176ee5703
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2019
ms.locfileid: "34808021"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="20aee-103">Configurar a caixa postal na nuvem</span><span class="sxs-lookup"><span data-stu-id="20aee-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="20aee-104">Este artigo é para o [administrador do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que deseja configurar o recurso de correio de voz na nuvem para todos os participantes da empresa.</span><span class="sxs-lookup"><span data-stu-id="20aee-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="20aee-105">O correio de voz na nuvem aceita o depósito de mensagens de correio de voz apenas em uma caixa de correio do Exchange e não é compatível com sistemas de email de terceiros.</span><span class="sxs-lookup"><span data-stu-id="20aee-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="20aee-106">Ambientes somente de nuvem: configurar o correio de voz na nuvem</span><span class="sxs-lookup"><span data-stu-id="20aee-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="20aee-107">Para os usuários do Skype for Business Online e dos planos de chamada, o correio de voz na nuvem é automaticamente configurado e provisionado para os usuários após a atribuição de uma licença do **sistema telefônico** e um número de telefone a ele.</span><span class="sxs-lookup"><span data-stu-id="20aee-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="20aee-108">Se o recurso do sistema de telefonia não estiver incluído no seu plano, talvez seja necessário comprar licenças complementares do **sistema telefônico** .</span><span class="sxs-lookup"><span data-stu-id="20aee-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="20aee-109">Você também pode precisar comprar uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="20aee-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="20aee-110">Consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="20aee-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="20aee-111">[Atribuir ou remover licenças do Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [atribuir licenças do Microsoft Teams](assign-teams-licenses.md)e licenças do Exchange Online às pessoas de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="20aee-111">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="20aee-112">Depois disso, elas poderão receber mensagens de voz!</span><span class="sxs-lookup"><span data-stu-id="20aee-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="20aee-113">O suporte para a transcrição de correio de voz foi adicionado a partir de março de 2017 e é habilitado por padrão para todas as organizações e usuários.</span><span class="sxs-lookup"><span data-stu-id="20aee-113">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="20aee-114">Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="20aee-114">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="20aee-115">Sistema de Telefonia com ambientes locais</span><span class="sxs-lookup"><span data-stu-id="20aee-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="20aee-116">As informações a seguir tratam da configuração do correio de voz em nuvem para trabalhar com ambientes de plano de chamada local.</span><span class="sxs-lookup"><span data-stu-id="20aee-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="20aee-117">Se o recurso do sistema de telefonia não estiver incluído no seu plano, talvez seja necessário comprar licenças complementares do **sistema telefônico** .</span><span class="sxs-lookup"><span data-stu-id="20aee-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="20aee-118">Você também precisa comprar uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="20aee-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="20aee-119">Consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="20aee-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="20aee-120">[Atribuir ou remover licenças do Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [atribuir licenças do Microsoft Teams](assign-teams-licenses.md)e licenças do Exchange Online às pessoas de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="20aee-120">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="20aee-121">Siga as instruções correspondentes à solução de chamadas PSTN locais implantadas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="20aee-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="20aee-122">Para o Cloud Connector Edition, siga as instruções na seção **habilitar usuários para voz do sistema de telefone e serviços de correio de voz** do [guia configurar o Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="20aee-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="20aee-123">Para chamadas PSTN com o Skype for Business Server, siga [habilitar o recurso usuários do Enterprise Voice no local](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span><span class="sxs-lookup"><span data-stu-id="20aee-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="20aee-124">Para o roteamento direto do Teams, siga a seção **Configurar o número de telefone e habilitar o** recurso de correio de voz empresarial e [Configurar o roteamento direto](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span><span class="sxs-lookup"><span data-stu-id="20aee-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="20aee-125">O suporte para a transcrição de correio de voz foi adicionado a partir de março de 2017 e é habilitado por padrão para todas as organizações e usuários.</span><span class="sxs-lookup"><span data-stu-id="20aee-125">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="20aee-126">Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="20aee-126">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="20aee-127">As mensagens de correio de voz são entregues à caixa de correio do Exchange do usuário via SMTP roteado por meio do Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="20aee-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="20aee-128">Para habilitar a entrega bem-sucedida dessas mensagens, certifique-se de que os conectores do Exchange estejam configurados corretamente entre seus servidores Exchange e a proteção do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="20aee-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection.</span></span> <span data-ttu-id="20aee-129">[Usar conectores para configurar o fluxo de emails](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="20aee-129">[Use Connectors to Configure Mail Flow](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

6. <span data-ttu-id="20aee-130">Para habilitar recursos de correio de voz, como personalizar saudações e correio de voz visual nos clientes Skype for Business, é necessário conectividade do Office 365 para a caixa de correio do Exchange Server via Exchange Web Services.</span><span class="sxs-lookup"><span data-stu-id="20aee-130">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="20aee-131">Para habilitar essa conectividade, você deve configurar o novo protocolo de autenticação OAuth do Exchange descrito em [Configurar a autenticação OAuth entre as organizações Exchange e Exchange Online](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="20aee-131">To enable this connectivity you must configure the new Exchange Oauth authentication protocol describe in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span></span> 

> [!NOTE]
> <span data-ttu-id="20aee-132">O assistente híbrido do Exchange executado do Exchange 2013 CU5 ou superior atenderá aos requisitos nas etapas 5 e 6 automaticamente.</span><span class="sxs-lookup"><span data-stu-id="20aee-132">The Exchange Hybrid Wizard run from Exchange 2013 CU5 or greater will handle the requirements in steps 5 and 6 automatically.</span></span> 

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="20aee-133">Configuração de políticas de caixa postal em sua organização</span><span class="sxs-lookup"><span data-stu-id="20aee-133">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="20aee-134">Para clientes do Skype for Business, desabilitar o correio de voz por meio de uma política de chamadas do Microsoft Teams também pode desabilitar o serviço de correio de voz para seus usuários do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="20aee-134">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="20aee-135">A transcrição do correio de voz é habilitada por padrão e o mascaramento de obscenidades está desativado por padrão para todas as organizações e usuários; no entanto, você pode controlá-los usando os cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="20aee-135">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="20aee-136">As mensagens de correio de voz recebidas pelos usuários em sua organização são transcritas na região onde o seu locatário do Office 365 está hospedado.</span><span class="sxs-lookup"><span data-stu-id="20aee-136">Voicemail messages received by users in your organization are transcribed in the region where your Office 365 tenant is hosted.</span></span> <span data-ttu-id="20aee-137">A região em que seu locatário está hospedado pode não ser a mesma região em que o usuário que está recebendo a mensagem de correio de voz está localizado.</span><span class="sxs-lookup"><span data-stu-id="20aee-137">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="20aee-138">Para exibir a região em que seu locatário está hospedado, vá para a página de [perfil da organização](https://go.microsoft.com/fwlink/p/?linkid=2067339) e clique em **Exibir detalhes** ao lado de **local de dados**.</span><span class="sxs-lookup"><span data-stu-id="20aee-138">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20aee-139">Você não pode criar uma nova instância de política para transcrição e a máscara de obscenidades de transcrição usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não pode remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="20aee-139">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="20aee-140">Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="20aee-140">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="20aee-141">Para ver todas as instâncias de política de correio de voz disponíveis, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="20aee-141">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="20aee-142">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="20aee-142">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="20aee-144">Desativação da transcrição para sua organização</span><span class="sxs-lookup"><span data-stu-id="20aee-144">Turning off transcription for your organization</span></span>

<span data-ttu-id="20aee-145">Como a configuração padrão para a transcrição está ativada para sua organização, talvez você queira desabilitá-la usando [set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="20aee-145">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="20aee-146">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="20aee-146">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="20aee-147">Ativação do mascaramento de obscenidades para sua organização</span><span class="sxs-lookup"><span data-stu-id="20aee-147">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="20aee-148">Mascaramento de obscenidades está desativado por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="20aee-148">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="20aee-149">Se houver um requisito de negócios para habilitá-lo, você pode habilitar o mascaramento de obscenidades usando [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="20aee-149">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="20aee-150">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="20aee-150">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="20aee-151">Desativação da transcrição para usuário</span><span class="sxs-lookup"><span data-stu-id="20aee-151">Turning off transcription for a user</span></span>

<span data-ttu-id="20aee-152">As políticas de usuário são avaliadas antes das configurações organizacionais padrão.</span><span class="sxs-lookup"><span data-stu-id="20aee-152">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="20aee-153">Por exemplo, se a transcrição de correio de voz estiver habilitada para todos os seus usuários, você poderá atribuir uma política para desabilitar a transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="20aee-153">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="20aee-154">Para desabilitar a transcrição para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="20aee-154">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="20aee-155">Ativação do mascaramento de obscenidades para um usuário</span><span class="sxs-lookup"><span data-stu-id="20aee-155">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="20aee-156">Para habilitar o mascaramento de obscenidades para um usuário específico, você pode atribuir uma política para habilitar o mascaramento de obscenidades de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="20aee-156">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="20aee-157">Para habilitar o mascaramento de obscenidades para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="20aee-157">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="20aee-p114">[!IMPORTANTE] O serviço de caixa postal no Office 365 armazena em cache as políticas de caixa postal e atualiza o cache a cada 4 horas. Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas.</span><span class="sxs-lookup"><span data-stu-id="20aee-p114">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="20aee-160">Ajude os usuários a conhecer os recursos da caixa postal do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="20aee-160">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="20aee-161">Temos informações e artigos de treinamento para ajudar seus usuários a ser bem-sucedidos com o correio de voz do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="20aee-161">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="20aee-162">Indique os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="20aee-162">Point them to the following articles:</span></span>

- <span data-ttu-id="20aee-163">[Verifique a caixa postal e as opções do Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Este artigo explica como ouvir o seu correio de voz no Skype for Business, alterar a saudação da sua caixa postal, mudar suas configurações de correio de voz e ouvir o seu correio de voz em diferentes velocidades.</span><span class="sxs-lookup"><span data-stu-id="20aee-163">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="20aee-164">Treinamento do Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="20aee-164">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="20aee-165">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="20aee-165">Related topics</span></span>
[<span data-ttu-id="20aee-166">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="20aee-166">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="20aee-167">Veja aqui o que você obtém com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="20aee-167">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="20aee-168">Plano de migração para o Skype for Business Server e Exchange Server</span><span class="sxs-lookup"><span data-stu-id="20aee-168">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


