---
title: 'Lync Server 2013: usando a conectividade Lync-Skype como um usuário final'
description: 'Lync Server 2013: usando a conectividade do Lync-Skype como um usuário final.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd669a5cf0b15f7fb2d411e4456553f5469d9f96
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580377"
---
# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a><span data-ttu-id="2089d-103">Usando a conectividade Lync-Skype no Lync Server 2013 como um usuário final</span><span class="sxs-lookup"><span data-stu-id="2089d-103">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2089d-104">_**Última modificação do tópico:** 2016-12-27_</span><span class="sxs-lookup"><span data-stu-id="2089d-104">_**Topic Last Modified:** 2016-12-27_</span></span>

<span data-ttu-id="2089d-105">Lync-Skype conectividade permite que usuários do Skype e usuários do Lync adicionem uns aos outros como contatos, mensagens instantâneas do Exchange e façam chamadas de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="2089d-105">Lync-Skype Connectivity enables Skype users and Lync users to add each other as contacts, exchange instant messages and make audio and video calls.</span></span> <span data-ttu-id="2089d-106">Quando um usuário do Skype adiciona um usuário do Lync, um usuário do Skype cria um contato no Skype contendo o URI (Uniform Resource Identifier) do protocolo SIP do usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="2089d-106">When a Skype user adds a Lync user, a Skype user will create a contact in Skype containing the session initiation protocol (SIP) uniform resource identifier (URI) of the Lync user.</span></span> <span data-ttu-id="2089d-107">Por outro lado, quando um usuário do Lync adiciona um contato do Skype, o usuário do Lync criará um contato no Lync que conterá a conta da Microsoft (MSA) do usuário do Skype e não o nome de usuário do Skype.</span><span class="sxs-lookup"><span data-stu-id="2089d-107">Conversely, when a Lync user adds a Skype contact, the Lync user will create a contact in Lync that will contain the Microsoft Account (MSA) of the Skype user, and not the Skype user name.</span></span>

