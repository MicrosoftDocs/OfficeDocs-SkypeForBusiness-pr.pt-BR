---
title: 'Lync Server 2013: Configurar certificados para a interface de borda interna'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53ba11db5d2c9fc727b7720a1a10d5da547075c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="301da-102">Configurar certificados para a interface de borda interna no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="301da-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="301da-103">_**Tópico da última modificação:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="301da-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="301da-104">Ao executar o assistente de certificado, certifique-se de que você esteja conectado usando uma conta que seja membro de um grupo que tenha recebido as permissões apropriadas para o tipo de modelo de certificado que você vai usar.</span><span class="sxs-lookup"><span data-stu-id="301da-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="301da-105">Por padrão, uma solicitação de certificado do Lync Server 2013 usará o modelo de certificado de servidor Web.</span><span class="sxs-lookup"><span data-stu-id="301da-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="301da-106">Se você usar uma conta que seja um membro do grupo RTCUniversalServerAdmins para solicitar um certificado usando esse modelo, verifique se o grupo recebeu as permissões de Registro necessárias para usar esse modelo.</span><span class="sxs-lookup"><span data-stu-id="301da-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="301da-107">É necessário um único certificado na interface interna de cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="301da-107">A single certificate is required on the internal interface of each Edge Server.</span></span> <span data-ttu-id="301da-108">Certificados para a interface interna podem ser emitidos por uma CA (autoridade de certificação) corporativa interna ou uma CA pública.</span><span class="sxs-lookup"><span data-stu-id="301da-108">Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA.</span></span> <span data-ttu-id="301da-109">Se a sua organização tiver uma CA interna implantada, você poderá economizar na despesa de usar certificados públicos usando a CA interna para emitir o certificado para a interface interna.</span><span class="sxs-lookup"><span data-stu-id="301da-109">If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface.</span></span> <span data-ttu-id="301da-110">Você pode usar uma CA interna do Windows Server 2008 ou uma autoridade de certificação do Windows Server 2008 R2 para criar esses certificados.</span><span class="sxs-lookup"><span data-stu-id="301da-110">You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="301da-111">Para obter detalhes sobre esse e outros requisitos de certificado, consulte [requisitos de certificado para acesso de usuários externos no Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="301da-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="301da-112">Para configurar certificados na interface de borda interna em um site, use os procedimentos desta seção para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="301da-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="301da-113">Baixe a cadeia de certificação da CA para a interface interna para cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="301da-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="301da-114">Importar a cadeia de certificação da CA para a interface interna, em cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="301da-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="301da-115">Crie a solicitação de certificado para a interface interna, em um servidor de borda, chamado de primeiro servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="301da-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="301da-116">Importar o certificado para a interface interna no primeiro servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="301da-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="301da-117">Importar o certificado nos outros servidores de borda neste site (ou implantado atrás deste balanceador de carga).</span><span class="sxs-lookup"><span data-stu-id="301da-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="301da-118">Atribua o certificado para a interface interna de cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="301da-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="301da-119">Se você tiver mais de um site com servidores de borda (ou seja, uma topologia de borda de vários sites) ou conjuntos separados de servidores de Borda implantados por meio de balanceadores de carga diferentes, você precisará seguir estas etapas para cada site que tenha servidores de borda e para cada conjunto de servidores de borda implantado atrás de um balanceador de carga diferente.</span><span class="sxs-lookup"><span data-stu-id="301da-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="301da-120">As etapas para procedimentos nesta seção se baseiam no uso de uma autoridade&nbsp;de certificação do windows Server&nbsp;2008&nbsp;, do Windows Server 2008 R2, da autoridade de certificação do Windows Server 2012 ou da autoridade de certificação do Windows Server 2012 R2 para criar um certificado para cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="301da-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="301da-121">Para obter orientação passo a passo para qualquer outra autoridade de certificação, consulte a documentação dessa CA.</span><span class="sxs-lookup"><span data-stu-id="301da-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="301da-122">Por padrão, todos os usuários autenticados têm os direitos de usuário adequados para solicitar certificados.</span><span class="sxs-lookup"><span data-stu-id="301da-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="301da-123">Os procedimentos desta seção se baseiam na criação de solicitações de certificado no servidor de borda como parte do processo de implantação do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="301da-123">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process.</span></span> <span data-ttu-id="301da-124">É possível criar solicitações de certificado usando o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="301da-124">It is possible to create certificate requests using the Front End Server.</span></span> <span data-ttu-id="301da-125">Você pode fazer isso para concluir a solicitação de certificado no início do processo de planejamento e implantação antes de iniciar a implantação dos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="301da-125">You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers.</span></span> <span data-ttu-id="301da-126">Para fazer isso, você deve certificar-se de que o certificado que você solicitou está definido com uma chave privada exportável.</span><span class="sxs-lookup"><span data-stu-id="301da-126">To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="301da-127">Os procedimentos desta seção descrevem o uso de um arquivo. cer e de um arquivo. p7b para o certificado.</span><span class="sxs-lookup"><span data-stu-id="301da-127">The procedures in this section describe using a .cer and a .p7b file for the certificate.</span></span> <span data-ttu-id="301da-128">Se você usar um tipo de arquivo diferente, modifique esses procedimentos conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="301da-128">If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="301da-129">Para baixar a cadeia de certificação CA para a interface interna usando o site do certsrv</span><span class="sxs-lookup"><span data-stu-id="301da-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="301da-130">Faça logon em um servidor do Lync Server 2013 na rede interna (ou seja, não no servidor de borda) como membro do grupo **Administradores** .</span><span class="sxs-lookup"><span data-stu-id="301da-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="301da-131">Execute o seguinte comando em um prompt de comando clicando em **Iniciar**, em **executar**e, em seguida, digitando o seguinte:</span><span class="sxs-lookup"><span data-stu-id="301da-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="301da-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="301da-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="301da-133">Se estiver usando uma autoridade de certificação empresarial do Windows Server 2008 ou do Windows Server 2008 R2, você deve usar HTTPS, não http.</span><span class="sxs-lookup"><span data-stu-id="301da-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="301da-134">Na página web certsrv da AC emissora, em  **Selecione uma tarefa**, clique em **Download de um Certificado de Autoridade de Certificação, Cadeia de Certificados ou Lista de Certificados Revogados**.</span><span class="sxs-lookup"><span data-stu-id="301da-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="301da-135">Em **baixar um certificado de autoridade de certificação, uma cadeia de certificados ou uma CRL**, clique em **baixar cadeia de certificados da CA**.</span><span class="sxs-lookup"><span data-stu-id="301da-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="301da-136">Na caixa de diálogo **download de arquivo** , clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="301da-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="301da-137">Salve o arquivo. p7b na unidade de disco rígido no servidor e copie-o para uma pasta em cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="301da-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="301da-138">O arquivo. p7b contém todos os certificados que estão no caminho de certificação.</span><span class="sxs-lookup"><span data-stu-id="301da-138">The .p7b file contains all of the certificates that are in the certification path.</span></span> <span data-ttu-id="301da-139">Para exibir o caminho de certificação, abra o certificado do servidor e clique no caminho de certificação.</span><span class="sxs-lookup"><span data-stu-id="301da-139">To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="301da-140">Para exportar a cadeia de certificação da CA para a interface interna usando o MMC</span><span class="sxs-lookup"><span data-stu-id="301da-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="301da-141">Você pode exportar o certificado raiz da autoridade de certificação de qualquer computador ingressado no domínio usando o console de gerenciamento Microsoft (MMC).</span><span class="sxs-lookup"><span data-stu-id="301da-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="301da-142">Clique em **Iniciar**, clique em **executar**e digite **MMC**.</span><span class="sxs-lookup"><span data-stu-id="301da-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="301da-143">No console MMC, clique em **arquivo**, clique em **Adicionar/remover**.</span><span class="sxs-lookup"><span data-stu-id="301da-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="301da-144">Na lista de diálogo **Adicionar ou remover snap-ins** , selecione **certificados**e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="301da-144">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**.</span></span> <span data-ttu-id="301da-145">Quando solicitado, selecione **conta do computador**.</span><span class="sxs-lookup"><span data-stu-id="301da-145">When prompted, select **Computer Account**.</span></span> <span data-ttu-id="301da-146">Na caixa de diálogo **Selecionar Computador**, selecione **Computador Local**.</span><span class="sxs-lookup"><span data-stu-id="301da-146">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="301da-147">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="301da-147">Click **Finish**.</span></span> <span data-ttu-id="301da-148">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="301da-148">Click **OK**.</span></span>

