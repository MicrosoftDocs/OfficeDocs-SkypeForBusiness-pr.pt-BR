---
title: Configurar a caixa postal do Sistema de Telefonia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: f5dcf6012dc9ac6659d35c29a31ee6a5ff40eec2
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2018
ms.locfileid: "22135526"
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="0950d-103">Configurar a caixa postal do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="0950d-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="0950d-104">Este artigo destina-se o [administrador do Office 365](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que deseje configurar o recurso de caixa postal do sistema telefônico para que todos na empresa.</span><span class="sxs-lookup"><span data-stu-id="0950d-104">This article is for the [Office 365 admin](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0950d-105">Caixa postal do sistema telefônico oferece suporte a mensagens de caixa postal depositar somente em uma caixa de correio do Exchange e não tem suporte para qualquer sistemas de email de terceiros.</span><span class="sxs-lookup"><span data-stu-id="0950d-105">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> <span data-ttu-id="0950d-106">Como um mecanismo de fallback, caixa postal do sistema telefônico pode reenviar mensagens usando o SMTP, o que significa que os usuários com uma caixa de correio em um sistema de email de terceiros receberá suas mensagens de caixa postal com nenhum tempo de atividade do serviço garantido ou outros recursos de caixa postal, como a alteração suas saudações e outras configurações.</span><span class="sxs-lookup"><span data-stu-id="0950d-106">As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span> 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="0950d-107">Ambientes somente em nuvem: configurar a caixa postal do sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="0950d-107">Cloud-only environments: Set up Phone System voicemail</span></span>

<span data-ttu-id="0950d-108">Skype para usuários corporativos Online e planos de chamada, caixa postal do sistema telefônico é automaticamente configurado e provisionado para usuários depois que você atribuir uma licença de **Sistema telefônico** e um número de telefone para acessá-los.</span><span class="sxs-lookup"><span data-stu-id="0950d-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="0950d-109">Se o recurso de sistema telefônico não está incluído no seu plano, você pode precisar adquirir licenças de complemento do **Sistema telefônico** .</span><span class="sxs-lookup"><span data-stu-id="0950d-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="0950d-110">Você também pode precisar adquirir uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0950d-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="0950d-111">Consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="0950d-111">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="0950d-112">[Atribuir ou remover licenças para o Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), a [Atribuir Skype para licenças de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)e as licenças do Exchange Online para as pessoas na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="0950d-112">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="0950d-113">Depois disso, elas poderão receber mensagens de voz!</span><span class="sxs-lookup"><span data-stu-id="0950d-113">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="0950d-114">Suporte a transcrição do correio de voz foi adicionada a partir de março de 2017 e é habilitado por padrão para todos os usuários e organizações.</span><span class="sxs-lookup"><span data-stu-id="0950d-114">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="0950d-115">Você pode desabilitar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="0950d-115">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>
    
## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="0950d-116">Sistema telefônico com ambientes locais</span><span class="sxs-lookup"><span data-stu-id="0950d-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="0950d-117">As seguintes informações são sobre como configurar a caixa postal do sistema telefônico para funcionar com ambientes de chamar planejar locais.</span><span class="sxs-lookup"><span data-stu-id="0950d-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="0950d-118">Se o recurso de sistema telefônico não está incluído no seu plano, você pode precisar adquirir licenças de complemento do **Sistema telefônico** .</span><span class="sxs-lookup"><span data-stu-id="0950d-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="0950d-119">Você também precisará comprar uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0950d-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="0950d-120">Consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="0950d-120">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="0950d-121">[Atribuir ou remover licenças para o Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), a [Atribuir Skype para licenças de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)e as licenças do Exchange Online para as pessoas na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="0950d-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="0950d-122">Siga as instruções na seção **habilitar usuários para serviços de correio de voz e voz de sistema telefônico** a [Configurar Skype for Business Edition do conector de nuvem guia](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="0950d-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span></span>
    
4. <span data-ttu-id="0950d-123">Suporte a transcrição do correio de voz foi adicionada a partir de março de 2017 e é habilitado por padrão para todos os usuários e organizações.</span><span class="sxs-lookup"><span data-stu-id="0950d-123">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="0950d-124">Você pode desabilitar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="0950d-124">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span> 
    