<span data-ttu-id="2089d-108">**O que é um MSA?**</span><span class="sxs-lookup"><span data-stu-id="2089d-108">**What is an MSA?**</span></span> <span data-ttu-id="2089d-109">Os usuários do Skype devem entrar no Skype com uma conta da Microsoft (anteriormente denominada Windows Live ID) para se comunicar com contatos do Lync.</span><span class="sxs-lookup"><span data-stu-id="2089d-109">Skype users must sign in to Skype with a Microsoft account (previously called Windows Live ID) in order to communicate with Lync contacts.</span></span><span data-ttu-id="2089d-110">Uma conta da Microsoft consiste na combinação de um endereço de email e uma senha, que você também pode usar para entrar em serviços como a tecnologia de armazenamento do Microsoft OneDrive, o Windows Phone, o serviço de jogos do Microsoft Xbox LIVE online e o cliente de mensagens e colaboração do Microsoft Outlook (e, anteriormente, o serviço de email baseado na Web do Microsoft Hotmail ou o Windows Live Messenger).</span><span class="sxs-lookup"><span data-stu-id="2089d-110"> A Microsoft account consists of the combination of an email address and a password, which you can also use to sign in to services such as Microsoft OneDrive storage technology, Windows Phone, Microsoft Xbox LIVE online game service, and Microsoft Outlook messaging and collaboration client (and, previously, Microsoft Hotmail web-based e-mail service or Windows Live Messenger).</span></span><span data-ttu-id="2089d-111">Se você usar um endereço de email e uma senha para se conectar a esses ou outros serviços, você já tem uma conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2089d-111"> If you use an email address and a password to sign in to these or other services, you already have a Microsoft account.</span></span><span data-ttu-id="2089d-112">Para obter detalhes sobre como criar uma conta da Microsoft, consulte a página de inscrição da conta da Microsoft em [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061) .</span><span class="sxs-lookup"><span data-stu-id="2089d-112"> For details about creating a Microsoft Account, see the Microsoft account sign-up page at [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061).</span></span> <span data-ttu-id="2089d-113">Você pode mesclar sua conta do Skype existente com sua conta da Microsoft para logon único, em vários aplicativos e serviços.</span><span class="sxs-lookup"><span data-stu-id="2089d-113">You can merge your existing Skype account with your Microsoft account for single sign-on, across a variety of applications and services.</span></span> <span data-ttu-id="2089d-114">Depois que a conta for mesclada, um usuário do Skype poderá enviar uma solicitação de contato aos usuários do Lync.</span><span class="sxs-lookup"><span data-stu-id="2089d-114">Once the account is merged a Skype user can send a contact request to Lync users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2089d-115">Para que os usuários do Lync e do Skype se comuniquem entre si, os seguintes requisitos devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="2089d-115">In order for Lync and Skype users to fully communicate with each other, the following requirements must be met:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="2089d-116">Os usuários do Skype devem estar conectados ao cliente Skype com uma conta da Microsoft (MSA).</span><span class="sxs-lookup"><span data-stu-id="2089d-116">Skype users must be logged into their Skype client with a Microsoft Account (MSA).</span></span></P>
> <LI>
> <P><span data-ttu-id="2089d-117">Os usuários do Lync devem estar habilitados para conectividade de IM pública pelo administrador do Lync.</span><span class="sxs-lookup"><span data-stu-id="2089d-117">Lync users must be enabled for public IM connectivity by their Lync administrator.</span></span></P>
> <LI>
> <P><span data-ttu-id="2089d-118">Quando um usuário do Skype adiciona um contato do Lync, verifique se o Word Lync aparece abaixo do nome do contato.</span><span class="sxs-lookup"><span data-stu-id="2089d-118">When a Skype user adds a Lync contact, verify that the word Lync appears below the contact’s name.</span></span> <span data-ttu-id="2089d-119">Isso indica que um URI do Lync foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="2089d-119">This indicates that a Lync URI has been found.</span></span></P>
> <LI>
> <P><span data-ttu-id="2089d-120">Quando um usuário do Skype adiciona um contato do Lync e resultados de pesquisa zero são retornados para esse domínio do Lync, o processo de provisionamento PIC pode não ter sido concluído ou o domínio do Lync ainda não foi configurado.</span><span class="sxs-lookup"><span data-stu-id="2089d-120">When a Skype user adds a Lync contact and zero search results are returned for that Lync domain, the PIC provisioning process may not have completed, or the Lync domain has not yet been set up.</span></span></P>
> <LI>
> <P><span data-ttu-id="2089d-121">Dependendo das configurações de privacidade dos usuários do Lync e do Skype, IM, vídeo e presença podem não funcionar até que os novos contatos sejam aceitos por cada usuário.</span><span class="sxs-lookup"><span data-stu-id="2089d-121">Depending on the privacy settings of the Lync and Skype users, IM, video, and presence may not work until the new contacts are accepted by each user.</span></span></P></LI></UL>



</div>

<span data-ttu-id="2089d-122">**Para adicionar um contato do Skype ao Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="2089d-122">**To add a Skype contact to Lync 2013**</span></span>

1.  <span data-ttu-id="2089d-123">No Lync, clique em **Adicionar um contato, adicionar um contato que não está na minha organização**.</span><span class="sxs-lookup"><span data-stu-id="2089d-123">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="2089d-124">Na lista de provedores de contato disponíveis, selecione **Skype**.</span><span class="sxs-lookup"><span data-stu-id="2089d-124">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="2089d-125">No campo **endereço de mensagens instantâneas** , insira a conta da Microsoft (MSA) do usuário do Skype.</span><span class="sxs-lookup"><span data-stu-id="2089d-125">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user.</span></span>

