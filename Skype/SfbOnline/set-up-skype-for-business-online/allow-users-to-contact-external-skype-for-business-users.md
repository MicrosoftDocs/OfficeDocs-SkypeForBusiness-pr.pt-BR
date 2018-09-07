---
title: Permitir que os usuários entrem em contato com usuários externos do Skype for Business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: 79ba0754178e3d638520c932e6288a92ddf6e857
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854697"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="48610-103">Permitir que os usuários entrem em contato com usuários externos do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="48610-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="48610-104">Skype para federação de negócios não está disponível para o Office 365 operado pela 21Vianet e organizações do Office 365 Alemanha.</span><span class="sxs-lookup"><span data-stu-id="48610-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="48610-105">Siga as etapas descritas neste artigo quando:</span><span class="sxs-lookup"><span data-stu-id="48610-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="48610-p101">Você tiver usuários em diferentes domínios na sua empresa. Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="48610-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="48610-108">Desejar que as pessoas em sua organização usem o Skype for Business para entrar em contato com pessoas em empresas específicas de fora de sua organização.</span><span class="sxs-lookup"><span data-stu-id="48610-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
<span data-ttu-id="48610-109">-Você deseja qualquer pessoa no mundo que usa Skype for Business para conseguir encontrar e contatá-lo, usando seu endereço de email.</span><span class="sxs-lookup"><span data-stu-id="48610-109">-You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="48610-110">Se as configurações padrão do Skype for Business forem usadas, isso funcionará automaticamente.</span><span class="sxs-lookup"><span data-stu-id="48610-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="48610-111">Caso contrário, o usuário deverá verificar se a configuração não está bloqueando seu domínio.</span><span class="sxs-lookup"><span data-stu-id="48610-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="48610-112">Habilitar comunicações entre empresas para os usuários</span><span class="sxs-lookup"><span data-stu-id="48610-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="48610-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="48610-113"></span></span>

<span data-ttu-id="48610-114">Você deve ter [permissões de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) no Office 365 em ambas as organizações para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="48610-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="48610-115">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="48610-115">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="48610-116">Entrar com sua conta de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="48610-116">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="48610-117">No Centro de administração do Office 365, vá para **Centros de Administração** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="48610-117">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="48610-119">No **Centro de administração do Skype for Business**, escolha **Organização** > **Comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="48610-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
4. <span data-ttu-id="48610-120">Para configurar a comunicação com um negócio específicos ou com usuários em outro domínio, na caixa suspensa, escolha **em somente para domínios permitidos**.</span><span class="sxs-lookup"><span data-stu-id="48610-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="48610-p103">OU, se quiser habilitar a comunicação com todos que tiverem as políticas do Skype for Business, escolha **Ativado exceto para domínios bloqueados**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="48610-p103">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>
    
