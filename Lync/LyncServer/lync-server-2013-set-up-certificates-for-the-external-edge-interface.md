---
title: 'Lync Server 2013: Configurar certificados para a interface de borda externa'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1c836191c19eeadd915d0263c89b52289f60fe9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="4846f-102">Configurar certificados para a interface de borda externa para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4846f-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4846f-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="4846f-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4846f-104">Ao executar o assistente de certificado, certifique-se de que você esteja conectado usando uma conta que seja membro de um grupo que tenha recebido as permissões apropriadas para o tipo de modelo de certificado que você vai usar.</span><span class="sxs-lookup"><span data-stu-id="4846f-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="4846f-105">Por padrão, uma solicitação de certificado do Lync Server vai usar o modelo de certificado de servidor Web.</span><span class="sxs-lookup"><span data-stu-id="4846f-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="4846f-106">Se você usar uma conta que seja um membro do grupo RTCUniversalServerAdmins para solicitar um certificado usando esse modelo, verifique se o grupo recebeu as permissões de Registro necessárias para usar esse modelo.</span><span class="sxs-lookup"><span data-stu-id="4846f-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="4846f-107">Cada servidor de borda requer um certificado público na interface entre a rede de perímetro e a Internet, e o nome alternativo do requerente do certificado deve conter os nomes externos do serviço de borda de acesso e o serviço de borda de webconferências totalmente FQDNs (nomes de domínio qualificados).</span><span class="sxs-lookup"><span data-stu-id="4846f-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="4846f-108">Para obter detalhes sobre esse e outros requisitos de certificado, consulte [requisitos de certificado para acesso de usuários externos no Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="4846f-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="4846f-109">Para obter uma lista de autoridades de certificação (CAs) públicas que fornecem certificados compatíveis com requisitos específicos para certificados de comunicação unificada e que têm parceria com a Microsoft para garantir que elas funcionem com o assistente de certificado do Lync Server 2013, consulte o artigo 929395, "parceiros de certificado de comunicação unificada [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)para Exchange Server e para comunicações Server" em.</span><span class="sxs-lookup"><span data-stu-id="4846f-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="4846f-110">Configurar certificados nas interfaces externas</span><span class="sxs-lookup"><span data-stu-id="4846f-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="4846f-111">Para configurar um certificado na interface de borda externa em um site, use os procedimentos desta seção para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4846f-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="4846f-112">Crie a solicitação de certificado para a interface externa do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4846f-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="4846f-113">Envie a solicitação para sua CA pública.</span><span class="sxs-lookup"><span data-stu-id="4846f-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="4846f-114">Importar o certificado para a interface externa de cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4846f-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="4846f-115">Atribua o certificado para a interface externa de cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4846f-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="4846f-116">Se a sua implantação inclui vários servidores de borda, exporte o certificado juntamente com sua chave particular e copie-o para outros servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="4846f-116">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers.</span></span> <span data-ttu-id="4846f-117">Em seguida, para cada servidor de borda, importe-o e atribua-o conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4846f-117">Then, for each Edge Server, import it and assign it as previously described.</span></span> <span data-ttu-id="4846f-118">Repita esse procedimento para cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4846f-118">Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="4846f-119">Você pode solicitar certificados públicos diretamente de uma CA (autoridade de certificação) pública (por exemplo, do site de uma CA pública).</span><span class="sxs-lookup"><span data-stu-id="4846f-119">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA).</span></span> <span data-ttu-id="4846f-120">Os procedimentos desta seção usam o assistente de certificado para a maioria das tarefas de certificado.</span><span class="sxs-lookup"><span data-stu-id="4846f-120">The procedures in this section use the Certificate Wizard for most certificate tasks.</span></span> <span data-ttu-id="4846f-121">Se você optou por solicitar um certificado diretamente de uma CA pública, será necessário modificar cada procedimento conforme apropriado para solicitar, transportar e importar o certificado e também para importar a cadeia de certificados.</span><span class="sxs-lookup"><span data-stu-id="4846f-121">If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="4846f-122">Quando você solicita um certificado de uma autoridade de certificação externa, as credenciais fornecidas devem ter direitos de solicitar um certificado dessa CA.</span><span class="sxs-lookup"><span data-stu-id="4846f-122">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA.</span></span> <span data-ttu-id="4846f-123">Cada CA tem uma política de segurança que define quais credenciais (ou seja, nomes de usuário e grupo específicos) têm permissão para solicitar, emitir, gerenciar ou ler certificados.</span><span class="sxs-lookup"><span data-stu-id="4846f-123">Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="4846f-124">Se você decidir usar o console de gerenciamento da Microsoft (MMC) de certificados para importar a cadeia de certificados e o certificado, será necessário importá-los para o repositório de certificados do computador.</span><span class="sxs-lookup"><span data-stu-id="4846f-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="4846f-125">Se você importá-los para o repositório de certificados do usuário ou do serviço, o certificado não estará disponível para atribuição no assistente de certificado do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4846f-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="4846f-126">Para criar a solicitação de certificado para a interface externa do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="4846f-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="4846f-127">No servidor de borda, no assistente de implantação, ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.</span><span class="sxs-lookup"><span data-stu-id="4846f-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4846f-128">Se a sua organização quiser dar suporte à conectividade de mensagens instantâneas (IM) pública com a AOL, você não poderá usar o assistente de implantação do Lync Server para solicitar o certificado.</span><span class="sxs-lookup"><span data-stu-id="4846f-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="4846f-129">Em vez disso, execute as etapas na etapa "para criar uma solicitação de certificado para a interface externa do servidor de borda para dar suporte à conectividade de IM pública com a AOL", mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4846f-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="4846f-130">Se você tiver vários servidores de borda em um local em um pool, poderá executar o assistente de certificado do Lync Server 2013 em qualquer um dos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="4846f-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="4846f-131">Na página **Tarefas de Certificado Disponíveis**, clique em  **Criar uma nova solicitação de certificado**.</span><span class="sxs-lookup"><span data-stu-id="4846f-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="4846f-132">Na página **solicitação de certificado** , clique em **certificado de borda externa**.</span><span class="sxs-lookup"><span data-stu-id="4846f-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="4846f-133">Na página **solicitação atrasada ou imediata** , marque a caixa de seleção **preparar a solicitação agora, mas enviá-la mais tarde** .</span><span class="sxs-lookup"><span data-stu-id="4846f-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="4846f-134">Na página **arquivo de solicitação de certificado** , digite o caminho completo e o nome do arquivo para o qual a solicitação deve ser salva (por exemplo, c:\\CERT\_guia\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="4846f-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="4846f-135">Na página **especificar modelo de certificado alternativo** , para usar um modelo diferente do modelo padrão do webserver, marque a caixa de seleção **usar modelo de certificado alternativo para a autoridade de certificação selecionada** .</span><span class="sxs-lookup"><span data-stu-id="4846f-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="4846f-136">Na página **configurações de nome e segurança** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4846f-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="4846f-137">Em **nome amigável**, digite um nome de exibição para o certificado.</span><span class="sxs-lookup"><span data-stu-id="4846f-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="4846f-138">Em **comprimento de bit**, especifique o comprimento do bit (geralmente, o padrão de **2048**).</span><span class="sxs-lookup"><span data-stu-id="4846f-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="4846f-139">Verifique se a caixa de seleção **Marcar chave privada de certificado como exportável** está marcada.</span><span class="sxs-lookup"><span data-stu-id="4846f-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="4846f-140">Na página **informações da organização** , digite o nome da organização e da unidade organizacional (por exemplo, uma divisão ou um departamento).</span><span class="sxs-lookup"><span data-stu-id="4846f-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="4846f-141">Na página **informações geográficas** , especifique as informações de localização.</span><span class="sxs-lookup"><span data-stu-id="4846f-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="4846f-142">Na página **nome do assunto/nomes alternativos de assunto** , as informações a serem automaticamente preenchidas pelo assistente serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="4846f-142">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="4846f-143">Se forem necessários nomes alternativos de entidades adicionais, especifique-os nas próximas duas etapas.</span><span class="sxs-lookup"><span data-stu-id="4846f-143">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="4846f-144">Na **configuração de domínio SIP na página de nomes alternativos de entidades (SANs)** , marque a caixa de seleção domínio para adicionar um SIP. \<entrada\> sipdomain para a lista de nomes alternativos de assunto.</span><span class="sxs-lookup"><span data-stu-id="4846f-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="4846f-145">Na página **configurar nomes alternativos de entidades adicionais** , especifique os nomes alternativos de entidades adicionais necessários.</span><span class="sxs-lookup"><span data-stu-id="4846f-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="4846f-146">Na página **Resumo da solicitação** , examine as informações do certificado a serem usadas para gerar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="4846f-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="4846f-147">Depois que os comandos terminarem de ser executados, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4846f-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="4846f-148">Para exibir o log para a solicitação de certificado, clique em **Exibir log**.</span><span class="sxs-lookup"><span data-stu-id="4846f-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="4846f-149">Para concluir a solicitação de certificado, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4846f-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="4846f-150">Na página **arquivo de solicitação de certificado** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4846f-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="4846f-151">Para exibir o arquivo de solicitação de assinatura de certificado (CSR) gerado, clique em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="4846f-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="4846f-152">Para fechar o assistente, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="4846f-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="4846f-153">Copie o arquivo de saída para um local onde você possa enviá-lo para a CA pública.</span><span class="sxs-lookup"><span data-stu-id="4846f-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="4846f-154">Para criar uma solicitação de certificado para a interface externa do servidor de borda para dar suporte à conectividade de mensagem de chat pública com a AOL</span><span class="sxs-lookup"><span data-stu-id="4846f-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="4846f-155">Quando o modelo obrigatório estiver disponível para a autoridade de certificação, use o seguinte cmdlet do Windows PowerShell no servidor de borda para solicitar o certificado:</span><span class="sxs-lookup"><span data-stu-id="4846f-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="4846f-156">O nome de certificado padrão do modelo fornecido no Lync Server 2013 é o servidor Web.</span><span class="sxs-lookup"><span data-stu-id="4846f-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="4846f-157">Especifique somente o \<nome\> do modelo se precisar usar um modelo diferente do modelo padrão.</span><span class="sxs-lookup"><span data-stu-id="4846f-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4846f-158">Se a sua organização quiser dar suporte à conectividade de mensagem instantânea pública com a AOL, você deve usar o Windows PowerShell em vez do assistente de certificado para solicitar que o certificado seja atribuído à borda externa do serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="4846f-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="4846f-159">Isso ocorre porque o modelo de servidor Web do Lync Server 2013 que o assistente de certificado usa para solicitar um certificado não dá suporte à configuração de EKU de cliente.</span><span class="sxs-lookup"><span data-stu-id="4846f-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="4846f-160">Antes de usar o Windows PowerShell para criar o certificado, o administrador da CA deve criar e implantar um novo modelo compatível com o EKU do cliente.</span><span class="sxs-lookup"><span data-stu-id="4846f-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="4846f-161">Para enviar uma solicitação para uma autoridade de certificação pública</span><span class="sxs-lookup"><span data-stu-id="4846f-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="4846f-162">Abra o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="4846f-162">Open the output file.</span></span>

