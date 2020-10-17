---
title: 'Lync Server 2013: usando autenticação de dois fatores com o cliente Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a90dd3c40267f0994e7f41eabb689c869182cea7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508638"
---
# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="c80a1-102">Usando a autenticação de dois fatores com o Lync Client e o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c80a1-102">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c80a1-103">_**Última modificação do tópico:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="c80a1-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="c80a1-104">Este tópico descreveu como aproveitar a autenticação de dois fatores com o cliente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c80a1-104">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="c80a1-105">Entrar no Lync 2013 pela primeira vez</span><span class="sxs-lookup"><span data-stu-id="c80a1-105">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="c80a1-106">Suas informações de entrada do Lync geralmente são configuradas automaticamente quando o Lync 2013 é instalado.</span><span class="sxs-lookup"><span data-stu-id="c80a1-106">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="c80a1-107">Mas, na primeira vez que você usar o Lync, talvez seja necessário iniciar manualmente o cliente.</span><span class="sxs-lookup"><span data-stu-id="c80a1-107">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="c80a1-108">**Para entrar no Lync pela primeira vez**</span><span class="sxs-lookup"><span data-stu-id="c80a1-108">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="c80a1-109">Faça logon na rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c80a1-109">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="c80a1-110">Selecione **Iniciar** \> **todos os programas** \> **Microsoft Lync \> Lync 2013**.</span><span class="sxs-lookup"><span data-stu-id="c80a1-110">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="c80a1-111">Você deve ver a tela de entrada do Lync.</span><span class="sxs-lookup"><span data-stu-id="c80a1-111">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="c80a1-112">Se a caixa endereço de entrada já estiver preenchida, confirme se o endereço mostrado está correto.</span><span class="sxs-lookup"><span data-stu-id="c80a1-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="c80a1-113">Se ele não estiver correto, ou se a caixa estiver vazia, insira seu endereço de entrada do Lync (geralmente é o mesmo que seu endereço de email).</span><span class="sxs-lookup"><span data-stu-id="c80a1-113">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="c80a1-114">Se uma caixa de senha vazia for exibida, adicione sua senha.</span><span class="sxs-lookup"><span data-stu-id="c80a1-114">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="c80a1-115">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="c80a1-115">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="c80a1-116">Sair do Lync</span><span class="sxs-lookup"><span data-stu-id="c80a1-116">Sign out of Lync</span></span>

