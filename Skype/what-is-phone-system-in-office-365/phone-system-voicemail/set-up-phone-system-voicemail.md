---
title: "Configurar a caixa postal do sistema telefônico"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: 7d4ad9fa310ee8b90b813bfe949401c602c6a2f2
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="5df02-103">Configurar a caixa postal do sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="5df02-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="5df02-104">Este artigo destina-se o [administrador do Office 365](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que deseje configurar o recurso de caixa postal do sistema telefônico para que todos na empresa.</span><span class="sxs-lookup"><span data-stu-id="5df02-104">This article is for the [Office 365 admin](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5df02-105">Caixa postal do sistema telefônico oferece suporte a mensagens de caixa postal depositar somente em uma caixa de correio do Exchange e não tem suporte para qualquer sistemas de email de terceiros.</span><span class="sxs-lookup"><span data-stu-id="5df02-105">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> <span data-ttu-id="5df02-106">Como um mecanismo de fallback, caixa postal do sistema telefônico pode reenviar mensagens usando o SMTP, o que significa que os usuários com uma caixa de correio em um sistema de email de terceiros receberá suas mensagens de caixa postal com nenhum tempo de atividade do serviço garantido ou outros recursos de caixa postal, como a alteração suas saudações e outras configurações.</span><span class="sxs-lookup"><span data-stu-id="5df02-106">As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span> 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="5df02-107">Ambientes somente em nuvem: configurar a caixa postal do sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="5df02-107">Cloud-only environments: Set up Phone System voicemail</span></span>

<span data-ttu-id="5df02-108">Skype para usuários corporativos Online e planos de chamada, caixa postal do sistema telefônico é automaticamente configurado e provisionado para usuários depois que você atribuir uma licença de **Sistema telefônico** e um número de telefone para acessá-los.</span><span class="sxs-lookup"><span data-stu-id="5df02-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="5df02-109">Se o recurso de sistema telefônico não está incluído no seu plano, você pode precisar adquirir licenças de complemento do **Sistema telefônico** .</span><span class="sxs-lookup"><span data-stu-id="5df02-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="5df02-110">Você também pode precisar adquirir uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5df02-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="5df02-111">Consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="5df02-111">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="5df02-112">[Atribuir ou remover licenças para o Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), a [Atribuir Skype para licenças de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)e as licenças do Exchange Online para as pessoas na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="5df02-112">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="5df02-113">Depois que você fizer isso, eles poderão receber mensagens de caixa postal!</span><span class="sxs-lookup"><span data-stu-id="5df02-113">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="5df02-114">Suporte a transcrição do correio de voz foi adicionada a partir de março de 2017 e é habilitado por padrão para todos os usuários e organizações.</span><span class="sxs-lookup"><span data-stu-id="5df02-114">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="5df02-115">Você pode desabilitar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="5df02-115">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>
    
## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="5df02-116">Sistema telefônico com ambientes locais</span><span class="sxs-lookup"><span data-stu-id="5df02-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="5df02-117">As seguintes informações são sobre como configurar a caixa postal do sistema telefônico para funcionar com ambientes de chamar planejar locais.</span><span class="sxs-lookup"><span data-stu-id="5df02-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="5df02-118">Se o recurso de sistema telefônico não está incluído no seu plano, você pode precisar adquirir licenças de complemento do **Sistema telefônico** .</span><span class="sxs-lookup"><span data-stu-id="5df02-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="5df02-119">Você também precisará comprar uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5df02-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="5df02-120">Consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="5df02-120">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="5df02-121">[Atribuir ou remover licenças para o Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), a [Atribuir Skype para licenças de negócios e equipes da Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)e as licenças do Exchange Online para as pessoas na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="5df02-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="5df02-122">Siga as instruções na seção **habilitar usuários para serviços de correio de voz e voz de sistema telefônico** a [Configurar Skype for Business Edition do conector de nuvem guia](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="5df02-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span></span>
    
