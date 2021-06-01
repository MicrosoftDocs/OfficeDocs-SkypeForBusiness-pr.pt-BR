---
title: Permitir que os usuários do Skype for Business adicionem contatos do Skype
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
- LIL_Placement
description: 'Veja como permitir que as pessoas que estão usando o Skype for Business entrem em contato com os usuários do Skype for Business que estão foram da organização e os adicionem na sua lista de contatos.  '
ms.openlocfilehash: d68fc27dfb1c77935ce74e278092f6ed4ae3d7dc
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239830"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="76db3-103">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="76db3-103">Let Skype for Business users add Skype contacts</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="76db3-p101">Com o Skype for Business, os usuários podem pesquisar todos os usuários do Skype (o aplicativo gratuito!) e enviar mensagens instantâneas para eles. Este artigo explica o que você precisa fazer para adicionar contatos do Skype.</span><span class="sxs-lookup"><span data-stu-id="76db3-p101">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app! This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="76db3-106">Você deve ter [permissões de](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) administrador Microsoft 365 ou Office 365 fazer isso.</span><span class="sxs-lookup"><span data-stu-id="76db3-106">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Microsoft 365 or Office 365 to do this.</span></span>

<span data-ttu-id="76db3-107">![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="76db3-107">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="76db3-108">Entre com sua conta Microsoft 365 ou Office 365 admin em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) .</span><span class="sxs-lookup"><span data-stu-id="76db3-108">Sign in with your Microsoft 365 or Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="76db3-109">No centro de administração, vá para **Centros de Administração**  >  **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="76db3-109">In the admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Escolha o Centro de administração do Skype for Business.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="76db3-111">No **Centro de administração do Skype for Business**, escolha **Organização** > **Comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="76db3-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="76db3-112">Por padrão, seus usuários podem se comunicar com todas as outras pessoas do mundo que usam Skype for Business (supondo que seu firewall tenha sido configurado para permitir isso).</span><span class="sxs-lookup"><span data-stu-id="76db3-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Selecione a opção Permitir que as pessoas usem o Skype for Business para se comunicar com o Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="76db3-p102">Se você quer que seus usuários conversem com os usuários do Skype, MAS não quer que eles conversem com usuários que usam o Skype for Business, escolha **Ativado somente para os domínios permitidos**. Quando você habilita o contato com os usuários do Skype, o skype.com é adicionado automaticamente como um domínio permitido nos bastidores.</span><span class="sxs-lookup"><span data-stu-id="76db3-p102">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**. When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="76db3-p103">Se quiser permitir contato de todas as outras empesas do mundo que usam o Skype for Business, exceto algumas, escolha **Ativado exceto para domínios bloqueados**, e escolha **+** para adicionar aqueles domínios. Qualquer usuário poderá contatar você, exceto os domínios bloqueados. (Algumas empresas podem escolher essa opção, por exemplo, se estiverem em litígio e precisarem assegurar-se de que não haja contato com as outras empresas.)</span><span class="sxs-lookup"><span data-stu-id="76db3-p103">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains. Everyone will be able to contact you except people on those specific domains. (Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="76db3-119">Escolha **Permita que as pessoas usem o Skype for Business para se comunicar com usuários do Skype fora de sua organização**.</span><span class="sxs-lookup"><span data-stu-id="76db3-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="76db3-120">Se você estiver usando o Windows Firewall, o Skype for Business abrirá as portas necessárias automaticamente.</span><span class="sxs-lookup"><span data-stu-id="76db3-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="76db3-p104">Se a sua organização usa outra solução para restringir a conexão de computadores da rede à Internet, garanta que os computadores cliente possam acessar todos os [endereços IP e URLs](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para permitir a conectividade do Skype e a Pesquisa de Diretório do Skype. Talvez seja necessário adicioná-los à lista de permissão de saída na configuração do firewall ou da infraestrutura de proxy.</span><span class="sxs-lookup"><span data-stu-id="76db3-p104">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search. This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="76db3-p105">**AGUARDE 24 HORAS PARA FAZER O TESTE**. Em qualquer momento que você alterar as configurações das comunicações externas, poderá levar até 24 horas para as alterações serem efetivadas em todos os data centers.</span><span class="sxs-lookup"><span data-stu-id="76db3-p105">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="76db3-p106">Mostre aos usuários como pesquisar e adicionar contatos do Skype à sua lista de contatos do Skype for Business. Oriente-os a usar a opção [Procurar por pessoas no Skype for Business](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="76db3-p106">Show your users how to find and add Skype contacts to their list of Skype for Business contacts. Point them to [Search for people in Skype for Business](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="76db3-127">Testar e solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="76db3-127">Test and troubleshoot</span></span>

<span data-ttu-id="76db3-p107">Para testar sua configuração, você precisa de um contato no Skype que não seja protegido pelo firewall da empresa. Eles podem entrar no Skype usando uma conta do Gmail, do Outlook.com ou outro tipo de conta de email.</span><span class="sxs-lookup"><span data-stu-id="76db3-p107">To test your setup, you need a contact on Skype who's not behind your company firewall. They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="76db3-130">Depois de alterar as configurações de suas comunicações externas, **AGUARDE ATÉ 24 HORAS ANTES DE TESTAR**.</span><span class="sxs-lookup"><span data-stu-id="76db3-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="76db3-131">Saia do Skype for Business e entre novamente, assim você verá a opção para pesquisar o Diretório do Skype.</span><span class="sxs-lookup"><span data-stu-id="76db3-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Quando o Diretório do Skype estiver em destaque, você poderá pesquisar por pessoas que têm contas Skype.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="76db3-133">No Skype for Business, pesquise seu contato no Skype e envie uma solicitação para chat.</span><span class="sxs-lookup"><span data-stu-id="76db3-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="76db3-134">Se receber uma mensagem de que o envio não foi possível devido à política da empresa, verifique novamente as [configurações do firewall](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="76db3-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="76db3-135">Outra maneira de testar se o problema é o firewall é usar o wifi de um lugar que não tenha firewall, como uma cafeteria, e usar o Skype for Business para enviar uma solicitação ao contato do Skype para chat.</span><span class="sxs-lookup"><span data-stu-id="76db3-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="76db3-p108">**Se você enviou uma solicitação ao seu contado do Skype e ele nunca a recebeu**, peça que ele envie uma solicitação de chat para você. Se o problema for estabelecimento de conexão entre o Skype e o Skype for Business, isso geralmente resolve o problema.</span><span class="sxs-lookup"><span data-stu-id="76db3-p108">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat. If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="76db3-138">Agora, se a mensagem for enviada da cafeteria, mas não de seu trabalho, então você saberá que o problema é o firewall.</span><span class="sxs-lookup"><span data-stu-id="76db3-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="76db3-139">O que você pode ou não fazer</span><span class="sxs-lookup"><span data-stu-id="76db3-139">What you can and can't do</span></span>

- <span data-ttu-id="76db3-140">**Skype for Businessno Mac** não tem a capacidade de pesquisar e comunicar-se com contatos do Skype.</span><span class="sxs-lookup"><span data-stu-id="76db3-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="76db3-141">Quando a pesquisa de diretório está habilitada, você pode procurar e encontrar usuários do Skype e do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="76db3-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="76db3-142">Se, por algum motivo, não for possível encontrá-los pesquisando no diretório, você poderá enviar uma solicitação de contato para que eles entrem no Skype e a aceitem. Assim, você poderá enviar mensagens instantâneas a eles.</span><span class="sxs-lookup"><span data-stu-id="76db3-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="76db3-p110">Não é possível permitir a conectividade de mensagens instantâneas com outros provedores de mensagens instantâneas, como o Google ou Facebook. Você não pode usar o Skype for Business para enviar mensagens de texto de celular.</span><span class="sxs-lookup"><span data-stu-id="76db3-p110">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook. You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="76db3-145">Não é possível gravar chamadas de áudio ou vídeo entre um contato do Skype e um contato do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="76db3-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="76db3-146">Quais recursos estão disponíveis ao adicionar contatos do Skype?</span><span class="sxs-lookup"><span data-stu-id="76db3-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="76db3-147">Os contatos do Skype que entraram usando uma conta da Microsoft (antigo Windows Live ID) têm disponíveis alguns, mas não todos os recursos ao conversar com usuários do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="76db3-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="76db3-148">**Disponível para os contatos do Skype**</span><span class="sxs-lookup"><span data-stu-id="76db3-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="76db3-149">**Não disponível para os contatos do Skype**</span><span class="sxs-lookup"><span data-stu-id="76db3-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="76db3-150">Conversas com vídeo</span><span class="sxs-lookup"><span data-stu-id="76db3-150">Video conversations</span></span> <br/>  <span data-ttu-id="76db3-151">Troca de mensagens instantâneas de pessoa para pessoa</span><span class="sxs-lookup"><span data-stu-id="76db3-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="76db3-152">Presença</span><span class="sxs-lookup"><span data-stu-id="76db3-152">Presence</span></span> <br/> | <span data-ttu-id="76db3-153">Mensagens instantâneas de vários participantes</span><span class="sxs-lookup"><span data-stu-id="76db3-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="76db3-154">Conversas de áudio ou com vídeo com três ou mais pessoas</span><span class="sxs-lookup"><span data-stu-id="76db3-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="76db3-155">Compartilhamento de área de trabalho e de programa</span><span class="sxs-lookup"><span data-stu-id="76db3-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="76db3-156">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="76db3-156">Related topics</span></span>

[<span data-ttu-id="76db3-157">Permitir que os usuários entrem em contato com usuários externos do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="76db3-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="76db3-158">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="76db3-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
