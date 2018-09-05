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
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Consulte como configurar equipes para permitir que os usuários se comuniquem com usuários de outra organização.
ms.openlocfilehash: b8c3705b288abd81e85bd941ab019bb8e8e0e40e
ms.sourcegitcommit: 53c10589c284c6e4bbba574a7ba2df2d29519d1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2018
ms.locfileid: "23829110"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="ac671-103">Permitir que o bate-papo de usuários equipes e se comunicar com usuários de outra organização de equipes</span><span class="sxs-lookup"><span data-stu-id="ac671-103">Let your Teams users chat and communicate with users in another Teams organization</span></span>

<span data-ttu-id="ac671-104">Siga as etapas descritas neste artigo quando:</span><span class="sxs-lookup"><span data-stu-id="ac671-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="ac671-105">Você possui usuários em domínios diferentes em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="ac671-105">You have users in different domains in your business.</span></span> <span data-ttu-id="ac671-106">Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="ac671-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="ac671-107">Você deseja as pessoas na sua organização usar equipes para contatar pessoas na empresas específicas fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="ac671-107">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="ac671-108">Deseja que qualquer pessoa no mundo que usa as equipes possam encontrar e contatá-lo, usando seu endereço de email.</span><span class="sxs-lookup"><span data-stu-id="ac671-108">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="ac671-109">Se você e outro usuário habilitar o acesso externo e permitem uns dos outros domínios, isso funcionará.</span><span class="sxs-lookup"><span data-stu-id="ac671-109">If you and another user both enable External Access and allow each other's domains, this will work.</span></span> <span data-ttu-id="ac671-110">Se ela não funcionar, o outro usuário verifique se seu ou sua configuração não está bloqueando o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="ac671-110">If it doesn't work, the other user should make sure his or her configuration isn't blocking your domain.</span></span>

<span data-ttu-id="ac671-111">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ac671-111">Follow these steps:</span></span>

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a><span data-ttu-id="ac671-112">Permitir que o bate-papo de usuários equipes e se comunicar com usuários de outra organização de equipes</span><span class="sxs-lookup"><span data-stu-id="ac671-112">Let your Teams users chat and communicate with users in another Teams organization</span></span>

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a><span data-ttu-id="ac671-113">Etapa 1 - certificar-se de configurar as portas e URLs que são necessários.</span><span class="sxs-lookup"><span data-stu-id="ac671-113">Step 1 - Make sure to set up the ports and URLs that are needed.</span></span>

<span data-ttu-id="ac671-114">**O problema mais comum encontrado pelas pessoas ao configurar a comunicação entre empresas é como definir suas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) corretamente.**</span><span class="sxs-lookup"><span data-stu-id="ac671-114">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a><span data-ttu-id="ac671-115">Etapa 2 - habilitar a sua organização se comuniquem com outra organização de equipes</span><span class="sxs-lookup"><span data-stu-id="ac671-115">Step 2 - Enable your organization to communicate with another Teams organization</span></span>

