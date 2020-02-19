---
title: 'Lync Server 2013: configurar certificados no servidor que executa a Unificação de mensagens do Microsoft Exchange Server'
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
ms.openlocfilehash: 4bf3e665e0031596bc2db2273882aef379a96f2e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="78ba4-102">Configurar certificados no servidor que executa a Unificação de mensagens do Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="78ba4-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78ba4-103">_**Última modificação do tópico:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="78ba4-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="78ba4-104">Se você implantou a Unificação de mensagens (UM) do Exchange, conforme descrito em [Planning for Exchange Unified Messaging Integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) na documentação de planejamento e deseja fornecer recursos da um do Exchange para usuários do Enterprise Voice em sua organização, você pode usar os seguintes procedimentos para configurar o certificado no servidor que executa o Exchange um.</span><span class="sxs-lookup"><span data-stu-id="78ba4-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="78ba4-105">Para certificados internos, ambos os servidores que executam o Lync Server 2013 e os servidores que executam o Microsoft Exchange devem ter certificados de autoridade raiz confiáveis mutuamente confiáveis.</span><span class="sxs-lookup"><span data-stu-id="78ba4-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="78ba4-106">A autoridade de certificação (CA) pode ser a mesma ou uma autoridade de certificação diferente, desde que os servidores tenham o certificado raiz da autoridade de certificação registrado no repositório de certificados da autoridade raiz confiável.</span><span class="sxs-lookup"><span data-stu-id="78ba4-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="78ba4-107">O servidor do Exchange deve ser configurado com um certificado de servidor para se conectar ao Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="78ba4-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="78ba4-108">Baixe o certificado da autoridade de certificação do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="78ba4-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="78ba4-109">Instale o certificado da autoridade de certificação do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="78ba4-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="78ba4-110">Verifique se a autoridade de certificação está na lista de autoridades de certificação raiz confiáveis do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="78ba4-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="78ba4-111">Crie uma solicitação de certificado do Exchange Server e instale o certificado.</span><span class="sxs-lookup"><span data-stu-id="78ba4-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="78ba4-112">Atribua o certificado do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="78ba4-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="78ba4-113">Para baixar o certificação da autoridade de certificação</span><span class="sxs-lookup"><span data-stu-id="78ba4-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="78ba4-114">No servidor que executa o UM do Exchange, clique em **Iniciar**, clique em **executar**, digite **http://\<nome do servidor\>de CA de emissão/certsrv**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="78ba4-115">Em **Selecionar uma tarefa**, clique em **Download de um certificado de autoridade de certificação, cadeia de certificados ou lista de certificados revogados**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="78ba4-116">Em **baixar um certificado de autoridade de certificação, uma cadeia de certificados ou uma CRL**, selecione o **método de codificação como base 64**e clique em **baixar certificado de autoridade de certificação**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78ba4-117">Você também pode especificar a codificação de regras de codificação diferenciadas (DER) nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="78ba4-117">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="78ba4-118">Se você selecionar a codificação DER, o tipo de arquivo na próxima etapa deste procedimento e na etapa 10 de <STRONG>Para instalar o Certificado de autoridade de certificação</STRONG> é. p7b, em vez de .cer.</span><span class="sxs-lookup"><span data-stu-id="78ba4-118">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="78ba4-p103">Na caixa de diálogo **Download de Arquivo**, clique em **Salvar** e salve o arquivo no disco rígido no servidor. (O arquivo terá um .cer ou uma extensão de arquivo .p7b, dependendo da codificação que você selecionou na etapa anterior).</span><span class="sxs-lookup"><span data-stu-id="78ba4-p103">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="78ba4-121">Para instalar o certificado da autoridade de certificação</span><span class="sxs-lookup"><span data-stu-id="78ba4-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="78ba4-122">No servidor que executa o UM do Exchange, abra o console de gerenciamento Microsoft (MMC) clicando em **Iniciar**, clicando em **executar**, digitando **MMC** na caixa **abrir** e clicando em **OK**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="78ba4-123">No menu **Arquivo**, clique em **Adicionar/Remover Snap-in** e em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="78ba4-124">Na caixa **Adicionar Snap-in Autônomo**, clique em **Certificados** e em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="78ba4-125">Na caixa de diálogo **Snap-in de certificados**, clique em **Conta de computador** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="78ba4-126">Na caixa de diálogo **Selecionar computador** , verifique se a caixa de seleção **computador local: (o computador em que este console está sendo executado)** está marcada e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="78ba4-127">Clique em **Fechar** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="78ba4-128">Na árvore de console, expanda **Certificados (Computador Local)**, expanda **Autoridades de Certificação Raiz Confiáveis** e clique em **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="78ba4-129">Clique com o botão direito do mouse em **Certificados**, clique em **Todas as Tarefas** e em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="78ba4-130">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-130">Click **Next**.</span></span>

