---
title: Configurar a Caixa postal na nuvem
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
description: 'Saiba como configurar o Caixa postal na Nuvem para seus usuários. '
ms.openlocfilehash: c6fbd02e30c5be0280b05088a1cec281c2534039
ms.sourcegitcommit: 31c5b9cd3d4f500e1f9d7823052dae8f8c298b1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52901898"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="d0480-103">Configurar a Caixa postal na nuvem</span><span class="sxs-lookup"><span data-stu-id="d0480-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="d0480-104">Este artigo é para o administrador Microsoft 365 ou Office 365 conforme descrito em [Sobre](/microsoft-365/admin/add-users/about-admin-roles) funções de administrador que deseja configurar o recurso Caixa postal na Nuvem para todos na empresa.</span><span class="sxs-lookup"><span data-stu-id="d0480-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="d0480-105">Caixa postal na Nuvem suporta o depósito de mensagens de caixa postal somente em uma caixa de correio Exchange e não oferece suporte a sistemas de email de terceiros.</span><span class="sxs-lookup"><span data-stu-id="d0480-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="d0480-106">Quando um representante responde a uma chamada em nome de um representante, as notificações não estão disponíveis Caixa postal na Nuvem.</span><span class="sxs-lookup"><span data-stu-id="d0480-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="d0480-107">Os usuários podem receber notificações para chamadas perdidas.</span><span class="sxs-lookup"><span data-stu-id="d0480-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="d0480-108">Ambientes somente na nuvem: configurar o Caixa postal na Nuvem para usuários Sistema de Telefonia online</span><span class="sxs-lookup"><span data-stu-id="d0480-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="d0480-109">Para usuários Sistema de Telefonia online, Caixa postal na Nuvem é automaticamente configurada e provisionada para usuários depois que você atribui uma Sistema de Telefonia **aos** usuários.</span><span class="sxs-lookup"><span data-stu-id="d0480-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="d0480-110">Para usuários Skype for Business Sistema de Telefonia online com números de telefone fornecidos no local, talvez seja necessário habilitar a caixa postal hospedada com [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d0480-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="d0480-111">Configurar o Caixa postal na Nuvem para Exchange Server de Caixa de Correio</span><span class="sxs-lookup"><span data-stu-id="d0480-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="d0480-112">As informações a seguir são sobre Caixa postal na Nuvem para trabalhar com usuários que estão online para Sistema de Telefonia mas têm sua caixa de correio Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="d0480-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="d0480-113">As mensagens de caixa postal são entregues à caixa de correio Exchange dos usuários por meio de SMTP roteado por Proteção do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d0480-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="d0480-114">Para habilitar a entrega bem-sucedida dessas mensagens, certifique-se de que os conectores Exchange estão configurados corretamente entre seus servidores Exchange e Proteção do Exchange Online; [Use conectores para configurar o email Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="d0480-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="d0480-115">Para habilitar recursos de Caixa Postal, como personalização de saudações e caixa postal visual em clientes Skype for Business, a conectividade do Microsoft 365 ou Office 365 para Exchange caixa de correio do servidor Exchange por meio do Exchange Web Services é necessária.</span><span class="sxs-lookup"><span data-stu-id="d0480-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="d0480-116">Para habilitar essa conectividade, você deve configurar o novo protocolo de autenticação do Exchange Oauth descrito em [Configure OAuth authentication between Exchange](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)and Exchange Online organizations , or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span><span class="sxs-lookup"><span data-stu-id="d0480-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="d0480-117">Além disso, você deve configurar a integração e o Oauth entre o Skype for Business Online e o servidor Exchange descritos em [Configure Integration and OAuth between Skype for Business Online](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)e Exchange Server .</span><span class="sxs-lookup"><span data-stu-id="d0480-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="d0480-118">Configurar um Caixa postal na Nuvem para Skype for Business Server Usuários</span><span class="sxs-lookup"><span data-stu-id="d0480-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="d0480-119">Para configurar Skype for Business usuários de servidor para Caixa postal na Nuvem, consulte [Plan Caixa postal na Nuvem service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).</span><span class="sxs-lookup"><span data-stu-id="d0480-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="d0480-120">Habilitando a caixa postal protegida em sua organização</span><span class="sxs-lookup"><span data-stu-id="d0480-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="d0480-121">Quando alguém deixa uma mensagem de caixa postal para um usuário em sua organização, a caixa postal é entregue à caixa de correio do usuário como um anexo de mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="d0480-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="d0480-122">Usando regras de fluxo de emails para aplicar criptografia de mensagens, você pode impedir que essas mensagens de caixa postal seja encaminhada para outros destinatários.</span><span class="sxs-lookup"><span data-stu-id="d0480-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="d0480-123">Quando você habilita a caixa postal protegida, os usuários podem ouvir mensagens de caixa postal protegidas ligando para a caixa de correio de caixa postal ou abrindo Outlook mensagem no Outlook, Outlook na Web ou no Outlook para Android ou iOS.</span><span class="sxs-lookup"><span data-stu-id="d0480-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="d0480-124">As mensagens de caixa postal protegidas não podem ser abertas Skype for Business ou Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d0480-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="d0480-125">Para obter mais informações sobre criptografia de mensagens, consulte [Criptografia de email](/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="d0480-125">For more information about message encryption, see [Email encryption](/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="d0480-126">Para configurar a caixa postal protegida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d0480-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="d0480-127">Acesse e https://admin.microsoft.com entre usando uma conta com permissões de administrador global.</span><span class="sxs-lookup"><span data-stu-id="d0480-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="d0480-128">Selecione **Mostrar tudo** e vá para Centros de administração   >  **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="d0480-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="d0480-129">No Centro de administração Exchange, selecione **Regras de fluxo de**  >  **email**.</span><span class="sxs-lookup"><span data-stu-id="d0480-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="d0480-130">Selecione **+** **Adicionar** e, em seguida, selecione **Aplicar Criptografia de Mensagens do Office 365 e proteção de direitos a mensagens**.</span><span class="sxs-lookup"><span data-stu-id="d0480-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="d0480-131">Forneça um nome para a nova regra de fluxo de emails e, em Seguida, em Aplicar essa regra **se**, selecione **As** propriedades da mensagem Incluir o tipo  >  **de** mensagem Caixa  >  **postal**.</span><span class="sxs-lookup"><span data-stu-id="d0480-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="d0480-132">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0480-132">Select **OK**.</span></span>
6. <span data-ttu-id="d0480-133">Em **Fazer o seguinte,** selecione **Aplicar Criptografia de Mensagens do Office 365 proteção de** direitos e direitos à mensagem com e selecione **Selecionar um**.</span><span class="sxs-lookup"><span data-stu-id="d0480-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="d0480-134">Em **modelo RMS,** selecione **Não encaminhar**.</span><span class="sxs-lookup"><span data-stu-id="d0480-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="d0480-135">Selecione **OK** **e,** em seguida, Salvar .</span><span class="sxs-lookup"><span data-stu-id="d0480-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="d0480-136">Se a **lista de modelos RMS** estiver vazia, você precisará configurar a Criptografia de Mensagens.</span><span class="sxs-lookup"><span data-stu-id="d0480-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="d0480-137">Para obter mais informações sobre como configurar a Criptografia de Mensagens, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="d0480-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="d0480-138">Configurar novos recursos de Criptografia de Mensagens</span><span class="sxs-lookup"><span data-stu-id="d0480-138">Set up new Message Encryption capabilities</span></span>](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="d0480-139">Configurando e gerenciando modelos para a Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="d0480-139">Configuring and managing templates for Azure Information Protection</span></span>](/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="d0480-140">Opção Não Encaminhar para emails</span><span class="sxs-lookup"><span data-stu-id="d0480-140">Do Not Forward option for emails</span></span>](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="d0480-141">Ajudar seus usuários a aprender Teams recursos de caixa postal</span><span class="sxs-lookup"><span data-stu-id="d0480-141">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="d0480-142">Temos as seguintes informações para seus usuários sobre como gerenciar suas configurações de caixa postal, bem como outros recursos de chamada em Teams:</span><span class="sxs-lookup"><span data-stu-id="d0480-142">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="d0480-143">[Gerencie suas configurações de chamada em Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span><span class="sxs-lookup"><span data-stu-id="d0480-143">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="d0480-144">Este artigo explica como gerenciar todos os recursos de chamada Teams usuário final.</span><span class="sxs-lookup"><span data-stu-id="d0480-144">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="d0480-145">Ajude os usuários a conhecer os recursos da caixa postal do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d0480-145">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="d0480-146">Temos informações de treinamento e artigos para ajudar seus usuários a serem bem-sucedidos Skype for Business caixa postal.</span><span class="sxs-lookup"><span data-stu-id="d0480-146">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="d0480-147">Indique os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="d0480-147">Point them to the following articles:</span></span>

- <span data-ttu-id="d0480-148">[Verifique Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)caixa postal e opções : Este artigo explica como ouvir sua caixa postal no Skype for Business, alterar sua saudação de caixa postal, alterar suas configurações de caixa postal e ouvir sua caixa postal em velocidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="d0480-148">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="d0480-149">Treinamento do Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="d0480-149">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="d0480-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d0480-150">Related topics</span></span>
[<span data-ttu-id="d0480-151">Instalar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d0480-151">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="d0480-152">Veja o que você obtém com o Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="d0480-152">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="d0480-153">Plano de migração para o Skype for Business Server e Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d0480-153">Plan for Skype for Business Server and Exchange Server migration</span></span>](/SkypeForBusiness/hybrid/plan-um-migration)
