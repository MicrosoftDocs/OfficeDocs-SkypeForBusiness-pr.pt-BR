---
title: Configurar a caixa postal do Sistema de Telefonia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: fa0783cf51b7d3b7bf29b4948994060a3d1f63a1
ms.sourcegitcommit: 969a71ef0ac0030c27bd2455c3bf9d536dbcd752
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2018
ms.locfileid: "27182508"
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="aed13-103">Configurar a caixa postal do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="aed13-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="aed13-104">Este artigo destina-se o [administrador do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que deseje configurar o recurso de caixa postal do sistema telefônico para que todos na empresa.</span><span class="sxs-lookup"><span data-stu-id="aed13-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="aed13-p101">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems. As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span><span class="sxs-lookup"><span data-stu-id="aed13-p101">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems. As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span>

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="aed13-107">Ambientes somente em nuvem: configurar a caixa postal do sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="aed13-107">Cloud-only environments: Set up Phone System voicemail</span></span>

<span data-ttu-id="aed13-108">Skype para usuários corporativos Online e planos de chamada, caixa postal do sistema telefônico é automaticamente configurado e provisionado para usuários depois que você atribuir uma licença de **Sistema telefônico** e um número de telefone para acessá-los.</span><span class="sxs-lookup"><span data-stu-id="aed13-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="aed13-p102">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses. You may also need to purchase an Exchange Online license. See [Skype for Business and Microsoft Teams add-on licensing](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="aed13-p102">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses. You may also need to purchase an Exchange Online license. See [Skype for Business and Microsoft Teams add-on licensing](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
2. <span data-ttu-id="aed13-p103">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), and the Exchange Online licenses to the people in your business. After you do that, they will be able to receive voicemail messages!</span><span class="sxs-lookup"><span data-stu-id="aed13-p103">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), and the Exchange Online licenses to the people in your business. After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="aed13-p104">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span><span class="sxs-lookup"><span data-stu-id="aed13-p104">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="aed13-116">Sistema de Telefonia com ambientes locais</span><span class="sxs-lookup"><span data-stu-id="aed13-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="aed13-117">As seguintes informações são sobre como configurar a caixa postal do Sistema de Telefonia para funcionar com ambientes de Planos de Chamada locais.</span><span class="sxs-lookup"><span data-stu-id="aed13-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="aed13-p105">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses. You also need to purchase an Exchange Online license. See [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="aed13-p105">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses. You also need to purchase an Exchange Online license. See [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
2. <span data-ttu-id="aed13-121">[Atribuir ou remover licenças para o Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), a [Atribuir Skype para licenças de negócios e equipes da Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)e as licenças do Exchange Online para as pessoas na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="aed13-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="aed13-122">Siga as instruções na seção **habilitar usuários para serviços de correio de voz e voz de sistema telefônico** a [Configurar Skype for Business Edition do conector de nuvem guia](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="aed13-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span>

4. <span data-ttu-id="aed13-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span><span class="sxs-lookup"><span data-stu-id="aed13-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="aed13-125">Você também pode ver a [suporte da caixa postal do Azure para o Exchange Server](https://support.microsoft.com/kb/3195158) para aprender a configurar a entrega das mensagens de caixa postal do Azure para usuários do Sistema de Telefonia que possuem caixas de correio locais.</span><span class="sxs-lookup"><span data-stu-id="aed13-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>

6. <span data-ttu-id="aed13-126">Também leia e siga as etapas descritas no seguinte documento: [Assistente de configuração híbrida](https://docs.microsoft.com/en-us/exchange/hybrid-configuration-wizard)</span><span class="sxs-lookup"><span data-stu-id="aed13-126">Please also read and follow the steps outlined in the following document: [Hybrid Configuration wizard](https://docs.microsoft.com/en-us/exchange/hybrid-configuration-wizard)</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="aed13-127">Configuração de políticas de caixa postal em sua organização</span><span class="sxs-lookup"><span data-stu-id="aed13-127">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="aed13-128">A transcrição do correio de voz é habilitada por padrão e o mascaramento de obscenidades está desativado por padrão para todas as organizações e usuários; no entanto, você pode controlá-los usando os cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="aed13-128">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aed13-129">Não é possível criar uma nova instância de política para a transcrição e obscenidades transcrição mascaramento usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não é possível remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="aed13-129">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="aed13-130">Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="aed13-130">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="aed13-131">Para ver todas as instâncias de política de caixa postal disponível, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="aed13-131">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="aed13-132">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="aed13-132">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="aed13-134">Desativação da transcrição para sua organização</span><span class="sxs-lookup"><span data-stu-id="aed13-134">Turning off transcription for your organization</span></span>

<span data-ttu-id="aed13-135">Como a configuração padrão para a transcrição está em para sua organização, convém desabilitá-lo usando o [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="aed13-135">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="aed13-136">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="aed13-136">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="aed13-137">Ativação do mascaramento de obscenidades para sua organização</span><span class="sxs-lookup"><span data-stu-id="aed13-137">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="aed13-138">Mascaramento de obscenidades está desativado por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="aed13-138">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="aed13-139">Se houver um requisito de negócios para habilitá-lo, você pode habilitar o mascaramento de obscenidades usando [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="aed13-139">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="aed13-140">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="aed13-140">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="aed13-141">Desativação da transcrição para usuário</span><span class="sxs-lookup"><span data-stu-id="aed13-141">Turning off transcription for a user</span></span>

<span data-ttu-id="aed13-142">As políticas de usuário são avaliadas antes das configurações organizacionais padrão.</span><span class="sxs-lookup"><span data-stu-id="aed13-142">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="aed13-143">Por exemplo, se a transcrição da caixa postal estiver habilitada para todos os seus usuários, você pode atribuir uma política para desabilitar a transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="aed13-143">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="aed13-144">Para desabilitar a transcrição para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="aed13-144">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="aed13-145">Ativação do mascaramento de obscenidades para um usuário</span><span class="sxs-lookup"><span data-stu-id="aed13-145">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="aed13-146">Para habilitar o mascaramento de obscenidades para um usuário específico, você pode atribuir uma política para habilitar o mascaramento de obscenidades de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="aed13-146">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="aed13-147">Para habilitar o mascaramento de obscenidades para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="aed13-147">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="aed13-p111">[!IMPORTANTE] O serviço de caixa postal no Office 365 armazena em cache as políticas de caixa postal e atualiza o cache a cada 4 horas. Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas.</span><span class="sxs-lookup"><span data-stu-id="aed13-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="aed13-150">Ajude os usuários a conhecer os recursos da caixa postal do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="aed13-150">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="aed13-151">Temos informações de treinamento e artigos para ajudar seus usuários a obter êxito com Skype caixa postal de negócios.</span><span class="sxs-lookup"><span data-stu-id="aed13-151">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="aed13-152">Indique os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="aed13-152">Point them to the following articles:</span></span>

- <span data-ttu-id="aed13-153">[Verificar Skype para opções e caixa postal de negócios](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Este artigo explica como ouvir sua caixa postal no Skype para os negócios, alterar sua saudação da caixa postal, alterar as configurações de caixa postal e ouvir suas mensagens de voz em velocidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="aed13-153">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="aed13-154">Treinamento do Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="aed13-154">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="aed13-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="aed13-155">Related topics</span></span>
[<span data-ttu-id="aed13-156">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="aed13-156">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="aed13-157">Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="aed13-157">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)


