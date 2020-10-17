---
title: 'Lync Server 2013: configurar certificados para a interface de borda interna'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8f8c5c41eba828cb6514ba6963167d708ed203d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509888"
---
# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="2d1d8-102">Configurar certificados para a interface de borda interna no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d1d8-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d1d8-103">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="2d1d8-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2d1d8-104">Ao executar o Assistente de certificado, certifique-se de que esteja conectado usando uma conta membro de um grupo com as permissões apropriadas para o tipo de modelo de certificado que será usado.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="2d1d8-105">Por padrão, uma solicitação de certificado do Lync Server 2013 usará o modelo de certificado do servidor Web.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="2d1d8-106">Se uma conta membro do grupo RTCUniversalServerAdmins for utilizada para solicitar um certificado usando este modelo, verifique se foram atribuídas as permissões Inscrever a este grupo, necessárias para usar o modelo.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="2d1d8-p102">Um único certificado é necessário na interface interna de cada Servidor de Borda. Os certificados para a interface interna podem ser emitidos por uma autoridade de certificação empresarial interna ou por uma autoridade de certificação pública. Se a sua organização tiver uma autoridade de certificação interna implantada, poderá diminuir as despesas de uso de certificados públicos utilizando a autoridade de certificação interna para emitir o certificado para a interface interna. Você pode usar uma autoridade de certificação interna do Windows Server 2008 ou uma autoridade de certificação do Windows Server 2008 R2 para criar esses certificados.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p102">A single certificate is required on the internal interface of each Edge Server. Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA. If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface. You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="2d1d8-111">Para obter detalhes sobre esse e outros requisitos de certificado, consulte [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="2d1d8-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="2d1d8-112">Para configurar certificados na interface da borda interna em um site, use os procedimentos nesta seção para:</span><span class="sxs-lookup"><span data-stu-id="2d1d8-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="2d1d8-113">Fazer download da cadeia de certificação da AC para a interface interna para cada Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="2d1d8-114">Importar a cadeia de certificação do para a interface interna, em cada Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="2d1d8-115">Criar a solicitação de certificado da interface externa em um Servidor de Borda, considerado o primeiro Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="2d1d8-116">Importar o certificado da interface interna no primeiro Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="2d1d8-117">Importar o certificado nos outros Servidores de Borda neste local (ou implantados por trás deste balanceador de carga).</span><span class="sxs-lookup"><span data-stu-id="2d1d8-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="2d1d8-118">Atribuir o certificado à interface interna de cada Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="2d1d8-119">Se você tem mais de um local com Servidores de Borda (ou seja, uma topologia de borda de múltiplos locais) ou conjuntos separados de Servidores de Borda implantados por trás de diferentes balanceadores de carga, é necessário seguir estas etapas para cada local que possua Servidores de Borda e para cada conjunto de Servidores de Borda implantados por trás de um balanceador de carga diferente.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d1d8-120">As etapas para procedimentos nesta seção são baseadas no uso de uma AC do Windows Server 2008, da autoridade de certificação do Windows Server 2008 R2, da autoridade de certificação do Windows Server &nbsp; &nbsp; &nbsp; 2012 ou da autoridade de certificação do Windows Server 2012 R2 para criar um certificado para cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="2d1d8-121">Para uma orientação passo-a-passo para qualquer outra AC, consulte a documentação para aquela AC.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="2d1d8-122">Por padrão, todos os usuários autenticados possuem os direitos de usuário apropriados para solicitar certificados.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="2d1d8-p104">Os procedimentos nesta seção são baseados na criação de solicitações de certificado no Servidor de Borda como parte do processo de implantação do Servidor de Borda. É possível criar solicitações de certificado usando o Servidor Front End. Faça isso para concluir a solicitação do certificado mais cedo no processo de planejamento e implantação, antes de começar a implantação dos Servidores de Borda. Para isso, você deve garantir que o certificado a ser solicitado é definido como uma chave privada que pode ser exportada.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p104">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process. It is possible to create certificate requests using the Front End Server. You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers. To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="2d1d8-p105">Os procedimentos nesta seção descrevem a utilização de um arquivo .cer e um arquivo .p7b para o certificado. Se você usa um tipo diferente de arquivo, modifique estes procedimentos de acordo.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p105">The procedures in this section describe using a .cer and a .p7b file for the certificate. If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="2d1d8-129">Para fazer download da cadeia de certificação da AC para a interface interna usando o website certsrv</span><span class="sxs-lookup"><span data-stu-id="2d1d8-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="2d1d8-130">Faça logon em um servidor do Lync Server 2013 na rede interna (ou seja, não no servidor de borda) como um membro do grupo **Administradores** .</span><span class="sxs-lookup"><span data-stu-id="2d1d8-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="2d1d8-131">Execute o comando a seguir no prompt de comando, clicando em **Iniciar**, **Executar** e digitando:</span><span class="sxs-lookup"><span data-stu-id="2d1d8-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="2d1d8-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2d1d8-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2d1d8-133">Se estiver usando uma AC do Windows Server 2008 ou Windows Server 2008 R2 Enterprise, você deve usar https, não http.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="2d1d8-134">Na página web certsrv da AC emissora, em **Selecione uma tarefa**, clique em **Download de um Certificado de Autoridade de Certificação, Cadeia de Certificados ou Lista de Certificados Revogados**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="2d1d8-135">Em **Download de um Certificado de Autoridade de Certificação, Cadeia de Certificados ou Lista de Certificados Revogados**, clique em **Fazer download de cadeia de certificados de autoridade de certificação**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="2d1d8-136">Na caixa de diálogo **Download de Arquivo**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="2d1d8-137">Salve o arquivo .p7b na unidade de disco rígido e copie-o para uma pasta em cada Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2d1d8-p106">O arquivo .p7b contém todos os certificados existentes no caminho de certificação. Para exibir o caminho de certificação, abra o certificado do servidor e clique no caminho de certificação.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p106">The .p7b file contains all of the certificates that are in the certification path. To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="2d1d8-140">Para importar a cadeia de certificação da AC para a interface interna usando MMC</span><span class="sxs-lookup"><span data-stu-id="2d1d8-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="2d1d8-141">Você pode exportar o certificado raiz da autoridade de certificação de qualquer computador que ingressou no domínio usando o console de gerenciamento Microsoft (MMC).</span><span class="sxs-lookup"><span data-stu-id="2d1d8-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="2d1d8-142">Clique em **Iniciar**, **Executar** e depois digite **MMC**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="2d1d8-143">No console do MMC, clique em **Arquivo** e em **Adicionar/Remover**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="2d1d8-p108">Na lista de diálogos **Adicionar/Remover Snap-ins**, selecione **Certificados**, e depois clique em **Adicionar**. Ao ser solicitado, selecione **Conta do computador**. No diálogo **Selecionar computador**, selecione **Computador local**. Clique em **Finalizar**. Clique em**OK**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p108">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**. When prompted, select **Computer Account**. On the **Select Computer** dialog, select **Local Computer**. Click **Finish**. Click **OK**.</span></span>

