---
title: 'Lync Server 2013: Configurar regras de publicação na Web para um único pool interno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ffe61072df14e28c20c45eb72302905986c6357
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="1d140-102">Configurar regras de publicação na Web para um único pool interno no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d140-102">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d140-103">_**Tópico da última modificação:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="1d140-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="1d140-104">Microsoft Forefront Threat Management Gateway 2010 e roteamento de solicitação de aplicativo do Internet Information Server (IIS ARR) usa regras de publicação na Web para publicar recursos internos, como uma URL de reunião, para os usuários da Internet.</span><span class="sxs-lookup"><span data-stu-id="1d140-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="1d140-105">Além das URLs de serviços Web para os diretórios virtuais, você também deve criar regras de publicação para URLs simples, a URL LyncDiscover e o Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="1d140-105">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="1d140-106">Para cada URL simples, você deve criar uma regra individual no proxy inverso que aponta para essa URL simples.</span><span class="sxs-lookup"><span data-stu-id="1d140-106">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="1d140-107">Se você estiver implantando a mobilidade e usando a descoberta automática, será necessário criar uma regra de publicação para a URL do serviço de descoberta automática externa.</span><span class="sxs-lookup"><span data-stu-id="1d140-107">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="1d140-108">A descoberta automática também requer regras de publicação para a URL de serviços Web externos do Lync Server para o pool de directors e para o pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="1d140-108">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="1d140-109">Para obter detalhes sobre como criar as regras de publicação na Web para descoberta automática, consulte Configurando [o proxy reverso para a mobilidade no Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="1d140-109">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="1d140-110">Use os procedimentos a seguir para criar regras de publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="1d140-110">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1d140-111">Esses procedimentos pressupõem que você tenha instalado a edição padrão do Forefront Threat Management Gateway (TMG) 2010 ou instalou e configurou o Internet Information Server com a extensão de roteamento de solicitação de aplicativo (IIS ARR).</span><span class="sxs-lookup"><span data-stu-id="1d140-111">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="1d140-112">Você usa a TMG ou a ARR do IIS.</span><span class="sxs-lookup"><span data-stu-id="1d140-112">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="1d140-113">Para criar uma regra de publicação do servidor Web no computador executando o TMG 2010</span><span class="sxs-lookup"><span data-stu-id="1d140-113">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="1d140-114">Clique em **Iniciar**, selecionar **programas**, selecionar **Microsoft Forefront TMG**e, em seguida, clique em gerenciamento do **Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="1d140-114">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="1d140-115">No painel esquerdo, expanda **ServerName**, clique com o botão direito do mouse em **política de firewall**, selecione **novo**e clique em regra de **publicação de site da Web**.</span><span class="sxs-lookup"><span data-stu-id="1d140-115">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="1d140-116">Na página **Bem-vindo à nova regra de publicação na Web** , digite um nome para exibição para a regra de publicação (por exemplo, LyncServerWebDownloadsRule).</span><span class="sxs-lookup"><span data-stu-id="1d140-116">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="1d140-117">Na página **Selecionar ação da regra** , selecione **permitir**.</span><span class="sxs-lookup"><span data-stu-id="1d140-117">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="1d140-118">Na página **tipo de publicação** , selecione **publicar um único site da Web ou um balanceador de carga**.</span><span class="sxs-lookup"><span data-stu-id="1d140-118">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="1d140-119">Na página **segurança de conexão do servidor** , selecione **usar SSL para se conectar ao servidor Web ou ao farm de servidores publicado**.</span><span class="sxs-lookup"><span data-stu-id="1d140-119">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="1d140-120">Na página **detalhes da publicação interna** , digite o nome de domínio totalmente qualificado (FQDN) do Web farm interno que hospeda o conteúdo da sua reunião e o conteúdo do catálogo de endereços na caixa **nome do site interno** .</span><span class="sxs-lookup"><span data-stu-id="1d140-120">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d140-121">Se o seu servidor interno for um servidor de edição padrão, esse FQDN será o FQDN do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="1d140-121">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="1d140-122">Se o seu servidor interno for um pool de front-ends, esse FQDN será um VIP (IP virtual) do balanceador de carga de hardware que carrega o balanceamento de servidores internos de Web farm.</span><span class="sxs-lookup"><span data-stu-id="1d140-122">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="1d140-123">O servidor TMG deve ser capaz de resolver o FQDN para o endereço IP do servidor Web interno.</span><span class="sxs-lookup"><span data-stu-id="1d140-123">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="1d140-124">Se o servidor TMG não conseguir resolver o FQDN para o endereço IP correto, você pode selecionar <STRONG>usar um nome de computador ou endereço IP para se conectar ao servidor publicado</STRONG>e, em seguida, na caixa <STRONG>nome do computador ou</STRONG> <STRONG>endereço IP</STRONG> , digitar o endereço IP do w "interno" servidor da EB.</span><span class="sxs-lookup"><span data-stu-id="1d140-124">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="1d140-125">Se fizer isso, você deve garantir que a porta 53 esteja aberta no servidor TMG e que ela possa alcançar um servidor DNS que reside na rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="1d140-125">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="1d140-126">Você também pode usar entradas no arquivo hosts locais para fornecer resolução de nomes.</span><span class="sxs-lookup"><span data-stu-id="1d140-126">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="1d140-127">Na página **detalhes da publicação interna** , na caixa **caminho (opcional)** , digite \*\* / \*\* como o caminho da pasta a ser publicada.</span><span class="sxs-lookup"><span data-stu-id="1d140-127">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d140-128">No assistente de publicação de site, você pode especificar apenas um caminho.</span><span class="sxs-lookup"><span data-stu-id="1d140-128">In the website publishing wizard you can only specify one path.</span></span> <span data-ttu-id="1d140-129">Caminhos adicionais podem ser adicionados modificando as propriedades da regra.</span><span class="sxs-lookup"><span data-stu-id="1d140-129">Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="1d140-130">Na página **detalhes do nome público** , confirme se **esse nome de domínio** está selecionado em **aceitar solicitações por**, digite o FQDN dos serviços Web externos, na caixa **nome público** .</span><span class="sxs-lookup"><span data-stu-id="1d140-130">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="1d140-131">Na página **selecionar ouvinte da Web** , clique em **novo** para abrir o assistente de definição de novo ouvinte da Web.</span><span class="sxs-lookup"><span data-stu-id="1d140-131">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="1d140-132">Na página **Bem-vindo ao novo assistente de ouvinte da Web** , digite um nome para o ouvinte da Web na caixa **nome do ouvinte da Web** (por exemplo, LyncServerWebServers).</span><span class="sxs-lookup"><span data-stu-id="1d140-132">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="1d140-133">Na página **segurança de conexão do cliente** , selecione **exigir conexões SSL seguras com clientes**.</span><span class="sxs-lookup"><span data-stu-id="1d140-133">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="1d140-134">Na página **endereço IP do ouvinte da Web** , selecione **externo**e clique em **selecionar endereços IP**.</span><span class="sxs-lookup"><span data-stu-id="1d140-134">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="1d140-135">Na página **seleção de IP de ouvinte externo** , selecione o **endereço IP especificado no computador Forefront TMG na rede selecionada**, selecione o endereço IP apropriado e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1d140-135">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="1d140-136">Na página **certificados SSL** de ouvinte, selecione **atribuir um certificado para cada endereço IP**, selecione o endereço IP associado ao FQDN da Web externa e clique em **Selecionar certificado**.</span><span class="sxs-lookup"><span data-stu-id="1d140-136">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="1d140-137">Na página **Selecionar certificado** , selecione o certificado que corresponde aos nomes públicos especificados na etapa 9, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="1d140-137">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="1d140-138">Na página **configuração de autenticação** , selecione **sem autenticação**.</span><span class="sxs-lookup"><span data-stu-id="1d140-138">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="1d140-139">Na página **configuração de logon único** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1d140-139">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="1d140-140">Na página **concluindo o assistente de ouvinte da Web** , verifique se as configurações do **ouvinte da Web** estão corretas e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="1d140-140">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="1d140-141">Na página **delegação de autenticação** , selecione **sem delegação, mas o cliente pode autenticar diretamente**.</span><span class="sxs-lookup"><span data-stu-id="1d140-141">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="1d140-142">Na página **conjunto de usuários** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1d140-142">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="1d140-143">Na página **concluindo o assistente de nova regra de publicação na Web** , verifique se as configurações da regra de publicação da Web estão corretas e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="1d140-143">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="1d140-144">Clique em **aplicar** no painel detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="1d140-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="1d140-145">Para criar uma regra de publicação do servidor Web no computador que está executando o IIS ARR</span><span class="sxs-lookup"><span data-stu-id="1d140-145">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="1d140-146">Vincule o certificado que você usará para o proxy reverso para o protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1d140-146">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="1d140-147">Clique em **Iniciar**, selecione **programas**, selecione **Ferramentas administrativas**e, em seguida, clique em **Gerenciador dos serviços de informações da Internet (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="1d140-147">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d140-148">Ajuda adicional, capturas de tela e orientações sobre a implantação e configuração do IIS ARR podem ser encontradas no artigo NextHop <A href="http://go.microsoft.com/fwlink/?linkid=293391">usando o IIS arr como um proxy inverso para o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1d140-148">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="http://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="1d140-149">Se você ainda não tiver feito isso, importe o certificado que será usado para o proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="1d140-149">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="1d140-150">No **Gerenciador dos serviços de informações da Internet (IIS)**, clique no nome do servidor proxy reverso no tamanho esquerdo do console.</span><span class="sxs-lookup"><span data-stu-id="1d140-150">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="1d140-151">No meio do console em **IIS** , localize **certificados do servidor**.</span><span class="sxs-lookup"><span data-stu-id="1d140-151">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="1d140-152">Clique com o botão direito do mouse em **certificados de servidor** e selecione **abrir recurso**.</span><span class="sxs-lookup"><span data-stu-id="1d140-152">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="1d140-153">No lado direito do console, clique em **importar..**..</span><span class="sxs-lookup"><span data-stu-id="1d140-153">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="1d140-154">Digite o caminho e o nome do arquivo do certificado com a extensão ou clique em **...**</span><span class="sxs-lookup"><span data-stu-id="1d140-154">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="1d140-155">para procurar o certificado.</span><span class="sxs-lookup"><span data-stu-id="1d140-155">to browse for the certificate.</span></span> <span data-ttu-id="1d140-156">Selecione o certificado e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="1d140-156">Select the certificate and click **Open**.</span></span> <span data-ttu-id="1d140-157">Forneça a senha usada para proteger a chave privada (se você tiver atribuído uma senha ao exportar o certificado e a chave particular).</span><span class="sxs-lookup"><span data-stu-id="1d140-157">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="1d140-158">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d140-158">Click **OK**.</span></span> <span data-ttu-id="1d140-159">Se a importação do certificado tiver sido bem-sucedida, o certificado será exibido como uma entrada no meio do console como uma entrada em **certificados de servidor**.</span><span class="sxs-lookup"><span data-stu-id="1d140-159">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="1d140-160">Atribua o certificado a ser usado por HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1d140-160">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="1d140-161">No lado esquerdo do console, selecione o **site da Web padrão** do IIS Server.</span><span class="sxs-lookup"><span data-stu-id="1d140-161">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="1d140-162">No lado direito, clique em **associações..**..</span><span class="sxs-lookup"><span data-stu-id="1d140-162">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="1d140-163">Na caixa de diálogo **associações de site** , clique em **Adicionar..**..</span><span class="sxs-lookup"><span data-stu-id="1d140-163">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="1d140-164">Na caixa de diálogo **Adicionar Associação de site** , em **tipo:**, selecione **https**.</span><span class="sxs-lookup"><span data-stu-id="1d140-164">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="1d140-165">Selecionar https permitirá que você selecione o certificado que será usado para https.</span><span class="sxs-lookup"><span data-stu-id="1d140-165">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="1d140-166">Em **certificado SSL:**, selecione o certificado que você importou para o proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="1d140-166">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="1d140-167">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d140-167">Click **OK**.</span></span> <span data-ttu-id="1d140-168">Em seguida, clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="1d140-168">Then, click **Close**.</span></span> <span data-ttu-id="1d140-169">O certificado agora está associado ao proxy reverso para Secure Socket Layer (SSL) e Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="1d140-169">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1d140-170">Se você receber um aviso ao fechar as caixas de diálogo de associações em que os certificados intermediários estão ausentes, você precisará localizar e importar o certificado de autoridade raiz da CA pública e qualquer certificado intermediário da autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="1d140-170">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="1d140-171">Consulte as instruções na CA pública para a qual você solicitou o certificado e siga as instruções para solicitar e importar uma cadeia de certificados.</span><span class="sxs-lookup"><span data-stu-id="1d140-171">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="1d140-172">Se você exportou o certificado do servidor de borda, poderá exportar o certificado da CA raiz e qualquer certificado de autoridade de certificação intermediário associado ao servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="1d140-172">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="1d140-173">Importar o certificado da CA raiz para o computador (não ser confundido com o armazenamento do usuário) armazenamento de autoridades de certificação raiz confiáveis e certificados intermediários no repositório de autoridades de certificação intermediárias do computador.</span><span class="sxs-lookup"><span data-stu-id="1d140-173">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="1d140-174">No lado esquerdo do console abaixo do nome do servidor IIS, clique com o botão direito do mouse em **farm de servidores** e clique em **criar farm de servidores..**..</span><span class="sxs-lookup"><span data-stu-id="1d140-174">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1d140-175">Se você não vir o nó <STRONG>farms de servidores</STRONG> , será necessário instalar o roteamento de solicitação de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1d140-175">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="1d140-176">Para obter detalhes, consulte Configurando <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">servidores proxy reverso para o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1d140-176">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="1d140-177">Na caixa de diálogo **criar farm de servidores** no **nome do farm de servidores**, digite um nome (isso pode ser um nome amigável para fins de identificação) para a primeira URL.</span><span class="sxs-lookup"><span data-stu-id="1d140-177">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="1d140-178">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="1d140-178">Click **Next**.</span></span>

6.  <span data-ttu-id="1d140-179">Na caixa de diálogo **Adicionar servidor** no **endereço do servidor**, digite o nome de domínio totalmente qualificado (FQDN) dos serviços Web externos em seu servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1d140-179">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="1d140-180">Os nomes que serão usados aqui para fins de exemplo são os mesmos que são usados na seção de planejamento para o proxy reverso, de [Resumo de certificado-proxy reverso no Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="1d140-180">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="1d140-181">Fazendo referência ao plano de proxy reverso, digitamos o `webext.contoso.com`FQDN.</span><span class="sxs-lookup"><span data-stu-id="1d140-181">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="1d140-182">Confirme se a caixa de seleção ao lado de **online** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="1d140-182">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="1d140-183">Clique em **Adicionar** para adicionar o servidor ao pool de servidores Web para essa configuração.</span><span class="sxs-lookup"><span data-stu-id="1d140-183">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1d140-184">O Lync Server usa balanceadores de carga de hardware para o diretor de pools e servidores front-end para tráfego HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1d140-184">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="1d140-185">Você só vai fornecer um FQDN ao adicionar um servidor ao farm de servidores do IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="1d140-185">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="1d140-186">O FQDN será o servidor front-end ou o director em configurações de servidor sem pool ou o FQDN do balanceador de carga de hardware configurado para pools de servidores.</span><span class="sxs-lookup"><span data-stu-id="1d140-186">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="1d140-187">O único método suportado para balancear a carga de tráfego HTTP e HTTPS é usando balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="1d140-187">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="1d140-188">Na caixa de diálogo **Adicionar servidor** , clique em **Configurações avançadas..**..</span><span class="sxs-lookup"><span data-stu-id="1d140-188">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="1d140-189">Isso abre uma caixa de diálogo para definir o roteamento de solicitação de aplicativo para solicitações para o FQDN configurado.</span><span class="sxs-lookup"><span data-stu-id="1d140-189">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="1d140-190">O objetivo é redefinir qual porta será usada quando a solicitação for processada pelo IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="1d140-190">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="1d140-191">Por padrão, a porta HTTP de destino deve ser definida como 8080.</span><span class="sxs-lookup"><span data-stu-id="1d140-191">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="1d140-192">Clique em ao lado do **httpPort** atual do 80 e defina o valor como **8080**.</span><span class="sxs-lookup"><span data-stu-id="1d140-192">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="1d140-193">Clique em ao lado do **httpsPort** atual do 443 e defina o valor como **4443**.</span><span class="sxs-lookup"><span data-stu-id="1d140-193">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="1d140-194">Deixe o parâmetro de **peso** em 100.</span><span class="sxs-lookup"><span data-stu-id="1d140-194">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="1d140-195">Se necessário, você pode redefinir os pesos de uma determinada regra quando tiver estatísticas da linha de base.</span><span class="sxs-lookup"><span data-stu-id="1d140-195">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="1d140-196">Clique em **concluir** para concluir esta parte da configuração da regra.</span><span class="sxs-lookup"><span data-stu-id="1d140-196">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="1d140-197">Você pode ver uma caixa de diálogo regravar regras que informa que o Gerenciador do IIS pode criar uma regra de regravação de URL para direcionar todas as solicitações de entrada para o farm de servidores automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1d140-197">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="1d140-198">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="1d140-198">Click **Yes**.</span></span> <span data-ttu-id="1d140-199">Você vai ajustar as regras manualmente, mas selecionar Sim define a configuração inicial..</span><span class="sxs-lookup"><span data-stu-id="1d140-199">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="1d140-200">Clique no nome do farm de servidores que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="1d140-200">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="1d140-201">Em **farm de servidores** no modo de exibição recursos do Gerenciador do IIS, clique duas vezes em **cache**.</span><span class="sxs-lookup"><span data-stu-id="1d140-201">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="1d140-202">Desmarque **Habilitar cache de disco**.</span><span class="sxs-lookup"><span data-stu-id="1d140-202">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="1d140-203">Clique em **aplicar** à direita.</span><span class="sxs-lookup"><span data-stu-id="1d140-203">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="1d140-204">Clique no nome do farm de servidores.</span><span class="sxs-lookup"><span data-stu-id="1d140-204">Click the name of the server farm.</span></span> <span data-ttu-id="1d140-205">Em **Server farm** in IIS Manager Features View, clique duas vezes em **proxy**.</span><span class="sxs-lookup"><span data-stu-id="1d140-205">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="1d140-206">Na página Configurações de proxy, altere o valor de **tempo limite (segundos)** para um valor apropriado para a sua implantação.</span><span class="sxs-lookup"><span data-stu-id="1d140-206">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="1d140-207">Clique em **aplicar** para salvar a alteração.</span><span class="sxs-lookup"><span data-stu-id="1d140-207">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1d140-208">O valor de tempo limite do proxy é um número que varia de implantação para implantação.</span><span class="sxs-lookup"><span data-stu-id="1d140-208">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="1d140-209">Você deve monitorar a implantação e modificar o valor da melhor experiência para os clientes.</span><span class="sxs-lookup"><span data-stu-id="1d140-209">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="1d140-210">Talvez seja possível definir o valor tão baixo quanto 200.</span><span class="sxs-lookup"><span data-stu-id="1d140-210">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="1d140-211">Se você estiver oferecendo suporte a clientes móveis do Lync em seu ambiente, deve definir o valor como 960 para permitir o tempo limite de notificações por push do Office 365 que têm um valor de tempo limite de 900.</span><span class="sxs-lookup"><span data-stu-id="1d140-211">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="1d140-212">É muito provável que você precise aumentar o valor de tempo limite para evitar que o cliente se desconecte quando o valor for muito baixo ou diminuir o número se as conexões pelo proxy não forem desconectadas e muito demoradas após o cliente ter sido desconectado.</span><span class="sxs-lookup"><span data-stu-id="1d140-212">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="1d140-213">Monitoramento e alinhamento base o que é normal para o seu ambiente é o único meio preciso para determinar onde está a configuração certa para esse valor.</span><span class="sxs-lookup"><span data-stu-id="1d140-213">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="1d140-214">Clique no nome do farm de servidores.</span><span class="sxs-lookup"><span data-stu-id="1d140-214">Click the name of the server farm.</span></span> <span data-ttu-id="1d140-215">Em **farm de servidores** no modo de exibição recursos do Gerenciador do IIS, clique duas vezes em **regras de roteamento**.</span><span class="sxs-lookup"><span data-stu-id="1d140-215">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="1d140-216">Na caixa de diálogo regras de roteamento em roteamento, desmarque a caixa de seleção ao lado de habilitar o carregamento de SSL.</span><span class="sxs-lookup"><span data-stu-id="1d140-216">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="1d140-217">Se a capacidade de desmarcar a caixa de seleção não estiver disponível, marque a caixa de seleção **usar URL regravar para inspecionar solicitações de entrada**.</span><span class="sxs-lookup"><span data-stu-id="1d140-217">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="1d140-218">Clique em **aplicar** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="1d140-218">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1d140-219">Não há suporte para o carregamento de SSL pelo proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="1d140-219">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="1d140-220">Repita as etapas 5-11 para cada URL que deve passar pelo proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="1d140-220">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="1d140-221">Uma lista comum seria a seguinte:</span><span class="sxs-lookup"><span data-stu-id="1d140-221">A common list would be the following:</span></span>
    
      - <span data-ttu-id="1d140-222">Serviços Web de servidor front-end externo: webext.contoso.com (já configurado pela passagem inicial)</span><span class="sxs-lookup"><span data-stu-id="1d140-222">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="1d140-223">Serviços Web de diretor externo para Director: webdirext.contoso.com (opcional se um diretor estiver implantado)</span><span class="sxs-lookup"><span data-stu-id="1d140-223">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="1d140-224">Reunião simples de URL: meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d140-224">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="1d140-225">URL simples de discagem: dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d140-225">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="1d140-226">URL de descoberta automática do Lync: lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d140-226">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="1d140-227">URL do servidor dos Office Web Apps: officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1d140-227">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="1d140-228">A URL do servidor do Office Web Apps usará um endereço httpsPort diferente.</span><span class="sxs-lookup"><span data-stu-id="1d140-228">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="1d140-229">Na etapa 7, você define o <STRONG>httpsPort</STRONG> como <STRONG>443</STRONG> e o <STRONG>httpPort</STRONG> como a porta <STRONG>80</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1d140-229">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="1d140-230">Todas as outras definições de configuração são iguais.</span><span class="sxs-lookup"><span data-stu-id="1d140-230">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="1d140-231">No lado esquerdo do console, clique no nome do servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="1d140-231">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="1d140-232">No meio do console, localize a **URL reescrita** no **IIS**.</span><span class="sxs-lookup"><span data-stu-id="1d140-232">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="1d140-233">Clique duas vezes em URL reescrever para abrir a configuração de regras de recriação de URL.</span><span class="sxs-lookup"><span data-stu-id="1d140-233">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="1d140-234">Você deve ver regras para cada Server farm que você criou nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="1d140-234">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="1d140-235">Se você não tiver, confirme se clicou no nome do **servidor IIS** imediatamente abaixo do nó da **página inicial** no console do Gerenciador de servidor de informações da Internet.</span><span class="sxs-lookup"><span data-stu-id="1d140-235">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="1d140-236">Na caixa de diálogo de reconfiguração de **URL** , usando webext.contoso.com como exemplo, o nome completo da regra conforme exibido **é\_arr\_webext.contoso.com LoadBalance\_SSL**.</span><span class="sxs-lookup"><span data-stu-id="1d140-236">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="1d140-237">Clique duas vezes na regra para abrir a caixa de diálogo **Editar regra de entrada** .</span><span class="sxs-lookup"><span data-stu-id="1d140-237">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="1d140-238">Clique em **Adicionar..** .</span><span class="sxs-lookup"><span data-stu-id="1d140-238">Click **Add…**</span></span> <span data-ttu-id="1d140-239">na caixa de diálogo **condições** .</span><span class="sxs-lookup"><span data-stu-id="1d140-239">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="1d140-240">Na **condição adicionar** na **entrada de condição:** digite **{http\_host}**.</span><span class="sxs-lookup"><span data-stu-id="1d140-240">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="1d140-241">(À medida que você digita, é exibida uma caixa de diálogo que permite que você selecione a condição).</span><span class="sxs-lookup"><span data-stu-id="1d140-241">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="1d140-242">em **verificar se a cadeia de caracteres de entrada:** seleção **corresponde ao padrão**.</span><span class="sxs-lookup"><span data-stu-id="1d140-242">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="1d140-243">No tipo **\*** de **entrada padrão** .</span><span class="sxs-lookup"><span data-stu-id="1d140-243">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="1d140-244">O **caso de ignorar** deve ser selecionado.</span><span class="sxs-lookup"><span data-stu-id="1d140-244">**Ignore case** should be selected.</span></span> <span data-ttu-id="1d140-245">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d140-245">Click **OK**.</span></span>
    
      - <span data-ttu-id="1d140-246">Role a tela para baixo na caixa de diálogo **Editar regra de entrada** para localizar a caixa de diálogo de **ação** .</span><span class="sxs-lookup"><span data-stu-id="1d140-246">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="1d140-247">**Tipo de ação:** deve ser definido como **rota para o farm de servidores**, **esquema:** definido como **https://**, **farm de servidores:** definido como a URL à qual essa regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="1d140-247">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="1d140-248">Para este exemplo, isso deve ser definido como **webext.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="1d140-248">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="1d140-249">**Caminho:** é definido como **/{R: 0}**</span><span class="sxs-lookup"><span data-stu-id="1d140-249">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="1d140-250">Clique em **aplicar** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="1d140-250">Click **Apply** to save your changes.</span></span> <span data-ttu-id="1d140-251">Clique em **voltar às regras** para retornar às regras de regravação de URL.</span><span class="sxs-lookup"><span data-stu-id="1d140-251">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="1d140-252">Repita o procedimento definido na etapa 14 para cada regra de regravação de SSL que você definiu, uma por URL de farm de servidores.</span><span class="sxs-lookup"><span data-stu-id="1d140-252">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1d140-253">Por padrão, as regras HTTP também são criadas e são indicadas pelo nome semelhante às regras de SSL.</span><span class="sxs-lookup"><span data-stu-id="1d140-253">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="1d140-254">Para o nosso exemplo atual, a regra HTTP seria nomeada <STRONG>ARR_webext. contoso. com _loadbalance</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1d140-254">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="1d140-255">Nenhuma modificação é necessária para essas regras e eles podem ser ignorados com segurança.</span><span class="sxs-lookup"><span data-stu-id="1d140-255">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="1d140-256">Para modificar as propriedades da regra de publicação na Web no TMG 2010</span><span class="sxs-lookup"><span data-stu-id="1d140-256">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="1d140-257">Clique em **Iniciar**, aponte para **programas**, selecione **Microsoft Forefront TMG**e clique em **Gerenciamento do Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="1d140-257">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="1d140-258">No painel esquerdo, expanda **ServerName**e clique em **política de firewall**.</span><span class="sxs-lookup"><span data-stu-id="1d140-258">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="1d140-259">No painel detalhes, clique com o botão direito do mouse na regra de publicação do servidor Web que você criou no procedimento anterior (por exemplo, LyncServerExternalRule) e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1d140-259">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="1d140-260">Na página **Propriedades** , na guia **de** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1d140-260">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="1d140-261">Na lista **esta regra se aplica ao tráfego dessas fontes** , clique em **qualquer lugar**e, em seguida, clique em **remover**.</span><span class="sxs-lookup"><span data-stu-id="1d140-261">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="1d140-262">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1d140-262">Click **Add**.</span></span>
    
      - <span data-ttu-id="1d140-263">Em **adicionar entidades de rede**, expanda **redes**, clique em **externo**, clique em **Adicionar**e, em seguida, clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="1d140-263">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="1d140-264">Na guia **para** , certifique-se de que a caixa de seleção **encaminhar o cabeçalho original do host, em vez da opção atual** está marcada.</span><span class="sxs-lookup"><span data-stu-id="1d140-264">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="1d140-265">Na guia **ponte** , marque a caixa de seleção redirecionar **solicitação para porta SSL** e especifique a porta **4443**.</span><span class="sxs-lookup"><span data-stu-id="1d140-265">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="1d140-266">Na guia **nome público** , adicione as URLs simples (por exemplo, meet.contoso.com e Dialin.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1d140-266">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="1d140-267">Clique em **aplicar** para salvar as alterações e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d140-267">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="1d140-268">Clique em **aplicar** no painel detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="1d140-268">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="1d140-269">Para modificar as propriedades da regra de publicação na Web no IIS ARR</span><span class="sxs-lookup"><span data-stu-id="1d140-269">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="1d140-270">Clique em **Iniciar**, selecione **programas**, selecione **Ferramentas administrativas**e, em seguida, clique em **Gerenciador dos serviços de informações da Internet (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="1d140-270">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="1d140-271">No lado esquerdo do console, clique no nome do servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="1d140-271">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="1d140-272">No meio do console, localize a **URL reescrita** no **IIS**.</span><span class="sxs-lookup"><span data-stu-id="1d140-272">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="1d140-273">Clique duas vezes em URL reescrever para abrir a configuração de regras de recriação de URL.</span><span class="sxs-lookup"><span data-stu-id="1d140-273">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="1d140-274">Clique duas vezes na regra que você precisa modificar.</span><span class="sxs-lookup"><span data-stu-id="1d140-274">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="1d140-275">Faça suas modificações, conforme necessário, em **correspondência URL**, **condições**, **variáveis do servidor** ou **ação**.</span><span class="sxs-lookup"><span data-stu-id="1d140-275">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="1d140-276">Clique em **aplicar** para confirmar as alterações.</span><span class="sxs-lookup"><span data-stu-id="1d140-276">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="1d140-277">Clique em **retornar às regras** para modificar outras regras ou fechar o console do **Gerenciador do IIS** se você tiver concluído suas alterações.</span><span class="sxs-lookup"><span data-stu-id="1d140-277">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

