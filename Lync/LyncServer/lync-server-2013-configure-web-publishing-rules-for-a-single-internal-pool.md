---
title: 'Lync Server 2013: configurar regras de publicação na Web para um único pool interno'
description: 'Lync Server 2013: configurar regras de publicação na Web para um único pool interno.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45015c90fdac92fb488affc871f2cfaf9d7506a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560507"
---
# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="9c176-103">Configurar regras de publicação na Web para um único pool interno no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c176-103">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c176-104">_**Última modificação do tópico:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="9c176-104">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="9c176-105">O Microsoft Forefront Threat Management Gateway 2010 e o roteamento de solicitações de aplicativos do Internet Information Server (IIS ARR) usam regras de publicação na Web para publicar recursos internos, como uma URL de reunião, para os usuários na Internet.</span><span class="sxs-lookup"><span data-stu-id="9c176-105">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="9c176-106">Além das URLs de serviços Web para os diretórios virtuais, você também deve criar regras de publicação para URLs simples, a URL do LyncDiscover e o servidor do Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="9c176-106">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="9c176-107">Para cada URL simples, é necessário criar uma regra individual no proxy inverso que aponta para essa URL simples.</span><span class="sxs-lookup"><span data-stu-id="9c176-107">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="9c176-108">Se você implantar a versão móvel e usar a descoberta automática, é necessário criar uma regra de publicação para a URL do Serviço de Descoberta Automática externo.</span><span class="sxs-lookup"><span data-stu-id="9c176-108">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="9c176-109">A descoberta automática também requer regras de publicação para a URL externa dos serviços Web do Lync Server para seu pool de diretores e pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="9c176-109">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="9c176-110">Para obter detalhes sobre como criar as regras de publicação na Web para descoberta automática, consulte [Configurando o proxy reverso para mobilidade no Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="9c176-110">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="9c176-111">Use os procedimentos a seguir para criar regras de publicação da Web.</span><span class="sxs-lookup"><span data-stu-id="9c176-111">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9c176-112">Estes procedimentos presumem que você tenha instalado a edição Standard do Forefront Threat Management Gateway (TMG) 2010 ou tenha instalado e configurado o Internet Information Server com a extensão de roteamento de solicitação de aplicativo (IIS ARR).</span><span class="sxs-lookup"><span data-stu-id="9c176-112">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="9c176-113">Você usa a TMG ou a ARR do IIS.</span><span class="sxs-lookup"><span data-stu-id="9c176-113">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="9c176-114">Para criar uma regra de publicação de servidor Web no computador que está executando o TMG 2010</span><span class="sxs-lookup"><span data-stu-id="9c176-114">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="9c176-115">Clique em **Iniciar**, selecione **Programas**, selecione **Microsoft Forefront TMG** e clique em **Gerenciamento de forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="9c176-115">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="9c176-116">No painel esquerdo, expanda **ServerName**, clique com o botão direito do mouse em **Política de firewall**, selecione **Novo** e clique em **Regra de publicação de site**.</span><span class="sxs-lookup"><span data-stu-id="9c176-116">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="9c176-117">Na página **Bem-vindo à Nova Regra de Publicação da Web**, digite um nome de exibição para a regra de publicação (por exemplo, LyncServerWebDownloadsRule).</span><span class="sxs-lookup"><span data-stu-id="9c176-117">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="9c176-118">Na página **Selecionar Ação da Regra**, selecione **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="9c176-118">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="9c176-119">Na página **Tipo de Publicação**, selecione **Publicar um único site ou um balanceador de carga na Web** e clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="9c176-119">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="9c176-120">Na página **Segurança da Conexão do Servidor**, selecione **Usar SSL para conectar ao servidor da Web publicado ou ao farm de servidores**.</span><span class="sxs-lookup"><span data-stu-id="9c176-120">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="9c176-121">Na página **Detalhes de Publicação Interna**, digite o FQDN (nome de domínio totalmente qualificado) da Web farm interna que hospeda o conteúdo das reuniões e o conteúdo do Catálogo de Endereços na caixa **Nome do site interno**.</span><span class="sxs-lookup"><span data-stu-id="9c176-121">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9c176-122">Se o seu servidor interno é um servidor Standard Edition, este FQDN é o FQDN do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9c176-122">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="9c176-123">Se seu servidor interno é um pool de Front-Ends, este FQDN é um IP virtual (VIP) de balanceador de carga de hardware que equilibra a carga dos servidores de farm da web internos.</span><span class="sxs-lookup"><span data-stu-id="9c176-123">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="9c176-124">O servidor TMG deve ser capaz de resolver o FQDN ao endereço IP do servidor web interno.</span><span class="sxs-lookup"><span data-stu-id="9c176-124">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="9c176-125">Se o servidor TMG não puder resolver o FQDN para o endereço IP correto, você poderá selecionar <STRONG>usar um nome de computador ou endereço IP para se conectar ao servidor publicado</STRONG>e, em seguida, na caixa <STRONG>nome do computador ou</STRONG> <STRONG>endereço IP</STRONG> , digite o endereço IP do servidor Web interno.</span><span class="sxs-lookup"><span data-stu-id="9c176-125">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="9c176-126">Se você fizer isso, você deve verificar se a porta 53 é aberta no servidor TMG e se ela pode acessar um servidor DNS que reside na rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="9c176-126">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="9c176-127">Também  pode usar as entradas no arquivo de hosts local para fornecer uma resolução de nome.</span><span class="sxs-lookup"><span data-stu-id="9c176-127">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="9c176-128">Na página **detalhes de publicação interna** , na caixa **caminho (opcional)** , digite **/\*** como o caminho da pasta a ser publicada.</span><span class="sxs-lookup"><span data-stu-id="9c176-128">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9c176-p105">No assistente de publicação de site, só é possível especificar um caminho. Caminhos adicionais podem ser adicionados modificando as propriedades da regra.</span><span class="sxs-lookup"><span data-stu-id="9c176-p105">In the website publishing wizard you can only specify one path. Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="9c176-131">Na página **Detalhes do Nome Público**, confirme se   \*\*Este nome de domínio \*\* está selecionado para **Aceitar Solicitações de**, digite o FQDN dos serviços Web externos na caixa **Nome Público**.</span><span class="sxs-lookup"><span data-stu-id="9c176-131">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="9c176-132">Na página **Selecionar Ouvinte da Web**, clique em **Novo** para abror o Assistente para Definição de Novo Ouvinte da Web.</span><span class="sxs-lookup"><span data-stu-id="9c176-132">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="9c176-133">Na página **Bem-vindo ao Assistente de Novo Ouvinte da Web**, digite um nome para o ouvinte da Web na caixa **Nome do ouvinte da Web** (por exemplo, LyncServerWebServers) e clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="9c176-133">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="9c176-134">Na página **Segurança da Conexão do Cliente**, selecione **Exigir conexões SSL seguras com clientes**.</span><span class="sxs-lookup"><span data-stu-id="9c176-134">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="9c176-135">Na página **Endereços IP do Ouvinte da Web**, selecione **Externo** e clique em **Selecionar Endereços IP**.</span><span class="sxs-lookup"><span data-stu-id="9c176-135">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="9c176-136">Na página **Seleção do IP do Ouvinte Externo**, selecione **Endereços IP especificados no computador do Forefront TMG da rede selecionada**, selecione o endereço IP apropriado e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9c176-136">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="9c176-137">Na página **Certificados SSL de Ouvinte**, selecione **Atribuir um certificado para cada endereço IP**, selecione o endereço IP que está associado ao FQDN da Web externo e clique em **Selecionar Certificado**.</span><span class="sxs-lookup"><span data-stu-id="9c176-137">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="9c176-138">Na página **Selecionar Certificado**, selecione o certificado que corresponde ao nome público especificado na etapa 9 e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="9c176-138">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="9c176-139">Na página **Configuração da Autenticação**, selecione **Sem Autenticação**.</span><span class="sxs-lookup"><span data-stu-id="9c176-139">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="9c176-140">Na página **Configurações de Logon Único**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9c176-140">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="9c176-141">Na página **Concluindo o Assistente de Novo Ouvinte da Web**, verifique se as configurações de **Ouvinte da Web** estão corretas e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="9c176-141">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="9c176-142">Na página **Delegação de autenticação**, selecione **Nenhuma delegação, mas o cliente pode autenticar diretamente**.</span><span class="sxs-lookup"><span data-stu-id="9c176-142">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="9c176-143">Na página **Conjunto de Usuários**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9c176-143">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="9c176-144">Na página **Concluir o novo assistente da regra de publicação da Web**, verifique se as configurações da regra de publicação da Web estão corretas e clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9c176-144">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="9c176-145">Clique em **Aplicar** no painel de detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="9c176-145">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="9c176-146">Para criar uma regra de publicação de servidor Web no computador que executa o IIS ARR</span><span class="sxs-lookup"><span data-stu-id="9c176-146">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="9c176-147">Vincule o certificado que você usará para o proxy reverso para o protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9c176-147">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="9c176-148">Clique em **Iniciar**, selecione **programas**, selecione **Ferramentas administrativas**e clique em **Gerenciador dos serviços de informações da Internet (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="9c176-148">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9c176-149">Ajuda adicional, capturas de tela e orientações sobre a implantação e configuração do IIS ARR podem ser encontradas no artigo NextHop <A href="https://go.microsoft.com/fwlink/?linkid=293391">usando o IIS arr como um proxy reverso para o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9c176-149">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="https://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="9c176-150">Se você ainda não tiver feito isso, importe o certificado que será usado para o proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="9c176-150">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="9c176-151">No **Gerenciador de serviços de informações da Internet (IIS)**, clique no nome do servidor proxy reverso no tamanho da esquerda do console.</span><span class="sxs-lookup"><span data-stu-id="9c176-151">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="9c176-152">No meio do console em **IIS** , localize **certificados de servidor**.</span><span class="sxs-lookup"><span data-stu-id="9c176-152">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="9c176-153">Clique com o botão direito do mouse em **certificados de servidor** e selecione **abrir recurso**.</span><span class="sxs-lookup"><span data-stu-id="9c176-153">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="9c176-154">No lado direito do console, clique em **importar...**.</span><span class="sxs-lookup"><span data-stu-id="9c176-154">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="9c176-155">Digite o caminho e o nome de arquivo do certificado com a extensão ou clique em **..** .</span><span class="sxs-lookup"><span data-stu-id="9c176-155">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="9c176-156">para procurar o certificado.</span><span class="sxs-lookup"><span data-stu-id="9c176-156">to browse for the certificate.</span></span> <span data-ttu-id="9c176-157">Selecione o certificado e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="9c176-157">Select the certificate and click **Open**.</span></span> <span data-ttu-id="9c176-158">Forneça a senha usada para proteger a chave privada (se você tiver atribuído uma senha ao exportar o certificado e a chave privada).</span><span class="sxs-lookup"><span data-stu-id="9c176-158">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="9c176-159">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c176-159">Click **OK**.</span></span> <span data-ttu-id="9c176-160">Se a importação do certificado tiver sido bem-sucedida, o certificado aparecerá como uma entrada no meio do console como uma entrada em **certificados de servidor**.</span><span class="sxs-lookup"><span data-stu-id="9c176-160">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="9c176-161">Atribua o certificado a ser usado por HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9c176-161">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="9c176-162">No lado esquerdo do console, selecione o **site da Web padrão** do servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="9c176-162">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="9c176-163">No lado direito, clique em **ligações..**..</span><span class="sxs-lookup"><span data-stu-id="9c176-163">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="9c176-164">Na caixa de diálogo **ligações do site** , clique em **Adicionar..**..</span><span class="sxs-lookup"><span data-stu-id="9c176-164">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="9c176-165">Na caixa de diálogo **Adicionar Associação de site** , em **tipo:**, selecione **https**.</span><span class="sxs-lookup"><span data-stu-id="9c176-165">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="9c176-166">Selecionar https permitirá que você selecione o certificado a ser usado para https.</span><span class="sxs-lookup"><span data-stu-id="9c176-166">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="9c176-167">Em **certificado SSL:**, selecione o certificado que você importou para o proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="9c176-167">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="9c176-168">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c176-168">Click **OK**.</span></span> <span data-ttu-id="9c176-169">Em seguida, clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="9c176-169">Then, click **Close**.</span></span> <span data-ttu-id="9c176-170">O certificado agora está ligado ao proxy reverso para SSL (Secure Socket Layer) e TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="9c176-170">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9c176-171">Se você receber um aviso ao fechar as caixas de diálogo de vinculação que os certificados intermediários estão ausentes, será necessário localizar e importar o certificado de autoridade raiz da autoridade de certificação pública e quaisquer certificados de autoridade de certificação intermediários.</span><span class="sxs-lookup"><span data-stu-id="9c176-171">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="9c176-172">Consulte as instruções na AC pública para a qual você solicitou o certificado e siga as instruções para solicitar e importar uma cadeia de certificados.</span><span class="sxs-lookup"><span data-stu-id="9c176-172">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="9c176-173">Se você exportou o certificado do seu servidor de borda, é possível exportar o certificado de autoridade de certificação raiz e todos os certificados de autoridade de certificação intermediários associados ao servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="9c176-173">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="9c176-174">Importe o certificado de autoridade de certificação raiz para o computador (não deve ser confundido com o repositório do usuário) armazenamento de autoridades de certificação raiz confiáveis e certificados intermediários no repositório de autoridades de certificação intermediários do computador.</span><span class="sxs-lookup"><span data-stu-id="9c176-174">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="9c176-175">No lado esquerdo do console abaixo do nome do servidor IIS, clique com o botão direito do mouse em **farms de servidores** e clique em **criar farm de servidores..**..</span><span class="sxs-lookup"><span data-stu-id="9c176-175">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9c176-176">Se você não vir o nó <STRONG>farms de servidores</STRONG> , precisará instalar o roteamento de solicitação de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9c176-176">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="9c176-177">Para obter detalhes, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurando servidores de proxy reverso para o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9c176-177">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="9c176-178">Na caixa de diálogo **criar farm de servidores** no **nome do farm de servidores**, digite o nome a (pode ser um nome amigável para fins de identificação) para a primeira URL.</span><span class="sxs-lookup"><span data-stu-id="9c176-178">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="9c176-179">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9c176-179">Click **Next**.</span></span>