4.  <span data-ttu-id="301da-149">Expanda **Certificates (computador local)**.</span><span class="sxs-lookup"><span data-stu-id="301da-149">Expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="301da-150">Expanda **autoridades de certificação raiz confiáveis**, selecione **certificados**.</span><span class="sxs-lookup"><span data-stu-id="301da-150">Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="301da-151">Clique no certificado raiz emitido por sua AC.</span><span class="sxs-lookup"><span data-stu-id="301da-151">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="301da-152">Clique com o botão direito do mouse no certificado, selecione **todas as tarefas**, selecione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="301da-152">Right click the certificate, select **All Tasks**, select **Export**.</span></span> <span data-ttu-id="301da-153">O **Assistente para exportação de certificados** será aberto.</span><span class="sxs-lookup"><span data-stu-id="301da-153">The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="301da-154">No **Assistente de Exportação de Certificado**, clique em  **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="301da-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="301da-155">Na caixa de diálogo **exportar formato de arquivo** , selecione um formato para o qual exportar.</span><span class="sxs-lookup"><span data-stu-id="301da-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="301da-156">Recomendamos o **padrão de sintaxe da mensagem criptográfica \#– Certificados PKCS 7 (. P7B)**.</span><span class="sxs-lookup"><span data-stu-id="301da-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="301da-157">Se você selecionar o **padrão de sintaxe da mensagem criptográfica \#– Certificados PKCS 7 (. P7B)**, marque a caixa de seleção **incluir todos os certificados no caminho de certificação, se possível** , para exportar a cadeia de certificados, incluindo o certificado da CA raiz e qualquer certificado de autoridade de certificação intermediário.</span><span class="sxs-lookup"><span data-stu-id="301da-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="301da-158">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="301da-158">Click **Next**.</span></span>