2.  <span data-ttu-id="4846f-163">Copie e cole o conteúdo da solicitação de assinatura de certificado (CSR).</span><span class="sxs-lookup"><span data-stu-id="4846f-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="4846f-164">Se solicitado, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4846f-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="4846f-165">A **Microsoft** como a plataforma do servidor.</span><span class="sxs-lookup"><span data-stu-id="4846f-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="4846f-166">**IIS** como a versão.</span><span class="sxs-lookup"><span data-stu-id="4846f-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="4846f-167">**Servidor Web** como o tipo de uso.</span><span class="sxs-lookup"><span data-stu-id="4846f-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="4846f-168">**PKCS7** como o formato de resposta.</span><span class="sxs-lookup"><span data-stu-id="4846f-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="4846f-169">Quando a autoridade de certificação pública tiver verificado suas informações, você receberá uma mensagem de email com o texto necessário para o seu certificado.</span><span class="sxs-lookup"><span data-stu-id="4846f-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="4846f-170">Copie o texto da mensagem de email e salve o conteúdo em um arquivo de texto (. txt) em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="4846f-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="4846f-171">Para importar o certificado para a interface externa do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="4846f-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="4846f-172">Faça logon como membro do grupo Administradores para o mesmo servidor de borda em que você criou a solicitação de certificado.</span><span class="sxs-lookup"><span data-stu-id="4846f-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="4846f-173">No assistente de implantação, na página **implantar servidor de borda** , ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.</span><span class="sxs-lookup"><span data-stu-id="4846f-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="4846f-174">Na página **tarefas de certificado disponíveis** , clique em **importar um certificado de um arquivo. p7b, pfx ou. cer**.</span><span class="sxs-lookup"><span data-stu-id="4846f-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="4846f-175">Na página **importar certificado** , clique em **procurar** para localizar e selecionar o certificado que você solicitou para a interface externa do servidor de borda (ou, você pode digitar o caminho completo e o nome do arquivo).</span><span class="sxs-lookup"><span data-stu-id="4846f-175">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name).</span></span> <span data-ttu-id="4846f-176">Se o certificado contiver uma chave privada, selecione **arquivo de certificado contém a chave privada do certificado** e digite a senha da chave privada.</span><span class="sxs-lookup"><span data-stu-id="4846f-176">If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key.</span></span> <span data-ttu-id="4846f-177">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="4846f-177">Click **Next**.</span></span>

