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
description: 'Aprenda como configurar a caixa postal do sistema de telefonia (Cloud PBX) para seus usuários do Skype for Business. '
ms.openlocfilehash: d311c6d0c0f6965d81f557c2080a9bb331de557b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252885"
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="bc83a-103">Configurar a caixa postal do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="bc83a-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="bc83a-104">Este artigo destina-se ao [administrador do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que deseja configurar o recurso de caixa postal do Sistema de Telefonia para todos na empresa.</span><span class="sxs-lookup"><span data-stu-id="bc83a-104">This article is for the [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up Skype for Business Cloud PBX voicemail for everyone in their business.</span></span>

> [!NOTE]
> <span data-ttu-id="bc83a-105">A caixa postal do Sistema de Telefonia só suporta depositar mensagens de voz em uma caixa de correios do Exchange, mas não dá suporte a nenhum sistema de email de terceiros.</span><span class="sxs-lookup"><span data-stu-id="bc83a-105">Cloud PBX voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> <span data-ttu-id="bc83a-106">Como um mecanismo de fallback, a caixa postal do Sistema de Telefonia pode reenviar mensagens usando SMTP, o que significa que os usuários com uma caixa de correio em um sistema de email de terceiros receberão suas mensagens de voz sem serviço garantido de uptime ou outros recursos de caixa postal, como alterar as saudações e outras configurações.</span><span class="sxs-lookup"><span data-stu-id="bc83a-106">As a fallback mechanism, Cloud PBX Voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings .</span></span>

## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="bc83a-107">Ambientes somente em nuvem: configurar a caixa postal do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="bc83a-107">Set up Phone System voicemail</span></span>

<span data-ttu-id="bc83a-108">Para o Skype for Business Online e usuários de planos de chamada, a caixa postal do Sistema de Telefonia é automaticamente configurada e provisionada para usuários depois que você atribuir uma licença do **Sistema de Telefonia** e um número de telefone para acessá-los.</span><span class="sxs-lookup"><span data-stu-id="bc83a-108">For Skype for Business Online and PSTN Calling users, Cloud PBX voicemail is automatically set up and provisioned for users after you assign a Skype for Business Cloud PBX license and a phone number to them.</span></span>

1. <span data-ttu-id="bc83a-109">Se o recurso de Sistema de Telefonia não estiver incluído no seu plano, você pode precisar adquirir licenças de complemento do **Sistema de Telefonia**.</span><span class="sxs-lookup"><span data-stu-id="bc83a-109">If the Cloud PBX feature isn't included in your plan, you may need to purchase Cloud PBX add-on licenses.</span></span> <span data-ttu-id="bc83a-110">Você também precisará comprar uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bc83a-110">You may also need to purchase an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="bc83a-111">Confira [Licenciamento de complementos do Skype for Business e do Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="bc83a-111">[Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>

2. <span data-ttu-id="bc83a-112">[Atribuir ou remover licenças de assinatura no Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), a [Atribuir licenças do Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) e as licenças do Exchange Online para as pessoas da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="bc83a-112">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) and the[Assign Skype for Business licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) and Exchange Online Plan 2 licenses to the people in your business.</span></span> <span data-ttu-id="bc83a-113">Depois disso, elas poderão receber mensagens de voz!</span><span class="sxs-lookup"><span data-stu-id="bc83a-113">After you do that, they will be able to receive voicemail messages!</span></span>

3. <span data-ttu-id="bc83a-114">O suporte para transcrição da caixa postal foi incluído a partir de março de 2017 e é habilitado por padrão para todas as organizações e usuários.</span><span class="sxs-lookup"><span data-stu-id="bc83a-114">Support for Voicemail transcription has been added as of March 2017 and is enabled by default for all tenants and users.</span></span> <span data-ttu-id="bc83a-115">Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="bc83a-115">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="bc83a-116">Sistema de Telefonia com ambientes locais</span><span class="sxs-lookup"><span data-stu-id="bc83a-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="bc83a-117">As seguintes informações são sobre como configurar a caixa postal do Sistema de Telefonia para funcionar com ambientes de Planos de Chamada locais.</span><span class="sxs-lookup"><span data-stu-id="bc83a-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>

1. <span data-ttu-id="bc83a-118">Se o recurso de Sistema de Telefonia não estiver incluído no seu plano, você pode precisar adquirir licenças de complemento do **Sistema de Telefonia**.</span><span class="sxs-lookup"><span data-stu-id="bc83a-118">If the Cloud PBX feature isn't included in your plan, you may need to purchase Cloud PBX add-on licenses.</span></span> <span data-ttu-id="bc83a-119">Você também precisará comprar uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bc83a-119">You also need to purchase an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="bc83a-120">Confira [Licenciamento de complementos do Skype for Business e do Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="bc83a-120">[Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>

2. <span data-ttu-id="bc83a-121">[Atribuir ou remover licenças de assinatura no Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), a [Atribuir licenças do Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) e as licenças do Exchange Online para as pessoas da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="bc83a-121">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) and the[Assign Skype for Business licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) and Exchange Online Plan 2 licenses to the people in your business.</span></span>

