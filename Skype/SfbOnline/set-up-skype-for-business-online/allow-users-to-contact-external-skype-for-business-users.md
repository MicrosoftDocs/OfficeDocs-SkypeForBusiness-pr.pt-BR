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
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: 'Veja como configurar o Skype for Business para permitir que os usuários conversem com usuários em outra organização ou permitir que contatos externos conversem com eles. '
ms.openlocfilehash: 8acab73fec7337ee70cd8b5059b00df42e836e62
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093505"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="7217f-103">Permitir que os usuários entrem em contato com usuários externos do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7217f-103">Allow users to contact external Skype for Business users</span></span>
  
<span data-ttu-id="7217f-104">Siga as etapas descritas neste artigo quando:</span><span class="sxs-lookup"><span data-stu-id="7217f-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="7217f-p101">Você tiver usuários em diferentes domínios na sua empresa. Por exemplo, Rob@ContosoEast.com e Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="7217f-p101">You have users on different domains in your business. For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>

- <span data-ttu-id="7217f-107">Desejar que as pessoas em sua organização usem o Skype for Business para entrar em contato com pessoas em empresas específicas de fora de sua organização.</span><span class="sxs-lookup"><span data-stu-id="7217f-107">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="7217f-108">Você deseja que qualquer outra pessoa no mundo que use o Skype for Business possa encontrar e entrar em contato com você usando seu endereço de email.</span><span class="sxs-lookup"><span data-stu-id="7217f-108">You want anyone else in the world who uses Skype for Business to be able to find and contact you using your email address.</span></span> <span data-ttu-id="7217f-109">Se as configurações padrão do Skype for Business forem usadas, isso funcionará automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7217f-109">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="7217f-110">Caso contrário, o usuário deverá verificar se a configuração não está bloqueando seu domínio.</span><span class="sxs-lookup"><span data-stu-id="7217f-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>

## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="7217f-111">Habilitar comunicações entre empresas para os usuários</span><span class="sxs-lookup"><span data-stu-id="7217f-111">Enable business-to-business communications for your users</span></span>

<span data-ttu-id="7217f-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="7217f-112"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="7217f-113">Você deve ter [permissões de](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) administrador no Microsoft 365 ou Office 365 em ambas as organizações para fazer essa comunicação.</span><span class="sxs-lookup"><span data-stu-id="7217f-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this communication.</span></span>