8.  <span data-ttu-id="301da-159">Na caixa de diálogo **arquivo para exportação** na entrada nome do arquivo, digite um nome de caminho e arquivo (extensão padrão é. p7b) para o certificado exportado.</span><span class="sxs-lookup"><span data-stu-id="301da-159">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate.</span></span> <span data-ttu-id="301da-160">Opcionalmente, clique em **procurar**, localize um diretório para colocar o certificado exportado e forneça um nome para o certificado exportado.</span><span class="sxs-lookup"><span data-stu-id="301da-160">Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate.</span></span> <span data-ttu-id="301da-161">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="301da-161">Click **Save**.</span></span> <span data-ttu-id="301da-162">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="301da-162">Click **Next**.</span></span>

9.  <span data-ttu-id="301da-163">Examine o resumo de ações e clique em **concluir** para concluir a exportação do certificado.</span><span class="sxs-lookup"><span data-stu-id="301da-163">Review the summary of actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="301da-164">Clique em **OK** para confirmar que a exportação foi bem sucedida.</span><span class="sxs-lookup"><span data-stu-id="301da-164">Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="301da-165">Para importar a cadeia de certificação da CA para a interface interna</span><span class="sxs-lookup"><span data-stu-id="301da-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="301da-166">Em cada servidor de borda, abra o MMC (console de gerenciamento Microsoft) clicando em **Iniciar**, clicando em **executar**, digitando **MMC** na caixa **abrir** e, em seguida, clicando em **OK**.</span><span class="sxs-lookup"><span data-stu-id="301da-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="301da-167">No menu **arquivo** , clique em **Adicionar/remover snap-in**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="301da-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="301da-168">Na caixa **Adicionar Snap-ins Autônomos** , clique em **certificados**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="301da-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="301da-169">Na caixa de diálogo  **Snap-in de certificados**, clique em  **Conta de computador**e, em seguida, clique em  **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="301da-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="301da-170">Na caixa de diálogo **Selecionar computador** , verifique se a caixa de seleção **computador local: (o computador em que este console está sendo executado)** está marcada e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="301da-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="301da-171">Clique em **fechar**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="301da-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="301da-172">Na árvore de console, expanda **certificados (computador local)**, clique com o botão direito do mouse em **autoridades de certificação raiz confiáveis**, aponte para **todas as tarefas**e, em seguida, clique em **importar**.</span><span class="sxs-lookup"><span data-stu-id="301da-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="301da-173">No assistente, em **arquivo a ser**importado, especifique o nome do arquivo do certificado (ou seja, o nome que você especificou quando baixou a cadeia de certificação CA para a interface interna no procedimento anterior).</span><span class="sxs-lookup"><span data-stu-id="301da-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="301da-174">Repita esse procedimento em cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="301da-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="301da-175">Para criar a solicitação de certificado para a interface interna</span><span class="sxs-lookup"><span data-stu-id="301da-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="301da-176">Em um dos servidores de borda, inicie o assistente de implantação e, em seguida, ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="301da-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="301da-177">Se você tiver vários servidores de borda em um local em um pool, poderá executar o assistente de certificado em qualquer um dos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="301da-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="301da-178">Depois de executar a etapa 3 na primeira vez, o botão muda para <STRONG>executar novamente</STRONG>, e uma marca de seleção verde que indica que a conclusão bem-sucedida da tarefa não é exibida até que todos os certificados exijam a solicitação, instalação e atribuição.</span><span class="sxs-lookup"><span data-stu-id="301da-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="301da-179">Na página **Tarefas de Certificado Disponíveis**, clique em  **Criar uma nova solicitação de certificado**.</span><span class="sxs-lookup"><span data-stu-id="301da-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="301da-180">Na página **solicitação de certificado** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="301da-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="301da-181">Na página  **Solicitações Atrasadas ou Imediatas**, clique em  **Preparar a solicitação agora, mas enviá-la depois**.</span><span class="sxs-lookup"><span data-stu-id="301da-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="301da-182">Na página **arquivo de solicitação de certificado** , digite o caminho completo e o nome do arquivo para o qual a solicitação deve ser salva (por exemplo, **c\_:\\borda interna do CERT\_. cer**).</span><span class="sxs-lookup"><span data-stu-id="301da-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="301da-183">Na página **especificar modelo de certificado alternativo** , para usar um modelo diferente do modelo padrão do webserver, marque a caixa de seleção **usar modelo de certificado alternativo para a autoridade de certificação selecionada** .</span><span class="sxs-lookup"><span data-stu-id="301da-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="301da-184">Na página **configurações de nome e segurança** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="301da-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="301da-185">Em **nome amigável**, digite um nome de exibição para o certificado (por exemplo, borda interna).</span><span class="sxs-lookup"><span data-stu-id="301da-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="301da-186">Em **comprimento de bit**, especifique o comprimento do bit (geralmente, o padrão de **2048**).</span><span class="sxs-lookup"><span data-stu-id="301da-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="301da-187">Comprimentos de bit mais altos oferecem mais segurança, mas têm um impacto negativo na velocidade.</span><span class="sxs-lookup"><span data-stu-id="301da-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="301da-188">Se o certificado precisar ser exportável, marque a caixa de seleção **Marcar chave privada de certificado como** exportável.</span><span class="sxs-lookup"><span data-stu-id="301da-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="301da-189">Na página **informações da organização** , digite o nome da organização e a unidade organizacional (ou) (por exemplo, uma divisão ou um departamento).</span><span class="sxs-lookup"><span data-stu-id="301da-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="301da-190">Na página **informações** geográficas, especifique as informações de localização.</span><span class="sxs-lookup"><span data-stu-id="301da-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="301da-191">Na página **nome do assunto/nomes alternativos de assunto** , as informações a serem automaticamente preenchidas pelo assistente serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="301da-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="301da-192">Na página **configurar nomes alternativos de entidades adicionais** , especifique os nomes alternativos de entidades adicionais necessários.</span><span class="sxs-lookup"><span data-stu-id="301da-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="301da-193">Na página **Resumo da solicitação** , examine as informações do certificado que serão usadas para gerar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="301da-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="301da-194">Depois que os comandos forem concluídos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="301da-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="301da-195">Para exibir o log para a solicitação de certificado, clique em **Exibir log**.</span><span class="sxs-lookup"><span data-stu-id="301da-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="301da-196">Para concluir a solicitação de certificado, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="301da-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="301da-197">Na página **arquivo de solicitação de certificado** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="301da-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="301da-198">Para exibir o arquivo de solicitação de assinatura de certificado (CSR) gerado, clique em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="301da-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="301da-199">Para fechar o assistente, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="301da-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="301da-200">Envie este arquivo para a sua CA (por email ou outro método compatível com sua organização para a sua CA corporativa) e, quando você receber o arquivo de resposta, copie o novo certificado para este computador para que ele esteja disponível para importação.</span><span class="sxs-lookup"><span data-stu-id="301da-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="301da-201">Para importar o certificado para a interface interna</span><span class="sxs-lookup"><span data-stu-id="301da-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="301da-202">Faça logon no servidor de borda em que você criou a solicitação de certificado como membro do grupo Administradores local.</span><span class="sxs-lookup"><span data-stu-id="301da-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="301da-203">No assistente de implantação, ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.</span><span class="sxs-lookup"><span data-stu-id="301da-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="301da-204">Depois de executar a etapa 3 na primeira vez, o botão muda para **executar novamente**, mas uma marca de seleção verde (indicando a conclusão bem-sucedida da tarefa) não é exibida até que todos os certificados exijam que os certificados tenham sido solicitados, instalados e atribuídos.</span><span class="sxs-lookup"><span data-stu-id="301da-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="301da-205">Na página **tarefas de certificado disponíveis** , clique em **importar um certificado de a. Arquivo P7b,. pfx ou. cer**.</span><span class="sxs-lookup"><span data-stu-id="301da-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="301da-206">Na página **importar certificado** , digite o caminho completo e o nome do arquivo do certificado que você solicitou e recebeu para a interface interna deste servidor de borda (ou clique em **procurar** para localizar e selecionar o arquivo).</span><span class="sxs-lookup"><span data-stu-id="301da-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="301da-207">Se você estiver importando certificados para outros membros do pool um certificado contendo uma chave privada, marque a caixa de seleção o **arquivo de certificado contém a chave privada da Certifcate** e especifique a senha.</span><span class="sxs-lookup"><span data-stu-id="301da-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="301da-208">Para exportar o certificado com a chave privada para servidores de borda em um pool</span><span class="sxs-lookup"><span data-stu-id="301da-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="301da-209">Faça logon como membro do grupo Administradores para o mesmo servidor de borda no qual você importou o certificado.</span><span class="sxs-lookup"><span data-stu-id="301da-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="301da-210">Clique em **Iniciar**, clique em **executar**e digite **MMC**.</span><span class="sxs-lookup"><span data-stu-id="301da-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="301da-211">No console do MMC, clique em **arquivo**, clique em **Adicionar/remover snap-in**.</span><span class="sxs-lookup"><span data-stu-id="301da-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="301da-212">Na página Adicionar ou remover snap-ins, clique em **certificados**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="301da-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="301da-213">Na caixa de diálogo snap-in de certificados, selecione **conta de computador**.</span><span class="sxs-lookup"><span data-stu-id="301da-213">In the Certificates snap-in dialog, select **Computer account**.</span></span> <span data-ttu-id="301da-214">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="301da-214">Click **Next**.</span></span> <span data-ttu-id="301da-215">Em Selecionar computador, selecione **computador local: (o computador no qual este console está sendo executado)**.</span><span class="sxs-lookup"><span data-stu-id="301da-215">In Select Computer, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="301da-216">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="301da-216">Click **Finish**.</span></span> <span data-ttu-id="301da-217">Clique em **OK** para concluir a configuração do console MMC.</span><span class="sxs-lookup"><span data-stu-id="301da-217">Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="301da-218">Clique duas vezes em **Certificados (Computador Local)** para expandir os repositórios de certificados.</span><span class="sxs-lookup"><span data-stu-id="301da-218">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="301da-219">Clique duas vezes em **pessoal**e, em seguida, clique duas vezes em **certificados**.</span><span class="sxs-lookup"><span data-stu-id="301da-219">Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="301da-220">Se não houver certificados no armazenamento pessoal de certificados do computador local, não há uma chave privada associada ao certificado que foi importado.</span><span class="sxs-lookup"><span data-stu-id="301da-220">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="301da-221">Examine as etapas de solicitação e importação.</span><span class="sxs-lookup"><span data-stu-id="301da-221">Review the request and import steps.</span></span> <span data-ttu-id="301da-222">Se o problema persistir, entre em contato com o administrador ou o provedor da autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="301da-222">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="301da-223">No armazenamento de certificados pessoal do computador local, clique com o botão direito do mouse no certificado que você está exportando.</span><span class="sxs-lookup"><span data-stu-id="301da-223">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting.</span></span> <span data-ttu-id="301da-224">Clique em **todas as tarefas**, clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="301da-224">Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="301da-225">No Assistente para exportação de certificados, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="301da-225">In the Certificate Export Wizard, click **Next**.</span></span> <span data-ttu-id="301da-226">Selecione **Sim, exportar a chave privada**.</span><span class="sxs-lookup"><span data-stu-id="301da-226">Select **Yes, export the private key**.</span></span> <span data-ttu-id="301da-227">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="301da-227">Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="301da-228">Se a seleção <STRONG>Sim, exportar a chave privada</STRONG> não estiver disponível, a chave privada associada a esse certificado não foi marcada para exportação.</span><span class="sxs-lookup"><span data-stu-id="301da-228">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="301da-229">Você precisará solicitar o certificado novamente, certificando-se de que o certificado esteja marcado para permitir a exportação da chave privada antes de continuar com a exportação.</span><span class="sxs-lookup"><span data-stu-id="301da-229">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="301da-230">Entre em contato com o administrador ou provedor da autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="301da-230">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="301da-231">Na caixa de diálogo Exportar formatos de arquivo, selecione **troca de informações\#pessoais – PKCS 12 (. PFX)** e, em seguida, selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="301da-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="301da-232">Incluir todos os certificados no caminho de certificação, se possível</span><span class="sxs-lookup"><span data-stu-id="301da-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="301da-233">Exportar todas as propriedades estendidas</span><span class="sxs-lookup"><span data-stu-id="301da-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="301da-234">Ao exportar o certificado de um servidor de borda, não selecione <STRONG>excluir a chave privada se a exportação for bem-sucedida</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="301da-234">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="301da-235">Selecionar essa opção exigirá que você importe o certificado e a chave privada para esse servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="301da-235">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="301da-236">Clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="301da-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="301da-237">Se você quiser atribuir uma senha para proteger a chave privada, digite uma senha para a chave privada.</span><span class="sxs-lookup"><span data-stu-id="301da-237">If you want to assign password to protect the private key, type a password for the private key.</span></span> <span data-ttu-id="301da-238">Digite a senha novamente para confirmá-la.</span><span class="sxs-lookup"><span data-stu-id="301da-238">Re-enter the password to confirm.</span></span> <span data-ttu-id="301da-239">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="301da-239">Click **Next**.</span></span>

