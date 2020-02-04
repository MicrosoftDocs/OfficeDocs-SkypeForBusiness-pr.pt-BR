---
title: 'Lync Server 2013: Configurando o proxy reverso para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51fffae60df68a6aa2843919f95d7a00590ddd65
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a><span data-ttu-id="e7b93-102">Configurando o proxy reverso para mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7b93-102">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7b93-103">_**Tópico da última modificação:** 2014-03-20_</span><span class="sxs-lookup"><span data-stu-id="e7b93-103">_**Topic Last Modified:** 2014-03-20_</span></span>

<span data-ttu-id="e7b93-104">Se quiser usar a descoberta automática para clientes de dispositivos móveis, você precisará modificar uma nova regra de publicação na Web para o proxy reverso se você atualizou ou não as listas de nomes alternativos de entidades nos certificados de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="e7b93-104">If you want to use automatic discovery for mobile device clients, you need to modify an existing or create a new web publishing rule for the reverse proxy whether or not you update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="e7b93-105">Se você decidir usar HTTPS para solicitações iniciais de serviço de descoberta automática do Lync Server 2013 e atualizar as listas de nomes alternativos de entidades nos certificados de proxy reverso, será necessário atribuir o certificado público atualizado ao ouvinte SSL (Secure Sockets Layer) em seu proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="e7b93-105">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="e7b93-106">Para obter detalhes sobre as entradas de nomes alternativos de entidades necessárias, consulte [requisitos técnicos de mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="e7b93-106">For details about the required subject alternative name entries, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="e7b93-107">Em seguida, você precisará modificar o ouvinte existente para os serviços Web externos ou criar uma nova regra de publicação na Web para a URL externa do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="e7b93-107">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="e7b93-108">Se você ainda não tiver uma regra de publicação na Web para a URL externa de serviços Web do Lync Server 2013 para seu pool de front-ends, também precisará publicar uma regra para isso.</span><span class="sxs-lookup"><span data-stu-id="e7b93-108">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool, you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7b93-109">A regra de publicação de proxy reverso e a escuta podem atender tanto os serviços Web externos quanto o serviço de descoberta automática, desde que o certificado atribuído ao ouvinte contenha o nome da entidade e os nomes alternativos de assunto necessários para ambos.</span><span class="sxs-lookup"><span data-stu-id="e7b93-109">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="e7b93-110">Para obter detalhes sobre a configuração padrão do ouvinte da Web e da regra de publicação, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurando servidores proxy reverso para o Lync Server 2013</A> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="e7b93-110">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="e7b93-111">Se você decidir usar HTTP para solicitações de serviço de descoberta automática iniciais para que você não precise atualizar nomes alternativos de entidades para o proxy reverso, será necessário criar ou modificar uma regra de publicação na Web para a porta 80.</span><span class="sxs-lookup"><span data-stu-id="e7b93-111">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="e7b93-112">Os procedimentos desta seção descrevem como criar ou modificar as regras de publicação na Web no Microsoft Forefront Threat Management Gateway 2010 para descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="e7b93-112">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7b93-113">Esses procedimentos pressupõem que você tenha instalado a edição padrão do Forefront Threat Management Gateway (TMG) 2010.</span><span class="sxs-lookup"><span data-stu-id="e7b93-113">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010.</span></span> <span data-ttu-id="e7b93-114">Se você estiver usando outro proxy reverso, os procedimentos serão similares, mas precisarão ser mapeados para a documentação do produto de terceiros.</span><span class="sxs-lookup"><span data-stu-id="e7b93-114">If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="e7b93-115">Para criar uma regra de publicação na Web para a URL de descoberta automática externa</span><span class="sxs-lookup"><span data-stu-id="e7b93-115">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="e7b93-116">Clique em **Iniciar**, aponte para **programas**, aponte para **Microsoft Forefront TMG**e clique em **Gerenciamento do Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-116">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="e7b93-117">No painel esquerdo, expanda **ServerName**, clique com o botão direito do mouse em **política de firewall**, aponte para **novo**e clique em regra de **publicação de site da Web**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-117">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="e7b93-118">Na página **Bem-vindo à nova regra de publicação na Web** , digite um nome para exibição para a nova regra de publicação (por exemplo, LyncDiscoveryURL).</span><span class="sxs-lookup"><span data-stu-id="e7b93-118">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="e7b93-119">Na página **Selecionar ação da regra** , selecione **permitir**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-119">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="e7b93-120">Na página **tipo de publicação** , selecione **publicar um único site da Web ou um balanceador de carga**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-120">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="e7b93-121">Na página **segurança de conexão do servidor** , selecione **usar SSL para se conectar ao servidor Web ou ao farm de servidores publicado**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-121">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="e7b93-122">Na página **detalhes da publicação interna** , em **nome do site interno**, digite o nome de domínio totalmente qualificado (FQDN) do seu pool de diretor (por exemplo, lyncdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="e7b93-122">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="e7b93-123">Se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, digite o endereço VIP do balanceador de carga de hardware (HLB) na frente do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="e7b93-123">If you are creating a rule for the external Web Services URL on the Front End pool, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="e7b93-124">Na página **detalhes da publicação interna** , em **caminho (opcional)**, digite \*\* / \*\* como o caminho da pasta a ser publicada e, em seguida, selecione **encaminhar o cabeçalho original do host**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-124">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="e7b93-125">Na página de **detalhes do nome público** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e7b93-125">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="e7b93-126">Em **aceitar solicitações por**, selecione **este nome de domínio**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-126">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="e7b93-127">Em **nome público**, digite **lyncdiscover.** \<sipdomain\> (a URL do serviço de descoberta automática externa).</span><span class="sxs-lookup"><span data-stu-id="e7b93-127">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="e7b93-128">Se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, digite o FQDN dos serviços Web externos em seu pool de front-ends (por exemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e7b93-128">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="e7b93-129">Em **caminho**, digite \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="e7b93-129">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="e7b93-130">Na página **selecionar ouvinte da Web** , no **ouvinte da Web**, selecione seu ouvinte SSL existente com o certificado público atualizado.</span><span class="sxs-lookup"><span data-stu-id="e7b93-130">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="e7b93-131">Na página **delegação de autenticação** , selecione **sem delegação, mas o cliente pode autenticar diretamente**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-131">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="e7b93-132">Na página **conjunto de usuários** , selecione **todos os usuários**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-132">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="e7b93-133">Na página **concluindo o assistente de nova regra de publicação na Web** , verifique se as configurações da regra de publicação da Web estão corretas e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-133">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="e7b93-134">Na lista do Forefront TMG de regras de publicação na Web, clique duas vezes na nova regra que você acabou de adicionar para abrir **as propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-134">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="e7b93-135">Na guia **para** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e7b93-135">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="e7b93-136">Selecione **encaminhar o cabeçalho original do host em vez do verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-136">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="e7b93-137">**As solicitações selecionadas parecem vir do computador com o FOREFRONT TMG**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-137">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="e7b93-138">Na guia **ponte** , configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e7b93-138">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="e7b93-139">Selecione **servidor Web**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-139">Select **Web server**.</span></span>
    
      - <span data-ttu-id="e7b93-140">Selecione **redirecionar solicitações para porta http**e digite **8080** para o número da porta.</span><span class="sxs-lookup"><span data-stu-id="e7b93-140">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="e7b93-141">Selecione **redirecionar solicitações para porta SSL**e digite **4443** para o número da porta.</span><span class="sxs-lookup"><span data-stu-id="e7b93-141">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="e7b93-142">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-142">Click **OK**.</span></span>

18. <span data-ttu-id="e7b93-143">Clique em **aplicar** no painel detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="e7b93-143">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="e7b93-144">Clique em **testar regra** para verificar se a nova regra está configurada corretamente.</span><span class="sxs-lookup"><span data-stu-id="e7b93-144">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="e7b93-145">Para modificar uma regra de publicação da Web existente para adicionar a SAN e a URL de descoberta automática externa</span><span class="sxs-lookup"><span data-stu-id="e7b93-145">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="e7b93-146">Clique em **Iniciar**, aponte para **programas**, aponte para **Microsoft Forefront TMG**e clique em **Gerenciamento do Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-146">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7b93-147">Você irá repetir a modificação para cada regra de publicação e ouvinte que você tiver.</span><span class="sxs-lookup"><span data-stu-id="e7b93-147">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="e7b93-148">Geralmente, isso será uma regra e um ouvinte para os pools de front-end e um para os directors opcionais ou os pools de directors, se você os tiver implantado.</span><span class="sxs-lookup"><span data-stu-id="e7b93-148">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="e7b93-149">No painel esquerdo, expanda **ServerName**, clique com o botão direito do mouse em **política de firewall**, clique na regra aplicável.</span><span class="sxs-lookup"><span data-stu-id="e7b93-149">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule.</span></span> <span data-ttu-id="e7b93-150">Na guia **tarefas** , clique em **Editar regra selecionada**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-150">On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="e7b93-151">Na guia **nome público** , nesta **regra aplica-se a**, selecione **solicitações para os seguintes sites da Web**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-151">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="e7b93-152">Clique em **Adicionar**, digite o nome do novo site de descoberta automática (por exemplo, "lyncdiscover.contoso.com") e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-152">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="e7b93-153">Na guia **ouvinte** , clique em **Selecionar certificado** e atribua o novo certificado às entradas adicionadas de San de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="e7b93-153">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries.</span></span> <span data-ttu-id="e7b93-154">Feche as propriedades do ouvinte e publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="e7b93-154">Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="e7b93-155">Clique em **aplicar** no painel detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="e7b93-155">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="e7b93-156">Clique em **testar regra** para verificar se a nova regra está configurada corretamente.</span><span class="sxs-lookup"><span data-stu-id="e7b93-156">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="e7b93-157">Para criar uma regra de publicação na Web para a porta 80</span><span class="sxs-lookup"><span data-stu-id="e7b93-157">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="e7b93-158">Clique em **Iniciar**, aponte para **programas**, aponte para **Microsoft Forefront TMG**e clique em **Gerenciamento do Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-158">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="e7b93-159">No painel esquerdo, expanda **ServerName**, clique com o botão direito do mouse em **política de firewall**, aponte para **novo**e clique em regra de **publicação de site da Web**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-159">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="e7b93-160">Na página **Bem-vindo à nova regra de publicação na Web** , digite um nome para exibição para a nova regra de publicação (por exemplo, descoberta automática do LYNC (http)).</span><span class="sxs-lookup"><span data-stu-id="e7b93-160">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="e7b93-161">Na página **Selecionar ação da regra** , selecione **permitir**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-161">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="e7b93-162">Na página **tipo de publicação** , selecione **publicar um único site da Web ou um balanceador de carga**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-162">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="e7b93-163">Na página **segurança de conexão do servidor** , selecione **usar conexões não seguras para se conectar ao servidor Web ou ao farm de servidores publicado**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-163">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="e7b93-164">Na página **detalhes da publicação interna** , em **nome do site interno**, digite o endereço VIP do balanceador de carga de hardware (HLB) na frente do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="e7b93-164">On the **Internal Publishing Details** page, in **Internal Site name**, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="e7b93-165">Na página **detalhes da publicação interna** , em **caminho (opcional)**, digite \*\* / \*\* como o caminho da pasta a ser publicada e, em seguida, selecione **encaminhar o cabeçalho do host original em vez do especificado no campo nome do site interno**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-165">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="e7b93-166">Na página de **detalhes do nome público** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e7b93-166">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="e7b93-167">Em **aceitar solicitações por**, selecione **este nome de domínio**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-167">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="e7b93-168">Em **nome público**, digite **lyncdiscover.** \<sipdomain\> (a URL do serviço de descoberta automática externa).</span><span class="sxs-lookup"><span data-stu-id="e7b93-168">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="e7b93-169">Em **caminho**, digite \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="e7b93-169">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="e7b93-170">Na página **selecionar ouvinte da Web** , no **ouvinte da Web**, selecione um ouvinte da Web ou use o assistente de definição novo ouvinte da Web para criar um novo.</span><span class="sxs-lookup"><span data-stu-id="e7b93-170">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="e7b93-171">Na página **delegação de autenticação** , selecione **sem delegação e o cliente não pode autenticar diretamente**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-171">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="e7b93-172">Na página **conjunto de usuários** , selecione **todos os usuários**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-172">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="e7b93-173">Na página **concluindo o assistente de nova regra de publicação na Web** , verifique se as configurações da regra de publicação da Web estão corretas e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-173">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="e7b93-174">Na lista do Forefront TMG de regras de publicação na Web, clique duas vezes na nova regra que você acabou de adicionar para abrir **as propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-174">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="e7b93-175">Na guia **ponte** , configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e7b93-175">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="e7b93-176">Selecione **servidor Web**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-176">Select **Web server**.</span></span>
    
      - <span data-ttu-id="e7b93-177">Selecione **redirecionar solicitações para porta http**e digite **8080** para o número da porta.</span><span class="sxs-lookup"><span data-stu-id="e7b93-177">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="e7b93-178">Verifique se **a seleção redirecionar solicitações para a porta SSL** não está selecionada.</span><span class="sxs-lookup"><span data-stu-id="e7b93-178">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="e7b93-179">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7b93-179">Click **OK**.</span></span>

17. <span data-ttu-id="e7b93-180">Clique em **aplicar** no painel detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="e7b93-180">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="e7b93-181">Clique em **testar regra** para verificar se a nova regra está configurada corretamente.</span><span class="sxs-lookup"><span data-stu-id="e7b93-181">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="e7b93-182">Verifique se a URL do serviço de descoberta automática externa não está definida em nenhuma outra regra de publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="e7b93-182">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7b93-183">Confira também</span><span class="sxs-lookup"><span data-stu-id="e7b93-183">See Also</span></span>


[<span data-ttu-id="e7b93-184">Configurando servidores de proxy reverso para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7b93-184">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[<span data-ttu-id="e7b93-185">Requisitos técnicos para mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7b93-185">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

