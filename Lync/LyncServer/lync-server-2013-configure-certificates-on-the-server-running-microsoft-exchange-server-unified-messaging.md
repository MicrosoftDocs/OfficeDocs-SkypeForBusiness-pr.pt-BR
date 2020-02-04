---
title: 'Lync Server 2013: configurar certificados no servidor que executa o Microsoft Exchange Server Unified Messaging'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d31ed8b750d0162a2c09d49ca8a350731896086
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="2877e-102">Configurar certificados no servidor que executa o Microsoft Exchange Server Unified Messaging</span><span class="sxs-lookup"><span data-stu-id="2877e-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2877e-103">_**Tópico da última modificação:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="2877e-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="2877e-104">Se você tiver implantado UM (a) da Exchange Unified Messaging (UM), conforme descrito em [planejamento para a integração de Unificação de mensagens do Exchange no Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) na documentação de planejamento e desejar fornecer recursos de um do Exchange para usuários de Enterprise Voice em sua organização, você pode usar os procedimentos a seguir para configurar o certificado no servidor que executa o Exchange um.</span><span class="sxs-lookup"><span data-stu-id="2877e-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2877e-105">Para certificados internos, os servidores que executam o Lync Server 2013 e os servidores que executam o Microsoft Exchange devem ter certificados de autoridade raiz confiáveis que sejam confiáveis mutuamente.</span><span class="sxs-lookup"><span data-stu-id="2877e-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="2877e-106">A autoridade de certificação (CA) pode ser a mesma ou uma autoridade de certificação diferente, desde que os servidores tenham o certificado raiz da autoridade de certificação registrado no repositório de certificados da autoridade raiz confiável.</span><span class="sxs-lookup"><span data-stu-id="2877e-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="2877e-107">O servidor Exchange deve ser configurado com um certificado de servidor para se conectar ao Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="2877e-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="2877e-108">Baixe o certificado da CA para o servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="2877e-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="2877e-109">Instale o certificado da CA para o servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="2877e-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="2877e-110">Verifique se a CA está na lista de autoridades de certificação raiz confiáveis do servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="2877e-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="2877e-111">Crie uma solicitação de certificado para o servidor Exchange e instale o certificado.</span><span class="sxs-lookup"><span data-stu-id="2877e-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="2877e-112">Atribua o certificado para o servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="2877e-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="2877e-113">Para baixar o certificado da CA</span><span class="sxs-lookup"><span data-stu-id="2877e-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="2877e-114">No servidor que executa o Exchange UM, clique em **Iniciar**, clique em **executar**, digite **http://\<nome do seu servidor\>da CA de emissão/certsrv**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2877e-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="2877e-115">Em **Selecione uma tarefa**, clique em **baixar um certificado de autoridade de certificação, uma cadeia de certificados ou uma CRL**.</span><span class="sxs-lookup"><span data-stu-id="2877e-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="2877e-116">Em **baixar um certificado de autoridade de certificação, uma cadeia de certificados ou uma CRL**, selecione **método de codificação para base 64**e, em seguida, clique em **baixar certificado da CA**.</span><span class="sxs-lookup"><span data-stu-id="2877e-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2877e-117">Você também pode especificar a codificação de regras de codificação diferenciadas (DER) nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="2877e-117">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="2877e-118">Se você selecionar codificação DER, o tipo de arquivo na próxima etapa deste procedimento e na etapa 10 da <STRONG>para instalar o certificado da CA</STRONG> será. p7b em vez de. cer.</span><span class="sxs-lookup"><span data-stu-id="2877e-118">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="2877e-119">Na caixa de diálogo **download de arquivo** , clique em **salvar**e salve o arquivo no disco rígido no servidor.</span><span class="sxs-lookup"><span data-stu-id="2877e-119">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="2877e-120">(O arquivo terá uma extensão de arquivo. cer ou. p7b, dependendo da codificação que você selecionou na etapa anterior.)</span><span class="sxs-lookup"><span data-stu-id="2877e-120">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="2877e-121">Para instalar o certificado da CA</span><span class="sxs-lookup"><span data-stu-id="2877e-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="2877e-122">No servidor que executa o Exchange UM, abra o MMC (console de gerenciamento Microsoft) clicando em **Iniciar**, em **executar**, digitando **MMC** na caixa **abrir** e, em seguida, clicando em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2877e-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="2877e-123">No menu **arquivo** , clique em **Adicionar/remover snap-in**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2877e-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="2877e-124">Na caixa **Adicionar Snap-ins Autônomos** , clique em **certificados**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2877e-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="2877e-125">Na caixa de diálogo  **Snap-in de certificados**, clique em  **Conta de computador**e, em seguida, clique em  **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2877e-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="2877e-126">Na caixa de diálogo **Selecionar computador** , verifique se a caixa de seleção **computador local: (o computador em que este console está sendo executado)** está marcada e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="2877e-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="2877e-127">Clique em **fechar**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2877e-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="2877e-128">Na árvore de console, expanda **certificados (computador local)**, expanda **autoridades de certificação raiz confiáveis**e clique em **certificados**.</span><span class="sxs-lookup"><span data-stu-id="2877e-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="2877e-129">Clique com o botão direito do mouse em **certificados**, clique em **todas as tarefas**e clique em **importar**.</span><span class="sxs-lookup"><span data-stu-id="2877e-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="2877e-130">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="2877e-130">Click **Next**.</span></span>