4.  <span data-ttu-id="2d1d8-p109">Expanda **Certificados (Computador local)**. Expanda **Autoridades de Certificação Raiz Confiáveis.**, selecione **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p109">Expand **Certificates (Local Computer)**. Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="2d1d8-p110">Clique no certificado raiz emitido por sua AC. Clique com o botão direito no certificado, selecione **Todas as tarefas**, selecione **Exportar**. O **Assistente de Exportação de Certificado** será aberto.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p110">Click the root certificate issued by your CA. Right click the certificate, select **All Tasks**, select **Export**. The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="2d1d8-154">No **Assistente de Exportação de Certificado**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="2d1d8-155">Na caixa de diálogo **Formato do arquivo de exportação**, selecione um formato para exportar.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="2d1d8-156">Recomendamos o **padrão de sintaxe de mensagens criptografadas – \# Certificados PKCS 7 (. P7B)**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="2d1d8-157">Se você selecionar o **padrão de sintaxe de mensagens criptografadas – \# Certificados PKCS 7 (. P7B)**, marque a caixa de seleção **incluir todos os certificados no caminho de certificação, se possível** , para exportar a cadeia de certificados, incluindo o certificado de autoridade de certificação raiz e quaisquer certificados de autoridade de certificação intermediários.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="2d1d8-158">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-158">Click **Next**.</span></span>

