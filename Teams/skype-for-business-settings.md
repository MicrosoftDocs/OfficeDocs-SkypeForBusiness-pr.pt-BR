---
title: Gerenciar as configurações do Skype for Business no centro de administração do Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como gerenciar as configurações dos recursos do Skype for Business no centro de administração do Microsoft Teams.
ms.openlocfilehash: 0a74b2586fa706dc8fe9db73c58b7d938eae59ee
ms.sourcegitcommit: 54e685b07d1c23100951d46913480989f046d534
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2020
ms.locfileid: "48827755"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="6a642-103">Gerenciar as configurações do Skype for Business no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a642-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="6a642-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="6a642-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="6a642-105">Como administrador, o centro de administração do Microsoft Teams é onde você gerencia os recursos do Skype for Business para os usuários do Skype for Business em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6a642-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="6a642-106">Você pode gerenciar as configurações [de sua organização](#manage-skype-for-business-settings-for-your-organization) na página do **Skype for Business** e as configurações [para usuários individuais](#manage-skype-for-business-settings-for-individual-users) na guia **Skype for Business** de páginas de detalhes do usuário.</span><span class="sxs-lookup"><span data-stu-id="6a642-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="6a642-107">Você só verá a página do **Skype for Business** se o modo de coexistência de sua organização não estiver definido **somente como Teams**.</span><span class="sxs-lookup"><span data-stu-id="6a642-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="6a642-108">Da mesma forma, você só verá a guia **Skype for Business** para um usuário se o modo de coexistência do usuário não for **somente de equipe**.</span><span class="sxs-lookup"><span data-stu-id="6a642-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="6a642-109">Para saber mais sobre os modos de coexistência, consulte [entender equipes e a coexistência e interoperabilidade do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e [definir suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6a642-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6a642-110">As configurações do Skype for Business estavam anteriormente no **portal herdado** no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6a642-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="6a642-111">Com o descontinuação do portal herdado, migramos as configurações para esses novos locais no centro de administração do teams para gerenciamento do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6a642-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="6a642-112">Você deve receber a função de administrador global do [Azure ad](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ou administrador do Skype for Business para gerenciar os recursos do Skype for Business no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6a642-112">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="6a642-113">Gerenciar as configurações do Skype for Business para sua organização</span><span class="sxs-lookup"><span data-stu-id="6a642-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="6a642-114">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **configurações de toda a organização**  >  **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="6a642-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="6a642-115">A partir daqui, você pode configurar e gerenciar a transmissão de reunião do Skype, a privacidade de presença e as notificações de dispositivos móveis para todos os usuários do Skype for Business em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6a642-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="6a642-116">Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="6a642-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="6a642-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="6a642-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="6a642-118">Use as configurações a seguir para gerenciar a [transmissão de reunião do Skype](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6a642-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Captura de tela das configurações de transmissão de reunião do Skype no centro de administração":::

- <span data-ttu-id="6a642-120">**Transmissões de reunião do Skype** : Ative esta opção para habilitar a transmissão de reunião do Skype para sua organização.</span><span class="sxs-lookup"><span data-stu-id="6a642-120">**Skype Meeting Broadcasts** : Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="6a642-121">Depois de habilitar esse recurso, você precisará [configurar sua rede para a transmissão de reunião do Skype](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span><span class="sxs-lookup"><span data-stu-id="6a642-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="6a642-122">**Consulte recursos de visualização** : ative esse recurso para obter acesso antecipado aos novos recursos.</span><span class="sxs-lookup"><span data-stu-id="6a642-122">**See preview features** : Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="6a642-123">Os **organizadores podem agendar reuniões anônimas** : Ative esta opção se quiser que os organizadores criem eventos de transmissão que permitam que qualquer pessoa de fora da sua organização ingresse sem precisar entrar.</span><span class="sxs-lookup"><span data-stu-id="6a642-123">**Organizers can schedule anonymous meetings** : Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="6a642-124">**Grave reuniões de transmissão de reunião do Skype** : Ative esta opção para habilitar os organizadores e apresentadores para gravar reuniões.</span><span class="sxs-lookup"><span data-stu-id="6a642-124">**Record Skype Meeting Broadcast meetings** : Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="6a642-125">**URL de suporte da assistência técnica para participantes** : digite a URL de suporte da sua organização que os participantes da reunião poderão usar se precisarem de ajuda durante uma reunião.</span><span class="sxs-lookup"><span data-stu-id="6a642-125">**Helpdesk support URL for attendees** : Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="6a642-126">Presença e notificações móveis</span><span class="sxs-lookup"><span data-stu-id="6a642-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="6a642-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="6a642-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="6a642-128">Use as configurações a seguir para gerenciar a privacidade de presença do Skype for Business e as notificações do celular em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6a642-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Captura de tela das configurações de presença no centro de administração":::

#### <a name="presence"></a><span data-ttu-id="6a642-130">Presença</span><span class="sxs-lookup"><span data-stu-id="6a642-130">Presence</span></span>

<span data-ttu-id="6a642-131">Por padrão, os usuários do Skype for Business em sua organização podem ver o status de presença (como disponível, ocupado ou ausente) de outros usuários do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6a642-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="6a642-132">Escolha uma das opções a seguir para definir quem pode ver a presença de seus usuários do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6a642-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="6a642-133">**Exibir automaticamente as informações de presença** : qualquer usuário do Skype for Business em sua organização que não tenha sido adicionado à lista **externa** ou **bloqueada** do usuário poderá ver a presença do usuário.</span><span class="sxs-lookup"><span data-stu-id="6a642-133">**Automatically display presence information** : Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="6a642-134">**Exibir informações de presença somente para os contatos de um usuário** : qualquer usuário do Skype for Business na lista de contatos do usuário que não é adicionado à lista **externa** ou **bloqueada** pode ver a presença do usuário.</span><span class="sxs-lookup"><span data-stu-id="6a642-134">**Display presence information only to a user's contacts** : Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="6a642-135">Os usuários podem substituir essa configuração no Skype for Business indo até **configurações**  >  **ferramentas**  >  **Opções**.</span><span class="sxs-lookup"><span data-stu-id="6a642-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="6a642-136">Notificações de celular</span><span class="sxs-lookup"><span data-stu-id="6a642-136">Mobile notifications</span></span>

<span data-ttu-id="6a642-137">Você pode definir se seus usuários móveis do Skype for Business recebem alertas sobre mensagens instantâneas recebidas e perdidas, mensagens de correio de voz e chamadas perdidas por meio de um serviço de notificação por push.</span><span class="sxs-lookup"><span data-stu-id="6a642-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="6a642-138">Dependendo dos dispositivos móveis usados em sua organização, você pode usar o serviço de **notificação por push da Microsoft** , o **serviço de notificação por push da Apple** ou ambos.</span><span class="sxs-lookup"><span data-stu-id="6a642-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service** , the **Apple Push Notification Service** , or both.</span></span>

<span data-ttu-id="6a642-139">Considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6a642-139">Keep the following in mind:</span></span>

- <span data-ttu-id="6a642-140">Se você desativar as notificações por push, os usuários receberão todos os alertas da próxima vez que iniciarem o Skype for Business em seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="6a642-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="6a642-141">Por padrão, as notificações por push estão ativadas.</span><span class="sxs-lookup"><span data-stu-id="6a642-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="6a642-142">Usuários individuais podem desativá-los no Skype for Business em seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="6a642-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="6a642-143">Quando você desativa as notificações push, os usuários não podem ativá-las.</span><span class="sxs-lookup"><span data-stu-id="6a642-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6a642-144">[!IMPORTANTE] A Microsoft usa outras empresas para fornecer notificações por celular para o Skype for Business em tempo real para os usuários do Windows Phone, iPhone e iPad.</span><span class="sxs-lookup"><span data-stu-id="6a642-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="6a642-145">Consulte esta [política de privacidade](https://go.microsoft.com/fwlink/p/?linkid=247732).</span><span class="sxs-lookup"><span data-stu-id="6a642-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="6a642-146">Gerenciar as configurações do Skype for Business para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="6a642-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="6a642-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="6a642-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="6a642-148">Para gerenciar as configurações do Skype for Business para usuários individuais, na navegação à esquerda do centro de administração do Teams, vá para **usuários** , clique no nome de exibição do usuário para abrir a página de detalhes do usuário e, em seguida, selecione a guia **configurações do Skype for Business** . Aqui, você pode configurar o acesso externo e as configurações de reunião para o usuário.</span><span class="sxs-lookup"><span data-stu-id="6a642-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users** , click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Captura de tela da guia do Skype for Business na página de detalhes do usuário":::

### <a name="external-access-settings"></a><span data-ttu-id="6a642-150">Configurações de acesso externo</span><span class="sxs-lookup"><span data-stu-id="6a642-150">External access settings</span></span>

<span data-ttu-id="6a642-151">Você pode permitir ou bloquear seletivamente se um usuário pode se comunicar com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6a642-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="6a642-152">**Usuários externos do Skype for Business** : Ative esta opção se quiser permitir que o usuário se comunique com usuários do Skype for Business em domínios federados.</span><span class="sxs-lookup"><span data-stu-id="6a642-152">**External Skype for Business users** : Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="6a642-153">**Usuários externos do Skype** : Ative esta opção se quiser permitir que o usuário se comunique com usuários do Skype.</span><span class="sxs-lookup"><span data-stu-id="6a642-153">**External Skype users** : Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="6a642-154">Configurações de reunião</span><span class="sxs-lookup"><span data-stu-id="6a642-154">Meeting settings</span></span>

<span data-ttu-id="6a642-155">Você pode definir as seguintes configurações de reunião para o usuário.</span><span class="sxs-lookup"><span data-stu-id="6a642-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="6a642-156">**Áudio & vídeo** : escolha uma das seguintes configurações de áudio e vídeo:</span><span class="sxs-lookup"><span data-stu-id="6a642-156">**Audio & Video** : Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="6a642-157">**None** : o usuário não pode usar áudio ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="6a642-157">**None** : User can't use audio or video.</span></span>
    - <span data-ttu-id="6a642-158">**Somente áudio** : o usuário pode usar áudio, mas não vídeo.</span><span class="sxs-lookup"><span data-stu-id="6a642-158">**Audio only** : User can use audio but not video.</span></span>
    - <span data-ttu-id="6a642-159">**Áudio e vídeo** : o usuário pode usar áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="6a642-159">**Audio and video** : User can use audio and video.</span></span>
    - <span data-ttu-id="6a642-160">**Áudio e vídeo (HD)** : o usuário pode usar áudio e vídeo de alta definição.</span><span class="sxs-lookup"><span data-stu-id="6a642-160">**Audio and video (HD)** : User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="6a642-161">**Grave conversas & reuniões** : Ative esta opção para permitir que o usuário grave conversas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="6a642-161">**Record conversations & meetings** : Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="6a642-162">**Conformidade** : Ative esta opção se você for obrigado legalmente a reter informações armazenadas eletronicamente.</span><span class="sxs-lookup"><span data-stu-id="6a642-162">**Compliance** : Turn this on if you're legally required to retain electronically stored information.</span></span> 