10. <span data-ttu-id="78ba4-p104">Clique em **Procurar** para localizar o arquivo e clique em **Avançar**. (O arquivo terá uma extensão de arquivo .cer ou .p7b, dependendo da codificação que você selecionou na etapa 3 de **Para baixar o certificado de autoridade de certificação**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-p104">Click **Browse** to locate the file, and then click **Next**. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="78ba4-133">Clique em **Colocar todos os certificados no repositório a seguir**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="78ba4-134">Clique em **Procurar** e selecione **Autoridades de Certificação Raiz Confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="78ba4-135">Clique em **Avançar** para verificar as configurações e, em seguida, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="78ba4-136">Para verificar se a autoridade de certificação está na lista de autoridades de certificação raiz confiáveis</span><span class="sxs-lookup"><span data-stu-id="78ba4-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="78ba4-137">No servidor que executa o UM do Exchange, no MMC expanda **certificados (computador local)**, expanda **autoridades de certificação raiz confiáveis**e clique em **certificados**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="78ba4-138">No painel de detalhes, verifique se a autoridade de certificação está na lista de autoridades de certificação confiáveis.</span><span class="sxs-lookup"><span data-stu-id="78ba4-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="78ba4-139">Para configurar a UM do Exchange Server 2013 com o Lync Server</span><span class="sxs-lookup"><span data-stu-id="78ba4-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="78ba4-140">Para obter detalhes, consulte "integrar o Exchange 2013 UM com Lync Server" na documentação do Exchange [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372)Server em.</span><span class="sxs-lookup"><span data-stu-id="78ba4-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="78ba4-141">Para criar uma solicitação de certificado e instalar o certificado no Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="78ba4-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="78ba4-142">No servidor que executa o um do Exchange, clique em **Iniciar**, clique em **executar**, digite **\<http://** nome do servidor**\>** de CA de emissão/certsrv e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<** name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="78ba4-143">Em **Selecionar uma tarefa**, clique em **Solicitar um Certificado**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="78ba4-144">Em **Solicitar um Certificado**, clique em **Solicitação avançada de certificado**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="78ba4-145">Em **Solicitação Avançada de Certificado**, clique em **Criar e enviar uma solicitação para a autoridade de certificação**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="78ba4-146">Em **Solicitação Avançada de Certificado**, selecione **Servidor Web** ou outro modelo de certificado de servidor configurado para autenticação de servidor.</span><span class="sxs-lookup"><span data-stu-id="78ba4-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="78ba4-147">Em **informações de identificação para modelo offline**, na caixa **nome** , digite o nome de domínio totalmente qualificado (FQDN) do servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="78ba4-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78ba4-148">Você deve inserir o FQDN do Exchange Server para que a comunicação funcione.</span><span class="sxs-lookup"><span data-stu-id="78ba4-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="78ba4-149">Em **Opções de Chave**, clique na caixa de seleção **Armazenar certificado no armazenamento de certificados do computador local**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="78ba4-150">Clique no botão **Enviar** na parte inferior da página da Web.</span><span class="sxs-lookup"><span data-stu-id="78ba4-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="78ba4-151">Na caixa de diálogo que solicita a confirmação, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="78ba4-152">Na página Certificado Emitido, em **Certificado Emitido**, clique em **Instalar este certificado**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="78ba4-153">Na caixa de diálogo que solicita a confirmação, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="78ba4-154">Verifique se a mensagem "O novo certificado foi instalado com êxito" é exibida.</span><span class="sxs-lookup"><span data-stu-id="78ba4-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="78ba4-155">Para criar um certificado no Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="78ba4-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="78ba4-156">Faça logon no servidor que está executando o UM do Exchange com os direitos de usuário apropriados.</span><span class="sxs-lookup"><span data-stu-id="78ba4-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="78ba4-157">Para obter detalhes, consulte "permissões de acesso do [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)cliente" em.</span><span class="sxs-lookup"><span data-stu-id="78ba4-157">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="78ba4-158">Consulte os seguintes procedimentos para criar o certificado:</span><span class="sxs-lookup"><span data-stu-id="78ba4-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="78ba4-159">"Criar um novo certificado do Exchange" em[https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="78ba4-159">"Create a New Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="78ba4-160">"Importar um certificado do Exchange" em[https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="78ba4-160">"Import an Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78ba4-161">Para o certificado <STRONG>Nome da Entidade</STRONG>, digite o FQDN do Exchange Server para que as comunicações funcionem.</span><span class="sxs-lookup"><span data-stu-id="78ba4-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="78ba4-162">Para atribuir o certificado no Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="78ba4-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="78ba4-163">No servidor que executa o Exchange UM, abra o MMC.</span><span class="sxs-lookup"><span data-stu-id="78ba4-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="78ba4-164">Na árvore de console, expanda **Pessoal** e clique em **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="78ba4-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="78ba4-165">No painel de detalhes, verifique se o certificado pessoal é exibido.</span><span class="sxs-lookup"><span data-stu-id="78ba4-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="78ba4-166">Clique duas vezes no certificado para ler seus detalhes e verificar se ele é válido.</span><span class="sxs-lookup"><span data-stu-id="78ba4-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78ba4-167">Possivelmente levará alguns minutos para que o certificado apareça como válido.</span><span class="sxs-lookup"><span data-stu-id="78ba4-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="78ba4-168">Reinicie o serviço de Unificação de Mensagens do Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="78ba4-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78ba4-169">O servidor que está executando a Unificação de Mensagens do Exchange Server 2007 SP1 recupera automaticamente o certificado correto.</span><span class="sxs-lookup"><span data-stu-id="78ba4-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="78ba4-170">Abra o Visualizador de Eventos e procure a ID de Evento 1112, que especifica qual certificado foi recuperado pelo servidor que está executando a Unificação de Mensagens do Exchange Server 2007 SP1.</span><span class="sxs-lookup"><span data-stu-id="78ba4-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="78ba4-171">Para atribuir o certificado no Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="78ba4-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="78ba4-172">Faça logon no servidor que está executando o UM do Exchange com os direitos de usuário apropriados.</span><span class="sxs-lookup"><span data-stu-id="78ba4-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="78ba4-173">Para obter detalhes, consulte "permissões de acesso do [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)cliente" em.</span><span class="sxs-lookup"><span data-stu-id="78ba4-173">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="78ba4-174">Para obter o procedimento para atribuir o certificado, consulte "atribuir serviços a um certificado" [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497)em.</span><span class="sxs-lookup"><span data-stu-id="78ba4-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

