---
title: Comunicar-se com os usuários do Teams em outra organização
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: Veja como configurar o Microsoft Teams para permitir que os usuários se comuniquem com os usuários de outra organização.
ms.openlocfilehash: f34bd66b018d84a759c2bfbd5a61b6e112245abc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299939"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="4364b-103">Permitir que os usuários do seu Team conversem e se comuniquem com usuários em outra organização de equipes</span><span class="sxs-lookup"><span data-stu-id="4364b-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="4364b-104">Siga as etapas descritas neste artigo quando:</span><span class="sxs-lookup"><span data-stu-id="4364b-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="4364b-105">Você tem usuários em domínios diferentes na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="4364b-105">You have users in different domains in your business.</span></span> <span data-ttu-id="4364b-106">Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="4364b-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="4364b-107">Você quer que as pessoas em sua organização usem o Teams para entrar em contato com pessoas em empresas específicas fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4364b-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="4364b-108">Você quer que qualquer outro usuário do mundo que use o Microsoft Teams possa encontrá-lo e contatá-lo usando seu endereço de e-mail.</span><span class="sxs-lookup"><span data-stu-id="4364b-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="4364b-109">Se você e outro usuário habilitarem o acesso externo e permitirem os domínios uns dos outros, isso funcionará.</span><span class="sxs-lookup"><span data-stu-id="4364b-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="4364b-110">Se não funcionar, o outro usuário deve verificar se a configuração dele não está bloqueando o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="4364b-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="4364b-111">Isso permitirá que os usuários localizem, liguem e enviem mensagens instantâneas, além de configurar reuniões com você.</span><span class="sxs-lookup"><span data-stu-id="4364b-111">This will allow users to find, call, and send you instant messages, as well as set up meetings with you.</span></span> <span data-ttu-id="4364b-112">Se você quiser que os usuários externos tenham acesso a equipes e canais, o acesso de convidado pode ser uma melhor maneira de começar.</span><span class="sxs-lookup"><span data-stu-id="4364b-112">If you want external users to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="4364b-113">Siga as etapas deste artigo e certifique-se de [ativar o acesso de convidado](set-up-guests.md) para que os usuários possam se comunicar.</span><span class="sxs-lookup"><span data-stu-id="4364b-113">Follow the steps in this article and make sure to [turn on guest access](set-up-guests.md) so that users can communicate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4364b-114">Para federar-se atualmente no cliente do Microsoft Teams para um usuário externo fora de sua organização que não seja um convidado do seu AAD/locatário, você deve ser configurado corretamente para o Hybrid e movido para o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="4364b-114">In order to currently federate within the Microsoft Teams client to an external user outside of your organization who's not currently a Guest of your AAD/Tenant, you must be correctly setup for hybrid and moved to Skype for Business Online.</span></span> <span data-ttu-id="4364b-115">A partir de 2/25/2019, as equipes ainda não dão suporte à Federação nativa sem que o usuário do perfil SIP seja hospedado no Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="4364b-115">As of 2/25/2019, Teams doesn't yet support native federation without the user of the SIP profile being homed in Skype for Business Online.</span></span> <span data-ttu-id="4364b-116">Para saber mais sobre como configurar sua conta para Hybrid e depois movê-la para o Microsoft Teams, consulte [atualizar a implantação híbrida do Skype for Business para](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4364b-116">For more on setting up your account for Hybrid and then moved to Teams, please see [Upgrade Skype for Business Hybrid Deployment to Teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="4364b-117">Permitir que os usuários do seu Team conversem e se comuniquem com usuários em outra organização de equipes</span><span class="sxs-lookup"><span data-stu-id="4364b-117">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="4364b-118">Siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4364b-118">Follow these steps.</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="4364b-119">Etapa 1: Certifique-se de configurar as portas e URLs que são necessárias.</span><span class="sxs-lookup"><span data-stu-id="4364b-119">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="4364b-120">**O problema mais comum encontrado pelas pessoas ao configurar a comunicação entre empresas é como definir suas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) corretamente.**</span><span class="sxs-lookup"><span data-stu-id="4364b-120">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="4364b-121">Etapa 2-habilitar sua organização a se comunicar com outra organização de equipes</span><span class="sxs-lookup"><span data-stu-id="4364b-121">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="4364b-122">![Teams-logo-30x30. png](media/teams-logo-30x30.png) **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="4364b-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

   1. <span data-ttu-id="4364b-123">No painel de navegação esquerdo, vá para >  **configurações de toda a organização\*\*\*\*acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="4364b-123">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="4364b-124">Na parte superior da página de **acesso externo** , clique em **acesso externo** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="4364b-124">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="4364b-125">Se você quiser permitir que todas as organizações de equipe se comuniquem com os usuários da sua organização, pule para a etapa 5.</span><span class="sxs-lookup"><span data-stu-id="4364b-125">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="4364b-126">Se quiser limitar quais organizações podem se comunicar com os usuários em sua organização, você pode permitir todos, mas alguns domínios, ou somente permitir organizações específicas.</span><span class="sxs-lookup"><span data-stu-id="4364b-126">If you want to limit which organizations can communicate with users in your organization you can either allow all but some domains, or only allow specific organizations.</span></span> <span data-ttu-id="4364b-127">Para permitir todos, mas alguns domínios, adicione os domínios que você deseja bloquear clicando em **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="4364b-127">To allow all but some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="4364b-128">No painel **Adicionar um domínio** , insira o nome do domínio, clique em **bloqueado** e em **concluído**.</span><span class="sxs-lookup"><span data-stu-id="4364b-128">In the **Add a domain** pane, put in the domain name, click **Blocked** and then **Done**.</span></span> <span data-ttu-id="4364b-129">Para limitar as comunicações a organizatioins específicas, adicione esses domínios à lista com um status de por **devido**.</span><span class="sxs-lookup"><span data-stu-id="4364b-129">To limit communications to specific organizatioins, add those domains to the list with a status of **Alowed**.</span></span> <span data-ttu-id="4364b-130">Depois que você adicionar qualquer domínio à lista de permissões, as comunicações com outras organizações serão limitadas apenas às organizações cujos domínios estiverem na lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="4364b-130">Once you have added any domain to the Allow list, communications to other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 
   
   5. <span data-ttu-id="4364b-131">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4364b-131">Click **Save**.</span></span> 

   6. <span data-ttu-id="4364b-132">Em seguida, verifique se o administrador na organização outras equipes executa essas mesmas etapas.</span><span class="sxs-lookup"><span data-stu-id="4364b-132">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="4364b-133">Por exemplo, na lista de **domínios permitidos** , o administrador precisará inserir o domínio para sua empresa se eles limitarem quais organizações podem se comunicar com seus usuários.</span><span class="sxs-lookup"><span data-stu-id="4364b-133">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="4364b-134">Etapa 3-testar</span><span class="sxs-lookup"><span data-stu-id="4364b-134">Step 3 - Test it</span></span>