<span data-ttu-id="c80a1-117">Quando terminar de usar o Lync, você poderá fechar a exibição, sair da sessão ou sair do programa, tudo a partir do menu arquivo.</span><span class="sxs-lookup"><span data-stu-id="c80a1-117">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="c80a1-118">A tabela a seguir explica as diferenças nas opções.</span><span class="sxs-lookup"><span data-stu-id="c80a1-118">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c80a1-119">Opção</span><span class="sxs-lookup"><span data-stu-id="c80a1-119">Option</span></span></th>
<th><span data-ttu-id="c80a1-120">Função</span><span class="sxs-lookup"><span data-stu-id="c80a1-120">What it does</span></span></th>
<th><span data-ttu-id="c80a1-121">Como realizá-lo</span><span class="sxs-lookup"><span data-stu-id="c80a1-121">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c80a1-122">Fechar</span><span class="sxs-lookup"><span data-stu-id="c80a1-122">Close</span></span></p></td>
<td><p><span data-ttu-id="c80a1-123">Fecha a tela do Lync, mas permite que a sessão do Lync identificada com sua ID de usuário continue a ser executada.</span><span class="sxs-lookup"><span data-stu-id="c80a1-123">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="c80a1-124">Isso é feito para que você possa continuar a receber notificações e interagir com outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="c80a1-124">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="c80a1-125">Você pode obter novamente a exibição a qualquer momento clicando no ícone do Lync na barra de tarefas ou na área de notificação na parte inferior da tela.</span><span class="sxs-lookup"><span data-stu-id="c80a1-125">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="c80a1-126">Na janela principal do Lync, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="c80a1-126">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="c80a1-127">Selecione o botão <strong>Opções</strong> e, em seguida, selecione <strong>arquivo</strong> &gt; <strong>fechar</strong>.</span><span class="sxs-lookup"><span data-stu-id="c80a1-127">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="c80a1-128">Clique no botão <strong>fechar</strong> (X) no canto superior direito da janela.</span><span class="sxs-lookup"><span data-stu-id="c80a1-128">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c80a1-129">Sair</span><span class="sxs-lookup"><span data-stu-id="c80a1-129">Sign out</span></span></p></td>
<td><p><span data-ttu-id="c80a1-130">Encerra a sessão do Lync associada à sua ID de usuário, mas o Lync continua a ser executado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="c80a1-130">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="c80a1-131">Quando você sair, a janela de entrada será exibida.</span><span class="sxs-lookup"><span data-stu-id="c80a1-131">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="c80a1-132">Selecione <STRONG>excluir minhas informações de entrada</STRONG> ao sair para remover o registro de sua ID de logon e senha do computador.</span><span class="sxs-lookup"><span data-stu-id="c80a1-132">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="c80a1-133">Isso pode tornar mais fácil para as pessoas de suporte solucionar problemas de entrada.</span><span class="sxs-lookup"><span data-stu-id="c80a1-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="c80a1-134">Também pode ajudar a garantir que as informações de entrada sejam mais seguras, tornando difícil para os usuários não autorizados fazer logon com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="c80a1-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="c80a1-135">Na janela principal do Lync, selecione o botão <strong>Opções</strong> e, em seguida, selecione <strong>arquivo</strong> &gt; <strong>sair</strong>.</span><span class="sxs-lookup"><span data-stu-id="c80a1-135">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c80a1-136">Sair</span><span class="sxs-lookup"><span data-stu-id="c80a1-136">Exit</span></span></p></td>
<td><p><span data-ttu-id="c80a1-137">Encerra a sessão do Lync e desliga o Lync no seu computador.</span><span class="sxs-lookup"><span data-stu-id="c80a1-137">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="c80a1-138">Após sair, se você quiser reiniciar o Lync, selecione <strong>Iniciar</strong> &gt; <strong>todos os programas</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span><span class="sxs-lookup"><span data-stu-id="c80a1-138">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="c80a1-139">Na janela principal do Lync, selecione o botão <strong>Opções</strong> e, em seguida, selecione <strong>arquivo</strong> &gt; <strong>sair</strong>.</span><span class="sxs-lookup"><span data-stu-id="c80a1-139">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="c80a1-140">Entrar no Lync com um cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="c80a1-140">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="c80a1-141">Algumas organizações agora usam um processo de entrada em várias etapas, chamado de autenticação de dois fatores, para aumentar a segurança dos seus usuários do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="c80a1-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="c80a1-142">Se você espera usar essa opção, precisará de um "cartão inteligente" para entrar no Lync.</span><span class="sxs-lookup"><span data-stu-id="c80a1-142">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="c80a1-143">Os cartões inteligentes vêm em duas variedades, físico e virtual:</span><span class="sxs-lookup"><span data-stu-id="c80a1-143">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="c80a1-144">**Físico**     Sobre o tamanho de um cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="c80a1-144">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="c80a1-145">Você o insere em um leitor de cartão inteligente ao fazer logon.</span><span class="sxs-lookup"><span data-stu-id="c80a1-145">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="c80a1-146">**Virtual**     Não é um objeto físico, mas um identificador eletrônico que é gravado em um chip especial no computador, que, em essência, cria o cartão inteligente em seu computador.</span><span class="sxs-lookup"><span data-stu-id="c80a1-146">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="c80a1-147">Disponível somente para uso com computadores com Windows 8 que contenham o chip TPM (Trusted Platform Module).</span><span class="sxs-lookup"><span data-stu-id="c80a1-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="c80a1-148">Registrar seu cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="c80a1-148">Enroll your smart card</span></span>

