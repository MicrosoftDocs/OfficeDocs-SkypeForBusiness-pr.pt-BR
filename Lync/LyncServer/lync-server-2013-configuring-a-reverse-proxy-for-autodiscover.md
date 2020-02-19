---
title: 'Lync Server 2013: Configurando um proxy reverso para descoberta automática'
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
ms.openlocfilehash: 7c50704508c09d1f30a9fb8e31060e2a3b69885d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="83db8-102">Configurando um proxy reverso para descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83db8-102">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83db8-103">_**Última modificação do tópico:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="83db8-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="83db8-104">A descoberta automática e o suporte de clientes que usam a descoberta automática exigem a modificação de uma regra de publicação da Web existente ou a criação de uma nova regra de publicação na Web para o proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="83db8-104">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="83db8-105">A modificação ou a criação de uma nova regra de publicação não depende da decisão de atualizar ou não atualizar as listas de nomes alternativos de entidades nos certificados de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="83db8-105">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="83db8-106">Se você decidir usar HTTPS para solicitações iniciais do serviço de descoberta automática do Lync Server 2013 e atualizar as listas de nomes alternativos de entidade nos certificados de proxy reverso, você precisará atribuir o certificado público atualizado ao ouvinte SSL (Secure Sockets Layer) no seu proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="83db8-106">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="83db8-107">A atualização necessária para o certificado externo (público) incluirá a entrada de nome alternativo de entidade (SAN) para o lyncdiscover. \<nome\>do domínio.</span><span class="sxs-lookup"><span data-stu-id="83db8-107">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="83db8-108">Você precisará modificar o ouvinte existente para os serviços Web externos ou criar uma nova regra de publicação na Web para a URL externa do serviço de descoberta automática, por exemplo, **lyncdiscover.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="83db8-108">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="83db8-109">Se você ainda não tiver uma regra de publicação na Web para a URL dos serviços Web externos do Lync Server 2013 para o pool de front-ends e o pool de diretores (se você tiver implantado diretores), você também precisará publicar uma regra para isso.</span><span class="sxs-lookup"><span data-stu-id="83db8-109">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83db8-110">A regra de publicação de proxy reversa e o ouvinte podem fornecer serviços tanto para Web externa quanto para o Serviço de Descoberta Automática, desde que o certificado atribuído ao ouvinte possua o nome de assunto necessário e os nomes alternativos de assunto para ambos.</span><span class="sxs-lookup"><span data-stu-id="83db8-110">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="83db8-111">Para obter detalhes sobre a configuração padrão do ouvinte da Web e da regra de publicação, confira <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurando servidores de proxy reverso para o Lync Server 2013</A> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="83db8-111">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="83db8-112">Se você decidir usar HTTP para solicitações iniciais de Serviço Descoberta Automática para que não precise atualizar nomes alternativos de assunto para o proxy reverso, você precisará criar ou modificar uma regra de publicação na Web para a porta 80.</span><span class="sxs-lookup"><span data-stu-id="83db8-112">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="83db8-113">Os procedimentos nesta seção descrevem como criar ou modificar as regras de publicação na Web no Microsoft Forefront Threat Management Gateway 2010 para descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="83db8-113">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83db8-p104">Esses procedimentos assumem que você possui a Standard Edition do Forefront Threat Management Gateway (TMG) 2010 instalado. Se você estiver utilizando outro proxy reverso, os procedimentos são similares, mas precisarão ser mapeados para a documentação do produto de terceiro.</span><span class="sxs-lookup"><span data-stu-id="83db8-p104">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="83db8-116">Para criar uma regra de publicação na Web para a URL externa de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="83db8-116">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="83db8-117">Clique em **Iniciar**, aponte para **Programas**, **Microsoft Forefront TMG** e, então, clique em **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="83db8-117">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="83db8-118">No painel esquerdo, expanda **Nome do Servidor**, clique com o botão direito do mouse em **Diretiva de Firewall**, aponte para **Novo** e clique em **Regra de Publicação de Site**.</span><span class="sxs-lookup"><span data-stu-id="83db8-118">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="83db8-119">Na página **Bem-vindo à nova regra de publicação na Web**, digite um nome para exibição para a nova regra de publicação (por exemplo, LyncDiscoveryURL).</span><span class="sxs-lookup"><span data-stu-id="83db8-119">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="83db8-120">Na página **Selecionar Ação de Regra**, selecione **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="83db8-120">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="83db8-121">Na página **Tipo de Publicação**, selecione **Publicar um único site da Web ou balanceador de carga**.</span><span class="sxs-lookup"><span data-stu-id="83db8-121">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="83db8-122">Na página **Segurança da Conexão do Servidor**, selecione **Usar SSL para conectar ao servidor Web ou ao farm de servidores publicado**.</span><span class="sxs-lookup"><span data-stu-id="83db8-122">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="83db8-123">Na página **detalhes de publicação interna** , em **nome do site interno**, digite o nome de domínio totalmente qualificado (FQDN) do seu pool de diretor (por exemplo, lyncdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="83db8-123">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="83db8-124">Se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, digite o FQDN do pool de front-ends (por exemplo, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="83db8-124">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="83db8-125">Na página **detalhes de publicação interna** , em **caminho (opcional)**, digite \*\* / \*\* como o caminho da pasta a ser publicada e, em seguida, selecione **encaminhar o cabeçalho de host original**.</span><span class="sxs-lookup"><span data-stu-id="83db8-125">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="83db8-126">Na página **Detalhes do Nome Público**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83db8-126">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="83db8-127">Em **Aceitar Solicitações para**, selecione **Este nome de domínio**.</span><span class="sxs-lookup"><span data-stu-id="83db8-127">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="83db8-128">Em **nome público**, digite **lyncdiscover.** \<sipdomain\> (a URL externa do serviço de descoberta automática).</span><span class="sxs-lookup"><span data-stu-id="83db8-128">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="83db8-129">Se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, digite o FQDN dos serviços Web externos em seu pool de front-ends (por exemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="83db8-129">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="83db8-130">Em **caminho**, digite \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="83db8-130">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="83db8-131">Na página **Selecionar Ouvinte da Web**, no **Ouvinte da Web**, selecione o Ouvinte SSL existente com o certificado público atualizado.</span><span class="sxs-lookup"><span data-stu-id="83db8-131">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="83db8-132">Na página **Delegação de Autenticação**, selecione **Nenhuma delegação, mas o cliente pode autenticar diretamente**.</span><span class="sxs-lookup"><span data-stu-id="83db8-132">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="83db8-133">Na página **Conjunto de Usuários**, selecione **Todos os Usuários**.</span><span class="sxs-lookup"><span data-stu-id="83db8-133">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="83db8-134">Na página **Concluindo o Assistente de Nova Regra de Publicação de Web**, verifique se as configurações da regra de publicação de Web estão corretas e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="83db8-134">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="83db8-135">Na lista Forefront TMG de regras de publicação, clique duas vezes na nova regra que você acabou de adicionar para abrir **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="83db8-135">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="83db8-136">Na guia **Para**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83db8-136">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="83db8-137">Selecione **Encaminhar o cabeçalho de host original em vez do presente**.</span><span class="sxs-lookup"><span data-stu-id="83db8-137">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="83db8-138">Selecione **As solicitações parecem vir de computador do Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="83db8-138">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="83db8-139">Na guia **Ponte**, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83db8-139">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="83db8-140">Selecione **Servidor Web**.</span><span class="sxs-lookup"><span data-stu-id="83db8-140">Select **Web server**.</span></span>
    
      - <span data-ttu-id="83db8-141">Selecione **Redirecionar solicitações para a porta HTTP** e digite **8080** como número da porta.</span><span class="sxs-lookup"><span data-stu-id="83db8-141">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="83db8-142">Selecione   **Redirecionar solicitações para a porta SSL** e digite **4443** para o número da porta.</span><span class="sxs-lookup"><span data-stu-id="83db8-142">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="83db8-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="83db8-143">Click **OK**.</span></span>

18. <span data-ttu-id="83db8-144">Clique em **Aplicar** no painel de detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="83db8-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="83db8-145">Clique em **Regra de Teste** para verificar se a nova regra está definida corretamente.</span><span class="sxs-lookup"><span data-stu-id="83db8-145">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="83db8-146">Para modificar uma regra de publicação Web existente para adicionar o SAN de Descoberta Automática externa e URL</span><span class="sxs-lookup"><span data-stu-id="83db8-146">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="83db8-147">Clique em **Iniciar**, aponte para **Programas**, aponte para **Microsoft Forefront TMG** e clique em **Gerenciamento do Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="83db8-147">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="83db8-148">Você irá repetir a modificação para cada regra de publicação e ouvinte que possuir.</span><span class="sxs-lookup"><span data-stu-id="83db8-148">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="83db8-149">Normalmente, será uma regra e um ouvinte para os pools de front-ends e um para os diretores opcionais ou pools de diretores, se você os tiver implantado.</span><span class="sxs-lookup"><span data-stu-id="83db8-149">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="83db8-p108">No painel à esquerda, expanda **ServerName**, clique com o botão direito em **Política de firewall** e clique na regra aplicável. Na aba **Tarefas**, clique na **regra Editar selecionado**.</span><span class="sxs-lookup"><span data-stu-id="83db8-p108">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="83db8-152">Na aba **Nome público**, em **Esta regra se aplica a**, selecione **Solicitações para os seguintes sites da Web**.</span><span class="sxs-lookup"><span data-stu-id="83db8-152">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="83db8-153">Clique em **Adicionar**, digite o nome do site de Descoberta Automática novo (por exemplo, “lyncdiscover.contoso.com”) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="83db8-153">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="83db8-p109">Na aba **Ouvinte**, clique em **Selecionar certificado** e atribua o novo certificado com as entradas SAN da Descoberta Automática adicionadas. Feche o Ouvinte e as propriedades de Publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="83db8-p109">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="83db8-156">Clique em **Aplicar** no painel de detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="83db8-156">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="83db8-157">Clique em **Testar regra** para verificar se a nova regra foi definida corretamente.</span><span class="sxs-lookup"><span data-stu-id="83db8-157">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="83db8-158">Para criar uma regra de publicação na Web para a porta 80</span><span class="sxs-lookup"><span data-stu-id="83db8-158">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="83db8-159">Clique em **Iniciar**, aponte para **Programas**, **Microsoft Forefront TMG** e, então, clique em **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="83db8-159">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="83db8-160">No painel esquerdo, expanda **Nome do Servidor**, clique com o botão direito do mouse em **Diretiva de Firewall**, aponte para **Novo** e clique em **Regra de Publicação de Site**.</span><span class="sxs-lookup"><span data-stu-id="83db8-160">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="83db8-161">Na página **Bem-vindo à nova regra de publicação na Web**, digite um nome para exibição para a nova regra de publicação (por exemplo, Descoberta Automática do Lync (HTTP)).</span><span class="sxs-lookup"><span data-stu-id="83db8-161">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="83db8-162">Na página **Selecionar Ação de Regra**, selecione **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="83db8-162">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="83db8-163">Na página **Tipo de Publicação**, selecione **Publicar um único site ou um balanceador de carga na Web** e clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="83db8-163">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="83db8-164">Na página **Segurança da Conexão do Servidor**, selecione **Usar conexões não seguras para conectar ao servidor Web ou ao farm de servidores publicado**.</span><span class="sxs-lookup"><span data-stu-id="83db8-164">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="83db8-165">Na página **detalhes de publicação interna** , em **nome do site interno**, digite o FQDN dos serviços Web internos para seu pool de front-ends (por exemplo, lyncpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="83db8-165">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="83db8-166">Na página **detalhes de publicação interna** , em **caminho (opcional)**, digite \*\* / \*\* como o caminho da pasta a ser publicada e, em seguida, selecione **encaminhar o cabeçalho de host original em vez do especificado no campo nome do site interno**.</span><span class="sxs-lookup"><span data-stu-id="83db8-166">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="83db8-167">Na página **Detalhes do Nome Público**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83db8-167">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="83db8-168">Em **Aceitar Solicitações para**, selecione **Este nome de domínio**.</span><span class="sxs-lookup"><span data-stu-id="83db8-168">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="83db8-169">Em **nome público**, digite **lyncdiscover.** \<sipdomain\> (a URL externa do serviço de descoberta automática).</span><span class="sxs-lookup"><span data-stu-id="83db8-169">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="83db8-170">Em **caminho**, digite \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="83db8-170">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="83db8-171">Em **Selecionar Ouvinte da Web**, em **Ouvinte da Web**, selecione um Ouvinte da Web ou use o Assistente de Nova Definição de Ouvinte da Web para criar um novo.</span><span class="sxs-lookup"><span data-stu-id="83db8-171">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="83db8-172">Na página **Delegação de Autenticação**, selecione **Nenhuma delegação, e o cliente não pode autenticar diretamente**.</span><span class="sxs-lookup"><span data-stu-id="83db8-172">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="83db8-173">Na página **Conjunto de Usuários**, selecione **Todos os Usuários**.</span><span class="sxs-lookup"><span data-stu-id="83db8-173">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="83db8-174">Na página **Concluindo o Assistente de Nova Regra de Publicação de Web**, verifique se as configurações da regra de publicação de Web estão corretas e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="83db8-174">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="83db8-175">Na lista Forefront TMG de regras de publicação, clique duas vezes na nova regra que você acabou de adicionar para abrir **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="83db8-175">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="83db8-176">Na guia **Ponte**, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83db8-176">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="83db8-177">Selecione **Servidor Web**.</span><span class="sxs-lookup"><span data-stu-id="83db8-177">Select **Web server**.</span></span>
    
      - <span data-ttu-id="83db8-178">Selecione   **Redirecionar solicitações para a porta HTTP** e digite **8080** para o número da porta.</span><span class="sxs-lookup"><span data-stu-id="83db8-178">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="83db8-179">Verifique se **Redirecionar solicitações para a porta SSL** não está selecionada.</span><span class="sxs-lookup"><span data-stu-id="83db8-179">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="83db8-180">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="83db8-180">Click **OK**.</span></span>

17. <span data-ttu-id="83db8-181">Clique em **Aplicar** no painel de detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="83db8-181">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="83db8-182">Clique em **Regra de Teste** para verificar se a nova regra está definida corretamente.</span><span class="sxs-lookup"><span data-stu-id="83db8-182">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="83db8-183">Verifique se a URL do Serviço Descoberta Automática externo não está definida em nenhuma outra regra de publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="83db8-183">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="83db8-184">Confira também</span><span class="sxs-lookup"><span data-stu-id="83db8-184">See Also</span></span>


[<span data-ttu-id="83db8-185">Configurando servidores de proxy reverso para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83db8-185">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

