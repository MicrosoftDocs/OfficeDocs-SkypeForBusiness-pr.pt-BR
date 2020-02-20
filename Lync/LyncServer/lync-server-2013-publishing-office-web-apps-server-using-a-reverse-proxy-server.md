---
title: Publicar o servidor do Office Web Apps usando um servidor de proxy reverso
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
ms.openlocfilehash: 6964c111fa6ca7225c25884c52d02564314ececf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="d65e8-102">Publicar o servidor do Office Web Apps no Lync Server 2013 usando um servidor de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="d65e8-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d65e8-103">_**Última modificação do tópico:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="d65e8-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="d65e8-104">Se você quiser que os usuários externos (ou seja, usuários que estão fazendo logon de fora do firewall de sua organização) tenha acesso às apresentações do Office Web Apps Server PowerPoint, será necessário usar o Office Web Apps Server e um servidor de proxy reverso como o Microsoft Forefront Threat Management Gateway.</span><span class="sxs-lookup"><span data-stu-id="d65e8-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="d65e8-105">Isso também significa que você precisará criar e configurar uma regra de publicação de site; Essa regra ajudará a garantir que os usuários possam se conectar ao servidor.</span><span class="sxs-lookup"><span data-stu-id="d65e8-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="d65e8-106">Se não for necessário fornecer acesso aos usuários externos, não será necessário configurar uma regra de publicação de site.</span><span class="sxs-lookup"><span data-stu-id="d65e8-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="d65e8-107">Para configurar uma regra de publicação de site no Forefront Threat Management Gateway complete o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="d65e8-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="d65e8-108">Clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Forefront TMG** e em **Gerenciamento do Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="d65e8-109">No Forefront TMG, clique com o botão direito do mouse em **Política de Firewall**, aponte para **Novo** e clique em **Regra de Publicação de Site**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="d65e8-110">No Assistente de Nova Regra de Publicação na Web, na página **Bem-vindo ao Assistente de Nova Regra de Publicação na Web**, digite um nome para sua nova regra na caixa **Nome da regra de publicação na Web** (por exemplo, **Regra do Office Web Apps Server**) e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="d65e8-111">Na página **Especificar Ação de Regra**, selecione **Permitir** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="d65e8-112">Na página **Tipo de Publicação**, selecione **Publicar um único site ou balanceador de carga** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="d65e8-113">Na página **Segurança da Conexão do Servidor**, selecione **Usar SSL para se conectar ao servidor Web ou farm de servidores publicado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="d65e8-p102">Na página **Detalhes de Publicação Interna**, digite o FQDN de seu servidor Office Web Apps (por exemplo, **officewebapps01.contoso.com**) na caixa **Nome de site interno** e clique em **Avançar**. O nome digitado na caixa **Nome do site interno** precisa aparecer no campo Assunto ou no campo Nome Alternativo da Entidade do certificado atribuído ao Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="d65e8-p102">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**. The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="d65e8-116">Na página **detalhes de publicação interna** , digite \*\* / \*\* na caixa **caminho (opcional)** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="d65e8-117">A sintaxe\* /ajudará a garantir que todas as pastas e subpastas do site sejam publicadas.</span><span class="sxs-lookup"><span data-stu-id="d65e8-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="d65e8-118">Na página **Detalhes do Nome Público**, selecione **Este nome de domínio (digite abaixo)** na lista suspensa **Aceitar solicitações para** e digite o nome de domínio totalmente qualificado de seu Office Web Apps Server na caixa Nome público.</span><span class="sxs-lookup"><span data-stu-id="d65e8-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="d65e8-119">Esse nome deve ser o nome usado para acessar seu site.</span><span class="sxs-lookup"><span data-stu-id="d65e8-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="d65e8-120">Por exemplo, se o seu site é acessado http://officewebapps01.contoso.com usando a URL, você deve inserir **officewebapps01.contoso.com** na caixa **nome público** .</span><span class="sxs-lookup"><span data-stu-id="d65e8-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="d65e8-121">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-121">Click **Next**.</span></span>

