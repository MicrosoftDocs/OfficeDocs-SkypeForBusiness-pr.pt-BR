---
title: Permitir que os usuários entrem em contato com usuários externos do Skype for Business
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
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
ms.openlocfilehash: 3656038efa660db0b63f382908f4de5a8b7172d4
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344556"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="c10df-103">Permitir que os usuários entrem em contato com usuários externos do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c10df-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="c10df-104">A Federação do Skype for Business não está disponível para o Office 365 operado pela 21Vianet e pelas organizações da Alemanha do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c10df-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="c10df-105">Siga as etapas descritas neste artigo quando:</span><span class="sxs-lookup"><span data-stu-id="c10df-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="c10df-p101">Você tiver usuários em diferentes domínios na sua empresa. Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="c10df-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="c10df-108">Desejar que as pessoas em sua organização usem o Skype for Business para entrar em contato com pessoas em empresas específicas de fora de sua organização.</span><span class="sxs-lookup"><span data-stu-id="c10df-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="c10df-109">Você quer que qualquer outro usuário do mundo que use o Skype for Business possa encontrá-lo e contatá-lo usando o seu endereço de e-mail.</span><span class="sxs-lookup"><span data-stu-id="c10df-109">You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="c10df-110">Se as configurações padrão do Skype for Business forem usadas, isso funcionará automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c10df-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="c10df-111">Caso contrário, o usuário deverá verificar se a configuração não está bloqueando seu domínio.</span><span class="sxs-lookup"><span data-stu-id="c10df-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="c10df-112">Habilitar comunicações entre empresas para os usuários</span><span class="sxs-lookup"><span data-stu-id="c10df-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="c10df-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="c10df-113"></span></span>

