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
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Saiba como configurar a Caixa Postal na Nuvem para seus usuários. '
ms.openlocfilehash: 81e5f83b251a0bd648cb2ab2afd69f35357fc49f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662206"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="436c5-103">Configurar a caixa postal na nuvem</span><span class="sxs-lookup"><span data-stu-id="436c5-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="436c5-104">Este artigo é destinado ao administrador do Microsoft 365 [](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) ou do Office 365 conforme descrito em Sobre funções de administrador que querem configurar o recurso Caixa Postal na Nuvem para todos na empresa.</span><span class="sxs-lookup"><span data-stu-id="436c5-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="436c5-105">A Caixa Postal na Nuvem é compatível com o depósito de mensagens de voz somente em uma caixa de correio do Exchange e não dá suporte a sistemas de email de terceiros.</span><span class="sxs-lookup"><span data-stu-id="436c5-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="436c5-106">Quando um representante atende uma chamada em nome de um delegador, as notificações não estão disponíveis na Caixa Postal da Nuvem.</span><span class="sxs-lookup"><span data-stu-id="436c5-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="436c5-107">Os usuários podem receber notificações de chamadas perdidas.</span><span class="sxs-lookup"><span data-stu-id="436c5-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="436c5-108">Ambientes somente na nuvem: Configurar a Caixa Postal na Nuvem para usuários do Sistema Telefônico Online</span><span class="sxs-lookup"><span data-stu-id="436c5-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="436c5-109">Para usuários do Sistema Telefônico Online, **a** Caixa Postal na Nuvem é configurada e provisionada automaticamente para os usuários depois que você atribui uma licença do Sistema de Telefonia aos usuários.</span><span class="sxs-lookup"><span data-stu-id="436c5-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="436c5-110">Para usuários do Sistema Telefônico Do Skype for Business Online com números de telefone fornecidos localmente, talvez seja necessário habilitar a caixa postal hospedada com [Set-CsUser -HostedVoicemail $True.](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="436c5-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="436c5-111">Configurar a caixa postal na nuvem para usuários da caixa de correio do Exchange Server</span><span class="sxs-lookup"><span data-stu-id="436c5-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="436c5-112">As informações a seguir são sobre como configurar a Caixa Postal da Nuvem para trabalhar com usuários que estão online para o Sistema de Telefonia, mas têm suas caixas de correio no Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="436c5-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="436c5-113">As mensagens de voz são entregues na caixa de correio do Exchange dos usuários por meio de SMTP roteado pela Proteção do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="436c5-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="436c5-114">Para habilitar a entrega bem-sucedida dessas mensagens, verifique se os Conectores do Exchange estão configurados corretamente entre os servidores Exchange e a Proteção do Exchange Online; [Use conectores para configurar o fluxo de email.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)</span><span class="sxs-lookup"><span data-stu-id="436c5-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="436c5-115">Para habilitar recursos de caixa postal, como personalização de saudações e caixa postal visual em clientes do Skype for Business, é necessária conectividade do Microsoft 365 ou do Office 365 com a caixa de correio do servidor Exchange por meio do Exchange Web Services.</span><span class="sxs-lookup"><span data-stu-id="436c5-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="436c5-116">Para habilitar essa conectividade, você deve configurar o novo protocolo de autenticação do Exchange Oauth descrito em Configurar autenticação [OAuth](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)entre as organizações do Exchange e do Exchange Online ou executar o Assistente Híbrido do Exchange a partir do Exchange 2013 CU5 ou superior.</span><span class="sxs-lookup"><span data-stu-id="436c5-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="436c5-117">Além disso, você deve configurar a integração e o Oauth entre o Skype for Business Online e o servidor Exchange descritos em Configurar Integração e [OAuth entre o Skype for Business Online e o Exchange Server.](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)</span><span class="sxs-lookup"><span data-stu-id="436c5-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="436c5-118">Configurar a caixa postal na nuvem para usuários do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="436c5-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="436c5-119">Para configurar os usuários do servidor Skype for Business para a Caixa Postal na Nuvem, consulte o serviço Planejar Caixa Postal na Nuvem [para usuários locais.](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)</span><span class="sxs-lookup"><span data-stu-id="436c5-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="436c5-120">Habilitando a caixa postal protegida em sua organização</span><span class="sxs-lookup"><span data-stu-id="436c5-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="436c5-121">Quando alguém deixa uma mensagem de voz para um usuário em sua organização, a caixa postal é entregue na caixa de correio do usuário como um anexo de mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="436c5-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="436c5-122">Usando regras de fluxo de email para aplicar criptografia de mensagens, você pode impedir que essas mensagens de voz seja encaminhadas para outros destinatários.</span><span class="sxs-lookup"><span data-stu-id="436c5-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="436c5-123">Quando você habilita a caixa postal protegida, os usuários podem ouvir mensagens de voz protegidas ligando para sua caixa postal ou abrindo a mensagem no Outlook, no Outlook na Web ou no Outlook para Android ou iOS.</span><span class="sxs-lookup"><span data-stu-id="436c5-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="436c5-124">As mensagens de voz protegidas não podem ser abertas no Skype for Business ou no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="436c5-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="436c5-125">Para obter mais informações sobre criptografia de mensagem, consulte [Criptografia de email.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="436c5-125">For more information about message encryption, see [Email encryption](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="436c5-126">Para configurar a caixa postal protegida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="436c5-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="436c5-127">Acesse e https://admin.microsoft.com entre usando uma conta com permissões de administrador global.</span><span class="sxs-lookup"><span data-stu-id="436c5-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="436c5-128">Selecione **Mostrar tudo e** vá para Centros de administração **do**  >  **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="436c5-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="436c5-129">No Centro de Administração do Exchange, selecione **Regras de Fluxo de**  >  **Email.**</span><span class="sxs-lookup"><span data-stu-id="436c5-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="436c5-130">Selecione **+** **Adicionar** e, em seguida, **aplique Criptografia de Mensagem do Office 365** e proteção de direitos às mensagens.</span><span class="sxs-lookup"><span data-stu-id="436c5-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="436c5-131">Forneça um nome para a nova regra de fluxo de email e, em Seguida, em Aplicar esta regra, selecione As propriedades da mensagem Incluir o tipo de mensagem  >    >  **Caixa postal.**</span><span class="sxs-lookup"><span data-stu-id="436c5-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="436c5-132">Selecione **OK.**</span><span class="sxs-lookup"><span data-stu-id="436c5-132">Select **OK**.</span></span>
6. <span data-ttu-id="436c5-133">Em **Fazer o seguinte,** selecione Aplicar Criptografia de Mensagem do **Office 365** e proteção de direitos à mensagem com e selecione **Selecione uma.**</span><span class="sxs-lookup"><span data-stu-id="436c5-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="436c5-134">Em **modelo RMS,** selecione **Não encaminhar.**</span><span class="sxs-lookup"><span data-stu-id="436c5-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="436c5-135">Selecione **OK** e, em **seguida, Salvar.**</span><span class="sxs-lookup"><span data-stu-id="436c5-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="436c5-136">Se a **lista de modelos rms** estiver vazia, você precisará configurar a Criptografia de Mensagens.</span><span class="sxs-lookup"><span data-stu-id="436c5-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="436c5-137">Para obter mais informações sobre como configurar a Criptografia de Mensagens, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="436c5-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="436c5-138">Configurar novos recursos de Criptografia de Mensagem</span><span class="sxs-lookup"><span data-stu-id="436c5-138">Set up new Message Encryption capabilities</span></span>](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="436c5-139">Configurando e gerenciando modelos para a Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="436c5-139">Configuring and managing templates for Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="436c5-140">Opção Não Encaminhar para emails</span><span class="sxs-lookup"><span data-stu-id="436c5-140">Do Not Forward option for emails</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="436c5-141">Configuração de políticas de caixa postal em sua organização</span><span class="sxs-lookup"><span data-stu-id="436c5-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="436c5-142">Para clientes do Skype for Business, desabilitar a caixa postal por meio de uma política de chamada do Microsoft Teams também pode desabilitar o serviço de caixa postal para os usuários do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="436c5-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="436c5-143">A transcrição do correio de voz é habilitada por padrão e o mascaramento de obscenidades está desativado por padrão para todas as organizações e usuários; no entanto, você pode controlá-los usando os cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="436c5-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="436c5-144">As mensagens de voz recebidas pelos usuários em sua organização são transcritas na região onde sua organização do Microsoft 365 ou do Office 365 está hospedada.</span><span class="sxs-lookup"><span data-stu-id="436c5-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="436c5-145">A região onde seu locatário está hospedado pode não ser a mesma região onde o usuário que recebe a mensagem de voz está localizado.</span><span class="sxs-lookup"><span data-stu-id="436c5-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="436c5-146">Para exibir a região onde seu locatário [](https://go.microsoft.com/fwlink/p/?linkid=2067339) está hospedado, vá para a página de perfil da Organização e clique em Exibir detalhes **ao** lado de Local **de dados.**</span><span class="sxs-lookup"><span data-stu-id="436c5-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="436c5-147">Não é possível criar uma nova instância de política para mascaramento de transcrição e transcrição usando o cmdlet **New-CsOnlineVoiceMailPolicy** e não é possível remover uma instância de política existente usando o cmdlet **Remove-CsOnlineVoiceMailPolicy.**</span><span class="sxs-lookup"><span data-stu-id="436c5-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="436c5-148">Você pode gerenciar as configurações da transcrição para os usuários usando as políticas de caixa postal.</span><span class="sxs-lookup"><span data-stu-id="436c5-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="436c5-149">Para ver todas as instâncias de política de caixa postal disponíveis, você pode usar o cmdlet [Get-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798311.aspx)</span><span class="sxs-lookup"><span data-stu-id="436c5-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="436c5-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="436c5-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="436c5-152">Desativação da transcrição para sua organização</span><span class="sxs-lookup"><span data-stu-id="436c5-152">Turning off transcription for your organization</span></span>

<span data-ttu-id="436c5-153">Como a configuração padrão para transcrição está ínteque para sua organização, talvez você queira desabilitá-la usando [Set-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798310.aspx)</span><span class="sxs-lookup"><span data-stu-id="436c5-153">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="436c5-154">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="436c5-154">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="436c5-155">Ativação do mascaramento de obscenidades para sua organização</span><span class="sxs-lookup"><span data-stu-id="436c5-155">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="436c5-156">Mascaramento de obscenidades está desativado por padrão para sua organização.</span><span class="sxs-lookup"><span data-stu-id="436c5-156">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="436c5-157">Se houver um requisito de negócios para habilitá-lo, você pode habilitar o mascaramento de obscenidades usando [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="436c5-157">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="436c5-158">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="436c5-158">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="436c5-159">Desativação da transcrição para usuário</span><span class="sxs-lookup"><span data-stu-id="436c5-159">Turning off transcription for a user</span></span>

<span data-ttu-id="436c5-160">As políticas de usuário são avaliadas antes das configurações organizacionais padrão.</span><span class="sxs-lookup"><span data-stu-id="436c5-160">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="436c5-161">Por exemplo, se a transcrição da caixa postal estiver habilitada para todos os usuários, você poderá atribuir uma política para desabilitar a transcrição para um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy.](https://technet.microsoft.com/library/mt798309.aspx)</span><span class="sxs-lookup"><span data-stu-id="436c5-161">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="436c5-162">Para desabilitar a transcrição para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="436c5-162">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="436c5-163">Ativação do mascaramento de obscenidades para um usuário</span><span class="sxs-lookup"><span data-stu-id="436c5-163">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="436c5-164">Para habilitar o mascaramento de obscenidades para um usuário específico, você pode atribuir uma política para habilitar o mascaramento de obscenidades de um usuário específico usando o cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="436c5-164">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="436c5-165">Para habilitar o mascaramento de obscenidades para um único usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="436c5-165">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="436c5-166">O serviço de caixa postal no Microsoft 365 e no Office 365 armazena em cache políticas de caixa postal e atualiza o cache a cada 4 horas.</span><span class="sxs-lookup"><span data-stu-id="436c5-166">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="436c5-167">Portanto as alterações de política que você faz podem levar até 4 horas para serem aplicadas.</span><span class="sxs-lookup"><span data-stu-id="436c5-167">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="436c5-168">Ajude os usuários a conhecer os recursos de caixa postal do Teams</span><span class="sxs-lookup"><span data-stu-id="436c5-168">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="436c5-169">Temos as seguintes informações para seus usuários sobre como gerenciar suas configurações de caixa postal, bem como outros recursos de chamada no Teams:</span><span class="sxs-lookup"><span data-stu-id="436c5-169">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="436c5-170">[Gerencie suas configurações de chamada no Teams.](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="436c5-170">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="436c5-171">Este artigo explica como gerenciar todos os recursos de chamada do Teams do usuário final.</span><span class="sxs-lookup"><span data-stu-id="436c5-171">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="436c5-172">Ajude os usuários a conhecer os recursos da caixa postal do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="436c5-172">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="436c5-173">Temos informações de treinamento e artigos para ajudar seus usuários a serem bem-sucedidos com a caixa postal do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="436c5-173">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="436c5-174">Indique os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="436c5-174">Point them to the following articles:</span></span>

- <span data-ttu-id="436c5-175">Verifique a caixa postal e as opções do [Skype for Business:](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)este artigo explica como ouvir sua caixa postal no Skype for Business, alterar a saudação da caixa postal, alterar as configurações da caixa postal e ouvir sua caixa postal em velocidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="436c5-175">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="436c5-176">Treinamento do Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="436c5-176">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="436c5-177">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="436c5-177">Related topics</span></span>
[<span data-ttu-id="436c5-178">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="436c5-178">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="436c5-179">Veja o que você obtém com o Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="436c5-179">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="436c5-180">Plano de migração para o Skype for Business Server e Exchange Server</span><span class="sxs-lookup"><span data-stu-id="436c5-180">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