11. <span data-ttu-id="d65e8-122">Na página **Selecionar Ouvinte da Web**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="d65e8-123">No Assistente de Definição de Novo Ouvinte da Web, digite um nome para o novo ouvinte da Web (por exemplo, **SSL**) na caixa **Nome do ouvinte da Web** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="d65e8-124">Na página **Segurança de Conexão do Cliente**, selecione **Exigir conexões SSL seguras com clientes** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="d65e8-125">Na página **Endereço IP do Ouvinte da Web**, selecione **Externo**, selecione **Interno** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="d65e8-126">Na página **Certificados SSL do Ouvinte**, selecione **Usar um único certificado para este Ouvinte da Web** e clique em **Selecionar Certificado**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="d65e8-127">Na caixa de diálogo **Selecionar Certificado**, selecione o certificado a ser usado para esse Ouvinte da Web e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="d65e8-128">Na página **Certificados SSL do Ouvinte**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="d65e8-129">Na página **Configurações de Autenticação**, selecione **Sem Autenticação** na lista suspensa **Selecionar como os clientes fornecerão credenciais para o Forefront TMG** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="d65e8-130">Na página **Configurações de Logon Único**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="d65e8-p105">Na página **Concluindo o Assistente de Novo Ouvinte da Web**, revise o resumo das opções de configuração feitas. Quando estiver pronto, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-p105">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made. When ready, click **Finish**.</span></span>

21. <span data-ttu-id="d65e8-133">Na página **Selecionar Ouvinte da Web**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="d65e8-134">Na página **Delegação de Autenticação**, selecione **Nenhuma delegação, mas o cliente pode autenticar diretamente** na lista suspensa **Selecionar o método usado pelo Forefront TMG para autenticar para o servidor Web publicado** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="d65e8-p106">Na página **Conjuntos de Usuários**, confirme se os conjuntos de usuário apropriados estão listados. Por padrão, esse é o conjunto de usuários **Todos os Usuários**. Clique em **Adicionar** para adicionar outros conjuntos de usuário que você possa ter definido. Após a conclusão, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-p106">On the **User Sets** page, confirm that the appropriate user sets are listed. By default, this is the **All Users** user set. Click **Add** to add other user sets you may have defined. When complete, click **Next**.</span></span>

24. <span data-ttu-id="d65e8-139">Na página **Concluindo o Assistente de Nova Regra de Publicação**, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="d65e8-p107">Observe que clicar em **Concluir** não significa que você concluiu o processo; ou seja, isso não aplica e habilita automaticamente a nova regra. Em vez disso, será necessário clicar no botão **Aplicar** que aparecerá na interface de usuário do Forefront TMG. Ao clicar em **Aplicar** a caixa de diálogo **Descrição da Alteração de Configuração** aparecerá. Clique em **Aplicar** nessa caixa de diálogo para habilitar a nova regra de publicação.</span><span class="sxs-lookup"><span data-stu-id="d65e8-p107">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule. Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface. When you click **Apply** the **Configuration Change Description** dialog box will appear. Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="d65e8-144">Após a aplicação da nova regra, será necessário fazer algumas pequenas modificações na regra para garantir que os usuários possam usar os novos recursos de apresentação do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="d65e8-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="d65e8-145">Para fazer isso, complete o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="d65e8-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="d65e8-146">No Forefront TMG, clique com o botão direito do mouse no nome da nova regra de publicação e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="d65e8-147">Na caixa de diálogo **Propriedades**, na guia **Para**, selecione a opção **Encaminhar o cabeçalho de host original em vez do presente**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="d65e8-148">Na guia **Tráfego**, clique em **Filtragem** e clique em **Configurar HTTP**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="d65e8-149">Na caixa de diálogo **Configurando a política HTTP para regra**, desmarque a caixa de seleção **Verificar normalização** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="d65e8-150">Na caixa de diálogo **Propriedades**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="d65e8-p109">No Forefront TMG, clique em **Aplicar** para habilitar as alterações. quando a caixa de diálogo **Descrição da Alteração de Configuração** aparecer, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="d65e8-p109">In Forefront TMG, click **Apply** to enable the changes. When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="d65e8-153">Após concluir a instalação, você pode testar o servidor do Office Web Apps usando os procedimentos no tópico [validando a configuração do servidor do Office Web Apps no Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span><span class="sxs-lookup"><span data-stu-id="d65e8-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