5.  <span data-ttu-id="4846f-178">Na página **importar Resumo do certificado** , examine o resumo e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4846f-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="4846f-179">Na **execução de comandos**, examine os resultados da importação, clique em **Exibir log** para obter mais informações conforme necessário e clique em **concluir** para concluir a importação de certificado.</span><span class="sxs-lookup"><span data-stu-id="4846f-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="4846f-180">Se você estiver configurando um pool do servidor de borda, exporte o certificado com sua chave privada, conforme descrito no procedimento "para exportar o certificado com a chave privada para servidores de borda em um pool" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4846f-180">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic.</span></span> <span data-ttu-id="4846f-181">Copie o arquivo de certificado exportado para os outros servidores de borda e importe-o para a loja do computador em cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4846f-181">Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="4846f-182">Para exportar o certificado com a chave privada para servidores de borda em um pool</span><span class="sxs-lookup"><span data-stu-id="4846f-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="4846f-183">Faça logon como membro do grupo Administradores para o mesmo servidor de borda no qual você importou o certificado.</span><span class="sxs-lookup"><span data-stu-id="4846f-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="4846f-184">Clique em **Iniciar**, clique em **executar**e digite **MMC**.</span><span class="sxs-lookup"><span data-stu-id="4846f-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="4846f-185">No console do console de gerenciamento Microsoft (MMC), clique em **arquivo**e, em seguida, clique em **Adicionar/remover snap-in**.</span><span class="sxs-lookup"><span data-stu-id="4846f-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="4846f-186">Em **Adicionar ou remover snap-ins**, clique em **certificados**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4846f-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="4846f-187">Na caixa de diálogo **certificados** , selecione **conta de computador**, clique em **Avançar**, selecione **computador local: (o computador em que este console está sendo executado)** em **Selecionar computador**, clique em **concluir** e, em seguida, clique em **OK** para concluir a configuração do console do MMC.</span><span class="sxs-lookup"><span data-stu-id="4846f-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="4846f-188">Clique duas vezes em **certificados (computador local)** para expandir os repositórios de certificados, clique duas vezes em **pessoal**e, em seguida, clique duas vezes em **certificados**.</span><span class="sxs-lookup"><span data-stu-id="4846f-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4846f-189">Se não houver certificados no armazenamento pessoal de certificados do computador local, não há uma chave privada associada ao certificado que foi importado.</span><span class="sxs-lookup"><span data-stu-id="4846f-189">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="4846f-190">Examine as etapas de solicitação e importação.</span><span class="sxs-lookup"><span data-stu-id="4846f-190">Review the request and import steps.</span></span> <span data-ttu-id="4846f-191">Se o problema persistir, entre em contato com o administrador ou o provedor da autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="4846f-191">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="4846f-192">No **repositório pessoal de certificados do computador local**, clique com o botão direito do mouse no certificado que você está exportando, clique em **todas as tarefas**e, em seguida, clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="4846f-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="4846f-193">No Assistente para exportação de certificados, clique em **Avançar**, selecione **Sim, exportar a chave particular**e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4846f-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4846f-194">Se a seleção <STRONG>Sim, exportar a chave privada</STRONG> não estiver disponível, a chave privada associada a esse certificado não foi marcada para exportação.</span><span class="sxs-lookup"><span data-stu-id="4846f-194">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="4846f-195">Você precisará solicitar o certificado novamente, certificando-se de que o certificado esteja marcado para permitir a exportação da chave privada antes de continuar com a exportação.</span><span class="sxs-lookup"><span data-stu-id="4846f-195">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="4846f-196">Entre em contato com o administrador ou provedor da autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="4846f-196">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="4846f-197">Na caixa de diálogo Exportar formatos de arquivo, selecione **troca de informações\#pessoais – PKCS 12 (. PFX)** e, em seguida, selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4846f-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="4846f-198">Incluir todos os certificados no caminho de certificação, se possível</span><span class="sxs-lookup"><span data-stu-id="4846f-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="4846f-199">Exportar todas as propriedades estendidas</span><span class="sxs-lookup"><span data-stu-id="4846f-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="4846f-200">Ao exportar o certificado de um servidor de borda, não selecione <STRONG>excluir a chave privada se a exportação for bem-sucedida</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4846f-200">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="4846f-201">Selecionar essa opção exigirá que você importe o certificado e a chave privada para esse servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4846f-201">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="4846f-202">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="4846f-202">Click **Next**.</span></span>

