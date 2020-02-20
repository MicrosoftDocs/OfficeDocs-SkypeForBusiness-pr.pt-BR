---
title: 'Lync Server 2013: configurar certificados para a interface de borda externa'
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
ms.openlocfilehash: 0aadbc9603fb62a2dacf78129aef3bf448da2f05
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="16bff-102">Configurar certificados para a interface de borda externa para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16bff-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16bff-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="16bff-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="16bff-104">Ao executar o Assistente de certificado, certifique-se de que esteja conectado usando uma conta membro de um grupo com as permissões apropriadas para o tipo de modelo de certificado que será usado.</span><span class="sxs-lookup"><span data-stu-id="16bff-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="16bff-105">Por padrão, uma solicitação de certificado do Lync Server usará o modelo de certificado do servidor Web.</span><span class="sxs-lookup"><span data-stu-id="16bff-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="16bff-106">Se você usar uma conta membro do grupo RTCUniversalServerAdmins para solicitar um certificado usando este modelo, verifique se o grupo foi atribuído com permissões de Inscrição necessárias para usar este modelo.</span><span class="sxs-lookup"><span data-stu-id="16bff-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="16bff-107">Cada Servidor de Borda requer um certificado público na interface entre a rede de perímetro e a Internet, e o nome alternativo da entidade do certificado deve conter nomes externos do serviço de Borda de Acesso e FQDNs (nomes de domínio totalmente qualificado) do serviço de Borda de Webconferência.</span><span class="sxs-lookup"><span data-stu-id="16bff-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="16bff-108">Para obter detalhes sobre esse e outros requisitos de certificado, consulte [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="16bff-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="16bff-109">Para obter uma lista de CAs (autoridades de certificação) públicas que fornecem certificados compatíveis com requisitos específicos para certificados de comunicações unificadas e que têm a parceria com a Microsoft para garantir que eles funcionem com o assistente de certificado do Lync Server 2013, consulte o artigo 929395 da base de dados de conhecimento da Microsoft, [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)"em.</span><span class="sxs-lookup"><span data-stu-id="16bff-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="16bff-110">Configurando certificados nas interfaces externas</span><span class="sxs-lookup"><span data-stu-id="16bff-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="16bff-111">Para configurar um certificado na interface de borda externa em um site, use os procedimentos desta seção para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="16bff-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="16bff-112">Crie a solicitação de certificado para a interface externa do Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="16bff-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="16bff-113">Envie a solicitação à autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="16bff-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="16bff-114">Importe o certificado da interface externa de cada Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="16bff-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="16bff-115">Atribua o certificado à interface externa de cada Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="16bff-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="16bff-p102">Se sua implantação incluir vários Servidores de Borda, exporte o certificado junto com sua chave privada e o copie para os Servidores de Borda. Em seguida, para cada Servidor de Borda, importe-o e atribua-o conforme descrito anteriormente. Repita este procedimento para cada Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="16bff-p102">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers. Then, for each Edge Server, import it and assign it as previously described. Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="16bff-p103">Você pode solicitar os certificados públicos diretamente de uma autoridade de certificação pública (como a partir do site de uma autoridade de certificação pública). Os procedimentos nesta seção usam o Assistente de Certificados na maioria das tarefas do certificado. Se você optar por solicitar um certificado diretamente a partir de uma autoridade de certificação pública, precisará modificar cada procedimento conforme apropriado para solicitar, transportar e importar o certificado e também para importar a cadeia de certificados.</span><span class="sxs-lookup"><span data-stu-id="16bff-p103">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA). The procedures in this section use the Certificate Wizard for most certificate tasks. If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="16bff-p104">Quando você solicita um certificado junto a uma autoridade de certificação externa, as credenciais fornecidas devem ter direitos para solicitar um certificado nessa autoridade de certificação. Cada autoridade de certificação tem uma política de segurança que define quais credenciais (ou seja, nomes de usuário e grupo específicos) têm permissão para solicitar, emitir, gerenciar ou ler certificados.</span><span class="sxs-lookup"><span data-stu-id="16bff-p104">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA. Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="16bff-124">Se você decidir usar MMC (Console de Gerenciamento Microsoft) de Certificados para importar a cadeia de certificados e o certificado, deverá importá-los para o repositório de certificados do computador.</span><span class="sxs-lookup"><span data-stu-id="16bff-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="16bff-125">Se você importá-los para o repositório de certificados do usuário ou serviço, o certificado não estará disponível para atribuição no assistente de certificado do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="16bff-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="16bff-126">Para criar a solicitação de certificado para a interface externa do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="16bff-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="16bff-127">No Servidor de Borda, no Assistente de Implantação, próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="16bff-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16bff-128">Se sua organização desejar oferecer suporte à conectividade pública de mensagens instantâneas com o AOL, você não pode usar o Assistente de Implantação do Lync Server para solicitar o certificado.</span><span class="sxs-lookup"><span data-stu-id="16bff-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="16bff-129">Em vez disso, execute as etapas no procedimento "Para criar uma solicitação de certificado para a interface externa do Servidor de Borda para oferecer suporte à conectividade pública de IM com o AOL" posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="16bff-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="16bff-130">Se houver vários servidores de borda em um único local em um pool, você poderá executar o assistente de certificado do Lync Server 2013 em qualquer um dos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="16bff-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="16bff-131">Na página **Tarefas de Certificado Disponíveis**, clique em **Criar uma nova solicitação de certificado**.</span><span class="sxs-lookup"><span data-stu-id="16bff-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="16bff-132">Na página **Solicitação de Certificado**, clique em **Certificado de Borda Externa**.</span><span class="sxs-lookup"><span data-stu-id="16bff-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="16bff-133">Na página **Solicitação Atrasada ou Imediata**, marque a caixa de seleção **Preparar a solicitação agora, mas enviá-la depois**.</span><span class="sxs-lookup"><span data-stu-id="16bff-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="16bff-134">Na página **arquivo de solicitação de certificado** , digite o caminho completo e o nome do arquivo para o qual a solicitação será salva (por exemplo, c:\\CERT\_externos\_Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="16bff-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="16bff-135">Na página **Especificar Modelo de Certificado Alternativo**, para usar um modelo diferente do modelo WebServer padrão, marque a caixa de seleção **Usar o modelo de certificado alternativo para a autoridade de certificação selecionada**.</span><span class="sxs-lookup"><span data-stu-id="16bff-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="16bff-136">Na página **Nome e Configurações de Segurança**, siga estes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="16bff-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="16bff-137">Em **Nome amigável**, digite um nome para exibição do certificado.</span><span class="sxs-lookup"><span data-stu-id="16bff-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="16bff-138">Em **Comprimento de bit**, especifique o comprimento de bit (geralmente, o padrão de **2048**).</span><span class="sxs-lookup"><span data-stu-id="16bff-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="16bff-139">Verifique se a caixa de seleção **Marcar chave privada de certificado como exportável**  está marcada.</span><span class="sxs-lookup"><span data-stu-id="16bff-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="16bff-140">Na página **Informações da Organização**, digite o nome da organização e a unidade organizacional (por exemplo, uma divisão ou departamento).</span><span class="sxs-lookup"><span data-stu-id="16bff-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="16bff-141">Na página **Informações Geográficas**, especifique as informações de localização.</span><span class="sxs-lookup"><span data-stu-id="16bff-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="16bff-p107">Na página **Nome da Entidade/Nomes Alternativos da Entidade**, as informações a serem preenchidas automaticamente pelo assistente são exibidas. Se nomes alternativos de entidade adicionais forem necessários, especifique-os nas próximas duas etapas.</span><span class="sxs-lookup"><span data-stu-id="16bff-p107">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="16bff-144">Na página **configuração do domínio SIP em nomes alternativos da entidade (SANs)** , marque a caixa de seleção domínio para adicionar um SIP. \<entrada\> sipdomain para a lista de nomes alternativos de entidade.</span><span class="sxs-lookup"><span data-stu-id="16bff-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="16bff-145">Na página **Configurar Nomes Alternativos da Entidade Adicionais**, especifique qualquer nome alternativo adicional da entidade necessário.</span><span class="sxs-lookup"><span data-stu-id="16bff-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="16bff-146">Na página **Resumo da Solicitação**, examine as informações do certificado a ser usado para gerar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="16bff-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="16bff-147">Após o término da execução de comandos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="16bff-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="16bff-148">Para exibir o log para a solicitação de certificado, clique em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="16bff-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="16bff-149">Para concluir a solicitação de certificado, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="16bff-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="16bff-150">Na página **Arquivo de Solicitação de Certificado**, execute os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="16bff-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="16bff-151">Para exibir um arquivo CSR (solicitação de assinatura de certificado) gerado, clique em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="16bff-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="16bff-152">Para fechar o assistente, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="16bff-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="16bff-153">Copie o arquivo de saída para um local de onde você possa enviá-lo à autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="16bff-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="16bff-154">Para criar uma solicitação de certificado para a interface externa do Servidor de Borda para oferecer suporte à conectividade pública de IM com o AOL</span><span class="sxs-lookup"><span data-stu-id="16bff-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="16bff-155">Quando o modelo necessário estiver disponível para a autoridade de certificação, use o seguinte cmdlet do Windows PowerShell no servidor de borda para solicitar o certificado:</span><span class="sxs-lookup"><span data-stu-id="16bff-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="16bff-156">O nome de certificado padrão do modelo fornecido no Lync Server 2013 é o servidor Web.</span><span class="sxs-lookup"><span data-stu-id="16bff-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="16bff-157">Só especifique o \<nome\> do modelo se você precisar usar um modelo diferente do modelo padrão.</span><span class="sxs-lookup"><span data-stu-id="16bff-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16bff-158">Se sua organização quiser suportar a conectividade pública de IM com o AOL, você deve usar o Windows PowerShell em vez do assistente de certificado para solicitar que o certificado seja atribuído à borda externa do serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="16bff-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="16bff-159">Isso ocorre porque o modelo de servidor Web do Lync Server 2013 que o assistente de certificado usa para solicitar um certificado não dá suporte à configuração de EKU do cliente.</span><span class="sxs-lookup"><span data-stu-id="16bff-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="16bff-160">Antes de usar o Windows PowerShell para criar o certificado, o administrador da autoridade de certificação deve criar e implantar um novo modelo que dê suporte ao EKU do cliente.</span><span class="sxs-lookup"><span data-stu-id="16bff-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="16bff-161">Para enviar uma solicitação a uma autoridade de certificação pública</span><span class="sxs-lookup"><span data-stu-id="16bff-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="16bff-162">Abra o arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="16bff-162">Open the output file.</span></span>

