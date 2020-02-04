---
title: Publicando o servidor do Office Web Apps usando um servidor de proxy reverso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a81fff75adbeadb6cfcead3316dab2c89b4269
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="f0a65-102">Publicando o servidor do Office Web Apps no Lync Server 2013 usando um servidor proxy reverso</span><span class="sxs-lookup"><span data-stu-id="f0a65-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0a65-103">_**Tópico da última modificação:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="f0a65-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="f0a65-104">Se você quiser que os usuários externos (ou seja, os usuários que estão fazendo logon fora do firewall da sua organização) tenham acesso às apresentações do PowerPoint para servidor Web Apps do Office, será necessário usar o Office Web Apps Server e um servidor proxy reverso, como o Microsoft Forefront Gateway de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="f0a65-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="f0a65-105">Isso também significa que você vai precisar criar e configurar uma regra de publicação de site; Essa regra ajudará a garantir que os usuários possam se conectar ao servidor.</span><span class="sxs-lookup"><span data-stu-id="f0a65-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="f0a65-106">Se você não precisar fornecer acesso a usuários externos, não será necessário configurar uma regra de publicação de site.</span><span class="sxs-lookup"><span data-stu-id="f0a65-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="f0a65-107">Para configurar uma regra de publicação de site no Forefront Threat Management Gateway, conclua o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="f0a65-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="f0a65-108">Clique em **Iniciar**, em **todos os programas**, em **Microsoft Forefront TMG**e, em seguida, clique em gerenciamento do **Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="f0a65-109">No Forefront TMG, clique com o botão direito do mouse em **política de firewall**, aponte para **novo**e clique em regra de **publicação de site da Web**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="f0a65-110">No Assistente para nova regra de publicação na Web, na página **Bem-vindo ao novo assistente de regra de publicação na Web** , digite um nome para a nova regra na caixa **nome da regra de publicação na Web** (por exemplo, regra do servidor do **Office Web Apps**) e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="f0a65-111">Na página **especificar ação da regra** , selecione **permitir** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="f0a65-112">Na página **tipo de publicação** , selecione **publicar um único site ou balanceador de carga** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="f0a65-113">Na página **segurança de conexão do servidor** , selecione **usar SSL para se conectar ao servidor Web ou ao farm de servidores publicados** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="f0a65-114">Na página **detalhes da publicação interna** , digite o FQDN do servidor do Office Web Apps (por exemplo, **officewebapps01.contoso.com**) na caixa **nome do site interno** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-114">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**.</span></span> <span data-ttu-id="f0a65-115">O nome inserido na caixa **nome do site interno** deve aparecer no campo assunto ou no campo nome alternativo do assunto do certificado que você atribuiu ao servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="f0a65-115">The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="f0a65-116">Na página **detalhes da publicação interna** , digite \*\* / \*\* na caixa **caminho (opcional)** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="f0a65-117">A sintaxe\* /irá ajudar a garantir que todas as pastas e subpastas do site sejam publicadas.</span><span class="sxs-lookup"><span data-stu-id="f0a65-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="f0a65-118">Na página de **detalhes do nome público** , selecione **este nome de domínio (Digite abaixo)** na lista de **aceitar solicitações para** e digite o totalmente qualificado para o servidor do Office Web Apps na caixa nome público.</span><span class="sxs-lookup"><span data-stu-id="f0a65-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="f0a65-119">Esse nome deve ser o nome usado para acessar seu site.</span><span class="sxs-lookup"><span data-stu-id="f0a65-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="f0a65-120">Por exemplo, se o seu site for acessado http://officewebapps01.contoso.com usando a URL, você deverá digitar **officewebapps01.contoso.com** na caixa **nome público** .</span><span class="sxs-lookup"><span data-stu-id="f0a65-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="f0a65-121">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-121">Click **Next**.</span></span>

