---
title: Se comunicar com usuários de equipes em outra organização
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Strat_MT_TeamsAdmin
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Consulte como configurar equipes para permitir que os usuários se comuniquem com usuários de outra organização.
ms.openlocfilehash: da76d75ba44215b11b68550fa06d1fab87f19e56
ms.sourcegitcommit: 6732f56535d60a46e6998cde64103e8530dd6452
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/11/2018
ms.locfileid: "23937823"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="6f3be-103">Permitir que o bate-papo de usuários equipes e se comunicar com usuários de outra organização de equipes</span><span class="sxs-lookup"><span data-stu-id="6f3be-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="6f3be-104">Siga as etapas descritas neste artigo quando:</span><span class="sxs-lookup"><span data-stu-id="6f3be-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="6f3be-105">Você possui usuários em domínios diferentes em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="6f3be-105">You have users in different domains in your business.</span></span> <span data-ttu-id="6f3be-106">Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="6f3be-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="6f3be-107">Você deseja as pessoas na sua organização usar equipes para contatar pessoas na empresas específicas fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6f3be-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="6f3be-108">Deseja que qualquer pessoa no mundo que usa as equipes possam encontrar e contatá-lo, usando seu endereço de email.</span><span class="sxs-lookup"><span data-stu-id="6f3be-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="6f3be-109">Se você e outro usuário habilitar o acesso externo e permitem uns dos outros domínios, isso funcionará.</span><span class="sxs-lookup"><span data-stu-id="6f3be-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="6f3be-110">Se ela não funcionar, o outro usuário verifique se seu ou sua configuração não está bloqueando o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="6f3be-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="6f3be-111">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6f3be-111">Follow these steps:</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="6f3be-112">Permitir que o bate-papo de usuários equipes e se comunicar com usuários de outra organização de equipes</span><span class="sxs-lookup"><span data-stu-id="6f3be-112">Let your Teams users chat and communicate with users in another Teams organization</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="6f3be-113">Etapa 1 - certificar-se de configurar as portas e URLs que são necessários.</span><span class="sxs-lookup"><span data-stu-id="6f3be-113">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="6f3be-114">**O problema mais comum encontrado pelas pessoas ao configurar a comunicação entre empresas é como definir suas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) corretamente.**</span><span class="sxs-lookup"><span data-stu-id="6f3be-114">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="6f3be-115">Etapa 2 - habilitar a sua organização se comuniquem com outra organização de equipes</span><span class="sxs-lookup"><span data-stu-id="6f3be-115">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="6f3be-116">![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="6f3be-116">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

   1. <span data-ttu-id="6f3be-117">No painel de navegação esquerdo, vá para **configurações de toda a organização** > **acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="6f3be-117">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="6f3be-118">Na parte superior da página de **acesso externo** , clique em **acesso externo** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="6f3be-118">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="6f3be-119">Se você deseja permitir todas as organizações de equipes para se comunicar com usuários em sua organização, pule para a etapa 5.</span><span class="sxs-lookup"><span data-stu-id="6f3be-119">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span> 
   
   4. <span data-ttu-id="6f3be-120">Se quiser limitar quais as organizações podem se comunicar com usuários em sua organização, adicione o outro domínio da organização à lista de permissões, clicando em **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="6f3be-120">If you want to limit which organizations can communicate with users in your organization, add the other organization's domain to the allowed list by clicking **Add domain**.</span></span> <span data-ttu-id="6f3be-121">No painel de **Adicionar um domínio** , preparado o clique de nome de domínio **permitido** e **feito**.</span><span class="sxs-lookup"><span data-stu-id="6f3be-121">In the **Add a domain** pane, put in the domain name click **Allowed** and then **Done**.</span></span>

   4. <span data-ttu-id="6f3be-122">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6f3be-122">Click **Save**.</span></span> 

   5. <span data-ttu-id="6f3be-123">Verifique se que o administrador na organização do equipes segue essas etapas mesmas.</span><span class="sxs-lookup"><span data-stu-id="6f3be-123">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="6f3be-124">Por exemplo, em sua lista de **domínios permitidos** , seu administrador precisa insira o domínio para sua empresa se eles limitam o que as organizações podem se comunicar com seus usuários.</span><span class="sxs-lookup"><span data-stu-id="6f3be-124">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit which organizations can communicate with their users.</span></span> 

