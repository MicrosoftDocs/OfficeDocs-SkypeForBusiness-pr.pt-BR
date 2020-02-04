---
title: 'Lync Server 2013: Configurando um proxy inverso para descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a02bf765941c7240f08fecc91d5912f31a0f2f87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="c0545-102">Configurando um proxy inverso para descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0545-102">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0545-103">_**Tópico da última modificação:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="c0545-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="c0545-104">A descoberta automática e o suporte de clientes que usam a descoberta automática exigem a modificação de uma regra de publicação na Web existente ou a criação de uma nova regra de publicação na Web para o proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="c0545-104">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="c0545-105">A modificação ou criação de uma nova regra de publicação não depende da decisão de atualizar ou não atualizar as listas de nomes alternativos de entidades nos certificados de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="c0545-105">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="c0545-106">Se você decidir usar HTTPS para solicitações iniciais de serviço de descoberta automática do Lync Server 2013 e atualizar as listas de nomes alternativos de entidades nos certificados de proxy reverso, será necessário atribuir o certificado público atualizado ao ouvinte SSL (Secure Sockets Layer) em seu proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="c0545-106">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="c0545-107">A atualização necessária para o certificado externo (público) incluirá a entrada de nome alternativo (SAN) do assunto para lyncdiscover. \<nome\>do domínio.</span><span class="sxs-lookup"><span data-stu-id="c0545-107">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="c0545-108">Em seguida, você precisará modificar o ouvinte existente para os serviços Web externos ou criar uma nova regra de publicação na Web para a URL do serviço de descoberta automática externa, por exemplo, **lyncdiscover.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="c0545-108">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="c0545-109">Se você ainda não tiver uma regra de publicação na Web para a URL externa de serviços Web do Lync Server 2013 para seu pool de front-ends e pool de directors (se você tiver implantado directors), também precisará publicar uma regra para isso.</span><span class="sxs-lookup"><span data-stu-id="c0545-109">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0545-110">A regra de publicação de proxy reverso e a escuta podem atender tanto os serviços Web externos quanto o serviço de descoberta automática, desde que o certificado atribuído ao ouvinte contenha o nome da entidade e os nomes alternativos de assunto necessários para ambos.</span><span class="sxs-lookup"><span data-stu-id="c0545-110">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="c0545-111">Para obter detalhes sobre a configuração padrão do ouvinte da Web e da regra de publicação, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurando servidores proxy reverso para o Lync Server 2013</A> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="c0545-111">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="c0545-112">Se você decidir usar HTTP para solicitações de serviço de descoberta automática iniciais para que você não precise atualizar nomes alternativos de entidades para o proxy reverso, será necessário criar ou modificar uma regra de publicação na Web para a porta 80.</span><span class="sxs-lookup"><span data-stu-id="c0545-112">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="c0545-113">Os procedimentos desta seção descrevem como criar ou modificar as regras de publicação na Web no Microsoft Forefront Threat Management Gateway 2010 para descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="c0545-113">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0545-114">Esses procedimentos pressupõem que você tenha instalado a edição padrão do Forefront Threat Management Gateway (TMG) 2010.</span><span class="sxs-lookup"><span data-stu-id="c0545-114">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010.</span></span> <span data-ttu-id="c0545-115">Se você estiver usando outro proxy reverso, os procedimentos serão similares, mas precisarão ser mapeados para a documentação do produto de terceiros.</span><span class="sxs-lookup"><span data-stu-id="c0545-115">If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="c0545-116">Para criar uma regra de publicação na Web para a URL de descoberta automática externa</span><span class="sxs-lookup"><span data-stu-id="c0545-116">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="c0545-117">Clique em **Iniciar**, aponte para **programas**, aponte para **Microsoft Forefront TMG**e clique em **Gerenciamento do Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="c0545-117">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="c0545-118">No painel esquerdo, expanda **ServerName**, clique com o botão direito do mouse em **política de firewall**, aponte para **novo**e clique em regra de **publicação de site da Web**.</span><span class="sxs-lookup"><span data-stu-id="c0545-118">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="c0545-119">Na página **Bem-vindo à nova regra de publicação na Web** , digite um nome para exibição para a nova regra de publicação (por exemplo, LyncDiscoveryURL).</span><span class="sxs-lookup"><span data-stu-id="c0545-119">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="c0545-120">Na página **Selecionar ação da regra** , selecione **permitir**.</span><span class="sxs-lookup"><span data-stu-id="c0545-120">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="c0545-121">Na página **tipo de publicação** , selecione **publicar um único site da Web ou um balanceador de carga**.</span><span class="sxs-lookup"><span data-stu-id="c0545-121">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="c0545-122">Na página **segurança de conexão do servidor** , selecione **usar SSL para se conectar ao servidor Web ou ao farm de servidores publicado**.</span><span class="sxs-lookup"><span data-stu-id="c0545-122">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="c0545-123">Na página **detalhes da publicação interna** , em **nome do site interno**, digite o nome de domínio totalmente qualificado (FQDN) do seu pool de diretor (por exemplo, lyncdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="c0545-123">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="c0545-124">Se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, digite o FQDN do pool de front-ends (por exemplo, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="c0545-124">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="c0545-125">Na página **detalhes da publicação interna** , em **caminho (opcional)**, digite \*\* / \*\* como o caminho da pasta a ser publicada e, em seguida, selecione **encaminhar o cabeçalho original do host**.</span><span class="sxs-lookup"><span data-stu-id="c0545-125">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="c0545-126">Na página de **detalhes do nome público** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c0545-126">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="c0545-127">Em **aceitar solicitações por**, selecione **este nome de domínio**.</span><span class="sxs-lookup"><span data-stu-id="c0545-127">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="c0545-128">Em **nome público**, digite **lyncdiscover.** \<sipdomain\> (a URL do serviço de descoberta automática externa).</span><span class="sxs-lookup"><span data-stu-id="c0545-128">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="c0545-129">Se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, digite o FQDN dos serviços Web externos em seu pool de front-ends (por exemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c0545-129">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="c0545-130">Em **caminho**, digite \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="c0545-130">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="c0545-131">Na página **selecionar ouvinte da Web** , no **ouvinte da Web**, selecione seu ouvinte SSL existente com o certificado público atualizado.</span><span class="sxs-lookup"><span data-stu-id="c0545-131">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="c0545-132">Na página **delegação de autenticação** , selecione **sem delegação, mas o cliente pode autenticar diretamente**.</span><span class="sxs-lookup"><span data-stu-id="c0545-132">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="c0545-133">Na página **conjunto de usuários** , selecione **todos os usuários**.</span><span class="sxs-lookup"><span data-stu-id="c0545-133">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="c0545-134">Na página **concluindo o assistente de nova regra de publicação na Web** , verifique se as configurações da regra de publicação da Web estão corretas e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="c0545-134">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="c0545-135">Na lista do Forefront TMG de regras de publicação na Web, clique duas vezes na nova regra que você acabou de adicionar para abrir **as propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c0545-135">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="c0545-136">Na guia **para** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c0545-136">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="c0545-137">Selecione **encaminhar o cabeçalho original do host em vez do verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="c0545-137">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="c0545-138">**As solicitações selecionadas parecem vir do computador com o FOREFRONT TMG**.</span><span class="sxs-lookup"><span data-stu-id="c0545-138">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="c0545-139">Na guia **ponte** , configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c0545-139">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="c0545-140">Selecione **servidor Web**.</span><span class="sxs-lookup"><span data-stu-id="c0545-140">Select **Web server**.</span></span>
    
      - <span data-ttu-id="c0545-141">Selecione **redirecionar solicitações para porta http**e digite **8080** para o número da porta.</span><span class="sxs-lookup"><span data-stu-id="c0545-141">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="c0545-142">Selecione **redirecionar solicitações para porta SSL**e digite **4443** para o número da porta.</span><span class="sxs-lookup"><span data-stu-id="c0545-142">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="c0545-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0545-143">Click **OK**.</span></span>