11. <span data-ttu-id="301da-240">Digite um caminho e o nome de arquivo para o certificado exportado, usando uma extensão de arquivo .pfx.</span><span class="sxs-lookup"><span data-stu-id="301da-240">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="301da-241">O caminho deve ser acessível a todos os outros servidores de borda do pool ou disponível para transporte por meio de mídia removível-por exemplo, uma unidade flash USB.</span><span class="sxs-lookup"><span data-stu-id="301da-241">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="301da-242">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="301da-242">Click **Next**.</span></span>

12. <span data-ttu-id="301da-243">Examine o resumo na caixa de diálogo concluindo o assistente para exportação de certificados.</span><span class="sxs-lookup"><span data-stu-id="301da-243">Review the summary on the Completing the Certificate Export Wizard dialog.</span></span> <span data-ttu-id="301da-244">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="301da-244">Click **Finish**.</span></span>

13. <span data-ttu-id="301da-245">Clique em **OK** na caixa de diálogo da exportação com sucesso.</span><span class="sxs-lookup"><span data-stu-id="301da-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="301da-246">Importe o arquivo de certificado exportado para os outros servidores de borda seguindo as etapas descritas nos procedimentos [configurar certificados para a interface de borda externa dos procedimentos do Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="301da-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="301da-247">Para atribuir o certificado interno nos servidores de borda</span><span class="sxs-lookup"><span data-stu-id="301da-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="301da-248">Em cada servidor de borda, no assistente de implantação, ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.</span><span class="sxs-lookup"><span data-stu-id="301da-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="301da-249">Na página **tarefas de certificado disponíveis** , clique em **atribuir um certificado existente**.</span><span class="sxs-lookup"><span data-stu-id="301da-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="301da-250">Na página **Atribuição de Certificado**, selecione  **Interno à Borda** na lista.</span><span class="sxs-lookup"><span data-stu-id="301da-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="301da-251">Na página **repositório de certificados** , selecione o certificado que você importou para a borda interna (do procedimento anterior).</span><span class="sxs-lookup"><span data-stu-id="301da-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="301da-252">Na página **Resumo de atribuição de certificado** , examine suas configurações e clique em **Avançar** para atribuir os certificados.</span><span class="sxs-lookup"><span data-stu-id="301da-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="301da-253">Na página de conclusão do assistente, clique em  **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="301da-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="301da-254">Depois de usar esse procedimento para atribuir o certificado de borda interno, abra o snap-in de certificado em cada servidor, expanda **certificados (computador local)**, expanda **pessoal**, clique em **certificados**e verifique o painel de detalhes que o certificado de borda interna é listado.</span><span class="sxs-lookup"><span data-stu-id="301da-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="301da-255">Se a sua implantação incluir vários servidores de borda, repita esse procedimento para cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="301da-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

