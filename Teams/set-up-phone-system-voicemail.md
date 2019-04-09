---
title: Configurar a caixa postal na nuvem
author: CarolynRowe
ms.author: crowe
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba como configurar a caixa postal de nuvem para seus usuários. '
ms.openlocfilehash: 3f8729c9737bcbf0e7731ac61b38d56d708e15dc
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517148"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="f21d5-103">Configurar a caixa postal na nuvem</span><span class="sxs-lookup"><span data-stu-id="f21d5-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="f21d5-104">Este artigo destina-se o [administrador do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) que deseje configurar o recurso de caixa postal de nuvem para que todos na empresa.</span><span class="sxs-lookup"><span data-stu-id="f21d5-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="f21d5-105">Caixa postal de nuvem oferece suporte a mensagens de caixa postal depositar somente em uma caixa de correio do Exchange e não tem suporte para qualquer sistemas de email de terceiros.</span><span class="sxs-lookup"><span data-stu-id="f21d5-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="f21d5-106">Ambientes somente em nuvem: configurar a caixa postal de nuvem</span><span class="sxs-lookup"><span data-stu-id="f21d5-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="f21d5-107">Skype para usuários corporativos Online e planos de chamada, caixa postal de nuvem é automaticamente configurado e provisionado para usuários depois que você atribuir uma licença de **Sistema telefônico** e um número de telefone para acessá-los.</span><span class="sxs-lookup"><span data-stu-id="f21d5-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="f21d5-108">Se o recurso de sistema telefônico não está incluído no seu plano, você pode precisar adquirir licenças de complemento do **Sistema telefônico** .</span><span class="sxs-lookup"><span data-stu-id="f21d5-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="f21d5-109">Você também pode precisar adquirir uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f21d5-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="f21d5-110">Consulte [Licenciamento de complemento de equipes da Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="f21d5-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="f21d5-111">[Atribuir ou remover licenças para o Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), as [equipes da Microsoft atribuir licenças](assign-teams-licenses.md)e as licenças do Exchange Online para as pessoas na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="f21d5-111">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="f21d5-112">Depois disso, elas poderão receber mensagens de voz!</span><span class="sxs-lookup"><span data-stu-id="f21d5-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="f21d5-113">Suporte a transcrição do correio de voz foi adicionada a partir de março de 2017 e é habilitado por padrão para todos os usuários e organizações.</span><span class="sxs-lookup"><span data-stu-id="f21d5-113">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="f21d5-114">Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="f21d5-114">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="f21d5-115">Sistema de Telefonia com ambientes locais</span><span class="sxs-lookup"><span data-stu-id="f21d5-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="f21d5-116">As seguintes informações são sobre como configurar a caixa postal de nuvem para funcionar com ambientes de chamar planejar locais.</span><span class="sxs-lookup"><span data-stu-id="f21d5-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="f21d5-117">Se o recurso de sistema telefônico não está incluído no seu plano, você pode precisar adquirir licenças de complemento do **Sistema telefônico** .</span><span class="sxs-lookup"><span data-stu-id="f21d5-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="f21d5-118">Você também precisará comprar uma licença do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f21d5-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="f21d5-119">Consulte [Licenciamento de complemento de equipes da Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="f21d5-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="f21d5-120">[Atribuir ou remover licenças para o Office 365 para empresas](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), as [equipes da Microsoft atribuir licenças](assign-teams-licenses.md)e as licenças do Exchange Online para as pessoas na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="f21d5-120">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="f21d5-121">Siga as instruções correspondentes PSTN local chamando a solução implantada para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="f21d5-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="f21d5-122">Edition do conector de nuvem, siga as instruções na seção **habilitar usuários para serviços de caixa postal e voz do sistema telefônico** a [Configurar Skype for Business Edition do conector de nuvem guia](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="f21d5-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="f21d5-123">Para chamar com Skype para Business Server PSTN, siga a [habilitar os usuários para o Enterprise Voice no local](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span><span class="sxs-lookup"><span data-stu-id="f21d5-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="f21d5-124">Roteamento direto de equipes, siga a seção **Configurar o número de telefone e habilitar enterprise voice e caixa postal** de [Configurar o roteamento direto](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span><span class="sxs-lookup"><span data-stu-id="f21d5-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="f21d5-125">Suporte a transcrição do correio de voz foi adicionada a partir de março de 2017 e é habilitado por padrão para todos os usuários e organizações.</span><span class="sxs-lookup"><span data-stu-id="f21d5-125">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="f21d5-126">Você pode desativar a transcrição para sua organização usando o Windows PowerShell e seguindo as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="f21d5-126">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="f21d5-127">Mensagens de caixa postal são entregues a caixa de correio do Exchange dos usuários por meio do SMTP roteada por meio do Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="f21d5-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="f21d5-128">Para habilitar a entrega bem-sucedida dessas mensagens, certifique-se de que os conectores do Exchange estão configurados corretamente entre seus servidores Exchange e o Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="f21d5-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection.</span></span> <span data-ttu-id="f21d5-129">[Conectores de uso para configurar o fluxo de emails](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="f21d5-129">[Use Connectors to Configure Mail Flow](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

6. <span data-ttu-id="f21d5-130">Para habilitar os recursos de caixa postal como personalizando saudações e caixa postal visual no Skype para clientes corporativos, é necessária a conectividade do Office 365 para caixa postal do Exchange server por meio de serviços Web do Exchange.</span><span class="sxs-lookup"><span data-stu-id="f21d5-130">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="f21d5-131">Para habilitar essa conectividade, você deve configurar o novo Oauth do Exchange descrevem do protocolo de autenticação em [Configure OAuth authentication entre organizações do Exchange e o Exchange Online](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="f21d5-131">To enable this connectivity you must configure the new Exchange Oauth authentication protocol describe in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span></span> 

> [!NOTE]
> <span data-ttu-id="f21d5-132">O Assistente de híbrida do Exchange execução do Exchange 2013 CU5 ou superior lidará com os requisitos nas etapas 5 e 6 automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f21d5-132">The Exchange Hybrid Wizard run from Exchange 2013 CU5 or greater will handle the requirements in steps 5 and 6 automatically.</span></span> 

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="f21d5-133">Configuração de políticas de caixa postal em sua organização</span><span class="sxs-lookup"><span data-stu-id="f21d5-133">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="f21d5-134">A transcrição do correio de voz é habilitada por padrão e o mascaramento de obscenidades está desativado por padrão para todas as organizações e usuários; no entanto, você pode controlá-los usando os cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="f21d5-134">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f21d5-135">Não é possível criar uma nova instância de política para a transcrição e obscenidades transcrição mascaramento usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não é possível remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="f21d5-135">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="f21d5-136">Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="f21d5-136">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="f21d5-137">Para ver todas as instâncias de política de caixa postal disponível, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f21d5-137">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="f21d5-138">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="f21d5-138">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="f21d5-140">Desativação da transcrição para sua organização</span><span class="sxs-lookup"><span data-stu-id="f21d5-140">Turning off transcription for your organization</span></span>

<span data-ttu-id="f21d5-141">Como a configuração padrão para a transcrição está em para sua organização, convém desabilitá-lo usando o [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="f21d5-141">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="f21d5-142">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="f21d5-142">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="f21d5-143">Ativação do mascaramento de obscenidades para sua organização</span><span class="sxs-lookup"><span data-stu-id="f21d5-143">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="f21d5-144">Mascaramento de obscenidades está desativado por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f21d5-144">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="f21d5-145">Se houver um requisito de negócios para habilitá-lo, você pode habilitar o mascaramento de obscenidades usando [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="f21d5-145">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="f21d5-146">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="f21d5-146">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="f21d5-147">Desativação da transcrição para usuário</span><span class="sxs-lookup"><span data-stu-id="f21d5-147">Turning off transcription for a user</span></span>

<span data-ttu-id="f21d5-148">As políticas de usuário são avaliadas antes das configurações organizacionais padrão.</span><span class="sxs-lookup"><span data-stu-id="f21d5-148">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="f21d5-149">Por exemplo, se a transcrição da caixa postal estiver habilitada para todos os seus usuários, você pode atribuir uma política para desabilitar a transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="f21d5-149">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="f21d5-150">Para desabilitar a transcrição para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="f21d5-150">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="f21d5-151">Ativação do mascaramento de obscenidades para um usuário</span><span class="sxs-lookup"><span data-stu-id="f21d5-151">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="f21d5-152">Para habilitar o mascaramento de obscenidades para um usuário específico, você pode atribuir uma política para habilitar o mascaramento de obscenidades de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="f21d5-152">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="f21d5-153">Para habilitar o mascaramento de obscenidades para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="f21d5-153">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="f21d5-p113">[!IMPORTANTE] O serviço de caixa postal no Office 365 armazena em cache as políticas de caixa postal e atualiza o cache a cada 4 horas. Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas.</span><span class="sxs-lookup"><span data-stu-id="f21d5-p113">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="f21d5-156">Ajude os usuários a conhecer os recursos da caixa postal do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f21d5-156">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="f21d5-157">Temos informações de treinamento e artigos para ajudar seus usuários a obter êxito com Skype caixa postal de negócios.</span><span class="sxs-lookup"><span data-stu-id="f21d5-157">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="f21d5-158">Indique os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="f21d5-158">Point them to the following articles:</span></span>

- <span data-ttu-id="f21d5-159">[Verificar Skype para opções e caixa postal de negócios](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Este artigo explica como ouvir sua caixa postal no Skype para os negócios, alterar sua saudação da caixa postal, alterar as configurações de caixa postal e ouvir suas mensagens de voz em velocidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="f21d5-159">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="f21d5-160">Treinamento do Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="f21d5-160">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="f21d5-161">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f21d5-161">Related topics</span></span>
[<span data-ttu-id="f21d5-162">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f21d5-162">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="f21d5-163">Veja aqui o que você obtém com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="f21d5-163">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="f21d5-164">Plano de migração para o Skype for Business Server e Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f21d5-164">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