6.  <span data-ttu-id="9c176-180">Na caixa de diálogo **Adicionar servidor** no **endereço do servidor**, digite o FQDN (nome de domínio totalmente qualificado) dos serviços Web externos no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="9c176-180">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="9c176-181">Os nomes que serão usados aqui para fins de exemplo são os mesmos que são usados na seção de planejamento para o proxy reverso, [proxy de Resumo de certificado-reverso no Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="9c176-181">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="9c176-182">Referindo-se ao planejamento de proxy reverso, digitamos o FQDN `webext.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="9c176-182">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="9c176-183">Confirme se a caixa de seleção ao lado de **online** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="9c176-183">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="9c176-184">Clique em **Adicionar** para adicionar o servidor ao pool de servidores Web para essa configuração.</span><span class="sxs-lookup"><span data-stu-id="9c176-184">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="9c176-185">O Lync Server usa balanceadores de carga de hardware para o diretor de pool e servidores front-end para tráfego HTTP e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9c176-185">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="9c176-186">Você só fornecerá um FQDN ao adicionar um servidor ao farm de servidores do ARR do IIS.</span><span class="sxs-lookup"><span data-stu-id="9c176-186">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="9c176-187">O FQDN será o servidor front-end ou o diretor nas configurações de servidor sem pool ou o FQDN do balanceador de carga de hardware configurado para pools de servidores.</span><span class="sxs-lookup"><span data-stu-id="9c176-187">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="9c176-188">O único método com suporte para o balanceamento de carga de tráfego HTTP e HTTPS é usar balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="9c176-188">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="9c176-189">Na caixa de diálogo **Adicionar servidor** , clique em **Configurações avançadas..**..</span><span class="sxs-lookup"><span data-stu-id="9c176-189">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="9c176-190">Isso abre uma caixa de diálogo para definir o roteamento de solicitação de aplicativo para as solicitações para o FQDN configurado.</span><span class="sxs-lookup"><span data-stu-id="9c176-190">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="9c176-191">O objetivo é redefinir qual porta será usada quando a solicitação for processada pelo IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="9c176-191">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="9c176-192">Por padrão, a porta HTTP de destino deve ser definida como 8080.</span><span class="sxs-lookup"><span data-stu-id="9c176-192">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="9c176-193">Clique em próximo ao **httpPort atual 80** e defina o valor como **8080**.</span><span class="sxs-lookup"><span data-stu-id="9c176-193">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="9c176-194">Clique em próximo ao **httpsPort atual 443** e defina o valor como **4443**.</span><span class="sxs-lookup"><span data-stu-id="9c176-194">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="9c176-195">Deixe o parâmetro **Weight** em 100.</span><span class="sxs-lookup"><span data-stu-id="9c176-195">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="9c176-196">Se necessário, você pode redefinir os pesos de uma determinada regra quando tiver estatísticas da linha de base.</span><span class="sxs-lookup"><span data-stu-id="9c176-196">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="9c176-197">Clique em **concluir** para concluir esta parte da configuração da regra.</span><span class="sxs-lookup"><span data-stu-id="9c176-197">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="9c176-198">Você pode ver uma caixa de diálogo reescrever regras que informa que o Gerenciador do IIS pode criar uma regra de regravação de URL para rotear todas as solicitações de entrada para o farm de servidores automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9c176-198">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="9c176-199">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9c176-199">Click **Yes**.</span></span> <span data-ttu-id="9c176-200">Você vai ajustar as regras manualmente, mas selecionar Sim define a configuração inicial..</span><span class="sxs-lookup"><span data-stu-id="9c176-200">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="9c176-201">Clique no nome do farm de servidores que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="9c176-201">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="9c176-202">Em **farm de servidores** no modo de exibição de recursos do Gerenciador do IIS, clique duas vezes em **cache**.</span><span class="sxs-lookup"><span data-stu-id="9c176-202">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="9c176-203">Desmarque **Habilitar cache de disco**.</span><span class="sxs-lookup"><span data-stu-id="9c176-203">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="9c176-204">Clique em **aplicar** no lado direito.</span><span class="sxs-lookup"><span data-stu-id="9c176-204">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="9c176-205">Clique no nome do farm de servidores.</span><span class="sxs-lookup"><span data-stu-id="9c176-205">Click the name of the server farm.</span></span> <span data-ttu-id="9c176-206">Em **farm de servidores** no modo de exibição de recursos do Gerenciador do IIS, clique duas vezes em **proxy**.</span><span class="sxs-lookup"><span data-stu-id="9c176-206">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="9c176-207">Na página Configurações de proxy, altere o valor de **tempo limite (segundos)** para um valor apropriado para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="9c176-207">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="9c176-208">Clique em **aplicar** para salvar a alteração.</span><span class="sxs-lookup"><span data-stu-id="9c176-208">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9c176-209">O valor de tempo limite do proxy é um número que varia de implantação para implantação.</span><span class="sxs-lookup"><span data-stu-id="9c176-209">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="9c176-210">Você deve monitorar sua implantação e modificar o valor da melhor experiência para os clientes.</span><span class="sxs-lookup"><span data-stu-id="9c176-210">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="9c176-211">É possível definir o valor como baixo como 200.</span><span class="sxs-lookup"><span data-stu-id="9c176-211">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="9c176-212">Se você estiver dando suporte a clientes móveis do Lync em seu ambiente, você deve definir o valor como 960 para permitir o tempo limite de notificações por push do Office 365 que têm um valor de tempo limite de 900.</span><span class="sxs-lookup"><span data-stu-id="9c176-212">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="9c176-213">É muito provável que você precise aumentar o valor de tempo limite para evitar que o cliente seja desconectado quando o valor for muito baixo ou diminuir o número se as conexões por meio do proxy não forem desconectadas e muito longas após o cliente ter sido desconectado.</span><span class="sxs-lookup"><span data-stu-id="9c176-213">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="9c176-214">O monitoramento e o alinhamento básico o que é normal para o seu ambiente é a única maneira precisa de determinar onde a configuração correta é para esse valor.</span><span class="sxs-lookup"><span data-stu-id="9c176-214">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="9c176-215">Clique no nome do farm de servidores.</span><span class="sxs-lookup"><span data-stu-id="9c176-215">Click the name of the server farm.</span></span> <span data-ttu-id="9c176-216">Em **farm de servidores** no modo de exibição de recursos do Gerenciador do IIS, clique duas vezes em **regras de roteamento**.</span><span class="sxs-lookup"><span data-stu-id="9c176-216">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="9c176-217">Na caixa de diálogo regras de roteamento em roteamento, desmarque a caixa de seleção ao lado de habilitar descarregamento SSL.</span><span class="sxs-lookup"><span data-stu-id="9c176-217">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="9c176-218">Se a capacidade de desmarcar a caixa de seleção não estiver disponível, marque a caixa de seleção **usar URL Rewrite para inspecionar solicitações de entrada**.</span><span class="sxs-lookup"><span data-stu-id="9c176-218">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="9c176-219">Clique em **aplicar** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="9c176-219">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="9c176-220">Não há suporte para o descarregamento de SSL pelo proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="9c176-220">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="9c176-221">Repita as etapas 5-11 para cada URL que deve passar pelo proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="9c176-221">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="9c176-222">Uma lista comum seria a seguinte:</span><span class="sxs-lookup"><span data-stu-id="9c176-222">A common list would be the following:</span></span>
    
      - <span data-ttu-id="9c176-223">Serviços Web de servidor front-end externo: webext.contoso.com (já configurado pelo passo inicial)</span><span class="sxs-lookup"><span data-stu-id="9c176-223">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="9c176-224">Serviços Web do diretor externos para Diretor: webdirext.contoso.com (opcional se um diretor estiver implantado)</span><span class="sxs-lookup"><span data-stu-id="9c176-224">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="9c176-225">Reunião de URL simples: meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c176-225">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="9c176-226">Discagem de URL simples: dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c176-226">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="9c176-227">URL de descoberta automática do Lync: lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c176-227">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="9c176-228">URL do servidor do Office Web Apps: officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9c176-228">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="9c176-229">A URL do servidor do Office Web Apps usará um endereço httpsPort diferente.</span><span class="sxs-lookup"><span data-stu-id="9c176-229">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="9c176-230">Na etapa 7, você define o <STRONG>httpsPort</STRONG> como <STRONG>443</STRONG> e o <STRONG>httpPort</STRONG> como a porta <STRONG>80</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9c176-230">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="9c176-231">Todas as outras definições de configuração são as mesmas.</span><span class="sxs-lookup"><span data-stu-id="9c176-231">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="9c176-232">No lado esquerdo do console, clique no nome do servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="9c176-232">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="9c176-233">No meio do console, localize **regravação de URL** em **IIS**.</span><span class="sxs-lookup"><span data-stu-id="9c176-233">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="9c176-234">Clique duas vezes em URL Rewrite para abrir a configuração de regras de regravação de URL.</span><span class="sxs-lookup"><span data-stu-id="9c176-234">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="9c176-235">Você deve ver as regras de cada farm de servidores criado nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="9c176-235">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="9c176-236">Caso contrário, confirme se você clicou no nome do **servidor IIS** imediatamente abaixo do nó da **página inicial** no console do Gerenciador do servidor de informações da Internet.</span><span class="sxs-lookup"><span data-stu-id="9c176-236">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="9c176-237">Na caixa de diálogo de **reconfiguração de URL** , usando webext.contoso.com como exemplo, o nome completo da regra conforme exibido é **arr \_ webext.contoso.com \_ LoadBalance \_ SSL**.</span><span class="sxs-lookup"><span data-stu-id="9c176-237">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="9c176-238">Clique duas vezes na regra para abrir a caixa de diálogo **Editar regra de entrada** .</span><span class="sxs-lookup"><span data-stu-id="9c176-238">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="9c176-239">Clique em **Adicionar...**</span><span class="sxs-lookup"><span data-stu-id="9c176-239">Click **Add…**</span></span> <span data-ttu-id="9c176-240">na caixa de diálogo **condições** .</span><span class="sxs-lookup"><span data-stu-id="9c176-240">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="9c176-241">Na entrada **Adicionar condição** em **condição:** digite **{host http \_ }**.</span><span class="sxs-lookup"><span data-stu-id="9c176-241">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="9c176-242">(Conforme você digita, uma caixa de diálogo é exibida, permitindo que você selecione a condição).</span><span class="sxs-lookup"><span data-stu-id="9c176-242">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="9c176-243">em **verificar se a cadeia de caracteres de entrada:** Select **corresponde ao padrão**.</span><span class="sxs-lookup"><span data-stu-id="9c176-243">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="9c176-244">No tipo de **entrada padrão** **\*** .</span><span class="sxs-lookup"><span data-stu-id="9c176-244">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="9c176-245">O **caso de ignorar** deve ser selecionado.</span><span class="sxs-lookup"><span data-stu-id="9c176-245">**Ignore case** should be selected.</span></span> <span data-ttu-id="9c176-246">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c176-246">Click **OK**.</span></span>
    
      - <span data-ttu-id="9c176-247">Role para baixo na caixa de diálogo **Editar regra de entrada** para localizar a caixa de diálogo de **ação** .</span><span class="sxs-lookup"><span data-stu-id="9c176-247">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="9c176-248">**Tipo de ação:** deve ser definido como **rota para o farm de servidores**, **esquema:** definido como **https://**, **farm de servidores:** definido como a URL à qual essa regra se aplica.</span><span class="sxs-lookup"><span data-stu-id="9c176-248">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="9c176-249">Para este exemplo, ele deve ser definido como **webext.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="9c176-249">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="9c176-250">**Caminho:** está definido como **/{R: 0}**</span><span class="sxs-lookup"><span data-stu-id="9c176-250">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="9c176-251">Clique em **aplicar** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="9c176-251">Click **Apply** to save your changes.</span></span> <span data-ttu-id="9c176-252">Clique em **voltar às regras** para retornar às regras de regravação de URL.</span><span class="sxs-lookup"><span data-stu-id="9c176-252">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="9c176-253">Repita o procedimento definido na etapa 14 para cada regra de regravação SSL que você definiu, uma por URL de farm de servidores.</span><span class="sxs-lookup"><span data-stu-id="9c176-253">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="9c176-254">Por padrão, as regras HTTP também são criadas e são indicadas pelo nome semelhante às regras SSL.</span><span class="sxs-lookup"><span data-stu-id="9c176-254">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="9c176-255">Para o nosso exemplo atual, a regra HTTP seria nomeada <STRONG>ARR_webext. contoso. com _loadbalance</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9c176-255">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="9c176-256">Nenhuma modificação é necessária para essas regras e elas podem ser ignoradas com segurança.</span><span class="sxs-lookup"><span data-stu-id="9c176-256">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="9c176-257">Para modificar as propriedades da regra de publicação na Web no TMG 2010</span><span class="sxs-lookup"><span data-stu-id="9c176-257">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="9c176-258">Clique em **Iniciar**, aponte para **programas**, selecione **Microsoft Forefront TMG**e clique em **Gerenciamento do Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="9c176-258">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="9c176-259">No painel esquerdo, expanda **Nome do Servidor** e clique em **Política de Firewall**.</span><span class="sxs-lookup"><span data-stu-id="9c176-259">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="9c176-260">No painel de detalhes, clique com o botão direito do mouse na regra de publicação de servidor Web que você criou no procedimento anterior (por exemplo, LyncServerExternalRule) e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9c176-260">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="9c176-261">Na página **Propriedades**, clique na guia **De** e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9c176-261">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="9c176-262">Na lista **Esta regra aplica-se ao tráfego destas origens**, clique em **Qualquer Lugar** e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="9c176-262">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="9c176-263">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9c176-263">Click **Add**.</span></span>
    
      - <span data-ttu-id="9c176-264">Em **Adicionar Entidades de Rede**, expanda **Redes**, clique em **Externa**, clique em **Adicionar** e, em seguida, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="9c176-264">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="9c176-265">Na guia **Para**, verifique se a caixa de seleção **Encaminhar o cabeçalho do host original em vez do real** está marcada.</span><span class="sxs-lookup"><span data-stu-id="9c176-265">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="9c176-266">Na guia **Ponte**, marque a caixa de seleção **Redirecionar a solicitação para a porta SSL** e especifique a porta **4443**.</span><span class="sxs-lookup"><span data-stu-id="9c176-266">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="9c176-267">Na guia **Nome Público**, adicione as URLs simples (por exemplo, meet.contoso.com e dialin.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9c176-267">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="9c176-268">Clique em **Aplicar** para salvar as alterações e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c176-268">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="9c176-269">Clique em **Aplicar** no painel de detalhes para salvar as alterações e atualizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="9c176-269">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="9c176-270">Para modificar as propriedades da regra de publicação na Web no IIS ARR</span><span class="sxs-lookup"><span data-stu-id="9c176-270">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="9c176-271">Clique em **Iniciar**, selecione **programas**, selecione **Ferramentas administrativas**e clique em **Gerenciador dos serviços de informações da Internet (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="9c176-271">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="9c176-272">No lado esquerdo do console, clique no nome do servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="9c176-272">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="9c176-273">No meio do console, localize **regravação de URL** em **IIS**.</span><span class="sxs-lookup"><span data-stu-id="9c176-273">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="9c176-274">Clique duas vezes em URL Rewrite para abrir a configuração de regras de regravação de URL.</span><span class="sxs-lookup"><span data-stu-id="9c176-274">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="9c176-275">Clique duas vezes na regra que você precisa modificar.</span><span class="sxs-lookup"><span data-stu-id="9c176-275">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="9c176-276">Faça suas modificações, conforme necessário, em **URL de correspondência**, **condições**, **variáveis de servidor** ou **ação**.</span><span class="sxs-lookup"><span data-stu-id="9c176-276">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="9c176-277">Clique em **aplicar** para confirmar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="9c176-277">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="9c176-278">Clique em **voltar às regras** para modificar outras regras ou feche o console do **Gerenciador do IIS** se tiver concluído as alterações.</span><span class="sxs-lookup"><span data-stu-id="9c176-278">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