### <a name="step-3---test-it"></a><span data-ttu-id="6f3be-125">Etapa 3 - testá-lo</span><span class="sxs-lookup"><span data-stu-id="6f3be-125">Step 3 - Test it</span></span>
<span data-ttu-id="6f3be-126">Para testar sua configuração, você precisa de um usuário de equipes que não está atrás do firewall.</span><span class="sxs-lookup"><span data-stu-id="6f3be-126">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="6f3be-127">Depois que o administrador da organização e você tem alterado as configurações de **acesso externo** , você deve estar pronto.</span><span class="sxs-lookup"><span data-stu-id="6f3be-127">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="6f3be-128">No aplicativo de equipes, procurar a pessoa pelo endereço de email e enviar uma solicitação para o bate-papo.</span><span class="sxs-lookup"><span data-stu-id="6f3be-128">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="6f3be-129">Peça ao seu contato de equipes lhe enviar uma solicitação para o bate-papo.</span><span class="sxs-lookup"><span data-stu-id="6f3be-129">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="6f3be-130">Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).</span><span class="sxs-lookup"><span data-stu-id="6f3be-130">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="6f3be-131">Outra maneira para testar se o problema é seu firewall deve ir para um local de wifi não atrás do seu firewall, como um café e use equipes para enviar uma solicitação ao seu contato para o bate-papo.</span><span class="sxs-lookup"><span data-stu-id="6f3be-131">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="6f3be-132">Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.</span><span class="sxs-lookup"><span data-stu-id="6f3be-132">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="6f3be-133">Se comunicar com usuários em um Skype para a organização Business Online</span><span class="sxs-lookup"><span data-stu-id="6f3be-133">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="6f3be-134">Se você estiver configurando-lo para permitir que sua localização de usuários de equipes e visita os usuários que estão em um Skype para organização de negócios que limita quem pode contatar seus usuários, você pedirá que o administrador na organização que devem seguir estas etapas.</span><span class="sxs-lookup"><span data-stu-id="6f3be-134">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization that limits who can contact their users, you will ask the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="6f3be-135">![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **Usando Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="6f3be-135">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="6f3be-136">Ter o administrador em que a organização siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6f3be-136">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="6f3be-137">No Centro de administração do Office 365, vá para **Centros de Admin** > **equipes & Skype** > **portal herdada**.</span><span class="sxs-lookup"><span data-stu-id="6f3be-137">In the Office 365 admin center, go to **Admin Centers** > **Teams & Skype** > **Legacy portal**.</span></span>
  
2. <span data-ttu-id="6f3be-138">No **Centro de administração do Skype for Business**, escolha **Organização** > **Comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="6f3be-138">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="6f3be-139">Para configurar a comunicação com um negócio específicos ou com usuários em outro domínio, na caixa suspensa, escolha **em somente para domínios permitidos**.</span><span class="sxs-lookup"><span data-stu-id="6f3be-139">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="6f3be-140">OU, se deseja habilitar a comunicação com todas as outras pessoas no mundo que tenha aberto Skype para políticas de negócios, escolha **no, com exceção de domínios bloqueados**.</span><span class="sxs-lookup"><span data-stu-id="6f3be-140">OR, if they want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="6f3be-141">Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="6f3be-141">This is the default setting.</span></span>
    
4. <span data-ttu-id="6f3be-142">Em **bloqueado ou domínios permitidos**, escolha **+** e adicione o nome do domínio que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="6f3be-142">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="6f3be-143">Certificar-se de que o administrador na organização do segue essas etapas mesmas.</span><span class="sxs-lookup"><span data-stu-id="6f3be-143">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="6f3be-144">Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="6f3be-144">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="6f3be-145">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6f3be-145">Related topics</span></span>

<span data-ttu-id="6f3be-146">[Entrar no Microsoft Teams](sign-in-teams.md)
[para equipes de treinamento do usuário final](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="6f3be-146">[Sign in to Microsoft Teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

