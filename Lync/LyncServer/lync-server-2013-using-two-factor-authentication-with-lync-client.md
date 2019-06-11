---
title: 'Lync Server 2013: usando a autenticação de dois fatores com o cliente Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5af9e9b5268fd218bfe5856473124514cfe34945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="d3a38-102">Usando a autenticação de dois fatores com o Lync Client e o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3a38-102">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3a38-103">_**Tópico da última modificação:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="d3a38-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="d3a38-104">Este tópico descreveu como tirar proveito da autenticação de dois fatores com o cliente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d3a38-104">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="d3a38-105">Entrar no Lync 2013 pela primeira vez</span><span class="sxs-lookup"><span data-stu-id="d3a38-105">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="d3a38-106">Suas informações de entrada do Lync geralmente são configuradas automaticamente quando o Lync 2013 está instalado.</span><span class="sxs-lookup"><span data-stu-id="d3a38-106">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="d3a38-107">Mas, na primeira vez que você usar o Lync, talvez seja necessário iniciar manualmente o cliente.</span><span class="sxs-lookup"><span data-stu-id="d3a38-107">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="d3a38-108">**Para entrar no Lync pela primeira vez**</span><span class="sxs-lookup"><span data-stu-id="d3a38-108">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="d3a38-109">Faça logon na rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d3a38-109">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="d3a38-110">Selecione **Iniciar** \> **todos os programas** \> **Microsoft \> Lync Lync 2013**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-110">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="d3a38-111">Você verá a tela de entrada do Lync.</span><span class="sxs-lookup"><span data-stu-id="d3a38-111">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="d3a38-112">Se a caixa de endereço de entrada já estiver preenchida, confirme se o endereço mostrado está correto.</span><span class="sxs-lookup"><span data-stu-id="d3a38-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="d3a38-113">Se não estiver correto ou se a caixa estiver vazia, insira seu endereço de entrada do Lync (geralmente é o mesmo que o seu endereço de email).</span><span class="sxs-lookup"><span data-stu-id="d3a38-113">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="d3a38-114">Se uma caixa de senha vazia for exibida, adicione sua senha.</span><span class="sxs-lookup"><span data-stu-id="d3a38-114">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="d3a38-115">Selecione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-115">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="d3a38-116">Sair do Lync</span><span class="sxs-lookup"><span data-stu-id="d3a38-116">Sign out of Lync</span></span>