4. <span data-ttu-id="5df02-123">Suporte a transcrição do correio de voz foi adicionada a partir de março de 2017 e é habilitado por padrão para todos os usuários e organizações.</span><span class="sxs-lookup"><span data-stu-id="5df02-123">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="5df02-124">Você pode desabilitar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="5df02-124">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span> 
    
5. <span data-ttu-id="5df02-125">Você também pode ver a [caixa postal do Azure PBX suporte para o Exchange Server](https://support.microsoft.com/en-us/kb/3195158) para aprender a configurar a entrega das mensagens de caixa postal Azure para usuários de sistema telefônico que possuem um caixas de correio local.</span><span class="sxs-lookup"><span data-stu-id="5df02-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>
    
## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="5df02-126">Configuração de políticas de caixa postal em sua organização</span><span class="sxs-lookup"><span data-stu-id="5df02-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="5df02-127">Transcrição do correio de voz é habilitada por padrão para todas as organizações e usuários; No entanto, você pode controlá-la usando os cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="5df02-127">Voicemail transcription is enabled by default for all organizations and users; however, you can control it by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlets.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5df02-128">Não é possível criar uma nova instância de política para a transcrição usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não é possível remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="5df02-128">You can't create a new policy instance for transcription using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>
  
<span data-ttu-id="5df02-129">Você pode gerenciar as configurações de transcrição para seus usuários usando políticas de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="5df02-129">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="5df02-130">Para ver todas as instâncias de política de caixa postal disponível, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="5df02-130">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx) cmdlet.</span></span>
  
 <span data-ttu-id="5df02-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="5df02-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="5df02-133">Desativação da transcrição para sua organização</span><span class="sxs-lookup"><span data-stu-id="5df02-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="5df02-134">Como a configuração padrão para a transcrição está em para sua organização, convém desabilitá-lo usando o [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="5df02-134">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="5df02-135">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="5df02-135">To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="5df02-136">Desativação da transcrição para usuário</span><span class="sxs-lookup"><span data-stu-id="5df02-136">Turning off transcription for a user</span></span>

<span data-ttu-id="5df02-137">Políticas de usuário são avaliadas antes das configurações padrão organizacional.</span><span class="sxs-lookup"><span data-stu-id="5df02-137">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="5df02-138">Por exemplo, se a transcrição da caixa postal estiver habilitada para todos os seus usuários, você pode atribuir uma política para desabilitar a transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="5df02-138">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="5df02-139">Para desabilitar a transcrição para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="5df02-139">To disable transcription for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="5df02-p110">[!IMPORTANTE] O serviço de caixa postal no Office 365 armazena em cache as políticas de caixa postal e atualiza o cache a cada 4 horas. Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas.</span><span class="sxs-lookup"><span data-stu-id="5df02-p110">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span> 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="5df02-142">Ajude os usuários a conhecer os recursos da caixa postal do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5df02-142">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="5df02-143">Temos informações de treinamento e artigos para ajudar seus usuários a obter êxito com Skype caixa postal de negócios.</span><span class="sxs-lookup"><span data-stu-id="5df02-143">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="5df02-144">Apontá-los para os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="5df02-144">Point them to the following articles:</span></span>
  
- <span data-ttu-id="5df02-145">[Verificar Skype para opções e caixa postal de negócios](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Este artigo explica como ouvir sua caixa postal no Skype para os negócios, alterar sua saudação da caixa postal, alterar as configurações de caixa postal e ouvir suas mensagens de voz em velocidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="5df02-145">[Check Skype for Business voicemail and options](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>
    
- [<span data-ttu-id="5df02-146">Treinamento do Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="5df02-146">Skype for Business 2016 training</span></span>](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a><span data-ttu-id="5df02-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5df02-147">Related topics</span></span>
[<span data-ttu-id="5df02-148">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5df02-148">Set up Skype for Business Online</span></span>](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[<span data-ttu-id="5df02-149">Aqui está o que fazer com o sistema telefônico no Office 365</span><span class="sxs-lookup"><span data-stu-id="5df02-149">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)