4.  <span data-ttu-id="2089d-126">Na caixa suspensa **Adicionar a grupo de contatos** , selecione um grupo de contatos ao qual adicionar o usuário.</span><span class="sxs-lookup"><span data-stu-id="2089d-126">In the **Add to contact group** dropdown box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="2089d-127">Na caixa de lista suspensa **definir relação de privacidade** , selecione a configuração de contato apropriada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2089d-127">In the **Set privacy relationship** dropdown box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="2089d-128">Agora, o usuário será exibido como um contato no Lync.</span><span class="sxs-lookup"><span data-stu-id="2089d-128">The user will now appear as a contact in Lync.</span></span> <span data-ttu-id="2089d-129">Selecione o usuário, clique com o botão direito do mouse no nome do usuário e clique em **Ver cartão de visita** para exibir as propriedades do usuário.</span><span class="sxs-lookup"><span data-stu-id="2089d-129">Select the user, right-click the user name, and click **See Contact Card** to view the user properties.</span></span> <span data-ttu-id="2089d-130">Agora você pode estabelecer uma chamada de áudio ou vídeo com o usuário do Skype recentemente adicionado.</span><span class="sxs-lookup"><span data-stu-id="2089d-130">You can now establish an audio or video call with the newly added Skype user.</span></span>