5. <span data-ttu-id="48610-123">Em **bloqueado ou domínios permitidos**, escolha **+** e adicione o nome do domínio que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="48610-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
6. <span data-ttu-id="48610-124">Certificar-se de que o administrador na organização do segue essas etapas mesmas em seus **Skype para centro de administração de negócios**.</span><span class="sxs-lookup"><span data-stu-id="48610-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="48610-125">Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="48610-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
7. <span data-ttu-id="48610-126">Se você estiver usando o Windows Firewall, o Skype for Business abrirá as portas necessárias automaticamente.</span><span class="sxs-lookup"><span data-stu-id="48610-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="48610-127">Se a sua organização estiver usando uma solução de firewall diferente para restringir a conexão com a Internet nos computadores da rede, verifique se seus computadores clientes podem acessar os [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) a seguir.</span><span class="sxs-lookup"><span data-stu-id="48610-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="48610-128">Talvez seja necessário adicionar os FQDNs para a saída configuração da infraestrutura de lista no seu firewall ou proxy de permissões: \*\* \*. api.skype.com\*\*, \* **. users.storage.live.com**e **graph.skype.com**.</span><span class="sxs-lookup"><span data-stu-id="48610-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="48610-129">Para obter instruções sobre como abrir essas portas em seu firewall, consulte a documentação que o acompanha.</span><span class="sxs-lookup"><span data-stu-id="48610-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="48610-130">Para obter uma lista de todas as portas que precisam ser abertas, consulte [URLs do Office 365 e intervalos de endereços IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="48610-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

8. <span data-ttu-id="48610-131">Certifique-se de que o administrador da organização também tiver seguido essas etapas.</span><span class="sxs-lookup"><span data-stu-id="48610-131">Make sure that the administrator in the organization has also followed these steps.</span></span>
    
9. <span data-ttu-id="48610-p106">**AGUARDE 24 HORAS PARA FAZER O TESTE**. Em qualquer momento que você alterar as configurações das comunicações externas, poderá levar até 24 horas para as alterações serem efetivadas em todos os data centers.</span><span class="sxs-lookup"><span data-stu-id="48610-p106">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="48610-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Você pode permitir que seus usuários pesquisem todas as pessoas que usam o Skype (o aplicativo gratuito!) e enviem mensagens instantâneas para elas.</span><span class="sxs-lookup"><span data-stu-id="48610-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="48610-135">Para saber mais, consulte [Skype permitem que usuários corporativos adicionar contatos do Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="48610-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="48610-136">Testar e solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="48610-136">Test and troubleshoot</span></span>
<span data-ttu-id="48610-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="48610-137"></span></span>

 <span data-ttu-id="48610-138">**O problema mais comum encontrado pelas pessoas ao configurar a comunicação entre empresas é como definir suas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) corretamente.**</span><span class="sxs-lookup"><span data-stu-id="48610-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="48610-139">Para testar sua configuração, você precisa de um contato no Skype for Business que não seja protegido pelo firewall da empresa.</span><span class="sxs-lookup"><span data-stu-id="48610-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="48610-140">Depois de alterar as configurações de suas comunicações externas, **AGUARDE ATÉ 24 HORAS ANTES DE TESTAR**.</span><span class="sxs-lookup"><span data-stu-id="48610-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="48610-141">No Skype for Business, pesquise seu contato no Skype for Business, e envie uma solicitação para chat.</span><span class="sxs-lookup"><span data-stu-id="48610-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="48610-142">Se você receber uma mensagem que ele não pôde ser enviado devido à política da empresa, você precisará verificar novamente suas [URLs do Office 365 e intervalos de endereços IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="48610-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="48610-p108">Peça ao seu contato do Skype for Business para lhe enviar uma solicitação de conversa. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).</span><span class="sxs-lookup"><span data-stu-id="48610-p108">Ask your Skype for Business contact to send you a request to chat. If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="48610-p109">Para testar de outra maneira se o problema é o firewall, basta usar o wifi de um lugar que não tenha firewall, como uma cafeteria, e usar o Skype for Business para enviar uma solicitação ao contato do Skype para chat. Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.</span><span class="sxs-lookup"><span data-stu-id="48610-p109">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat. If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="48610-147">Como localizar pessoas e ser localizado ao conectar-se com outra empresa</span><span class="sxs-lookup"><span data-stu-id="48610-147">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="48610-148"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="48610-148"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="48610-149">Após habilitar comunicações externas com outro Skype para usuários corporativos, os usuários podem encontrar Skype federado para usuários comerciais pesquisando por seu nome de entrada: por exemplo, Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="48610-149">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="48610-150">Em seguida, será necessário adicionar a pessoa à sua lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="48610-150">Then they will need to add the person to their list of contacts.</span></span>
  
![Para localizar um usuário em uma empresa federada, você deve procurar por seus endereços de email (Isso é geralmente também seu nome de usuário).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="48610-152">Dicas para configurar comunicações com empresas federadas</span><span class="sxs-lookup"><span data-stu-id="48610-152">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="48610-153"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="48610-153"></span></span>

- <span data-ttu-id="48610-154">Para configurar a federação entre Skype para negócios 2015 e Skype para Business Online, consulte este artigo: [Configurar federação com Skype para negócios Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span><span class="sxs-lookup"><span data-stu-id="48610-154">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="48610-155">Para configurar a federação entre o Lync e Skype para Business Online, consulte este artigo: [Configurando o suporte de federação para um cliente Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span><span class="sxs-lookup"><span data-stu-id="48610-155">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="48610-156">Quando dois usuários do Skype for Business no Office 365 estão se comunicando entre si em domínios separados, eles só podem usar os recursos do Skype for Business (por exemplo, conversas por vídeo ou compartilhamento de área de trabalho) que estejam ativados em ambas as organizações.</span><span class="sxs-lookup"><span data-stu-id="48610-156">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="48610-157">Se um Skype para usuários de negócios de sua organização é colocado em um In-loco ou retenção de litígio, qualquer conversas de mensagens Instantâneas entre esse usuário e outra Skype para usuários corporativos ou Skype serão salvo no **Itens recuperáveis** em suas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="48610-157">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="48610-158">Essas conversas não serão salvas na pasta **Histórico da Conversa** de suas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="48610-158">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="48610-159">Desativar a comunicação externa para indivíduos específicos</span><span class="sxs-lookup"><span data-stu-id="48610-159">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="48610-160"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="48610-160"></span></span>

<span data-ttu-id="48610-161">Depois de habilitar a comunicação externa para toda a sua empresa, você poderá desativá-la para indivíduos específicos.</span><span class="sxs-lookup"><span data-stu-id="48610-161">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="48610-162">Entrar com sua conta de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="48610-162">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="48610-163">No Centro de administração do Office 365, vá para **usuários** > **usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="48610-163">In the Office 365 admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="48610-164">Na lista de usuários, escolha o usuário e, em **Mais Configurações**, clique em **Editar as propriedades do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="48610-164">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="48610-166">No **Skype para centro de administração de negócios**, escolha **comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="48610-166">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="48610-167">Na página **Opções** , todas as opções serão selecionadas.</span><span class="sxs-lookup"><span data-stu-id="48610-167">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="48610-168">Desmarque a comunicações que você deseja desabilitar.</span><span class="sxs-lookup"><span data-stu-id="48610-168">Clear the communications you want to disable.</span></span> <span data-ttu-id="48610-169">A imagem a seguir mostra que Júlio poderá se comunicar com pessoas em outras empresas confiáveis, mas não com outros usuários do Skype.</span><span class="sxs-lookup"><span data-stu-id="48610-169">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="48610-171">Escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="48610-171">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="48610-172">[!OBSERVAçãO] Talvez você precise aguardar até 24 horas para que as configurações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="48610-172">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="48610-173">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="48610-173">Related topics</span></span>
<span data-ttu-id="48610-174"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="48610-174"></span></span>

[<span data-ttu-id="48610-175">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="48610-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="48610-176">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="48610-176">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