18. <span data-ttu-id="c0545-144">Clique em **aplicar** no painel detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="c0545-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="c0545-145">Clique em **testar regra** para verificar se a nova regra está configurada corretamente.</span><span class="sxs-lookup"><span data-stu-id="c0545-145">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="c0545-146">Para modificar uma regra de publicação da Web existente para adicionar a SAN e a URL de descoberta automática externa</span><span class="sxs-lookup"><span data-stu-id="c0545-146">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="c0545-147">Clique em **Iniciar**, aponte para **programas**, aponte para **Microsoft Forefront TMG**e clique em **Gerenciamento do Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="c0545-147">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c0545-148">Você irá repetir a modificação para cada regra de publicação e ouvinte que você tiver.</span><span class="sxs-lookup"><span data-stu-id="c0545-148">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="c0545-149">Geralmente, isso será uma regra e um ouvinte para os pools de front-end e um para os directors opcionais ou os pools de directors, se você os tiver implantado.</span><span class="sxs-lookup"><span data-stu-id="c0545-149">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="c0545-150">No painel esquerdo, expanda **ServerName**, clique com o botão direito do mouse em **política de firewall**, clique na regra aplicável.</span><span class="sxs-lookup"><span data-stu-id="c0545-150">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule.</span></span> <span data-ttu-id="c0545-151">Na guia **tarefas** , clique em **Editar regra selecionada**.</span><span class="sxs-lookup"><span data-stu-id="c0545-151">On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="c0545-152">Na guia **nome público** , nesta **regra aplica-se a**, selecione **solicitações para os seguintes sites da Web**.</span><span class="sxs-lookup"><span data-stu-id="c0545-152">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="c0545-153">Clique em **Adicionar**, digite o nome do novo site de descoberta automática (por exemplo, "lyncdiscover.contoso.com") e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0545-153">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="c0545-154">Na guia **ouvinte** , clique em **Selecionar certificado** e atribua o novo certificado às entradas adicionadas de San de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="c0545-154">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries.</span></span> <span data-ttu-id="c0545-155">Feche as propriedades do ouvinte e publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="c0545-155">Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="c0545-156">Clique em **aplicar** no painel detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="c0545-156">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="c0545-157">Clique em **testar regra** para verificar se a nova regra está configurada corretamente.</span><span class="sxs-lookup"><span data-stu-id="c0545-157">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="c0545-158">Para criar uma regra de publicação na Web para a porta 80</span><span class="sxs-lookup"><span data-stu-id="c0545-158">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="c0545-159">Clique em **Iniciar**, aponte para **programas**, aponte para **Microsoft Forefront TMG**e clique em **Gerenciamento do Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="c0545-159">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="c0545-160">No painel esquerdo, expanda **ServerName**, clique com o botão direito do mouse em **política de firewall**, aponte para **novo**e clique em regra de **publicação de site da Web**.</span><span class="sxs-lookup"><span data-stu-id="c0545-160">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="c0545-161">Na página **Bem-vindo à nova regra de publicação na Web** , digite um nome para exibição para a nova regra de publicação (por exemplo, descoberta automática do LYNC (http)).</span><span class="sxs-lookup"><span data-stu-id="c0545-161">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="c0545-162">Na página **Selecionar ação da regra** , selecione **permitir**.</span><span class="sxs-lookup"><span data-stu-id="c0545-162">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="c0545-163">Na página **tipo de publicação** , selecione **publicar um único site da Web ou um balanceador de carga**.</span><span class="sxs-lookup"><span data-stu-id="c0545-163">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="c0545-164">Na página **segurança de conexão do servidor** , selecione **usar conexões não seguras para se conectar ao servidor Web ou ao farm de servidores publicado**.</span><span class="sxs-lookup"><span data-stu-id="c0545-164">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="c0545-165">Na página **detalhes da publicação interna** , em **nome do site interno**, digite o FQDN de serviços Web internos para o seu pool de front-end (por exemplo, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="c0545-165">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="c0545-166">Na página **detalhes da publicação interna** , em **caminho (opcional)**, digite \*\* / \*\* como o caminho da pasta a ser publicada e, em seguida, selecione **encaminhar o cabeçalho do host original em vez do especificado no campo nome do site interno**.</span><span class="sxs-lookup"><span data-stu-id="c0545-166">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="c0545-167">Na página de **detalhes do nome público** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c0545-167">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="c0545-168">Em **aceitar solicitações por**, selecione **este nome de domínio**.</span><span class="sxs-lookup"><span data-stu-id="c0545-168">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="c0545-169">Em **nome público**, digite **lyncdiscover.** \<sipdomain\> (a URL do serviço de descoberta automática externa).</span><span class="sxs-lookup"><span data-stu-id="c0545-169">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="c0545-170">Em **caminho**, digite \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="c0545-170">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="c0545-171">Na página **selecionar ouvinte da Web** , no **ouvinte da Web**, selecione um ouvinte da Web ou use o assistente de definição novo ouvinte da Web para criar um novo.</span><span class="sxs-lookup"><span data-stu-id="c0545-171">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="c0545-172">Na página **delegação de autenticação** , selecione **sem delegação e o cliente não pode autenticar diretamente**.</span><span class="sxs-lookup"><span data-stu-id="c0545-172">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="c0545-173">Na página **conjunto de usuários** , selecione **todos os usuários**.</span><span class="sxs-lookup"><span data-stu-id="c0545-173">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="c0545-174">Na página **concluindo o assistente de nova regra de publicação na Web** , verifique se as configurações da regra de publicação da Web estão corretas e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="c0545-174">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="c0545-175">Na lista do Forefront TMG de regras de publicação na Web, clique duas vezes na nova regra que você acabou de adicionar para abrir **as propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c0545-175">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="c0545-176">Na guia **ponte** , configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c0545-176">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="c0545-177">Selecione **servidor Web**.</span><span class="sxs-lookup"><span data-stu-id="c0545-177">Select **Web server**.</span></span>
    
      - <span data-ttu-id="c0545-178">Selecione **redirecionar solicitações para porta http**e digite **8080** para o número da porta.</span><span class="sxs-lookup"><span data-stu-id="c0545-178">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="c0545-179">Verifique se **a seleção redirecionar solicitações para a porta SSL** não está selecionada.</span><span class="sxs-lookup"><span data-stu-id="c0545-179">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="c0545-180">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0545-180">Click **OK**.</span></span>

17. <span data-ttu-id="c0545-181">Clique em **aplicar** no painel detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="c0545-181">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="c0545-182">Clique em **testar regra** para verificar se a nova regra está configurada corretamente.</span><span class="sxs-lookup"><span data-stu-id="c0545-182">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="c0545-183">Verifique se a URL do serviço de descoberta automática externa não está definida em nenhuma outra regra de publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="c0545-183">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c0545-184">Confira também</span><span class="sxs-lookup"><span data-stu-id="c0545-184">See Also</span></span>


[<span data-ttu-id="c0545-185">Configurando servidores de proxy reverso para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0545-185">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