8.  <span data-ttu-id="2d1d8-p112">Na caixa de diálogo **Arquivo para exportar**, na entrada do nome do arquivo, digite um caminho e nome de arquivo (a extensão padrão é .p7b) para o certificado exportado. Opcionalmente, clique em **Procurar**, localize um diretório para colocar o certificado exportado e forneça um nome para o certificado exportado. Clique em  **Salvar**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p112">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate. Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate. Click **Save**. Click **Next**.</span></span>

9.  <span data-ttu-id="2d1d8-p113">Revise o resumo de ações e clique em **Concluir** para concluir a exportação do certificado. Clique em **OK** para confirmar que a exportação foi bem sucedida.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p113">Review the summary of actions, and click **Finish** to complete the export of the certificate. Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="2d1d8-165">Para importar a cadeia de certificação da AC para a interface interna</span><span class="sxs-lookup"><span data-stu-id="2d1d8-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="2d1d8-166">Em cada Servidor de Borda, abra o Console de Gerenciamento Microsoft clicando em **Iniciar**, clicando em **Executar**, digitando **mmc** na caixa **Abrir** e clicando em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="2d1d8-167">No menu **Arquivo**, clique em **Adicionar/Remover Snap-in** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="2d1d8-168">Na caixa **Adicionar Snap-in Autônomo**, clique em **Certificados** e em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="2d1d8-169">Na caixa de diálogo **Snap-in de certificados**, clique em **Conta de computador** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="2d1d8-170">Na caixa de diálogo **Selecionar computador**, verifique se a caixa de seleção **Computador local: (o computador que este console está executando)** está marcada e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="2d1d8-171">Clique em **Fechar** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="2d1d8-172">Na árvore do console, expanda **Certificados (computador local)**, clique com o botão direito em **Autoridades de Certificação Confiáveis**, aponte para **Todas as tarefas** e clique em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="2d1d8-173">No assistente, em **Arquivo a ser importado**, especifique o nome do arquivo do certificado (ou seja, o nome que você especificou quando fez o download da cadeia de certificado da AC para a interface interna no procedimento anterior).</span><span class="sxs-lookup"><span data-stu-id="2d1d8-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="2d1d8-174">Repita esse procedimento em cada Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="2d1d8-175">Para criar a solicitação de certificado da interface interna</span><span class="sxs-lookup"><span data-stu-id="2d1d8-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="2d1d8-176">Em um dos Servidores de Borda, inicie o Assistente de Implantação e na **Etapa 3: Solicitar, Instalar ou Ceder Certificados**, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2d1d8-177">Se houver vários Servidores de Borda em uma localização em um pool, você pode executar o Assistente de Certificado em qualquer um deles.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="2d1d8-178">Depois de executar a Etapa 3 pela primeira vez, o botão é alterado para <STRONG>Executar novamente</STRONG> e uma marca de seleção verde que indica a conclusão bem sucedida da tarefa não é exibida até que todos os certificados tenham sido solicitados, instalados e cedidos.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="2d1d8-179">Na página **Tarefas de Certificado Disponíveis**, clique em **Criar uma nova solicitação de certificado**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="2d1d8-180">Na página **Solicitação de Certificado**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="2d1d8-181">Na página **Solicitações Atrasadas ou Imediatas**, clique em **Preparar a solicitação agora, mas enviá-la depois**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="2d1d8-182">Na página **arquivo de solicitação de certificado** , digite o caminho completo e o nome do arquivo para o qual a solicitação será salva (por exemplo, **c: \\ borda interna de CERT \_ \_ . cer**).</span><span class="sxs-lookup"><span data-stu-id="2d1d8-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="2d1d8-183">Na página **Especificar Modelo de Certificado Alternativo**, para usar um modelo diferentes do modelo padrão do WebServer, marque a opção **Usar modelo de certificado alternativo para a Autoridade de Certificação selecionada**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="2d1d8-184">Na página **Nome e Configurações de Segurança**, siga estes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="2d1d8-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="2d1d8-185">Em **Nome amigável**, digite um nome de exibição para o certificado (por exemplo, Borda Interna).</span><span class="sxs-lookup"><span data-stu-id="2d1d8-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="2d1d8-186">Em **Comprimento de bit**, especifique o comprimento de bit (normalmente o padrão de **2048**).</span><span class="sxs-lookup"><span data-stu-id="2d1d8-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2d1d8-187">Comprimentos de bit mais altos oferecem mais segurança, mas causam um impacto negativo sobre a velocidade.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="2d1d8-188">Se for necessário que o certificado seja exportável, marque a opção **Marcar chave privada do certificado como exportável**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="2d1d8-189">Na página **Informações da Organização**, digite o nome da organização e da unidade organizacional (UO) (por exemplo, uma divisão ou departamento).</span><span class="sxs-lookup"><span data-stu-id="2d1d8-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="2d1d8-190">Na página **Informações Geográficas**, especifique as informações de localização.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="2d1d8-191">Na página **Nome da Entidade/Nomes Alternativos da Entidade**, as informações que serão preenchidas automaticamente pelo assistente são exibidas.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="2d1d8-192">Na página **Configurar Nomes Alternativos da Entidade Adicionais**, especifique quaisquer nomes alternativos de entidade adicionais que sejam necessários.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="2d1d8-193">Na página **Resumo da Solicitação**, analise as informações do certificado a serem usadas para gerar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="2d1d8-194">Depois de concluir os comandos, siga o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="2d1d8-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="2d1d8-195">Para exibir o log da solicitação do certificado, clique em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="2d1d8-196">Para concluir a solicitação de certificado, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="2d1d8-197">Na página **Arquivo de Solicitação de Certificado**, execute os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="2d1d8-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="2d1d8-198">Para exibir um arquivo CSR (solicitação de assinatura de certificado) gerado, clique em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="2d1d8-199">Para fechar o assistente, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="2d1d8-200">Envie este arquivo para a sua AC (por e-mail ou por outro método aceito pela sua organização para sua AC corporativa) e, quando receber o arquivo de resposta, copie o novo certificado para este computador, para que esteja disponível para importação.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="2d1d8-201">Para importar o certificado da interface interna</span><span class="sxs-lookup"><span data-stu-id="2d1d8-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="2d1d8-202">Faça logon no Servidor de Borda em que você criou a solicitação de certificado como membro do grupo Administradores local.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="2d1d8-203">No Assistente de Implantação, em **Etapa 3: Solicitar, Instalar ou Ceder Certificados**, clique em **Executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="2d1d8-204">Depois de executar a Etapa 3 pela primeira vez, o botão é alterado para **Executar novamente**, mas uma marca de seleção verde que indica a conclusão bem sucedida da tarefa não é exibida até que todos os certificados tenham sido solicitados, instalados e cedidos.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="2d1d8-205">Na página **Tarefas de Certificado Disponíveis**, clique em **Importar um certificado de um arquivo .P7b, .pfx ou .cer**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="2d1d8-206">Na página **Importar Certificado**, digite o caminho completo e nome do arquivo do certificado que você solicitou e recebeu para a interface interna deste Servidor De Borda (ou clique em **Procurar** para localizar e selecionar o arquivo).</span><span class="sxs-lookup"><span data-stu-id="2d1d8-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="2d1d8-207">Se você estiver importando certificados para outros membros do pool, um certificado que contenha uma chave privada, marque a opção **O arquivo do certificado contém a chave privada do certificado** e especifique a senha.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="2d1d8-208">Para exportar o certificado com a chave privada para os Servidores de Borda em um pool</span><span class="sxs-lookup"><span data-stu-id="2d1d8-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="2d1d8-209">Faça logon como membro do grupo de Administradores para o mesmo Servidor de Borda no qual você importou o certificado.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="2d1d8-210">Clique em **Iniciar**, **Executar** e digite **MMC**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="2d1d8-211">No console do MMC, clique em **Arquivo** e em **Adicionar/Remover Snap-in**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="2d1d8-212">Na página Adicionar ou Remover Snap-ins, clique em **Certificados** e em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="2d1d8-p114">Na caixa de diálogo Snap-in de certificados, selecione **Conta de computador**. Clique em **Avançar**. Em Selecionar Computador, selecione **Computador local: (o computador no qual este console está sendo executado)**. Clique em **Concluir**. Clique em **OK** para concluir a configuração do console MMC.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p114">In the Certificates snap-in dialog, select **Computer account**. Click **Next**. In Select Computer, select **Local computer: (the computer this console is running on)**. Click **Finish**. Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="2d1d8-p115">Dê um duplo clique em **Certificados (Computador Local)** para expandir o repositório de certificados. Dê um duplo clique em **Pessoal** e em **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p115">Double-click **Certificates (Local Computer)** to expand the certificate stores. Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2d1d8-p116">Se não houver certificados no repositório Certificados Pessoais para o computador local, não existe chave privada associada ao certificado importado. Analise a solicitação e as etapas de importação. Se o problemas persistir, entre em contato com o administrador ou fornecedor da sua autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p116">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="2d1d8-p117">No repositório Certificados Pessoais para o computador local, clique com o botão direito no certificado que está exportando. Clique em **Todas as Tarefas** e em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p117">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting. Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="2d1d8-p118">No Assistente de Exportação de Certificado, clique em **Avançar**. Selecione **Sim, exportar a chave privada**. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p118">In the Certificate Export Wizard, click **Next**. Select **Yes, export the private key**. Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2d1d8-p119">Se a opção <STRONG>Sim, exportar a chave privada</STRONG> não estiver disponível, a chave privada associada a este certificado não foi marcada para exportação. Será necessário solicitar o certificado novamente, garantindo que esteja marcado para permitir a exportação da chave privada antes de dar continuidade à exportação. Entre em contato com o administrador ou fornecedor da sua autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p119">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="2d1d8-231">Na caixa de diálogo Exportar formatos de arquivo, selecione **troca de informações pessoais – PKCS \# 12 (. PFX)** e selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2d1d8-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="2d1d8-232">Incluir todos os certificados no caminho de certificação, se possível</span><span class="sxs-lookup"><span data-stu-id="2d1d8-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="2d1d8-233">Exportar todas as propriedades estendidas</span><span class="sxs-lookup"><span data-stu-id="2d1d8-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="2d1d8-p120">Ao exportar o certificado de um servidor de Borda, não selecione <STRONG>Excluir a chave privada se a exportação tiver êxito</STRONG>. Selecionar esta opção exigirá a importação do certificado e da chave privada para este Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p120">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="2d1d8-236">Clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="2d1d8-p121">Se desejar atribuir uma senha para proteger a chave privada, digite uma senha para a chave privada. Insira novamente a senha para confirmar. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p121">If you want to assign password to protect the private key, type a password for the private key. Re-enter the password to confirm. Click **Next**.</span></span>