2.  <span data-ttu-id="16bff-163">Copie e cole o conteúdo da CSR (Solicitação de Assinatura de Certificado).</span><span class="sxs-lookup"><span data-stu-id="16bff-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="16bff-164">Se solicitado, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="16bff-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="16bff-165">**Microsoft** como plataforma de servidor.</span><span class="sxs-lookup"><span data-stu-id="16bff-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="16bff-166">**IIS** como versão.</span><span class="sxs-lookup"><span data-stu-id="16bff-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="16bff-167">**Servidor Web** como o tipo de uso.</span><span class="sxs-lookup"><span data-stu-id="16bff-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="16bff-168">**PKCS7** como o formato de resposta.</span><span class="sxs-lookup"><span data-stu-id="16bff-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="16bff-169">Quando a autoridade de certificação pública tiver confirmado suas informações, você receberá uma mensagem de email contendo o texto necessário para o seu certificado.</span><span class="sxs-lookup"><span data-stu-id="16bff-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="16bff-170">Copie o texto da mensagem de email e salve o conteúdo em um arquivo de texto (.txt) no computador local.</span><span class="sxs-lookup"><span data-stu-id="16bff-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="16bff-171">Para importar o certificado da interface externa do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="16bff-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="16bff-172">Faça logon como membro do grupo de Administradores no mesmo Servidor de Borda no qual você criou a solicitação de certificado.</span><span class="sxs-lookup"><span data-stu-id="16bff-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="16bff-173">No Assistente de Implantação, na página **Implantar Servidor de Borda**, ao lado de **Etapa 3: solicitar, instalar ou atribuir certificados**, clique em **Executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="16bff-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="16bff-174">Na página **Tarefas de Certificado Disponíveis**, clique em **Importar um certificado de um arquivo. p7b, .pfx ou .cer**.</span><span class="sxs-lookup"><span data-stu-id="16bff-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="16bff-p110">Na página **Importar Certificado**, clique em **Procurar** para localizar e selecionar o certificado que você solicitou para a interface externa do Servidor de Borda (ou pode digitar o caminho completo e o nome do arquivo). Se o certificado tiver uma chave privada, selecione **Arquivo de certificado contém a chave privada do certificado**  e digite a senha da chave privada. Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="16bff-p110">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name). If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key. Click **Next**.</span></span>