<span data-ttu-id="c10df-114">Você deve ter [permissões de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) no Office 365 em ambas as organizações para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="c10df-114">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="c10df-115">![Um ícone mostrando o logotipo](../images/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do teams**</span><span class="sxs-lookup"><span data-stu-id="c10df-115">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="c10df-116">Entre com sua conta de administrador do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c10df-116">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="c10df-117">No centro de administração do Office 365, vá para**equipes**de **centros** > de administração.</span><span class="sxs-lookup"><span data-stu-id="c10df-117">In the Office 365 admin center, go to **Admin Centers** > **Teams**.</span></span>
    
    ![Escolha o administrador do teams.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="c10df-119">Na **central**do Teams, escolha **portal** 
 ![herdado **do Skype** > escolha o portal herdado do SfB.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="c10df-119">In the **Teams center**, choose **Skype** > **Legacy Portal** 
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>
 
4. <span data-ttu-id="c10df-120">No **centro de administração do Skype for Business** , escolha**comunicações externas**da **organização** > .</span><span class="sxs-lookup"><span data-stu-id="c10df-120">In the **Skype for Business admin center** , choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="c10df-121">Para configurar a comunicação com uma empresa específica ou com usuários em outro domínio, na caixa suspensa, escolha **ativado somente para os domínios permitidos**.</span><span class="sxs-lookup"><span data-stu-id="c10df-121">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="c10df-p103">OU, se quiser habilitar a comunicação com todos que tiverem as políticas do Skype for Business, escolha **Ativado exceto para domínios bloqueados**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="c10df-p103">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>
    
6. <span data-ttu-id="c10df-124">Em **domínios bloqueados ou permitidos**, **+** escolha e adicione o nome do domínio que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="c10df-124">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
7. <span data-ttu-id="c10df-125">Verifique se o administrador da outra organização executa essas mesmas etapas no centro de **Administração do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c10df-125">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="c10df-126">Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="c10df-126">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
8. <span data-ttu-id="c10df-127">Se você estiver usando o Windows Firewall, o Skype for Business abrirá as portas necessárias automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c10df-127">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="c10df-128">Se a sua organização estiver usando uma solução de firewall diferente para restringir a conexão com a Internet nos computadores da rede, verifique se seus computadores clientes podem acessar os [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) a seguir.</span><span class="sxs-lookup"><span data-stu-id="c10df-128">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="c10df-129">Isso pode exigir a adição dos FQDNs à lista de permissões de saída em seu firewall ou configuração de infraestrutura de proxy \*: \*\* \*. API.Skype.com\*\*, **. Users.Storage.Live.com**e **Graph.Skype.com**.</span><span class="sxs-lookup"><span data-stu-id="c10df-129">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="c10df-130">Para obter instruções sobre como abrir essas portas no firewall, consulte a documentação que a acompanha.</span><span class="sxs-lookup"><span data-stu-id="c10df-130">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="c10df-131">Para obter uma lista de todas as portas que você precisa abrir, consulte [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="c10df-131">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="c10df-132">Verifique se o administrador da organização também seguiu estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c10df-132">Make sure that the administrator in the organization has also followed these steps.</span></span>
    
10. <span data-ttu-id="c10df-p106">**AGUARDE 24 HORAS PARA FAZER O TESTE**. Em qualquer momento que você alterar as configurações das comunicações externas, poderá levar até 24 horas para as alterações serem efetivadas em todos os data centers.</span><span class="sxs-lookup"><span data-stu-id="c10df-p106">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="c10df-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Você pode permitir que seus usuários pesquisem todas as pessoas que usam o Skype (o aplicativo gratuito!) e enviem mensagens instantâneas para elas.</span><span class="sxs-lookup"><span data-stu-id="c10df-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="c10df-136">Para saber mais, confira [permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="c10df-136">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="c10df-137">Testar e solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="c10df-137">Test and troubleshoot</span></span>
<span data-ttu-id="c10df-138"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="c10df-138"></span></span>

 <span data-ttu-id="c10df-139">**O problema mais comum encontrado pelas pessoas ao configurar a comunicação entre empresas é como definir suas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) corretamente.**</span><span class="sxs-lookup"><span data-stu-id="c10df-139">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="c10df-140">Para testar sua configuração, você precisa de um contato no Skype for Business que não seja protegido pelo firewall da empresa.</span><span class="sxs-lookup"><span data-stu-id="c10df-140">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="c10df-141">Depois de alterar as configurações de suas comunicações externas, **AGUARDE ATÉ 24 HORAS ANTES DE TESTAR**.</span><span class="sxs-lookup"><span data-stu-id="c10df-141">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="c10df-142">No Skype for Business, pesquise seu contato no Skype for Business, e envie uma solicitação para chat.</span><span class="sxs-lookup"><span data-stu-id="c10df-142">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="c10df-143">Se você receber uma mensagem informando que ela não foi enviada devido à política da empresa, você precisa verificar novamente suas [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="c10df-143">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="c10df-p108">Peça ao seu contato do Skype for Business para lhe enviar uma solicitação de conversa. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).</span><span class="sxs-lookup"><span data-stu-id="c10df-p108">Ask your Skype for Business contact to send you a request to chat. If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="c10df-p109">Para testar de outra maneira se o problema é o firewall, basta usar o wifi de um lugar que não tenha firewall, como uma cafeteria, e usar o Skype for Business para enviar uma solicitação ao contato do Skype para chat. Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.</span><span class="sxs-lookup"><span data-stu-id="c10df-p109">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat. If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="c10df-148">Como localizar pessoas e ser localizado ao conectar-se com outra empresa</span><span class="sxs-lookup"><span data-stu-id="c10df-148">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="c10df-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="c10df-149"></span></span>

<span data-ttu-id="c10df-150">Depois de habilitar a comunicação externa com outros usuários do Skype for Business, os usuários podem encontrar usuários federados do Skype for Business procurando por seu nome de entrada: por exemplo, Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c10df-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="c10df-151">Então, eles deverão adicionar a pessoa à lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="c10df-151">Then they will need to add the person to their list of contacts.</span></span>
  
![Para localizar um usuário em uma empresa federada, você deve pesquisar seu endereço de email (geralmente, isso também é o nome do usuário).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="c10df-153">Dicas para configurar comunicações com empresas federadas</span><span class="sxs-lookup"><span data-stu-id="c10df-153">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="c10df-154"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="c10df-154"></span></span>

- <span data-ttu-id="c10df-155">Para configurar a Federação entre o Skype for Business 2015 e o Skype for Business Online, confira este artigo: [Configurar a Federação com o Skype for Business online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span><span class="sxs-lookup"><span data-stu-id="c10df-155">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="c10df-156">Para configurar a Federação entre o Lync e o Skype for Business Online, confira este artigo: Configurando o [suporte de Federação para um cliente do Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span><span class="sxs-lookup"><span data-stu-id="c10df-156">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="c10df-157">Quando dois usuários do Skype for Business no Office 365 estão se comunicando entre si em domínios separados, eles só podem usar os recursos do Skype for Business (por exemplo, conversas por vídeo ou compartilhamento de área de trabalho) que estejam ativados em ambas as organizações.</span><span class="sxs-lookup"><span data-stu-id="c10df-157">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="c10df-158">Se um usuário do Skype for Business em sua organização for colocado em um local ou em uma retenção de litígio, todas as conversas de mensagens instantâneas entre esse usuário e outros usuários do Skype for Business ou do Skype serão salvas em **itens recuperáveis** na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="c10df-158">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="c10df-159">Essas conversas não serão salvas na pasta **Histórico da Conversa** de suas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="c10df-159">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="c10df-160">Desativar a comunicação externa para indivíduos específicos</span><span class="sxs-lookup"><span data-stu-id="c10df-160">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="c10df-161"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="c10df-161"></span></span>

<span data-ttu-id="c10df-162">Depois de habilitar a comunicação externa para toda a sua empresa, você poderá desativá-la para indivíduos específicos.</span><span class="sxs-lookup"><span data-stu-id="c10df-162">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="c10df-163">Entre com sua conta de administrador do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c10df-163">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="c10df-164">No centro de administração do Office 365, vá \*\*\*\* > para usuários**ativos**do Office.</span><span class="sxs-lookup"><span data-stu-id="c10df-164">In the Office 365 admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="c10df-165">Na lista de usuários, escolha o usuário e, em **Mais Configurações**, clique em **Editar as propriedades do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c10df-165">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="c10df-167">No **centro de administração do Skype for Business**, escolha **comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="c10df-167">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="c10df-168">Na página **Opções** , todas as opções serão selecionadas.</span><span class="sxs-lookup"><span data-stu-id="c10df-168">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="c10df-169">Desmarque as comunicações que você deseja desabilitar.</span><span class="sxs-lookup"><span data-stu-id="c10df-169">Clear the communications you want to disable.</span></span> <span data-ttu-id="c10df-170">A imagem a seguir mostra que Júlio poderá se comunicar com pessoas em outras empresas confiáveis, mas não com outros usuários do Skype.</span><span class="sxs-lookup"><span data-stu-id="c10df-170">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="c10df-172">Escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c10df-172">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c10df-173">[!OBSERVAçãO] Talvez você precise aguardar até 24 horas para que as configurações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="c10df-173">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="c10df-174">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c10df-174">Related topics</span></span>
<span data-ttu-id="c10df-175"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="c10df-175"></span></span>

[<span data-ttu-id="c10df-176">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c10df-176">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="c10df-177">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="c10df-177">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