11. <span data-ttu-id="2d1d8-p122">Digite um caminho e nome de arquivo para o certificado exportado, usando uma extensão de arquivo .pfx. O caminho deve estar acessível a todos os outros servidores de Borda no pool ou disponível para transporte via mídia removível - por exemplo, um pen drive. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p122">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

12. <span data-ttu-id="2d1d8-p123">Analise o resumo na caixa de diálogo Concluindo o Assistente para Exportação de Certificados. Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-p123">Review the summary on the Completing the Certificate Export Wizard dialog. Click **Finish**.</span></span>

13. <span data-ttu-id="2d1d8-245">Clique em **OK** na caixa de diálogo da exportação com sucesso.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="2d1d8-246">Importe o arquivo de certificado exportado para os outros servidores de borda seguindo as etapas descritas nos procedimentos de [configuração de certificados para a interface de borda externa para o Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2d1d8-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="2d1d8-247">Para atribuir o certificado interno aos Servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="2d1d8-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="2d1d8-248">Em cada Servidor de Borda, no Assistente de Implantação, em **Etapa 3: Solicitar, Instalar ou Ceder Certificados**, clique em **Executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="2d1d8-249">Na página **Tarefas de Certificado Disponíveis**, clique em **Atribuir um certificado existente**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="2d1d8-250">Na página **Atribuição de Certificado**, selecione **Interno à Borda** na lista.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="2d1d8-251">Na página **Repositório de Certificados**, selecione o certificado importado para a borda interna (no procedimento anterior).</span><span class="sxs-lookup"><span data-stu-id="2d1d8-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="2d1d8-252">Na página **Resumo da Atribuição de Certificado**, analise suas configurações e clique em **Avançar** para atribuir os certificados.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="2d1d8-253">Na página de conclusão do assistente, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="2d1d8-254">Depois de usar este procedimento para atribuir o certificado de borda interna, abra o Snap-in de Certificados em cada servidor, expanda **Certificados (computador local)**, expanda **Pessoal**, clique em **Certificados** e verifique no painel de detalhes se o certificado da borda interna está listado.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="2d1d8-255">Se sua implantação incluir vários Servidores de Borda, repita este procedimento para cada um deles.</span><span class="sxs-lookup"><span data-stu-id="2d1d8-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