11. <span data-ttu-id="f0a65-122">Na página **selecionar ouvinte da Web** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="f0a65-123">No assistente de definição novo ouvinte da Web, digite um nome para o novo ouvinte da Web (por exemplo, **SSL**) na caixa **nome do ouvinte da Web** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="f0a65-124">Na página **segurança de conexão do cliente** , selecione **exigir conexões SSL seguras com clientes** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="f0a65-125">Na página **endereços IP do ouvinte da Web** , selecione **externo**, selecione **interno**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="f0a65-126">Na página **certificados SSL de ouvinte** , selecione **usar um único certificado para este ouvinte da Web** e clique em **Selecionar certificado**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="f0a65-127">Na caixa de diálogo **Selecionar certificado** , selecione o certificado a ser usado para este ouvinte da Web e clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="f0a65-128">Na página **certificados SSL de ouvinte** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="f0a65-129">Na página **configurações de autenticação** , selecione **sem autenticação** na lista suspensa **selecionar como os clientes fornecerão credenciais para a** lista suspensa do Forefront TMG e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="f0a65-130">Na página **configurações de logon único** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="f0a65-131">Na página **concluindo o assistente de Nova escuta da Web** , examine o resumo das opções de configuração que você fez.</span><span class="sxs-lookup"><span data-stu-id="f0a65-131">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made.</span></span> <span data-ttu-id="f0a65-132">Quando estiver pronto, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-132">When ready, click **Finish**.</span></span>

21. <span data-ttu-id="f0a65-133">Na página **selecionar ouvinte da Web** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="f0a65-134">Na página **delegação de autenticação** , selecione **sem delegação, mas o cliente pode autenticar diretamente** da **seleção do método usado pelo Forefront TMG para autenticação na lista suspensa do servidor Web publicado** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="f0a65-135">Na página **conjuntos de usuários** , confirme se os conjuntos de usuários apropriados estão listados.</span><span class="sxs-lookup"><span data-stu-id="f0a65-135">On the **User Sets** page, confirm that the appropriate user sets are listed.</span></span> <span data-ttu-id="f0a65-136">Por padrão, esse é o conjunto de **usuários todos os usuários** .</span><span class="sxs-lookup"><span data-stu-id="f0a65-136">By default, this is the **All Users** user set.</span></span> <span data-ttu-id="f0a65-137">Clique em **Adicionar** para adicionar outros conjuntos de usuários que você tenha definido.</span><span class="sxs-lookup"><span data-stu-id="f0a65-137">Click **Add** to add other user sets you may have defined.</span></span> <span data-ttu-id="f0a65-138">Quando concluir, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-138">When complete, click **Next**.</span></span>

24. <span data-ttu-id="f0a65-139">Na página **concluindo o assistente de nova regra de publicação na Web** , clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="f0a65-140">Observe que clicar em **concluir** não significa que você concluiu o processo; Isto é, isso não aplica e habilita automaticamente a nova regra.</span><span class="sxs-lookup"><span data-stu-id="f0a65-140">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule.</span></span> <span data-ttu-id="f0a65-141">Em vez disso, você precisará clicar no botão **aplicar** que será exibido na interface do usuário do Forefront TMG.</span><span class="sxs-lookup"><span data-stu-id="f0a65-141">Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface.</span></span> <span data-ttu-id="f0a65-142">Quando você clica em **aplicar** a caixa de diálogo **Descrição da alteração de configuração** será exibida.</span><span class="sxs-lookup"><span data-stu-id="f0a65-142">When you click **Apply** the **Configuration Change Description** dialog box will appear.</span></span> <span data-ttu-id="f0a65-143">Clique em **aplicar** nessa caixa de diálogo para habilitar a nova regra de publicação.</span><span class="sxs-lookup"><span data-stu-id="f0a65-143">Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="f0a65-144">Após a aplicação da nova regra, você precisará fazer algumas pequenas modificações na regra para garantir que os usuários possam usar os novos recursos de apresentação do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="f0a65-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="f0a65-145">Para fazer isso, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="f0a65-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="f0a65-146">No Forefront TMG, clique com o botão direito do mouse no nome da nova regra de publicação e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="f0a65-147">Na caixa de diálogo **Propriedades** , na guia **para** , selecione a opção **encaminhar o cabeçalho original do host, em vez do verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="f0a65-148">Na guia **tráfego** , clique em **filtragem** e, em seguida, clique em **Configurar http**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="f0a65-149">Na caixa de diálogo **Configurando a política http para a regra** , desmarque a caixa de seleção **verificar normalização** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="f0a65-150">Na caixa de diálogo **Propriedades** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="f0a65-151">No Forefront TMG, clique em **aplicar** para habilitar as alterações.</span><span class="sxs-lookup"><span data-stu-id="f0a65-151">In Forefront TMG, click **Apply** to enable the changes.</span></span> <span data-ttu-id="f0a65-152">Quando a caixa de diálogo **Descrição da alteração de configuração** for exibida, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="f0a65-152">When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="f0a65-153">Depois de concluir a instalação, você pode testar o servidor do Office Web Apps usando os procedimentos no tópico [validando a configuração do servidor do Office Web Apps no Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span><span class="sxs-lookup"><span data-stu-id="f0a65-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

