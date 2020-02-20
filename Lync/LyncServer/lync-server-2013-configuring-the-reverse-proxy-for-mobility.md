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
ms.openlocfilehash: 88a0d27967eab4da884694084926b35f2acf36d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a><span data-ttu-id="97a96-102">Configurando o proxy reverso para mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97a96-102">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97a96-103">_**Última modificação do tópico:** 2014-03-20_</span><span class="sxs-lookup"><span data-stu-id="97a96-103">_**Topic Last Modified:** 2014-03-20_</span></span>

<span data-ttu-id="97a96-104">Se você quiser usar a descoberta automática para clientes do dispositivo móvel, precisará modificar ou criar uma nova regra de publicação na Web para o proxy reverso quer você atualize ou não as listas de nome alternativo de assunto nos certificados de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="97a96-104">If you want to use automatic discovery for mobile device clients, you need to modify an existing or create a new web publishing rule for the reverse proxy whether or not you update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="97a96-105">Se você decidir usar HTTPS para solicitações iniciais do serviço de descoberta automática do Lync Server 2013 e atualizar as listas de nomes alternativos de entidade nos certificados de proxy reverso, você precisará atribuir o certificado público atualizado ao ouvinte SSL (Secure Sockets Layer) no seu proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="97a96-105">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="97a96-106">Para obter detalhes sobre as entradas de nome alternativo de entidade necessárias, consulte [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="97a96-106">For details about the required subject alternative name entries, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="97a96-107">Em seguida, você precisa modificar o ouvinte existente para serviçso da Web externos ou criar uma nova regra de publicação para o URL do Serviço Descoberta Automática externo.</span><span class="sxs-lookup"><span data-stu-id="97a96-107">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="97a96-108">Se você ainda não tiver uma regra de publicação na Web para a URL dos serviços Web externos do Lync Server 2013 para seu pool de front-ends, você também precisará publicar uma regra para isso.</span><span class="sxs-lookup"><span data-stu-id="97a96-108">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool, you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97a96-109">A regra de publicação de proxy reversa e o ouvinte podem fornecer serviços tanto para Web externa quanto para o Serviço de Descoberta Automática, desde que o certificado atribuído ao ouvinte possua o nome de assunto necessário e os nomes alternativos de assunto para ambos.</span><span class="sxs-lookup"><span data-stu-id="97a96-109">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="97a96-110">Para obter detalhes sobre a configuração padrão do ouvinte da Web e da regra de publicação, confira <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurando servidores de proxy reverso para o Lync Server 2013</A> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="97a96-110">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="97a96-111">Se você decidir usar HTTP para solicitações iniciais de Serviço Descoberta Automática para que não precise atualizar nomes alternativos de assunto para o proxy reverso, você precisará criar ou modificar uma regra de publicação na Web para a porta 80.</span><span class="sxs-lookup"><span data-stu-id="97a96-111">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="97a96-112">Os procedimentos nesta seção descrevem como criar ou modificar as regras de publicação na Web no Microsoft Forefront Threat Management Gateway 2010 para descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="97a96-112">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97a96-p103">Esses procedimentos assumem que você possui a Standard Edition do Forefront Threat Management Gateway (TMG) 2010 instalado. Se você estiver utilizando outro proxy reverso, os procedimentos são similares, mas precisarão ser mapeados para a documentação do produto de terceiro.</span><span class="sxs-lookup"><span data-stu-id="97a96-p103">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="97a96-115">Para criar uma regra de publicação na Web para a URL externa de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="97a96-115">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="97a96-116">Clique em **Iniciar**, aponte para **Programas**, **Microsoft Forefront TMG** e, então, clique em **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="97a96-116">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="97a96-117">No painel esquerdo, expanda **Nome do Servidor**, clique com o botão direito do mouse em **Diretiva de Firewall**, aponte para **Novo** e clique em **Regra de Publicação de Site**.</span><span class="sxs-lookup"><span data-stu-id="97a96-117">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="97a96-118">Na página **Bem-vindo à nova regra de publicação na Web**, digite um nome para exibição para a nova regra de publicação (por exemplo, LyncDiscoveryURL).</span><span class="sxs-lookup"><span data-stu-id="97a96-118">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="97a96-119">Na página **Selecionar Ação de Regra**, selecione **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="97a96-119">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="97a96-120">Na página **Tipo de Publicação**, selecione **Publicar um único site da Web ou balanceador de carga**.</span><span class="sxs-lookup"><span data-stu-id="97a96-120">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="97a96-121">Na página **Segurança da Conexão do Servidor**, selecione **Usar SSL para conectar ao servidor Web ou ao farm de servidores publicado**.</span><span class="sxs-lookup"><span data-stu-id="97a96-121">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="97a96-122">Na página **detalhes de publicação interna** , em **nome do site interno**, digite o nome de domínio totalmente qualificado (FQDN) do seu pool de diretor (por exemplo, lyncdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="97a96-122">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="97a96-123">Se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, digite o endereço VIP do balanceador de carga de hardware (HLB) na frente do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="97a96-123">If you are creating a rule for the external Web Services URL on the Front End pool, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="97a96-124">Na página **detalhes de publicação interna** , em **caminho (opcional)**, digite \*\* / \*\* como o caminho da pasta a ser publicada e, em seguida, selecione **encaminhar o cabeçalho de host original**.</span><span class="sxs-lookup"><span data-stu-id="97a96-124">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="97a96-125">Na página **Detalhes do Nome Público**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="97a96-125">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="97a96-126">Em **Aceitar Solicitações para**, selecione **Este nome de domínio**.</span><span class="sxs-lookup"><span data-stu-id="97a96-126">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="97a96-127">Em **nome público**, digite **lyncdiscover.** \<sipdomain\> (a URL externa do serviço de descoberta automática).</span><span class="sxs-lookup"><span data-stu-id="97a96-127">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="97a96-128">Se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, digite o FQDN dos serviços Web externos em seu pool de front-ends (por exemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="97a96-128">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="97a96-129">Em **caminho**, digite \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="97a96-129">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="97a96-130">Na página **Selecionar Ouvinte da Web**, no **Ouvinte da Web**, selecione o Ouvinte SSL existente com o certificado público atualizado.</span><span class="sxs-lookup"><span data-stu-id="97a96-130">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="97a96-131">Na página **Delegação de Autenticação**, selecione **Nenhuma delegação, mas o cliente pode autenticar diretamente**.</span><span class="sxs-lookup"><span data-stu-id="97a96-131">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="97a96-132">Na página **Conjunto de Usuários**, selecione **Todos os Usuários**.</span><span class="sxs-lookup"><span data-stu-id="97a96-132">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="97a96-133">Na página **Concluindo o Assistente de Nova Regra de Publicação de Web**, verifique se as configurações da regra de publicação de Web estão corretas e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="97a96-133">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="97a96-134">Na lista Forefront TMG de regras de publicação, clique duas vezes na nova regra que você acabou de adicionar para abrir **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="97a96-134">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="97a96-135">Na guia **Para**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="97a96-135">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="97a96-136">Selecione **Encaminhar o cabeçalho de host original em vez do presente**.</span><span class="sxs-lookup"><span data-stu-id="97a96-136">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="97a96-137">Selecione **As solicitações parecem vir de computador do Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="97a96-137">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="97a96-138">Na guia **Ponte**, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="97a96-138">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="97a96-139">Selecione **Servidor Web**.</span><span class="sxs-lookup"><span data-stu-id="97a96-139">Select **Web server**.</span></span>
    
      - <span data-ttu-id="97a96-140">Selecione **Redirecionar solicitações para a porta HTTP** e digite **8080** como número da porta.</span><span class="sxs-lookup"><span data-stu-id="97a96-140">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="97a96-141">Selecione   **Redirecionar solicitações para a porta SSL** e digite **4443** para o número da porta.</span><span class="sxs-lookup"><span data-stu-id="97a96-141">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="97a96-142">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="97a96-142">Click **OK**.</span></span>

18. <span data-ttu-id="97a96-143">Clique em **Aplicar** no painel de detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="97a96-143">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="97a96-144">Clique em **Regra de Teste** para verificar se a nova regra está definida corretamente.</span><span class="sxs-lookup"><span data-stu-id="97a96-144">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="97a96-145">Para modificar uma regra de publicação Web existente para adicionar o SAN de Descoberta Automática externa e URL</span><span class="sxs-lookup"><span data-stu-id="97a96-145">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="97a96-146">Clique em **Iniciar**, aponte para **Programas**, aponte para **Microsoft Forefront TMG** e clique em **Gerenciamento do Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="97a96-146">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="97a96-147">Você irá repetir a modificação para cada regra de publicação e ouvinte que possuir.</span><span class="sxs-lookup"><span data-stu-id="97a96-147">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="97a96-148">Normalmente, será uma regra e um ouvinte para os pools de front-ends e um para os diretores opcionais ou pools de diretores, se você os tiver implantado.</span><span class="sxs-lookup"><span data-stu-id="97a96-148">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="97a96-p107">No painel à esquerda, expanda **ServerName**, clique com o botão direito em **Política de firewall** e clique na regra aplicável. Na aba **Tarefas**, clique na **regra Editar selecionado**.</span><span class="sxs-lookup"><span data-stu-id="97a96-p107">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="97a96-151">Na aba **Nome público**, em **Esta regra se aplica a**, selecione **Solicitações para os seguintes sites da Web**.</span><span class="sxs-lookup"><span data-stu-id="97a96-151">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="97a96-152">Clique em **Adicionar**, digite o nome do site de Descoberta Automática novo (por exemplo, “lyncdiscover.contoso.com”) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="97a96-152">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="97a96-p108">Na aba **Ouvinte**, clique em **Selecionar certificado** e atribua o novo certificado com as entradas SAN da Descoberta Automática adicionadas. Feche o Ouvinte e as propriedades de Publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="97a96-p108">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="97a96-155">Clique em **Aplicar** no painel de detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="97a96-155">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="97a96-156">Clique em **Testar regra** para verificar se a nova regra foi definida corretamente.</span><span class="sxs-lookup"><span data-stu-id="97a96-156">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="97a96-157">Para criar uma regra de publicação na Web para a porta 80</span><span class="sxs-lookup"><span data-stu-id="97a96-157">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="97a96-158">Clique em **Iniciar**, aponte para **Programas**, **Microsoft Forefront TMG** e, então, clique em **Forefront TMG Management**.</span><span class="sxs-lookup"><span data-stu-id="97a96-158">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="97a96-159">No painel esquerdo, expanda **Nome do Servidor**, clique com o botão direito do mouse em **Diretiva de Firewall**, aponte para **Novo** e clique em **Regra de Publicação de Site**.</span><span class="sxs-lookup"><span data-stu-id="97a96-159">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="97a96-160">Na página **Bem-vindo à nova regra de publicação na Web**, digite um nome para exibição para a nova regra de publicação (por exemplo, Descoberta Automática do Lync (HTTP)).</span><span class="sxs-lookup"><span data-stu-id="97a96-160">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="97a96-161">Na página **Selecionar Ação de Regra**, selecione **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="97a96-161">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="97a96-162">Na página **Tipo de Publicação**, selecione **Publicar um único site ou um balanceador de carga na Web** e clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="97a96-162">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="97a96-163">Na página **Segurança da Conexão do Servidor**, selecione **Usar conexões não seguras para conectar ao servidor Web ou ao farm de servidores publicado**.</span><span class="sxs-lookup"><span data-stu-id="97a96-163">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="97a96-164">Na página **detalhes de publicação interna** , em **nome do site interno**, digite o endereço VIP do balanceador de carga de hardware (HLB) na frente do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="97a96-164">On the **Internal Publishing Details** page, in **Internal Site name**, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="97a96-165">Na página **detalhes de publicação interna** , em **caminho (opcional)**, digite \*\* / \*\* como o caminho da pasta a ser publicada e, em seguida, selecione **encaminhar o cabeçalho de host original em vez do especificado no campo nome do site interno**.</span><span class="sxs-lookup"><span data-stu-id="97a96-165">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="97a96-166">Na página **Detalhes do Nome Público**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="97a96-166">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="97a96-167">Em **Aceitar Solicitações para**, selecione **Este nome de domínio**.</span><span class="sxs-lookup"><span data-stu-id="97a96-167">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="97a96-168">Em **nome público**, digite **lyncdiscover.** \<sipdomain\> (a URL externa do serviço de descoberta automática).</span><span class="sxs-lookup"><span data-stu-id="97a96-168">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="97a96-169">Em **caminho**, digite \*\* / \*\*.</span><span class="sxs-lookup"><span data-stu-id="97a96-169">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="97a96-170">Em **Selecionar Ouvinte da Web**, em **Ouvinte da Web**, selecione um Ouvinte da Web ou use o Assistente de Nova Definição de Ouvinte da Web para criar um novo.</span><span class="sxs-lookup"><span data-stu-id="97a96-170">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="97a96-171">Na página **Delegação de Autenticação**, selecione **Nenhuma delegação, e o cliente não pode autenticar diretamente**.</span><span class="sxs-lookup"><span data-stu-id="97a96-171">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="97a96-172">Na página **Conjunto de Usuários**, selecione **Todos os Usuários**.</span><span class="sxs-lookup"><span data-stu-id="97a96-172">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="97a96-173">Na página **Concluindo o Assistente de Nova Regra de Publicação de Web**, verifique se as configurações da regra de publicação de Web estão corretas e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="97a96-173">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="97a96-174">Na lista Forefront TMG de regras de publicação, clique duas vezes na nova regra que você acabou de adicionar para abrir **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="97a96-174">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="97a96-175">Na guia **Ponte**, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="97a96-175">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="97a96-176">Selecione **Servidor Web**.</span><span class="sxs-lookup"><span data-stu-id="97a96-176">Select **Web server**.</span></span>
    
      - <span data-ttu-id="97a96-177">Selecione   **Redirecionar solicitações para a porta HTTP** e digite **8080** para o número da porta.</span><span class="sxs-lookup"><span data-stu-id="97a96-177">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="97a96-178">Verifique se **Redirecionar solicitações para a porta SSL** não está selecionada.</span><span class="sxs-lookup"><span data-stu-id="97a96-178">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="97a96-179">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="97a96-179">Click **OK**.</span></span>

17. <span data-ttu-id="97a96-180">Clique em **Aplicar** no painel de detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="97a96-180">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="97a96-181">Clique em **Regra de Teste** para verificar se a nova regra está definida corretamente.</span><span class="sxs-lookup"><span data-stu-id="97a96-181">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="97a96-182">Verifique se a URL do Serviço Descoberta Automática externo não está definida em nenhuma outra regra de publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="97a96-182">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="97a96-183">Confira também</span><span class="sxs-lookup"><span data-stu-id="97a96-183">See Also</span></span>


[<span data-ttu-id="97a96-184">Configurando servidores de proxy reverso para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97a96-184">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[<span data-ttu-id="97a96-185">Requisitos técnicos para mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97a96-185">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