<span data-ttu-id="7217f-114">![Um ícone mostrando o logotipo do Microsoft Teams ](../images/teams-logo-30x30.png) **Usando o centro de administração do Teams**</span><span class="sxs-lookup"><span data-stu-id="7217f-114">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="7217f-115">Entre com sua conta de administrador do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="7217f-115">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="7217f-116">No centro de administração, vá para **Admin Centers**  >  **Teams**.</span><span class="sxs-lookup"><span data-stu-id="7217f-116">In the admin center, go to **Admin Centers** > **Teams**.</span></span>

    ![Escolha o Administrador do Teams.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="7217f-118">Na central **do Teams,** escolha Portal Herdado do **Skype** Escolha o >  
  ![ Portal Herdado do SfB.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="7217f-118">In the **Teams center**, choose **Skype** > **Legacy Portal**
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>

4. <span data-ttu-id="7217f-119">No **Centro de administração Skype for Business**, escolha **Organização** > **Comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="7217f-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="7217f-120">Para configurar a comunicação com uma empresa específica ou com usuários em outro domínio, na caixa suspensa, escolha **Ativado somente para os domínios permitidos**.</span><span class="sxs-lookup"><span data-stu-id="7217f-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="7217f-p103">OU, se quiser habilitar a comunicação com todos que tiverem as políticas do Skype for Business, escolha **Ativado exceto para domínios bloqueados**. Esta é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="7217f-p103">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**. This is the default setting.</span></span>

6. <span data-ttu-id="7217f-123">Em **Domínios bloqueados ou permitidos,** escolha e adicione o **+** nome do domínio que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="7217f-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>

7. <span data-ttu-id="7217f-124">Certifique-se de que o administrador da outra organização faça essas mesmas etapas no centro **de administração do Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="7217f-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="7217f-125">Por exemplo, na lista **domínios permitidos** da outra organização, o administrador precisa inserir o domínio da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="7217f-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

8. <span data-ttu-id="7217f-126">Se você estiver usando o Windows Firewall, o Skype for Business abrirá as portas necessárias automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7217f-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>

    <span data-ttu-id="7217f-127">Se a sua organização estiver usando uma solução de firewall diferente para restringir a conexão com a Internet nos computadores da rede, verifique se seus computadores clientes podem acessar os [URLs e intervalos de endereços IP do Office 365](/microsoftteams/office-365-urls-ip-address-ranges) a seguir.</span><span class="sxs-lookup"><span data-stu-id="7217f-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="7217f-128">Isso pode exigir a adição de FQDNs à lista de autorizações de saída em sua configuração de infraestrutura de firewall ou proxy: **\* .api.skype.com,** \* *_.users.storage.live.com_* e **graph.skype.com**.</span><span class="sxs-lookup"><span data-stu-id="7217f-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \**_.users.storage.live.com_*, and **graph.skype.com**.</span></span> <span data-ttu-id="7217f-129">Para obter instruções sobre como abrir essas portas no firewall, verifique a documentação que veio com ela.</span><span class="sxs-lookup"><span data-stu-id="7217f-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>

    <span data-ttu-id="7217f-130">Para uma lista de todas as portas que você precisa abrir, consulte [URLs do Office 365 e intervalos de endereços IP.](/microsoftteams/office-365-urls-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="7217f-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="7217f-131">Certifique-se de que o administrador na organização também tenha seguido estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7217f-131">Make sure that the administrator in the organization has also followed these steps.</span></span>

10. <span data-ttu-id="7217f-132">**AGUARDE 24 HORAS PARA FAZER O TESTE**.</span><span class="sxs-lookup"><span data-stu-id="7217f-132">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="7217f-133">Quando você altera as configurações de comunicações externas, pode levar até 24 horas para que as alterações se preencham em todos os data centers.</span><span class="sxs-lookup"><span data-stu-id="7217f-133">When you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

<span data-ttu-id="7217f-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Você pode permitir que seus usuários pesquisem todas as pessoas que usam o Skype (o aplicativo gratuito!) e enviem mensagens instantâneas para elas.</span><span class="sxs-lookup"><span data-stu-id="7217f-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="7217f-135">Para saber mais, confira [Permitir que os usuários do Skype for Business adicionem contatos do Skype.](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="7217f-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="7217f-136">Testar e solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="7217f-136">Test and troubleshoot</span></span>

<span data-ttu-id="7217f-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="7217f-137"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="7217f-138">**O problema mais comum encontrado pelas pessoas ao configurar a comunicação entre empresas é como definir suas [URLs e intervalos de endereços IP do Office 365](/microsoftteams/office-365-urls-ip-address-ranges) corretamente.**</span><span class="sxs-lookup"><span data-stu-id="7217f-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="7217f-139">Para testar sua configuração, você precisa de um contato no Skype for Business que não seja protegido pelo firewall da empresa.</span><span class="sxs-lookup"><span data-stu-id="7217f-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="7217f-140">Depois de alterar as configurações de suas comunicações externas, **AGUARDE ATÉ 24 HORAS ANTES DE TESTAR**.</span><span class="sxs-lookup"><span data-stu-id="7217f-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>

2. <span data-ttu-id="7217f-141">No Skype for Business, pesquise seu contato no Skype for Business, e envie uma solicitação para chat.</span><span class="sxs-lookup"><span data-stu-id="7217f-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>

    <span data-ttu-id="7217f-142">Se você receber uma mensagem de que ela não pôde ser enviada devido à política da empresa, você precisará verificar duas vezes suas [URLs do Office 365](/microsoftteams/office-365-urls-ip-address-ranges)e intervalos de endereços IP.</span><span class="sxs-lookup"><span data-stu-id="7217f-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

3. <span data-ttu-id="7217f-p108">Peça ao seu contato do Skype for Business para lhe enviar uma solicitação de conversa. Se você não receber a solicitação, o problema são as suas configurações de firewall (assumindo que já tenha sido confirmado que as configurações de firewall estão corretas).</span><span class="sxs-lookup"><span data-stu-id="7217f-p108">Ask your Skype for Business contact to send you a request to chat. If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="7217f-145">Outra maneira de testar se o problema é o firewall é ir para um local wifi não atrás do firewall, como uma cafeteria.</span><span class="sxs-lookup"><span data-stu-id="7217f-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall, such as a coffee shop.</span></span> <span data-ttu-id="7217f-146">Use o Skype for Business para enviar uma solicitação ao seu contato para chat.</span><span class="sxs-lookup"><span data-stu-id="7217f-146">Use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="7217f-147">Se a mensagem for enviada de lá, mas não de seu trabalho, então você saberá que o problema é o firewall.</span><span class="sxs-lookup"><span data-stu-id="7217f-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="7217f-148">Como localizar pessoas e ser localizado ao conectar-se com outra empresa</span><span class="sxs-lookup"><span data-stu-id="7217f-148">How to find others, and be found, when connecting with another business</span></span>

<span data-ttu-id="7217f-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="7217f-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="7217f-150">Depois de habilitar a comunicação externa com outros usuários do Skype for Business, os usuários podem encontrar usuários federados do Skype for Business pesquisando seus nomes de login.</span><span class="sxs-lookup"><span data-stu-id="7217f-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in names.</span></span> <span data-ttu-id="7217f-151">Um exemplo é Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7217f-151">An example is Rob@contoso.com.</span></span> <span data-ttu-id="7217f-152">Então, eles deverão adicionar a pessoa à lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="7217f-152">Then they will need to add the person to their list of contacts.</span></span>
  
![Para encontrar um usuário em uma empresa federada, você deve pesquisar seu endereço de email (geralmente também é o nome de login).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="7217f-154">Dicas para configurar comunicações com empresas federadas</span><span class="sxs-lookup"><span data-stu-id="7217f-154">Tips on setting up communications with federated businesses</span></span>

<span data-ttu-id="7217f-155"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="7217f-155"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="7217f-156">Para configurar a federação entre o Skype for Business 2015 e o Skype for Business Online, consulte este artigo: [Configure federation with Skype for Business Online](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="7217f-156">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>

- <span data-ttu-id="7217f-157">Para configurar a federação entre o Lync e o Skype for Business Online, consulte este artigo: [Configuring Federation Support for a Lync Online Customer](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer).</span><span class="sxs-lookup"><span data-stu-id="7217f-157">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer).</span></span>

- <span data-ttu-id="7217f-158">Quando dois usuários do Skype for Business no Microsoft 365 ou No Office 365 estão se comunicando uns com os outros em domínios separados, eles só podem usar recursos do Skype for Business (por exemplo, conversas em vídeo ou compartilhamento de área de trabalho) que são ativos em ambas as organizações.</span><span class="sxs-lookup"><span data-stu-id="7217f-158">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>

- <span data-ttu-id="7217f-159">Se um usuário do Skype for Business em sua organização for colocado em uma In-Place ou Responsabilidade de Litígio,  qualquer conversa de mensagens entre esse usuário e outros usuários do Skype for Business ou skype será salva em Itens Recuperáveis em sua caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="7217f-159">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="7217f-160">Essas conversas não serão salvas na pasta **Histórico da Conversa** de suas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="7217f-160">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>

## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="7217f-161">Desativar a comunicação externa para indivíduos específicos</span><span class="sxs-lookup"><span data-stu-id="7217f-161">Turn off external communication for specific individuals</span></span>

<span data-ttu-id="7217f-162"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="7217f-162"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="7217f-163">Depois de habilitar a comunicação externa para toda a sua empresa, você poderá desativá-la para indivíduos específicos.</span><span class="sxs-lookup"><span data-stu-id="7217f-163">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="7217f-164">Entre com sua conta de administrador do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="7217f-164">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="7217f-165">No centro de administração, vá para **Usuários**  >  **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="7217f-165">In the admin center, go to **Users** > **Active users**.</span></span>

3. <span data-ttu-id="7217f-166">Na lista de usuários, escolha o usuário e, em **Mais Configurações**, clique em **Editar as propriedades do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="7217f-166">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>

    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="7217f-168">No Centro **de administração do Skype for Business,** escolha **Comunicações externas.**</span><span class="sxs-lookup"><span data-stu-id="7217f-168">In the **Skype for Business admin center**, choose **External communications**.</span></span>

    <span data-ttu-id="7217f-169">Na página **Opções,** todas as opções serão selecionadas.</span><span class="sxs-lookup"><span data-stu-id="7217f-169">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="7217f-170">Limpe as comunicações que você deseja desabilitar.</span><span class="sxs-lookup"><span data-stu-id="7217f-170">Clear the communications you want to disable.</span></span> <span data-ttu-id="7217f-171">A imagem a seguir mostra que Júlio poderá se comunicar com pessoas em outras empresas confiáveis, mas não com outros usuários do Skype.</span><span class="sxs-lookup"><span data-stu-id="7217f-171">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>

    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="7217f-173">Escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7217f-173">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="7217f-174">[!OBSERVAçãO] Talvez você precise aguardar até 24 horas para que as configurações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="7217f-174">You may have to wait for up to 24 hours for your changes to take effect.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="7217f-175">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7217f-175">Related topics</span></span>

<span data-ttu-id="7217f-176"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="7217f-176"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="7217f-177">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7217f-177">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="7217f-178">Permitir que os usuários do Skype for Business adicionem contatos do Skype</span><span class="sxs-lookup"><span data-stu-id="7217f-178">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