<span data-ttu-id="ac671-116">![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="ac671-116">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

   1. <span data-ttu-id="ac671-117">No painel de navegação esquerdo, vá para **configurações de toda a organização** > **acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="ac671-117">In the left navigation, go to **Org-wide settings** > **External access**.</span></span> 

   2. <span data-ttu-id="ac671-118">Na parte superior da página de **acesso externo** , clique em **acesso externo** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="ac671-118">At the top of the **External access** page, click **External access** to **On**.</span></span> 

   3. <span data-ttu-id="ac671-119">Adicione domínio da outra organização à lista de permissões, clicando em **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="ac671-119">Add the other organization's domain to the allowed list by clicking **Add domain**.</span></span> <span data-ttu-id="ac671-120">No painel de **Adicionar um domínio** , preparado o clique de nome de domínio **permitido** e **feito**.</span><span class="sxs-lookup"><span data-stu-id="ac671-120">In the **Add a domain** pane, put in the domain name click **Allowed** and then **Done**.</span></span>

   4. <span data-ttu-id="ac671-121">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ac671-121">Click **Save**.</span></span> 

   5. <span data-ttu-id="ac671-122">Verifique se que o administrador na organização do equipes segue essas etapas mesmas.</span><span class="sxs-lookup"><span data-stu-id="ac671-122">Then make sure the admin in the other Teams  organization does these same steps.</span></span> <span data-ttu-id="ac671-123">Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="ac671-123">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

### <a name="step-3---test-it"></a><span data-ttu-id="ac671-124">Etapa 3 - testá-lo</span><span class="sxs-lookup"><span data-stu-id="ac671-124">Step 3 - Test it</span></span>
<span data-ttu-id="ac671-125">Para testar sua configuração, você precisa de um usuário de equipes que não está atrás do firewall.</span><span class="sxs-lookup"><span data-stu-id="ac671-125">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
   1. <span data-ttu-id="ac671-126">Depois que o administrador da organização e você tem alterado as configurações de **acesso externo** , você deve estar pronto.</span><span class="sxs-lookup"><span data-stu-id="ac671-126">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>
    
   2. <span data-ttu-id="ac671-127">No aplicativo de equipes, procurar a pessoa pelo endereço de email e enviar uma solicitação para o bate-papo.</span><span class="sxs-lookup"><span data-stu-id="ac671-127">In the Teams app, search for the person by email address, and send a request to chat.</span></span>
    
   3. <span data-ttu-id="ac671-128">Peça ao seu contato de equipes lhe enviar uma solicitação para o bate-papo.</span><span class="sxs-lookup"><span data-stu-id="ac671-128">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="ac671-129">Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).</span><span class="sxs-lookup"><span data-stu-id="ac671-129">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
   4. <span data-ttu-id="ac671-130">Outra maneira para testar se o problema é seu firewall deve ir para um local de wifi não atrás do seu firewall, como um café e use equipes para enviar uma solicitação ao seu contato para o bate-papo.</span><span class="sxs-lookup"><span data-stu-id="ac671-130">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="ac671-131">Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.</span><span class="sxs-lookup"><span data-stu-id="ac671-131">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a><span data-ttu-id="ac671-132">Se comunicar com usuários em um Skype para a organização Business Online</span><span class="sxs-lookup"><span data-stu-id="ac671-132">Communicate with users in a Skype for Business Online organization</span></span>

<span data-ttu-id="ac671-133">Se você estiver definindo-la até permitir que os usuários de equipes localizar e contatar os usuários que estão em um Skype para organização de negócios, você será o administrador na organização que devem seguir estas etapas.</span><span class="sxs-lookup"><span data-stu-id="ac671-133">If you are setting it up to let your Teams users find and contact users that are in a Skype for Business organization, you will the admin in that organization to follow these steps.</span></span>

<span data-ttu-id="ac671-134">![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **Usando Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="ac671-134">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using Skype for Business admin center**</span></span> 

<span data-ttu-id="ac671-135">Ter o administrador em que a organização siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ac671-135">Have the admin in that organization do these steps:</span></span>
    
1. <span data-ttu-id="ac671-136">No Centro de administração do Office 365, vá para **Centros de Administração** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="ac671-136">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
  
2. <span data-ttu-id="ac671-137">No **Centro de administração do Skype for Business**, escolha **Organização** > **Comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="ac671-137">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
3. <span data-ttu-id="ac671-138">Para configurar a comunicação com um negócio específicos ou com usuários em outro domínio, na caixa suspensa, escolha **em somente para domínios permitidos**.</span><span class="sxs-lookup"><span data-stu-id="ac671-138">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="ac671-p107">OU, se quiser habilitar a comunicação com todos que tiverem as políticas do Skype for Business, escolha **Ativado exceto para domínios bloqueados**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="ac671-p107">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>
    
4. <span data-ttu-id="ac671-141">Em **bloqueado ou domínios permitidos**, escolha **+** e adicione o nome do domínio que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="ac671-141">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span> <span data-ttu-id="ac671-142">Certificar-se de que o administrador na organização do segue essas etapas mesmas.</span><span class="sxs-lookup"><span data-stu-id="ac671-142">Make sure the admin in the other organization does these same steps.</span></span> <span data-ttu-id="ac671-143">Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="ac671-143">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
### <a name="related-topics"></a><span data-ttu-id="ac671-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ac671-144">Related topics</span></span>

<span data-ttu-id="ac671-145">[Inscreva-se em equipes](sign-in-teams.md)
[para equipes de treinamento do usuário final](enduser-training.md)</span><span class="sxs-lookup"><span data-stu-id="ac671-145">[Sign in teams](sign-in-teams.md)
[End user training for Teams](enduser-training.md)</span></span>