<span data-ttu-id="4364b-135">Para testar a configuração, você precisará de um usuário do teams que não esteja atrás do seu firewall.</span><span class="sxs-lookup"><span data-stu-id="4364b-135">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="4364b-136">Depois que você e o administrador da organização tiverem alterado as configurações de **acesso externo** , você deverá ir bem.</span><span class="sxs-lookup"><span data-stu-id="4364b-136">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="4364b-137">No aplicativo Teams, procure a pessoa por endereço de e-mail e envie uma solicitação para conversar.</span><span class="sxs-lookup"><span data-stu-id="4364b-137">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="4364b-138">Peça ao contato do teams para lhe enviar uma solicitação para conversar.</span><span class="sxs-lookup"><span data-stu-id="4364b-138">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="4364b-139">Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).</span><span class="sxs-lookup"><span data-stu-id="4364b-139">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="4364b-140">Outra maneira de testar se o problema é o seu firewall é acessar um local WiFi que não está atrás do seu firewall, como uma lanchonete, e usar o Microsoft Teams para enviar uma solicitação ao seu contato para conversar.</span><span class="sxs-lookup"><span data-stu-id="4364b-140">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="4364b-141">Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.</span><span class="sxs-lookup"><span data-stu-id="4364b-141">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="4364b-142">Comunicar-se com usuários em uma organização do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4364b-142">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="4364b-143">Se você estiver configurando para permitir que seus usuários do teams localizem e entrem em contato com usuários que estão em uma organização do Skype for Business que limitam quem pode contatar seus usuários, você solicitará que o administrador dessa organização siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4364b-143">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="4364b-144">![SFB-logo-30x30. png](media/sfb-logo-30x30.png) **usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="4364b-144">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="4364b-145">Faça as seguintes etapas para o administrador da organização:</span><span class="sxs-lookup"><span data-stu-id="4364b-145">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="4364b-146">No centro de administração do Office 365, vá para **Centro** > de administração do **& portal do Skype** > **Legacy**.</span><span class="sxs-lookup"><span data-stu-id="4364b-146">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="4364b-147">No **Centro de administração do Skype for Business**, escolha **Organização** > **Comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="4364b-147">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="4364b-148">Para configurar a comunicação com uma empresa específica ou com usuários em outro domínio, na caixa suspensa, escolha **ativado somente para os domínios permitidos**.</span><span class="sxs-lookup"><span data-stu-id="4364b-148">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="4364b-149">OU, se quiserem habilitar a comunicação com todos os participantes do mundo que tenham as políticas do Skype for Business abertas, escolha **ativado exceto para os domínios bloqueados**.</span><span class="sxs-lookup"><span data-stu-id="4364b-149">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="4364b-150">Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="4364b-150">This is the default setting.</span></span>
    
4. <span data-ttu-id="4364b-151">Em **domínios bloqueados ou permitidos**, **+** escolha e adicione o nome do domínio que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="4364b-151">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="4364b-152">Certifique-se de que o administrador da outra organização faça as mesmas etapas.</span><span class="sxs-lookup"><span data-stu-id="4364b-152">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="4364b-153">Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="4364b-153">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="4364b-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4364b-154">Related topics</span></span>

<span data-ttu-id="4364b-155">[Entrar](sign-in-teams.md)
no[treinamento do usuário final do](enduser-training.md) Microsoft Teams para equipes</span><span class="sxs-lookup"><span data-stu-id="4364b-155">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