10. <span data-ttu-id="2877e-131">Clique em **procurar** para localizar o arquivo e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2877e-131">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="2877e-132">(O arquivo terá uma extensão de arquivo. cer ou. p7b, dependendo da codificação selecionada na etapa 3 de **para baixar o certificado da autoridade de certificação**.</span><span class="sxs-lookup"><span data-stu-id="2877e-132">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="2877e-133">Clique em **colocar todos os certificados no repositório a seguir**.</span><span class="sxs-lookup"><span data-stu-id="2877e-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="2877e-134">Clique em **procurar**e, em seguida, selecione **autoridades de certificação raiz confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="2877e-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="2877e-135">Clique em **Avançar** para verificar as configurações e, em seguida, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="2877e-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="2877e-136">Para verificar se a CA está na lista de autoridades de certificação raiz confiáveis</span><span class="sxs-lookup"><span data-stu-id="2877e-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="2877e-137">No servidor que executa o Exchange UM, no MMC expanda **certificados (computador local)**, expanda **autoridades de certificação raiz confiáveis**e clique em **certificados**.</span><span class="sxs-lookup"><span data-stu-id="2877e-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="2877e-138">No painel detalhes, verifique se a sua CA está na lista de CAs confiáveis.</span><span class="sxs-lookup"><span data-stu-id="2877e-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="2877e-139">Para configurar o Exchange Server 2013 UM com o Lync Server</span><span class="sxs-lookup"><span data-stu-id="2877e-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="2877e-140">Para obter detalhes, consulte "integrar o Exchange 2013 UM com o Lync Server" na documentação do [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)Exchange Server em.</span><span class="sxs-lookup"><span data-stu-id="2877e-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="2877e-141">Para criar uma solicitação de certificado e instalar o certificado no Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="2877e-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="2877e-142">No servidor que executa o Exchange um, clique em **Iniciar**, clique em **executar**, digite **\<http://** nome do seu servidor**\>** da CA de emissão/certsrv e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2877e-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<** name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="2877e-143">Em **Selecione uma tarefa**, clique em **solicitar um certificado**.</span><span class="sxs-lookup"><span data-stu-id="2877e-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="2877e-144">Em **solicitar um certificado**, clique em **solicitação avançada de certificado**.</span><span class="sxs-lookup"><span data-stu-id="2877e-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="2877e-145">Em **solicitação avançada de certificado**, clique em **criar e envie uma solicitação para esta ca**.</span><span class="sxs-lookup"><span data-stu-id="2877e-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="2877e-146">Em **solicitação de certificado avançada**, selecione **servidor Web** ou outro modelo de certificado de servidor configurado para autenticação do servidor.</span><span class="sxs-lookup"><span data-stu-id="2877e-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="2877e-147">Em **informações de identificação para modelo offline**, na caixa **nome** , digite o nome de domínio totalmente qualificado (FQDN) do servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="2877e-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2877e-148">Você deve digitar o FQDN do servidor Exchange para que as comunicações funcionem.</span><span class="sxs-lookup"><span data-stu-id="2877e-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="2877e-149">Em **Opções de chave**, clique na caixa de seleção **armazenar certificado no repositório de certificados do computador local** .</span><span class="sxs-lookup"><span data-stu-id="2877e-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="2877e-150">Clique no botão **Enviar** na parte inferior da página da Web.</span><span class="sxs-lookup"><span data-stu-id="2877e-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="2877e-151">Na caixa de diálogo que é exibida solicitando confirmação, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2877e-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="2877e-152">Na página certificado emitido, em **certificado emitido**, clique em **instalar este certificado**.</span><span class="sxs-lookup"><span data-stu-id="2877e-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="2877e-153">Na caixa de diálogo que é exibida solicitando confirmação, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2877e-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="2877e-154">Verifique se a mensagem "o novo certificado foi instalado com sucesso" é exibida.</span><span class="sxs-lookup"><span data-stu-id="2877e-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="2877e-155">Para criar um certificado no Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="2877e-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="2877e-156">Faça logon no servidor que está executando o Exchange UM com direitos de usuário adequados.</span><span class="sxs-lookup"><span data-stu-id="2877e-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="2877e-157">Para obter detalhes, consulte "permissões de acesso do [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)cliente" em.</span><span class="sxs-lookup"><span data-stu-id="2877e-157">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="2877e-158">Consulte os procedimentos a seguir para criar o certificado:</span><span class="sxs-lookup"><span data-stu-id="2877e-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="2877e-159">"Criar um novo certificado do Exchange" em[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="2877e-159">"Create a New Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="2877e-160">"Importar um certificado do Exchange" em[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="2877e-160">"Import an Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2877e-161">Para o <STRONG>nome do requerente</STRONG>do certificado, você deve digitar o FQDN do servidor Exchange para que as comunicações funcionem.</span><span class="sxs-lookup"><span data-stu-id="2877e-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="2877e-162">Para atribuir o certificado no Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="2877e-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="2877e-163">No servidor que executa o Exchange UM, abra o MMC.</span><span class="sxs-lookup"><span data-stu-id="2877e-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="2877e-164">Na árvore de console, expanda **pessoal** e, em seguida, clique em **certificados**.</span><span class="sxs-lookup"><span data-stu-id="2877e-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="2877e-165">No painel detalhes, verifique se o certificado pessoal está exibido.</span><span class="sxs-lookup"><span data-stu-id="2877e-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="2877e-166">Clique duas vezes no certificado para ler seus detalhes e verificar se ele é válido.</span><span class="sxs-lookup"><span data-stu-id="2877e-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2877e-167">Pode demorar alguns minutos para que o certificado seja exibido como válido.</span><span class="sxs-lookup"><span data-stu-id="2877e-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="2877e-168">Reinicie o serviço de Unificação de mensagens do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="2877e-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2877e-169">O servidor que executa o Exchange Server 2007 SP1 Unified Messaging recupera automaticamente o certificado correto.</span><span class="sxs-lookup"><span data-stu-id="2877e-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="2877e-170">Abra o Visualizador de eventos e procure o ID de evento 1112, que especifica qual certificado o servidor que está executando o Exchange Server 2007 SP1 Unified Messaging foi recuperado.</span><span class="sxs-lookup"><span data-stu-id="2877e-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="2877e-171">Para atribuir o certificado no Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="2877e-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="2877e-172">Faça logon no servidor que está executando o Exchange UM com direitos de usuário adequados.</span><span class="sxs-lookup"><span data-stu-id="2877e-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="2877e-173">Para obter detalhes, consulte "permissões de acesso do [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)cliente" em.</span><span class="sxs-lookup"><span data-stu-id="2877e-173">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="2877e-174">Para obter o procedimento para atribuir o certificado, consulte "atribuir serviços a um certificado" [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)em.</span><span class="sxs-lookup"><span data-stu-id="2877e-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