<span data-ttu-id="2089d-131">Para obter informações adicionais sobre o suporte para contatos, consulte [Adicionar um contato no Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span><span class="sxs-lookup"><span data-stu-id="2089d-131">For additional information on support for contacts, see [Add a contact in Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span></span>

<span data-ttu-id="2089d-132">Quando uma conta da Microsoft do usuário do Skype usa um nome de domínio personalizado, como o <strong>Bob@contoso.com</strong> , um usuário do Lync pode adicionar essa conta da Microsoft ao Lync de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="2089d-132">When a Skype user’s Microsoft account uses a custom domain name, such as <strong>bob@contoso.com</strong> , a Lync user can add that Microsoft account to Lync in two ways:</span></span>

1.  <span data-ttu-id="2089d-133">Use o ícone **Adicionar um contato** ou</span><span class="sxs-lookup"><span data-stu-id="2089d-133">Use the **Add a Contact** icon, or</span></span>

2.  <span data-ttu-id="2089d-134">Use o campo **localizar alguém ou uma sala, ou um campo discar um número** .</span><span class="sxs-lookup"><span data-stu-id="2089d-134">Use the **Find someone or a room, or a dial a number** field.</span></span>

<span data-ttu-id="2089d-135">Em cada instância, o usuário do Lync deve inserir o email do usuário do Skype no seguinte formato: <strong>usuário (nome de domínio) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="2089d-135">In each instance, the Lync user must enter the Skype user’s email in the following format: <strong>user(domain name)@msn.com</strong> .</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2089d-136">Esta etapa não é necessária para contas da Microsoft que usam os seguintes nomes de domínio: <STRONG>@live. com, @hotmail. com ou @outlook. com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2089d-136">This step is not required for Microsoft accounts that use the following domain names: <STRONG>@live.com, @hotmail.com or @outlook.com</STRONG>.</span></span> <span data-ttu-id="2089d-137">Para obter mais informações sobre nomes de domínio personalizados com suporte, consulte <A href="https://support.microsoft.com/kb/897567">domínios de mensagens instantâneas públicas compatíveis</A>.</span><span class="sxs-lookup"><span data-stu-id="2089d-137">For more information on supported custom domain names, see <A href="https://support.microsoft.com/kb/897567">Supported public IM domains</A>.</span></span>



</div>

<span data-ttu-id="2089d-138">**Para adicionar um contato do Skype ao Lync ao usar um nome de domínio personalizado**</span><span class="sxs-lookup"><span data-stu-id="2089d-138">**To add a Skype contact to Lync when using a custom domain name**</span></span>

1.  <span data-ttu-id="2089d-139">No Lync, clique em **Adicionar um contato, adicionar um contato que não está na minha organização**.</span><span class="sxs-lookup"><span data-stu-id="2089d-139">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="2089d-140">Na lista de provedores de contato disponíveis, selecione **Skype**.</span><span class="sxs-lookup"><span data-stu-id="2089d-140">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="2089d-141">No campo **endereço de mensagens instantâneas** , insira a conta da Microsoft (MSA) do usuário do Skype no formato <strong>usuário (nome de domínio) @msn. com</strong>.</span><span class="sxs-lookup"><span data-stu-id="2089d-141">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user in the format <strong>user(domain name)@msn.com</strong>.</span></span> <span data-ttu-id="2089d-142">Portanto, para o usuário bob@contoso.com, a entrada seria <strong> Bob (contoso. com) @msn. com <strong> .</span><span class="sxs-lookup"><span data-stu-id="2089d-142">So for user bob@contoso.com, the entry would be <strong>bob(contoso.com)@msn.com<strong> .</span></span>

4.  <span data-ttu-id="2089d-143">Na caixa de listagem suspensa **Adicionar ao grupo de contatos** , selecione um grupo de contatos ao qual adicionar o usuário.</span><span class="sxs-lookup"><span data-stu-id="2089d-143">In the **Add to contact group** drop-down list box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="2089d-144">Na caixa de listagem suspensa **definir relação de privacidade** , selecione a configuração de contato apropriada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2089d-144">In the **Set privacy relationship** drop-down list box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="2089d-145">Um usuário do Lync também pode usar a **localização de alguém ou uma sala, ou discar um** campo de número no Lync e adicionar um endereço semelhante ao seguinte <strong>usuário (nome de domínio) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="2089d-145">A Lync user can also use the **Find someone or a room, or dial a number** field in Lync, and add an address that resembles the following <strong>user(domain name)@msn.com</strong> .</span></span> <span data-ttu-id="2089d-146">Portanto, para a conta da Microsoft bob@contoso.com, a entrada seria <strong>Bob (contoso. com) @msn. com</strong> .</span><span class="sxs-lookup"><span data-stu-id="2089d-146">So for the bob@contoso.com Microsoft account, the entry would be <strong>bob(contoso.com)@msn.com</strong> .</span></span>

7.  <span data-ttu-id="2089d-147">Siga as etapas 4 e 5 anteriormente neste procedimento para adicionar o contato a um grupo de contatos e selecionar a relação de privacidade apropriada.</span><span class="sxs-lookup"><span data-stu-id="2089d-147">Follow steps 4 and 5 earlier in this procedure to add the contact to a contact group and to select the appropriate privacy relationship.</span></span>

<span data-ttu-id="2089d-148">**Para adicionar um contato do Lync ao Skype**</span><span class="sxs-lookup"><span data-stu-id="2089d-148">**To add a Lync contact to Skype**</span></span>

1.  <span data-ttu-id="2089d-149">Entrar no Skype.</span><span class="sxs-lookup"><span data-stu-id="2089d-149">Sign in to Skype.</span></span> <span data-ttu-id="2089d-150">O usuário do Skype deve estar conectado ao cliente Skype com uma conta da Microsoft (MSA).</span><span class="sxs-lookup"><span data-stu-id="2089d-150">The Skype user must be logged into their Skype client with a Microsoft Account (MSA).</span></span>

2.  <span data-ttu-id="2089d-151">Selecione o ícone adicionar contatos.</span><span class="sxs-lookup"><span data-stu-id="2089d-151">Select the Add Contacts icon.</span></span>

3.  <span data-ttu-id="2089d-152">Insira o URI do SIP do usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="2089d-152">Enter the SIP URI of the Lync user.</span></span> <span data-ttu-id="2089d-153">Por exemplo, bob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2089d-153">For example, bob@contoso.com.</span></span>

4.  <span data-ttu-id="2089d-154">Quando o Skype encontrar a correspondência nos resultados da pesquisa, procure o Word **Lync** abaixo do nome do usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="2089d-154">When Skype finds the match in the search results, look for the word **Lync** below the Lync user’s name.</span></span> <span data-ttu-id="2089d-155">Isso indica que o Skype localizou com êxito o URI SIP do cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="2089d-155">This indicates Skype successfully located the Lync client’s SIP URI.</span></span> <span data-ttu-id="2089d-156">Clique no nome.</span><span class="sxs-lookup"><span data-stu-id="2089d-156">Click the name.</span></span>

5.  <span data-ttu-id="2089d-157">No canto superior direito da janela, clique em Adicionar a contatos.</span><span class="sxs-lookup"><span data-stu-id="2089d-157">In the top right corner of the window, click Add to Contacts.</span></span>

6.  <span data-ttu-id="2089d-158">Agora, o novo contato será adicionado à sua lista de contatos, mas você verá um ponto de interrogação em vez do ícone de status até que aceite sua solicitação.</span><span class="sxs-lookup"><span data-stu-id="2089d-158">The new contact is now added to your contact list, but you’ll see a question mark instead of their status icon until they accept your request.</span></span> <span data-ttu-id="2089d-159">Quando o novo contato aceitar sua solicitação, você poderá ver quando elas estão online, iniciar conversas de IM e fazer chamadas de áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="2089d-159">When your new contact accepts your request, you will be able to see when they are online, initiate IM conversations, and make audio and video calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2089d-160">O administrador do Lync Server deve definir as configurações de política do usuário do Lync para permitir as solicitações de entrada.</span><span class="sxs-lookup"><span data-stu-id="2089d-160">The Lync Server administrator must configure the Lync user’s policy settings to allow incoming requests.</span></span> <span data-ttu-id="2089d-161">Caso contrário, o usuário do Lync não receberá solicitações de contato do usuário do Skype.</span><span class="sxs-lookup"><span data-stu-id="2089d-161">If not, the Lync user will not receive contact requests from the Skype user.</span></span> <span data-ttu-id="2089d-162">Dependendo da configuração das configurações de política do usuário do Lync, a solicitação para adicionar o usuário do Skype será exibida na guia <STRONG>novo</STRONG> do cliente Lync. Para começar a comunicar com o usuário do Skype, o usuário do Lync deve adicionar o usuário do Skype à lista de favoritos ou uma lista de contatos.</span><span class="sxs-lookup"><span data-stu-id="2089d-162">Depending on the configuration of the Lync user’s policy settings, the request to add the Skype user will appear on the Lync client’s <STRONG>New</STRONG> tab. To begin communicating with the Skype user, the Lync user must add the Skype user to either the Favorites list or a contact list.</span></span> <span data-ttu-id="2089d-163">A imagem abaixo mostra o local da <STRONG>nova</STRONG> guia no cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="2089d-163">The image below shows the location of the <STRONG>New</STRONG> tab in the Lync client.</span></span>

    
    </div>

<span data-ttu-id="2089d-164">Um usuário do Lync deve configurar alertas do Lync para garantir que as solicitações enviadas de um usuário do Skype apareçam e sejam detectáveis pelo usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="2089d-164">A Lync user must configure Lync alerts to ensure that requests sent from a Skype user appear and are discoverable by the Lync user.</span></span> <span data-ttu-id="2089d-165">Para configurar alertas do Lync, conclua o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="2089d-165">To configure Lync alerts, complete the procedure that follows.</span></span>

<span data-ttu-id="2089d-166">**Para configurar alertas do Lync**</span><span class="sxs-lookup"><span data-stu-id="2089d-166">**To configure Lync Alerts**</span></span>

1.  <span data-ttu-id="2089d-167">No cliente Lync, clique no ícone **Opções** .</span><span class="sxs-lookup"><span data-stu-id="2089d-167">From the Lync client, click the **Options** icon.</span></span>

2.  <span data-ttu-id="2089d-168">Selecione **alertas**.</span><span class="sxs-lookup"><span data-stu-id="2089d-168">Select **Alerts**.</span></span>

3.  <span data-ttu-id="2089d-169">Em **alertas gerais**, confira avisar **quando alguém me adicionar à sua lista de contatos**.</span><span class="sxs-lookup"><span data-stu-id="2089d-169">Under **General alerts**, check **Tell me when someone adds me to his or her contact list**.</span></span>

4.  <span data-ttu-id="2089d-170">Em **contatos não usando o Lync**, selecione **permitir convites, mas bloquear todas as outras comunicações**.</span><span class="sxs-lookup"><span data-stu-id="2089d-170">Under **Contacts not using Lync**, select **Allow invites but block all other communications**.</span></span>

5.  <span data-ttu-id="2089d-171">Clique em **OK** para fechar a janela Opções.</span><span class="sxs-lookup"><span data-stu-id="2089d-171">Click **OK** to close the Options window.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