5.  <span data-ttu-id="16bff-178">Na página **Importar Resumo de Certificado**, revise o resumo e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="16bff-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="16bff-179">Em **Executando Comandos**, revise os resultados da importação, clique em **Exibir Log** para obter mais informações conforme necessário e clique em **Concluir** para concluir a importação do certificado.</span><span class="sxs-lookup"><span data-stu-id="16bff-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="16bff-p111">Se você estiver configurando um pool de Servidores de Borda, exporte o certificado com sua chave privada, conforme descrito no procedimento "Para exportar o certificado com a chave particular para Servidores de Borda em um pool" neste tópico. Copie o arquivo de certificado exportado para os outros Servidores de Borda e importe-o para o repositório do computador em cada Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="16bff-p111">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic. Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="16bff-182">Para exportar o certificado com chave privada para os Servidores de Borda em um pool</span><span class="sxs-lookup"><span data-stu-id="16bff-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="16bff-183">Faça logon como membro do grupo de Administradores para o mesmo Servidor de Borda no qual você importou o certificado.</span><span class="sxs-lookup"><span data-stu-id="16bff-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="16bff-184">Clique em **Iniciar**, em **Executar** e digite **MMC**.</span><span class="sxs-lookup"><span data-stu-id="16bff-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="16bff-185">No console MMC (Console de Gerenciamento Microsoft), clique em **Arquivo** e em **Adicionar/Remover Snap-in**.</span><span class="sxs-lookup"><span data-stu-id="16bff-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="16bff-186">Em **Adicionar ou Remover Snap-ins**, clique em **Certificados** e em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="16bff-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="16bff-187">Na caixa de diálogo **Certificados**, selecione **Conta do computador**, clique em **Avançar**, selecione **Computador local: (o computador em que este console está sendo executado)** em **Selecionar Computador**, clique em **Concluir** e em **OK** para concluir a configuração do console MMC.</span><span class="sxs-lookup"><span data-stu-id="16bff-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="16bff-188">Clique duas vezes em **Certificados (Computador Local)** para expandir os repositórios de certificados, clique duas vezes em **Pessoais** e em **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="16bff-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="16bff-p112">Se não há certificados no repositório de Certificados Pessoais do computador local, não há uma chave privada associada como o certificado importado. Revise as etapas de solicitação e importação. Se o problema persistir, entre em contato com seu administrador da autoridade de certificação ou provedor</span><span class="sxs-lookup"><span data-stu-id="16bff-p112">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="16bff-192">No **Repositório de Certificados Pessoais do computador local**, clique com o botão direito do mouse no certificado que você está exportando, clique em **Todas as Tarefas** e em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="16bff-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="16bff-193">No Assistente para Exportação de Certificados, clique em **Avançar**, selecione **Sim, exportar a chave privada** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="16bff-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16bff-p113">Se a opção <STRONG>Sim, exportar a chave privada</STRONG> não estiver disponível, a chave privada associada a este certificado não foi marcada para exportação. Você precisará solicitar o certificado novamente, garantindo que o certificado esteja marcado para permitir a exportação de chave privada antes de poder continuar com a exportação. Contate seu administrador da autoridade de certificação ou provedor.</span><span class="sxs-lookup"><span data-stu-id="16bff-p113">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="16bff-197">Na caixa de diálogo Exportar formatos de arquivo, selecione **troca de informações\#pessoais – PKCS 12 (. PFX)** e selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="16bff-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="16bff-198">Incluir todos os certificados no caminho de certificação, se possível</span><span class="sxs-lookup"><span data-stu-id="16bff-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="16bff-199">Exportar todas as propriedades estendidas</span><span class="sxs-lookup"><span data-stu-id="16bff-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="16bff-p114">Quando exportar o certificado de um servidor de Borda, não selecione <STRONG>Excluir a chave privada se a exportação tiver êxito</STRONG>. Selecionar esta opção exigirá que você importe o certificado e a chave privada para este servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="16bff-p114">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="16bff-202">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="16bff-202">Click **Next**.</span></span>