<span data-ttu-id="c80a1-149">Para que você possa entrar com um cartão inteligente, o cartão deve ser "inscrito", ou seja, suas credenciais de usuário devem ser identificadas com o cartão.</span><span class="sxs-lookup"><span data-stu-id="c80a1-149">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="c80a1-150">Esse é o caso se o cartão for físico ou virtual.</span><span class="sxs-lookup"><span data-stu-id="c80a1-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="c80a1-151">Esse processo já pode ter sido realizado pelo administrador do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c80a1-151">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="c80a1-152">Verifique com eles se você não tiver certeza se isso foi feito.</span><span class="sxs-lookup"><span data-stu-id="c80a1-152">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c80a1-153">Como cada cartão inteligente virtual é associado apenas ao dispositivo em que ele está instalado, um cartão separado precisará ser inscrito para cada computador com o Windows 8 que você usa.</span><span class="sxs-lookup"><span data-stu-id="c80a1-153">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="c80a1-154">**Para registrar manualmente seu cartão inteligente**</span><span class="sxs-lookup"><span data-stu-id="c80a1-154">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="c80a1-155">Faça logon no computador em que você executará o Lync.</span><span class="sxs-lookup"><span data-stu-id="c80a1-155">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="c80a1-156">Usando o Internet Explorer, navegue até a página registro da Web da autoridade de certificação da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c80a1-156">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="c80a1-157">Pergunte ao administrador do Lync Server pelo endereço da Web desse recurso se você ainda não o tiver.</span><span class="sxs-lookup"><span data-stu-id="c80a1-157">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="c80a1-158">A URL se parecerá com esta: https://MyCA.\ [Yourcompanyname \] . com/certsrv.</span><span class="sxs-lookup"><span data-stu-id="c80a1-158">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c80a1-159">Se você estiver usando o Internet Explorer 10, talvez seja necessário exibir este site no modo de compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="c80a1-159">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="c80a1-160">Quando for solicitado a fazer logon na página de certificação, faça logon usando sua conta de domínio (em vez de como administrador do seu computador).</span><span class="sxs-lookup"><span data-stu-id="c80a1-160">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="c80a1-161">Na página de boas-vindas do site, selecione **solicitar um certificado**.</span><span class="sxs-lookup"><span data-stu-id="c80a1-161">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="c80a1-162">Selecione **solicitação avançada**.</span><span class="sxs-lookup"><span data-stu-id="c80a1-162">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="c80a1-163">Selecione **criar e enviar uma solicitação para esta autoridade de certificação**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c80a1-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="c80a1-164">Agora você verá uma página chamada Estação de registro de cartão inteligente.</span><span class="sxs-lookup"><span data-stu-id="c80a1-164">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="c80a1-165">Aprove a solicitação para instalar o controle ActiveX e preencha o formulário de solicitação de certificado avançado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c80a1-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="c80a1-166">Selecione **usuário de cartão inteligente** na lista suspensa **modelo de certificado** .</span><span class="sxs-lookup"><span data-stu-id="c80a1-166">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="c80a1-167">Selecione **criar novo conjunto de chaves**.</span><span class="sxs-lookup"><span data-stu-id="c80a1-167">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="c80a1-168">Encontre as informações do fabricante no rótulo do seu cartão inteligente e selecione o fabricante na lista suspensa **CSP** .</span><span class="sxs-lookup"><span data-stu-id="c80a1-168">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="c80a1-169">Selecione **CSP** como o formato de solicitação, se ainda não estiver selecionado.</span><span class="sxs-lookup"><span data-stu-id="c80a1-169">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="c80a1-170">Selecione **SHA1** na lista suspensa algoritmo de hash, se ainda não estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="c80a1-170">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="c80a1-171">Dê um nome ao seu certificado, que você reconhecerá e clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="c80a1-171">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="c80a1-172">Agora insira o cartão inteligente em branco no leitor de cartão anexado à estação de registro e clique em **registrar**.</span><span class="sxs-lookup"><span data-stu-id="c80a1-172">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="c80a1-173">Quando solicitado, insira seu número de identificação pessoal (PIN) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c80a1-173">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c80a1-174">Se sua pessoa de suporte técnico não tiver dado a você um PIN especial a ser usado para registrar seu cartão inteligente, use o valor padrão de PIN do cartão inteligente, que é 12345678.</span><span class="sxs-lookup"><span data-stu-id="c80a1-174">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="c80a1-175">Selecione a opção para forçar o usuário (você) a alterar o PIN na primeira vez que o cartão inteligente for usado.</span><span class="sxs-lookup"><span data-stu-id="c80a1-175">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="c80a1-176">Agora insira o cartão inteligente em branco no leitor de cartão anexado à estação de registro e clique em **registrar**.</span><span class="sxs-lookup"><span data-stu-id="c80a1-176">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="c80a1-177">Quando solicitado, insira seu número de identificação pessoal (PIN) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c80a1-177">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c80a1-178">Se sua pessoa de suporte técnico não tiver dado a você um PIN especial a ser usado para registrar seu cartão inteligente, use o valor padrão de PIN do cartão inteligente, que é 12345678.</span><span class="sxs-lookup"><span data-stu-id="c80a1-178">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="c80a1-179">Selecione a opção para forçar o usuário (você) a alterar o PIN na primeira vez que o cartão inteligente for usado.</span><span class="sxs-lookup"><span data-stu-id="c80a1-179">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="c80a1-180">Clique em **OK** para confirmar que o certificado exibido tem suas informações nele.</span><span class="sxs-lookup"><span data-stu-id="c80a1-180">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="c80a1-181">Após ver o aviso de que o certificado foi emitido, clique em **instalar este certificado** para concluir o processo de registro.</span><span class="sxs-lookup"><span data-stu-id="c80a1-181">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="c80a1-182">Entrar no Lync com suas credenciais de cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="c80a1-182">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="c80a1-183">Antes de usar o cartão inteligente pela primeira vez, é recomendável clicar em **excluir minhas informações de entrada** na página de entrada do Lync.</span><span class="sxs-lookup"><span data-stu-id="c80a1-183">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="c80a1-184">Isso limpa as credenciais de entrada armazenadas no computador e elimina uma possível fonte de erro.</span><span class="sxs-lookup"><span data-stu-id="c80a1-184">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="c80a1-185">**Para entrar no Lync com suas credenciais de cartão inteligente**</span><span class="sxs-lookup"><span data-stu-id="c80a1-185">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="c80a1-186">Inicie o cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="c80a1-186">Start the Lync client.</span></span>

2.  <span data-ttu-id="c80a1-187">Na tela de entrada, digite o nome da conta de usuário de entrada na caixa **endereço de entrada** e clique em **entrar**.</span><span class="sxs-lookup"><span data-stu-id="c80a1-187">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="c80a1-188">Se você estiver usando um cartão inteligente virtual, pule esta etapa.</span><span class="sxs-lookup"><span data-stu-id="c80a1-188">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="c80a1-189">Se você estiver usando um cartão inteligente físico, insira o cartão inteligente no leitor de cartão inteligente e, em seguida, clique em **OK** quando o cartão for detectado.</span><span class="sxs-lookup"><span data-stu-id="c80a1-189">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="c80a1-190">Digite o número PIN do cartão inteligente e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c80a1-190">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c80a1-191">Se você não recebeu um número PIN de cartão inteligente pelo pessoal de suporte, use o valor padrão, que é 12345678.</span><span class="sxs-lookup"><span data-stu-id="c80a1-191">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