11. <span data-ttu-id="4846f-203">Digite uma senha para a chave privada, digite a senha novamente para confirmá-la e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4846f-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="4846f-204">Digite um caminho e o nome de arquivo para o certificado exportado, usando uma extensão de arquivo .pfx.</span><span class="sxs-lookup"><span data-stu-id="4846f-204">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="4846f-205">O caminho deve ser acessível a todos os outros servidores de borda do pool ou disponível para transporte por meio de mídia removível-por exemplo, uma unidade flash USB.</span><span class="sxs-lookup"><span data-stu-id="4846f-205">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="4846f-206">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="4846f-206">Click **Next**.</span></span>

13. <span data-ttu-id="4846f-207">Examine o resumo em **concluindo o assistente para exportação de certificados**e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="4846f-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="4846f-208">Na caixa de diálogo exportação bem-sucedida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4846f-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="4846f-209">Importe o arquivo de certificado exportado para os outros servidores de borda seguindo as etapas descritas no procedimento "para importar o certificado para a interface externa do servidor de borda" anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4846f-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="4846f-210">Para atribuir o certificado para a interface externa do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="4846f-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="4846f-211">Em cada servidor de borda, no assistente de implantação, ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique **novamente em executar**.</span><span class="sxs-lookup"><span data-stu-id="4846f-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="4846f-212">Na página **tarefas de certificado disponíveis** , clique em **atribuir um certificado existente**.</span><span class="sxs-lookup"><span data-stu-id="4846f-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="4846f-213">Na página **atribuição de certificado** , clique em **certificado de borda externa** e marque a caixa de seleção **usos avançados de certificado** .</span><span class="sxs-lookup"><span data-stu-id="4846f-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="4846f-214">Na página **usos avançados de certificado** , marque todas as caixas de seleção para atribuir o certificado para todos os usos.</span><span class="sxs-lookup"><span data-stu-id="4846f-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="4846f-215">Na página **repositório de certificados** , selecione o certificado público que você solicitou e importou para a interface externa do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4846f-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4846f-216">Se o certificado que você solicitou e importado não estiver na lista, um dos métodos de solução de problemas será verificar se o nome da entidade e os nomes alternativos da entidade do certificado atendem a todos os requisitos do certificado e, se você importou manualmente o certificado e cadeia de certificados em vez de usar os procedimentos anteriores, que o certificado está no repositório de certificados correto (o repositório de certificados do computador, não o usuário ou o repositório de certificados do serviço).</span><span class="sxs-lookup"><span data-stu-id="4846f-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="4846f-217">Na página **Resumo de atribuição de certificado** , examine suas configurações e clique em **Avançar** para atribuir os certificados.</span><span class="sxs-lookup"><span data-stu-id="4846f-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="4846f-218">Na página de conclusão do assistente, clique em  **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="4846f-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="4846f-219">Depois de usar esse procedimento para atribuir o certificado de borda, abra o snap-in de certificado em cada servidor, expanda **certificados (computador local)**, expanda **pessoal**, clique em **certificados**e verifique no painel de detalhes se o certificado está listado.</span><span class="sxs-lookup"><span data-stu-id="4846f-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="4846f-220">Se a sua implantação incluir vários servidores de borda, repita esse procedimento para cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4846f-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