11. <span data-ttu-id="16bff-203">Digite uma senha para a chave privada, digite a senha novamente para confirmar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="16bff-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="16bff-p115">Digite um caminho e o nome do arquivo para o certificado exportado, usando uma extensão de arquivo .pfx. O caminho deve ser acessível para todos os outros servidores de Borda no pool ou disponível para transportar através de mídia removível - por exemplo, uma unidade flash USB. clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="16bff-p115">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

13. <span data-ttu-id="16bff-207">Revise o resumo em **Concluindo o Assistente para Exportação de Certificados** e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="16bff-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="16bff-208">Na caixa de diálogo de exportação bem-sucedida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="16bff-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="16bff-209">Importe o arquivo de certificado exportado para outros servidores de Borda seguindo as etapas descritas no procedimento "Para importar o certificado para a interface externa do Servidor de Borda" neste tópico.</span><span class="sxs-lookup"><span data-stu-id="16bff-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="16bff-210">Para atribuir o certificado à interface externa do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="16bff-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="16bff-211">Em cada Servidor de Borda, no Assistente de Implantação, próximo a **Etapa 3: Solicitar, instalar ou atribuir certificados**, clique em **Executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="16bff-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="16bff-212">Na página **Tarefas de Certificado Disponíveis**, clique em **Atribuir um certificado existente**.</span><span class="sxs-lookup"><span data-stu-id="16bff-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="16bff-213">Na página **Atribuição de Certificado**, clique em **Certificado de Borda Externa** e marque a caixa de seleção **Usos Avançados de Certificado**.</span><span class="sxs-lookup"><span data-stu-id="16bff-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="16bff-214">Na página **Usos Avançados de Certificado**, marque todas as caixas de seleção para atribuir o certificado a todos os usos.</span><span class="sxs-lookup"><span data-stu-id="16bff-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="16bff-215">Na página **Repositório de Certificados**, selecione o certificado público que você solicitou e importou para a interface externa do Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="16bff-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="16bff-216">Se o certificado solicitado e importado não estiver na lista, um dos métodos de solução de problemas é verificar se o nome da entidade e os nomes alternativos da entidade do certificado atendem a todos os requisitos do certificado. Se você importou manualmente o certificado e a cadeia de certificados em vez de usar os procedimentos anteriores, verifique se o certificado está no repositório de certificados correto (o repositório de certificados do computador, não o repositório de certificados do usuário ou serviço).</span><span class="sxs-lookup"><span data-stu-id="16bff-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="16bff-217">Na página **Resumo da Atribuição de Certificado**, revise suas configurações e clique em **Avançar** para atribuir certificados.</span><span class="sxs-lookup"><span data-stu-id="16bff-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="16bff-218">Na página de conclusão do assistente, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="16bff-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="16bff-219">Depois de usar este procedimento para atribuir o certificado de borda, abra o snap-in de Certificados em cada servidor, expanda **Certificados (Computador Local)**, expanda **Pessoais**, clique em **Certificados** e verifique se o certificado está listado no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="16bff-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="16bff-220">Se sua implantação inclui vários Servidores de Borda, repita este procedimento para cada Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="16bff-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