<span data-ttu-id="d3a38-117">Quando terminar de usar o Lync, você pode fechar a exibição, sair da sessão ou sair do programa, tudo a partir do menu arquivo.</span><span class="sxs-lookup"><span data-stu-id="d3a38-117">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="d3a38-118">A tabela a seguir explica as diferenças nas opções.</span><span class="sxs-lookup"><span data-stu-id="d3a38-118">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3a38-119">Opção</span><span class="sxs-lookup"><span data-stu-id="d3a38-119">Option</span></span></th>
<th><span data-ttu-id="d3a38-120">O que ela faz</span><span class="sxs-lookup"><span data-stu-id="d3a38-120">What it does</span></span></th>
<th><span data-ttu-id="d3a38-121">Como executar</span><span class="sxs-lookup"><span data-stu-id="d3a38-121">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3a38-122">Fechar</span><span class="sxs-lookup"><span data-stu-id="d3a38-122">Close</span></span></p></td>
<td><p><span data-ttu-id="d3a38-123">Fecha a exibição do Lync, mas permite que a sessão do Lync identificada com sua ID de usuário continue sendo executada.</span><span class="sxs-lookup"><span data-stu-id="d3a38-123">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="d3a38-124">Isso acontece para que você possa continuar a obter notificações e a interagir com outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="d3a38-124">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="d3a38-125">Você pode retomar a exibição a qualquer momento clicando no ícone do Lync na barra de tarefas ou na área de notificação na parte inferior da tela.</span><span class="sxs-lookup"><span data-stu-id="d3a38-125">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="d3a38-126">Na janela principal do Lync, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="d3a38-126">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="d3a38-127">Selecione o botão <strong>Opções</strong> e, em seguida, selecione <strong>arquivo</strong> &gt; <strong>fechar</strong>.</span><span class="sxs-lookup"><span data-stu-id="d3a38-127">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="d3a38-128">Clique no botão <strong>Fechar</strong> (X) no canto superior direito da janela.</span><span class="sxs-lookup"><span data-stu-id="d3a38-128">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3a38-129">Sair</span><span class="sxs-lookup"><span data-stu-id="d3a38-129">Sign out</span></span></p></td>
<td><p><span data-ttu-id="d3a38-130">Finaliza a sessão do Lync associada à sua ID de usuário, mas o Lync continua a ser executado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="d3a38-130">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="d3a38-131">Quando você sair, a janela de entrada aparecerá.</span><span class="sxs-lookup"><span data-stu-id="d3a38-131">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="d3a38-p105">Selecione <STRONG>Excluir minhas informações de entrada</STRONG> ao sair para remover o registro de sua ID de logon e da senha do computador. Fazer isso torna mais fácil para o pessoal de suporte solucionar problemas de entrada. Também ajuda a garantir que suas informações de entrada fiquem mais seguras ao dificultar que usuários não autorizados façam logon com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="d3a38-p105">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer. Doing this might make it easier for support people to troubleshoot sign-in issues. It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="d3a38-135">Na janela principal do Lync, selecione o botão <strong>Opções</strong> e, em seguida, selecione <strong>arquivo</strong> &gt; <strong>sair</strong>.</span><span class="sxs-lookup"><span data-stu-id="d3a38-135">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3a38-136">Fechar</span><span class="sxs-lookup"><span data-stu-id="d3a38-136">Exit</span></span></p></td>
<td><p><span data-ttu-id="d3a38-137">Encerra a sessão do Lync e desliga o Lync em seu computador.</span><span class="sxs-lookup"><span data-stu-id="d3a38-137">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="d3a38-138">Depois de sair, se você quiser reiniciar o Lync, selecione <strong>Iniciar</strong> &gt; <strong>todos os programas</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span><span class="sxs-lookup"><span data-stu-id="d3a38-138">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="d3a38-139">Na janela principal do Lync, selecione o botão <strong>Opções</strong> e, em seguida, selecione <strong>arquivo</strong> &gt; <strong>sair</strong>.</span><span class="sxs-lookup"><span data-stu-id="d3a38-139">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="d3a38-140">Entrar no Lync com um cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="d3a38-140">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="d3a38-141">Algumas organizações agora usam um processo de entrada em várias etapas, chamado de autenticação de dois fatores, para aumentar a segurança dos usuários do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d3a38-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="d3a38-142">Se você espera usar esta opção, precisará de um "cartão inteligente" para entrar no Lync.</span><span class="sxs-lookup"><span data-stu-id="d3a38-142">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="d3a38-143">Os cartões inteligentes vêm em duas variedades, físicas e virtuais:</span><span class="sxs-lookup"><span data-stu-id="d3a38-143">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="d3a38-144">**Físico**   sobre o tamanho de um cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="d3a38-144">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="d3a38-145">Você o insere em um leitor de cartão inteligente ao fazer logon.</span><span class="sxs-lookup"><span data-stu-id="d3a38-145">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="d3a38-146">**Virtual**   não é um objeto físico, mas um identificador eletrônico que é escrito para um chip especial em seu computador, que, em essência, cria o cartão inteligente no seu computador.</span><span class="sxs-lookup"><span data-stu-id="d3a38-146">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="d3a38-147">Disponível somente para uso com computadores com Windows 8 que contenham o chip TPM (Trusted Platform Module).</span><span class="sxs-lookup"><span data-stu-id="d3a38-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="d3a38-148">Registrar seu cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="d3a38-148">Enroll your smart card</span></span>