5. <span data-ttu-id="0950d-125">Você também pode ver a [caixa postal do Azure PBX suporte para o Exchange Server](https://support.microsoft.com/en-us/kb/3195158) para aprender a configurar a entrega das mensagens de caixa postal Azure para usuários de sistema telefônico que possuem um caixas de correio local.</span><span class="sxs-lookup"><span data-stu-id="0950d-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>
    
## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="0950d-126">Configuração de políticas de caixa postal em sua organização</span><span class="sxs-lookup"><span data-stu-id="0950d-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="0950d-127">Transcrição do correio de voz é habilitada por padrão e mascaramento de obscenidades transcrição está desabilitado por padrão para todas as organizações e usuários; No entanto, você pode controlá-los usando os cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0950d-127">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlets.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0950d-128">Não é possível criar uma nova instância de política para a transcrição e obscenidades transcrição mascaramento usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não é possível remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="0950d-128">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>
  
<span data-ttu-id="0950d-129">Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="0950d-129">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="0950d-130">Para ver todas as instâncias de política de caixa postal disponível, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0950d-130">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>
  
 <span data-ttu-id="0950d-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="0950d-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="0950d-133">Desativação da transcrição para sua organização</span><span class="sxs-lookup"><span data-stu-id="0950d-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="0950d-134">Como a configuração padrão para a transcrição está em para sua organização, convém desabilitá-lo usando o [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="0950d-134">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="0950d-135">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="0950d-135">To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="0950d-136">Ativando o mascaramento de obscenidades transcrição para sua organização</span><span class="sxs-lookup"><span data-stu-id="0950d-136">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="0950d-137">Mascaramento de obscenidades transcrição está desabilitado por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="0950d-137">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="0950d-138">Se houver um requisito de negócios para habilitá-lo, você pode habilitar obscenidades transcrição mascaramento usando [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="0950d-138">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="0950d-139">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="0950d-139">To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="0950d-140">Desativação da transcrição para usuário</span><span class="sxs-lookup"><span data-stu-id="0950d-140">Turning off transcription for a user</span></span>

<span data-ttu-id="0950d-141">As políticas de usuário são avaliadas antes das configurações organizacionais padrão.</span><span class="sxs-lookup"><span data-stu-id="0950d-141">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="0950d-142">Por exemplo, se a transcrição da caixa postal estiver habilitada para todos os seus usuários, você pode atribuir uma política para desabilitar a transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0950d-142">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="0950d-143">Para desabilitar a transcrição para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="0950d-143">To disable transcription for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="0950d-144">Ativando o mascaramento de obscenidades transcrições de um usuário</span><span class="sxs-lookup"><span data-stu-id="0950d-144">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="0950d-145">Para habilitar obscenidades transcrição mascaramento de um usuário específico, você pode atribuir uma política para habilitar obscenidades transcrição mascaramento de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0950d-145">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="0950d-146">Para habilitar obscenidades transcrição mascaramento de um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="0950d-146">To enable transcription profanity masking for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="0950d-p111">[!IMPORTANTE] O serviço de caixa postal no Office 365 armazena em cache as políticas de caixa postal e atualiza o cache a cada 4 horas. Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas.</span><span class="sxs-lookup"><span data-stu-id="0950d-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span> 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="0950d-149">Ajude os usuários a conhecer os recursos da caixa postal do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0950d-149">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="0950d-150">Temos informações de treinamento e artigos para ajudar seus usuários a obter êxito com Skype caixa postal de negócios.</span><span class="sxs-lookup"><span data-stu-id="0950d-150">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="0950d-151">Indique os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="0950d-151">Point them to the following articles:</span></span>
  
- <span data-ttu-id="0950d-152">[Verificar Skype para opções e caixa postal de negócios](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Este artigo explica como ouvir sua caixa postal no Skype para os negócios, alterar sua saudação da caixa postal, alterar as configurações de caixa postal e ouvir suas mensagens de voz em velocidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="0950d-152">[Check Skype for Business voicemail and options](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>
    
- [<span data-ttu-id="0950d-153">Treinamento do Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="0950d-153">Skype for Business 2016 training</span></span>](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a><span data-ttu-id="0950d-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="0950d-154">Related topics</span></span>
[<span data-ttu-id="0950d-155">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0950d-155">Set up Skype for Business Online</span></span>](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[<span data-ttu-id="0950d-156">Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="0950d-156">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

  
 