3. <span data-ttu-id="bc83a-122">Depois, siga as instruções na seção **Habilitar usuários para os serviços de caixa postal e de voz do Sistema de Telefonia** seção do [guia Configurar o Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="bc83a-122">Next, follow the instructions in the **Enable users for Cloud PBX voice and voice mail services** section of the[Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span></span>

4. <span data-ttu-id="bc83a-123">O suporte para transcrição da caixa postal foi incluído a partir de março de 2017 e é habilitado por padrão para todas as organizações e usuários.</span><span class="sxs-lookup"><span data-stu-id="bc83a-123">Support for Voicemail transcription has been added as of March 2017 and is enabled by default for all tenants and users.</span></span> <span data-ttu-id="bc83a-124">Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="bc83a-124">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="bc83a-125">Você também pode ver a [suporte da caixa postal do Azure para o Exchange Server](https://support.microsoft.com/en-us/kb/3195158) para aprender a configurar a entrega das mensagens de caixa postal do Azure para usuários do Sistema de Telefonia que possuem caixas de correio locais.</span><span class="sxs-lookup"><span data-stu-id="bc83a-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="bc83a-126">Configuração de políticas de caixa postal em sua organização</span><span class="sxs-lookup"><span data-stu-id="bc83a-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="bc83a-127">A transcrição do correio de voz é habilitada por padrão e o mascaramento de obscenidades está desativado por padrão para todas as organizações e usuários; no entanto, você pode controlá-los usando os cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="bc83a-127">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc83a-128">Você não pode criar uma nova instância para transcrição e mascaramento de obscenidades usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não pode remover uma instância existente de política usando o cmdlet **Remove-CsOnlineVoiceMailPolicy**.</span><span class="sxs-lookup"><span data-stu-id="bc83a-128">You can't create a new policy instance for transcription using the **New-CsOnlineVoiceMailPolicy** cmdlet and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="bc83a-129">Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="bc83a-129">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="bc83a-130">Para ver todas as instâncias de política de caixa postal disponíveis, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="bc83a-130">To see the all available voicemail policy instances, you can use the[Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="bc83a-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="bc83a-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>

![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)

### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="bc83a-133">Desativação da transcrição para sua organização</span><span class="sxs-lookup"><span data-stu-id="bc83a-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="bc83a-134">Como a configuração padrão para transcrição é ativada para sua organização, talvez você deseje desativá-la usando o cdmlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="bc83a-134">Because the default setting for transcription is on for your organization, you may want to disable it by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="bc83a-135">Para isso, execute:</span><span class="sxs-lookup"><span data-stu-id="bc83a-135">To do this run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="bc83a-136">Ativação do mascaramento de obscenidades para sua organização</span><span class="sxs-lookup"><span data-stu-id="bc83a-136">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="bc83a-137">Mascaramento de obscenidades está desativado por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="bc83a-137">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="bc83a-138">Se houver um requisito de negócios para habilitá-lo, você pode habilitar o mascaramento de obscenidades usando [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="bc83a-138">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="bc83a-139">Para isso, execute:</span><span class="sxs-lookup"><span data-stu-id="bc83a-139">To do this run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="bc83a-140">Desativação da transcrição para usuário</span><span class="sxs-lookup"><span data-stu-id="bc83a-140">Turning off transcription for a user</span></span>

<span data-ttu-id="bc83a-141">As políticas de usuário são avaliadas antes das configurações organizacionais padrão.</span><span class="sxs-lookup"><span data-stu-id="bc83a-141">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="bc83a-142">Por exemplo, se a transcrição da caixa postal for habilitada para todos os usuários, você pode atribuir uma política para desativar a transcrição de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="bc83a-142">For example, if voicemail transcription is enabled for all of your users you can assign a policy to disable transcription for a specific user using [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="bc83a-143">Para desativar a transcrição para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="bc83a-143">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="bc83a-144">Ativação do mascaramento de obscenidades para um usuário</span><span class="sxs-lookup"><span data-stu-id="bc83a-144">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="bc83a-145">Para habilitar o mascaramento de obscenidades para um usuário específico, você pode atribuir uma política para habilitar o mascaramento de obscenidades de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="bc83a-145">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="bc83a-146">Para habilitar o mascaramento de obscenidades para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="bc83a-146">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="bc83a-p111">[!IMPORTANTE] O serviço de caixa postal no Office 365 armazena em cache as políticas de caixa postal e atualiza o cache a cada 4 horas. Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas.</span><span class="sxs-lookup"><span data-stu-id="bc83a-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="bc83a-149">Ajude seus usuários a conhecerem os recursos da caixa postal do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bc83a-149">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="bc83a-150">Há uma grande quantidade de informação de treinamento e artigos para ajudar os usuários a terem êxito com a caixa postal do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="bc83a-150">We have a lot of training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="bc83a-151">Indique os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="bc83a-151">Point them to the following articles:</span></span>

- <span data-ttu-id="bc83a-152">[Verificar a caixa postal e as opções do Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): este artigo explica como ouvir as mensagens da caixa postal no Skype for Business, alterar a saudação da caixa postal e ouvir as mensagens da caixa postal em diferentes velocidades.</span><span class="sxs-lookup"><span data-stu-id="bc83a-152">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="bc83a-153">Treinamento do Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="bc83a-153">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="bc83a-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bc83a-154">Related topics</span></span>
[<span data-ttu-id="bc83a-155">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bc83a-155">Set up Skype for Business Online</span></span>](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[<span data-ttu-id="bc83a-156">Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="bc83a-156">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)