<span data-ttu-id="d3a38-149">Antes que seja possível entrar com um cartão inteligente, o cartão deverá ser "registrado" — ou seja, suas credenciais devem ser identificadas com o cartão.</span><span class="sxs-lookup"><span data-stu-id="d3a38-149">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="d3a38-150">Esse será o caso seja o cartão físico ou virtual.</span><span class="sxs-lookup"><span data-stu-id="d3a38-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="d3a38-151">Esse processo já pode ser realizado pelo administrador do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3a38-151">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="d3a38-152">Verifique com ele se não tiver certeza se isso foi feito.</span><span class="sxs-lookup"><span data-stu-id="d3a38-152">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d3a38-153">Como cada cartão inteligente virtual está associado somente ao dispositivo em que ele está instalado, um cartão separado precisará ser registrado para cada computador com o Windows 8 que você usar.</span><span class="sxs-lookup"><span data-stu-id="d3a38-153">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="d3a38-154">**Para registrar manualmente seu cartão inteligente**</span><span class="sxs-lookup"><span data-stu-id="d3a38-154">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="d3a38-155">Faça logon no computador em que você está executando o Lync.</span><span class="sxs-lookup"><span data-stu-id="d3a38-155">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="d3a38-156">Usando o Internet Explorer, navegue até a página de Registro da Autoridade de Certificação da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d3a38-156">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="d3a38-157">Pergunte ao administrador do Lync Server o endereço Web desse recurso, se ainda não o tiver.</span><span class="sxs-lookup"><span data-stu-id="d3a38-157">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="d3a38-158">A URL terá a seguinte aparência: https://MyCA.\[nomedesuaempresa\]. com/certsrv.</span><span class="sxs-lookup"><span data-stu-id="d3a38-158">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d3a38-159">Se você estiver usando o Internet Explorer 10, talvez precise exibir o site em Modo de Compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="d3a38-159">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="d3a38-160">Quando solicitado a fazer logon na página de certificação, faça logon usando sua conta de domínio (em vez do administrador do seu computador).</span><span class="sxs-lookup"><span data-stu-id="d3a38-160">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="d3a38-161">Na página de Boas-vindas do site, selecione **Solicitar um certificado**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-161">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="d3a38-162">Selecione **Solicitação Avançada**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-162">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="d3a38-163">Selecione **Criar e enviar uma solicitação para esta CA** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="d3a38-164">Agora você verá uma página chamada Estação de Registro de Cartão Inteligente.</span><span class="sxs-lookup"><span data-stu-id="d3a38-164">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="d3a38-165">Aprove a solicitação para instalar o controle ActiveX e então preencha o formulário Solicitação de Certificado Avançado desta forma:</span><span class="sxs-lookup"><span data-stu-id="d3a38-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="d3a38-166">Selecione **Usuário de cartão inteligente** na lista suspensa **Modelo de Certificado**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-166">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="d3a38-167">Selecione **Criar novo conjunto de chaves**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-167">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="d3a38-168">Localize as informações do fabricante no rótulo do seu cartão inteligente e selecione esse fabricante na lista suspensa **CSP**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-168">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="d3a38-169">Selecione **CSP** como o Formato de Solicitação, caso ainda não esteja selecionado.</span><span class="sxs-lookup"><span data-stu-id="d3a38-169">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="d3a38-170">Selecione **sha1** na lista suspensa Algoritmo de Hash, caso ainda não tenha sido selecionado.</span><span class="sxs-lookup"><span data-stu-id="d3a38-170">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="d3a38-171">Dê um nome ao seu certificado que seja fácil de reconhecer e clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-171">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="d3a38-172">Agora insira seu cartão inteligente em branco no leitor de cartão conectado à estação de registro e clique em **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-172">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="d3a38-173">Quando solicitado, insira seu número de identificação pessoal (PIN) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-173">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d3a38-174">Se o encarregado do suporte técnico não tiver dado um PIN para você registrar seu cartão inteligente, use o valor padrão de PIN de cartão inteligente, 12345678.</span><span class="sxs-lookup"><span data-stu-id="d3a38-174">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="d3a38-175">Selecione a opção para forçar o usuário (você) a alterar o PIN na primeira vez em que o cartão inteligente for usado.</span><span class="sxs-lookup"><span data-stu-id="d3a38-175">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="d3a38-176">Agora insira seu cartão inteligente em branco no leitor de cartão conectado à estação de registro e clique em **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-176">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="d3a38-177">Quando solicitado, insira seu número de identificação pessoal (PIN) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-177">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d3a38-178">Se o encarregado do suporte técnico não tiver dado um PIN para você registrar seu cartão inteligente, use o valor padrão de PIN de cartão inteligente, 12345678.</span><span class="sxs-lookup"><span data-stu-id="d3a38-178">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="d3a38-179">Selecione a opção para forçar o usuário (você) a alterar o PIN na primeira vez em que o cartão inteligente for usado.</span><span class="sxs-lookup"><span data-stu-id="d3a38-179">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="d3a38-180">Clique em **OK** para confirmar se o certificado exibido tem suas informações neles.</span><span class="sxs-lookup"><span data-stu-id="d3a38-180">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="d3a38-181">Assim que for exibido o aviso de que o certificado foi emitido, clique em **Instalar este certificado** para concluir o processo de registro.</span><span class="sxs-lookup"><span data-stu-id="d3a38-181">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="d3a38-182">Entre no Lync com as credenciais do seu cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="d3a38-182">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="d3a38-183">Antes de usar o cartão inteligente pela primeira vez, é recomendável clicar em **excluir minhas informações de entrada** na página de entrada do Lync.</span><span class="sxs-lookup"><span data-stu-id="d3a38-183">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="d3a38-184">Fazer isso limpará qualquer credencial de entrada armazenada no computador e eliminará uma possível origem de erros.</span><span class="sxs-lookup"><span data-stu-id="d3a38-184">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="d3a38-185">**Para entrar no Lync com as credenciais do seu cartão inteligente**</span><span class="sxs-lookup"><span data-stu-id="d3a38-185">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="d3a38-186">Inicie o cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="d3a38-186">Start the Lync client.</span></span>

2.  <span data-ttu-id="d3a38-187">Na tela Entrar, digite seu nome de conta de usuário na caixa **Endereço de entrada** e clique em **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-187">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="d3a38-188">Se você estiver usando um cartão inteligente virtual, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="d3a38-188">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="d3a38-189">Se estiver usando um cartão inteligente físico, insira o cartão inteligente no leitor de cartão inteligente quando solicitado e então clique em **OK** quando o cartão for detectado.</span><span class="sxs-lookup"><span data-stu-id="d3a38-189">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="d3a38-190">Digite o número PIN do seu cartão inteligente e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3a38-190">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d3a38-191">Se você não tiver recebido um número PIN de cartão inteligente do pessoal de suporte, use o valor padrão, que é 12345678.</span><span class="sxs-lookup"><span data-stu-id="d3a38-191">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

