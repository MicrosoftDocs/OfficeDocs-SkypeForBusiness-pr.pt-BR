---
title: Solicitar e configurar um certificado para seu proxy HTTP reverso
description: Solicitar e configurar um certificado para seu proxy HTTP reverso.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdeaa080e3ccb6a9895e18a6ac02084e99a1e33e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579037"
---
# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a><span data-ttu-id="74257-103">Solicitar e configurar um certificado para seu proxy HTTP reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74257-103">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74257-104">_**Última modificação do tópico:** 2014-02-14_</span><span class="sxs-lookup"><span data-stu-id="74257-104">_**Topic Last Modified:** 2014-02-14_</span></span>

<span data-ttu-id="74257-105">Você precisa instalar o certificado de autoridade de certificação (CA) raiz no servidor que executa o Microsoft Forefront Threat Management Gateway 2010 ou IIS ARR para a infraestrutura de CA que emitiu os certificados do servidor para os servidores internos que executam o Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74257-105">You need to install the root certification authority (CA) certificate on the server running Microsoft Forefront Threat Management Gateway 2010 or IIS ARR for the CA infrastructure that issued the server certificates to the internal servers running Microsoft Lync Server 2013.</span></span>

<span data-ttu-id="74257-p101">Você também deve instalar um certificado de servidor web público no seu servidor proxy reverso. Os nomes alternativos de entidade desse certificado devem conter os FQDNs (nomes de domínio totalmente qualificados) externos publicados de cada pool que é o início para usuários habilitados para acesso remoto, e os FQDNs externos de todos os Diretores ou pools de Diretores que serão usados dentro dessa infraestrutura de Borda. O nome alternativo da entidade também deve conter a URL simples de reunião, a URL simples de discagem e, se você estiver implantando aplicativos móveis e planejar usar descoberta automática, a URL do Serviço Descoberta Automática externo, como mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="74257-p101">You also must install a public web server certificate on your reverse proxy server. This certificate’s subject alternative names should contain the published external fully qualified domain names (FQDNs) of each pool that is home to users enabled for remote access, and the external FQDNs of all Directors or Director pools that will be used within that Edge infrastructure. The subject alternative name must also contain the meeting simple URL, the dial-in simple URL, and, if you are deploying mobile applications and plan to use automatic discovery, the external Autodiscover Service URL as shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="74257-109">Valor</span><span class="sxs-lookup"><span data-stu-id="74257-109">Value</span></span></th>
<th><span data-ttu-id="74257-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="74257-110">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74257-111">Nome da entidade</span><span class="sxs-lookup"><span data-stu-id="74257-111">Subject name</span></span></p></td>
<td><p><span data-ttu-id="74257-112">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="74257-112">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="74257-113">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74257-113">webext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74257-114">Nome alternativo da entidade</span><span class="sxs-lookup"><span data-stu-id="74257-114">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="74257-115">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="74257-115">Pool FQDN</span></span></p></td>
<td><p><span data-ttu-id="74257-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74257-116">webext.contoso.com</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="74257-117">O nome da entidade também deve estar presente no nome alternativo da entidade.</span><span class="sxs-lookup"><span data-stu-id="74257-117">The subject name must also be present in the subject alternative name.</span></span>

</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74257-118">Nome alternativo da entidade</span><span class="sxs-lookup"><span data-stu-id="74257-118">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="74257-119">Serviços Web de diretor opcional (se o diretor estiver implantado)</span><span class="sxs-lookup"><span data-stu-id="74257-119">Optional Director Web Services (if Director is deployed)</span></span></p></td>
<td><p><span data-ttu-id="74257-120">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74257-120">webdirext.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74257-121">Nome alternativo da entidade</span><span class="sxs-lookup"><span data-stu-id="74257-121">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="74257-122">URL simples de reunião</span><span class="sxs-lookup"><span data-stu-id="74257-122">Meeting simple URL</span></span></p>



> [!NOTE]
> <span data-ttu-id="74257-p102">Todas as URLs simples de reunião devem estar no nome alternativo da região. Cada domínio SIP deve ter pelo menos uma URL simples de reunião ativa.</span><span class="sxs-lookup"><span data-stu-id="74257-p102">All meeting simple URLs must be in the subject alternative name. Each SIP domain must have at least one active meeting simple URL.</span></span>

</td>
<td><p><span data-ttu-id="74257-125">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74257-125">meet.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74257-126">Nome alternativo da entidade</span><span class="sxs-lookup"><span data-stu-id="74257-126">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="74257-127">URL simples de discagem</span><span class="sxs-lookup"><span data-stu-id="74257-127">Dial-in simple URL</span></span></p></td>
<td><p><span data-ttu-id="74257-128">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74257-128">dialin.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74257-129">Nome alternativo da entidade</span><span class="sxs-lookup"><span data-stu-id="74257-129">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="74257-130">Servidor do Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="74257-130">Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="74257-131">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74257-131">officewebapps01.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74257-132">Nome alternativo da entidade</span><span class="sxs-lookup"><span data-stu-id="74257-132">Subject alternative name</span></span></p></td>
<td><p><span data-ttu-id="74257-133">URL de Serviço Descoberta Automática Externo</span><span class="sxs-lookup"><span data-stu-id="74257-133">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="74257-134">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="74257-134">lyncdiscover.contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="74257-135">Se você estiver usando o Microsoft Exchange Server, você também precisará configurar regras de proxy reverso para as URLs de descoberta automática e serviços Web do Exchange.</span><span class="sxs-lookup"><span data-stu-id="74257-135">If you are also using Microsoft Exchange Server you will also need to configure reverse proxy rules for the Exchange autodiscover and web services URLs.</span></span>

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="74257-136">Se sua implantação interna consiste em mais de um servidor Standard Edition ou pool de Front-End, você deve configurar regras de publicação na Web para cada FQDN de web farm externo e será necessário um ouvinte da web e certificado para cada um, ou você deve obter um certificado cujo nome alternativo da entidade contém os nomes usados por todos os pools, atribuí-lo a um ouvinte da web e compartilhá-lo entre várias regras de publicação na web.</span><span class="sxs-lookup"><span data-stu-id="74257-136">If your internal deployment consists of more than one Standard Edition server or Front End pool, you must configure web publishing rules for each external web farm FQDN and you will either need a certificate and web listener for each, or you must obtain a certificate whose subject alternative name contains the names used by all of the pools, assign it to a web listener, and share it among multiple web publishing rules.</span></span>



</div>

<div>

## <a name="create-a-certificate-request"></a><span data-ttu-id="74257-137">Criar uma solicitação de certificado</span><span class="sxs-lookup"><span data-stu-id="74257-137">Create a Certificate Request</span></span>

<span data-ttu-id="74257-138">Você cria uma solicitação de certificado no proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="74257-138">You create a certificate request on the reverse proxy.</span></span> <span data-ttu-id="74257-139">Você cria uma solicitação em outro computador, mas deve exportar o certificado assinado com a chave privada e importá-lo para o proxy reverso depois de ter recebido a autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="74257-139">You create a request on another computer, but you must export the signed certificate with the private key and import it onto the reverse proxy once you have received it from the public certification authority.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="74257-140">Uma solicitação de certificado ou uma solicitação de assinatura de certificado (CSR) é uma solicitação para uma autoridade de certificação pública (AC) confiável para validar e assinar a chave pública do computador solicitante.</span><span class="sxs-lookup"><span data-stu-id="74257-140">A certificate request or a certificate signing request (CSR) is a request to a trusted public certification authority (CA) to validate and sign the requesting computer’s public key.</span></span> <span data-ttu-id="74257-141">Quando um certificado é gerado, uma chave pública e uma chave privada são criadas.</span><span class="sxs-lookup"><span data-stu-id="74257-141">When a certificate is generated, a public key and a private key are created.</span></span> <span data-ttu-id="74257-142">Somente a chave pública é compartilhada e assinada.</span><span class="sxs-lookup"><span data-stu-id="74257-142">Only the public key is shared and signed.</span></span> <span data-ttu-id="74257-143">Como o nome indica, a chave pública é disponibilizada para qualquer solicitação Pública.</span><span class="sxs-lookup"><span data-stu-id="74257-143">As the name implies, the public key is made available to any public request.</span></span> <span data-ttu-id="74257-144">A chave pública é usada por clientes, servidores e outros solicitantes que precisam trocar informações com segurança e validar a identidade de um computador.</span><span class="sxs-lookup"><span data-stu-id="74257-144">The public key is for use by clients, servers and other requesters that need to exchange information securely and validate a computer’s identity.</span></span> <span data-ttu-id="74257-145">A chave privada é mantida protegida e é usada apenas pelo computador que criou o par de chaves para descriptografar mensagens criptografadas com sua chave pública.</span><span class="sxs-lookup"><span data-stu-id="74257-145">The private key is kept secured and is used only by the computer that created the key pair to decrypt messages encrypted with its public key.</span></span> <span data-ttu-id="74257-146">A chave privada pode ser usada para outros fins.</span><span class="sxs-lookup"><span data-stu-id="74257-146">The private key can be used for other purposes.</span></span> <span data-ttu-id="74257-147">Para fins de proxy reverso, a criptografia de dados é o uso principal.</span><span class="sxs-lookup"><span data-stu-id="74257-147">For reverse proxy purposes, data encipherment is the primary use.</span></span> <span data-ttu-id="74257-148">Secondarily, a autenticação de certificado no nível de chave do certificado é outra, e é limitada somente à validação de que um solicitante tem a chave pública do computador ou que o computador para o qual você tem uma chave pública é realmente o computador que ele alega ser.</span><span class="sxs-lookup"><span data-stu-id="74257-148">Secondarily, the certificate authentication at the certificate key level is another use, and is limited only to validation that a requester has the computer’s public key, or that the computer that you have a public key for is actually the computer that it claims to be.</span></span>



</div>

<div>


> [!TIP]
> <span data-ttu-id="74257-149">Se você planejar os certificados do servidor de borda e os certificados de proxy reverso ao mesmo tempo, observe que há uma grande semelhança entre os dois requisitos de certificado.</span><span class="sxs-lookup"><span data-stu-id="74257-149">If you plan your Edge Server certificates and your reverse proxy certificates at the same time, you should notice that there is a great deal of similarity between the two certificate requirements.</span></span> <span data-ttu-id="74257-150">Ao configurar e solicitar seu certificado de servidor de borda, combine o servidor de borda e os nomes alternativos de entidade de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="74257-150">When you configure and request your Edge Server certificate, combine the Edge Server and the reverse proxy subject alternative names.</span></span> <span data-ttu-id="74257-151">Você pode usar o mesmo certificado para seu proxy reverso se exportar o certificado e a chave privada e copiar o arquivo exportado para o proxy reverso e, em seguida, importar o par de certificados/chaves e atribuí-lo conforme necessário nos próximos procedimentos.</span><span class="sxs-lookup"><span data-stu-id="74257-151">You can use the same certificate for your reverse proxy if you export the certificate and the private key and copy the exported file to the reverse proxy and then import the certificate/key pair and assign it as needed in the upcoming procedures.</span></span> <span data-ttu-id="74257-152">Consulte os requisitos de certificado para o plano do servidor &nbsp; <A href="lync-server-2013-plan-for-edge-server-certificates.md">de borda para certificados de servidor de borda no lync Server 2013</A> e o resumo de certificado de proxy reverso <A href="lync-server-2013-certificate-summary-reverse-proxy.md">-proxy reverso no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="74257-152">Refer to the certificate requirements for the Edge Server&nbsp;<A href="lync-server-2013-plan-for-edge-server-certificates.md">Plan for Edge Server certificates in Lync Server 2013</A> and the reverse proxy <A href="lync-server-2013-certificate-summary-reverse-proxy.md">Certificate summary - Reverse proxy in Lync Server 2013</A>.</span></span> <span data-ttu-id="74257-153">Certifique-se de criar o certificado com uma chave privada exportável.</span><span class="sxs-lookup"><span data-stu-id="74257-153">Make sure that you create the certificate with an exportable private key.</span></span> <span data-ttu-id="74257-154">A criação da solicitação de certificado e certificado com uma chave privada exportável é necessária para servidores de borda em pool, portanto, esta é uma prática normal e o assistente de certificado no assistente de implantação do Lync Server para o servidor de borda permitirá que você defina o sinalizador de <STRONG>exportação de chave privada</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="74257-154">Creating the certificate and certificate request with an exportable private key is required for pooled Edge Servers, so this is a normal practice and the Certificate Wizard in the Lync Server Deployment Wizard for the Edge Server will allow you to set the <STRONG>Make private key exportable</STRONG> flag.</span></span> <span data-ttu-id="74257-155">Quando receber a solicitação de certificado de volta da autoridade de certificação pública, você exportará o certificado e a chave privada.</span><span class="sxs-lookup"><span data-stu-id="74257-155">Once you receive the certificate request back from the public certification authority, you will export the certificate and the private key.</span></span> <span data-ttu-id="74257-156">Consulte a seção "para exportar o certificado com a chave privada para servidores de borda em um pool" no tópico <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">configurar certificados para a interface de borda externa do Lync Server 2013</A> para obter detalhes sobre como criar e exportar o certificado com uma chave privada.</span><span class="sxs-lookup"><span data-stu-id="74257-156">See the section “To export the certificate with the private key for Edge Servers in a pool” in the topic <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Set up certificates for the external edge interface for Lync Server 2013</A> for details on how to create and export your certificate with a private key.</span></span> <span data-ttu-id="74257-157">A extensão do certificado deve ser do tipo <STRONG>. pfx</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="74257-157">The extension of the certificate should be of type <STRONG>.pfx</STRONG>.</span></span>



</div>

<span data-ttu-id="74257-158">Para gerar uma solicitação de assinatura de certificado no computador onde o certificado e a chave privada serão atribuídos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="74257-158">To generate a certificate signing request on the computer where the certificate and private key will be assigned, you do the following:</span></span>

<span data-ttu-id="74257-159">**Criar uma solicitação de assinatura de certificado**</span><span class="sxs-lookup"><span data-stu-id="74257-159">**Creating a certificate signing request**</span></span>

1.  <span data-ttu-id="74257-160">Abra o console de gerenciamento Microsoft (MMC) e adicione o snap-in certificados e selecione **computadores**e, em seguida, expanda **pessoal**.</span><span class="sxs-lookup"><span data-stu-id="74257-160">Open the Microsoft Management Console (MMC) and add the Certificates snap-in and select **Computers**, then expand **Personal**.</span></span> <span data-ttu-id="74257-161">Para obter detalhes sobre como criar um console de certificados no MMC (console de gerenciamento Microsoft), consulte [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616) .</span><span class="sxs-lookup"><span data-stu-id="74257-161">For details on how to create a certificates console in the Microsoft Management Console (MMC), see [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616).</span></span>

2.  <span data-ttu-id="74257-162">Clique com o botão direito do mouse em **certificados**, clique em **todas as tarefas**, em **operações avançadas**, em **criar solicitação personalizada**.</span><span class="sxs-lookup"><span data-stu-id="74257-162">Right-click **Certificates**, click **All Tasks**, click **Advanced Operations**, click **Create Custom Request**.</span></span>

3.  <span data-ttu-id="74257-163">Na página **registro de certificado** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="74257-163">On the **Certificate Enrollment** page, click **Next**.</span></span>

4.  <span data-ttu-id="74257-164">Na página **selecionar política de registro de certificado** em **solicitação personalizada**, selecione **continuar sem política de registro**.</span><span class="sxs-lookup"><span data-stu-id="74257-164">On the **Select Certificate Enrollment Policy** page under **Custom Request**, select **Proceed without enrollment policy**.</span></span> <span data-ttu-id="74257-165">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="74257-165">Click **Next**.</span></span>

5.  <span data-ttu-id="74257-166">Na página **solicitação personalizada** , em **modelo** selecionar **(sem modelo) chave herdada**.</span><span class="sxs-lookup"><span data-stu-id="74257-166">On the **Custom Request** page, for **Template** select **(No template) Legacy key**.</span></span> <span data-ttu-id="74257-167">Salvo indicação em contrário pelo provedor de certificados, deixe **suprimir as extensões padrão** desmarcadas e a seleção de **formato de solicitação** no **PKCS \# 10**.</span><span class="sxs-lookup"><span data-stu-id="74257-167">Unless otherwise directed by your certificate provider, leave **Suppress default extensions** unchecked and the **Request format** selection on **PKCS \#10**.</span></span> <span data-ttu-id="74257-168">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="74257-168">Click **Next**.</span></span>

6.  <span data-ttu-id="74257-169">Na página **informações do certificado** , clique em **detalhes**e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="74257-169">On the **Certificate Information** page, click **Details**, then click **Properties**.</span></span>

7.  <span data-ttu-id="74257-170">Na página de **Propriedades do certificado** , na guia **geral** , no campo **nome amigável** , digite um nome para esse certificado.</span><span class="sxs-lookup"><span data-stu-id="74257-170">On the **Certificate Properties** page on the **General** tab in the **Friendly Name** field, type a name for this certificate.</span></span> <span data-ttu-id="74257-171">Opcionalmente, digite uma descrição no campo **Descrição** .</span><span class="sxs-lookup"><span data-stu-id="74257-171">Optionally, type a description in the **Description** field.</span></span> <span data-ttu-id="74257-172">O nome amigável e a descrição normalmente são usados pelo administrador para identificar qual é a finalidade do certificado, como o **ouvinte de proxy reverso para o Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="74257-172">The Friendly Name and description are typically used by the Administrator to identify what the certificate purpose is, such as **Reverse Proxy Listener for Lync Server**.</span></span>

8.  <span data-ttu-id="74257-173">Selecione a guia **assunto** . Em **nome do assunto** para o **tipo**, selecione **nome comum** para o tipo de nome de entidade.</span><span class="sxs-lookup"><span data-stu-id="74257-173">Select the **Subject** tab. Under **Subject name** for the **Type**, select **Common name** for the Subject name type.</span></span> <span data-ttu-id="74257-174">Para o **valor**, digite o nome da entidade que você usará para o proxy reverso e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="74257-174">For the **Value**, type the subject name that you will use for the reverse proxy, and then click **Add**.</span></span> <span data-ttu-id="74257-175">No exemplo fornecido na tabela deste tópico, o nome da entidade é webext.contoso.com e deve ser digitado no campo value para o nome do assunto.</span><span class="sxs-lookup"><span data-stu-id="74257-175">In the example provided in the table in this topic, the subject name is webext.contoso.com and would be typed into the Value field for the Subject name.</span></span>

9.  <span data-ttu-id="74257-176">Na guia **assunto** em **nome alternativo**, selecione **DNS** na lista suspensa para **tipo**.</span><span class="sxs-lookup"><span data-stu-id="74257-176">On the **Subject** tab under **Alternative name**, select **DNS** from the drop down for **Type**.</span></span> <span data-ttu-id="74257-177">Para cada nome alternativo de entidade definido que você precisa no certificado, digite o nome de domínio totalmente qualificado e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="74257-177">For each defined subject alternative name that you require on the certificate, type the fully qualified domain name, then click **Add**.</span></span> <span data-ttu-id="74257-178">Por exemplo, na tabela há três nomes alternativos da entidade, meet.contoso.com, dialin.contoso.com e lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="74257-178">For example, in the table there are three subject alternative names, meet.contoso.com, dialin.contoso.com, and lyncdiscover.contoso.com.</span></span> <span data-ttu-id="74257-179">No campo **valor** , digite Meet.contoso.com e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="74257-179">In the **Value** field, type meet.contoso.com, then click **Add**.</span></span> <span data-ttu-id="74257-180">Repita o procedimento para cada nome alternativo de entidade que você precisa definir.</span><span class="sxs-lookup"><span data-stu-id="74257-180">Repeat for each subject alternative names that you need to define.</span></span>

10. <span data-ttu-id="74257-181">Na página de **Propriedades do certificado** , clique na guia **extensões** . Nesta página, você definirá os objetivos da chave criptográfica no **uso da chave** e o uso estendido da chave no **uso estendido de chave (políticas de aplicativo)**.</span><span class="sxs-lookup"><span data-stu-id="74257-181">On the **Certificate Properties** page, click the **Extensions** tab. On this page, you will define the cryptographic key purposes in **Key usage** and the extended key usage in **Extended Key Usage (application policies)**.</span></span>

11. <span data-ttu-id="74257-182">Clique na seta **uso da chave** para mostrar as **opções disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="74257-182">Click the **Key usage** arrow to show the **Available options**.</span></span> <span data-ttu-id="74257-183">Em opções disponíveis, clique em **assinatura digital**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="74257-183">Under Available options, click **Digital signature**, then click **Add**.</span></span> <span data-ttu-id="74257-184">Clique em **codificação de chave**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="74257-184">Click **Key encipherment**, then click **Add**.</span></span> <span data-ttu-id="74257-185">Se a caixa de seleção **tornar esses usos de chave críticos** estiver desmarcada, marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="74257-185">If the checkbox for **Make these key usages critical** is unchecked, select the checkbox.</span></span>

12. <span data-ttu-id="74257-186">Clique na seta **uso estendido da chave (políticas de aplicativo)** para mostrar as **opções disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="74257-186">Click the **Extended Key Usage (application policies)** arrow to show the **Available options**.</span></span> <span data-ttu-id="74257-187">Em opções disponíveis, clique em **autenticação do servidor**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="74257-187">Under Available options, click **Server Authentication**, then click **Add**.</span></span> <span data-ttu-id="74257-188">Clique em **autenticação do cliente**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="74257-188">Click **Client Authentication**, then click **Add**.</span></span> <span data-ttu-id="74257-189">Se a caixa de seleção para **tornar crítico os usos estendidos de chave** for marcada, desmarque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="74257-189">If the check box for **Make the Extended Key Usages critical** is checked, unselect the checkbox.</span></span> <span data-ttu-id="74257-190">Ao contrário da caixa de seleção uso da chave (que deve ser marcada), você deve ter certeza de que a caixa de seleção uso estendido de chave não está marcada.</span><span class="sxs-lookup"><span data-stu-id="74257-190">Contrary to the Key usage checkbox (which must be checked) you must be sure that the Extended Key Usage checkbox is not checked.</span></span>

13. <span data-ttu-id="74257-191">Na página de **Propriedades do certificado** , clique na guia **chave privada** . Clique na seta **Opções de chave** .</span><span class="sxs-lookup"><span data-stu-id="74257-191">On the **Certificate Properties** page, click the **Private Key** tab. Click the **Key options** arrow.</span></span> <span data-ttu-id="74257-192">Em **tamanho da chave**, selecione **2048** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="74257-192">For **Key size**, select **2048** from the drop down.</span></span> <span data-ttu-id="74257-193">Se você estiver gerando esse par de chaves e o CSR em um computador diferente do proxy reverso para o qual esse certificado se destina, selecione **tornar a chave privada exportável**.</span><span class="sxs-lookup"><span data-stu-id="74257-193">If you are generating this key pair and CSR on a computer other than the reverse proxy that this certificate is intended for, select **Make private key exportable**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" /><span data-ttu-id="74257-195">Observação de segurança:</span><span class="sxs-lookup"><span data-stu-id="74257-195">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="74257-196">Selecionar <strong>tornar uma chave privada exportável</strong> é geralmente avisado quando você tem mais de um proxy reverso em um farm, pois você copiará o certificado e a chave privada para cada computador no farm.</span><span class="sxs-lookup"><span data-stu-id="74257-196">Selecting <strong>Make a private key exportable</strong> is generally advised when you have more than one reverse proxy in a farm because you will copy the certificate and the private key to each machine in the farm.</span></span> <span data-ttu-id="74257-197">Se você permitir uma chave privada exportável, deverá ter cuidado adicional com o certificado e o computador em que ele é gerado.</span><span class="sxs-lookup"><span data-stu-id="74257-197">If you do allow for an exportable private key, you must take extra care with the certificate and the computer that it is generated on.</span></span> <span data-ttu-id="74257-198">A chave privada, se comprometida, tornará o certificado inútil, bem como exporá potencialmente o computador ou os computadores para acesso externo e outras vulnerabilidades de segurança.</span><span class="sxs-lookup"><span data-stu-id="74257-198">The private key, if compromised, will render the certificate useless as well as potentially expose the computer or computers to external access and other security vulnerabilities.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. <span data-ttu-id="74257-199">Na guia **chave privada** , clique na seta **tipo de chave** .</span><span class="sxs-lookup"><span data-stu-id="74257-199">On the **Private Key** tab, click the **Key type** arrow.</span></span> <span data-ttu-id="74257-200">Selecione a opção **Exchange** .</span><span class="sxs-lookup"><span data-stu-id="74257-200">Select the **Exchange** option.</span></span>

15. <span data-ttu-id="74257-201">Clique em **OK** para salvar as **Propriedades de certificado** que você definiu.</span><span class="sxs-lookup"><span data-stu-id="74257-201">Click **OK** to save the **Certificate Properties** that you have set.</span></span>

16. <span data-ttu-id="74257-202">Na página **registro de certificado** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="74257-202">On the **Certificate Enrollment** page, click **Next**.</span></span>

17. <span data-ttu-id="74257-203">Na página **onde você deseja salvar a solicitação offline?** , você será solicitado a fornecer um **nome de arquivo** e um formato de **arquivo** para salvar a solicitação de assinatura de certificado.</span><span class="sxs-lookup"><span data-stu-id="74257-203">On the **Where do you want to save the offline request?** page, you are prompted for a **File Name** and a **File Format** for saving the certificate signing request.</span></span>

18. <span data-ttu-id="74257-204">No campo de entrada **nome do arquivo** , digite um caminho e um nome de arquivo para a solicitação ou clique em **procurar** para selecionar um local para o arquivo e digite o nome do arquivo para a solicitação.</span><span class="sxs-lookup"><span data-stu-id="74257-204">In the **File Name** entry field, type a path and filename for the request, or click **Browse** to select a location for the file and type the filename for the request.</span></span>

19. <span data-ttu-id="74257-205">Em **formato de arquivo**, clique em **base 64** ou **binário**.</span><span class="sxs-lookup"><span data-stu-id="74257-205">For **File format**, click either **Base 64** or **Binary**.</span></span> <span data-ttu-id="74257-206">Selecione **Base 64** , a menos que você tenha instruído de outra forma pelo fornecedor de seus certificados.</span><span class="sxs-lookup"><span data-stu-id="74257-206">Select **Base 64** unless you are instructed otherwise by the vendor for your certificates.</span></span>

20. <span data-ttu-id="74257-207">Localize o arquivo de solicitação que você salvou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="74257-207">Locate the request file that you saved in the previous step.</span></span> <span data-ttu-id="74257-208">Envie para sua autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="74257-208">Submit to your public certification authority.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="74257-209">A Microsoft identificou autoridades de certificação públicas que atendem aos requisitos para fins de comunicação unificada.</span><span class="sxs-lookup"><span data-stu-id="74257-209">Microsoft has identified Public CAs that meets the requirements for Unified Communications purposes.</span></span> <span data-ttu-id="74257-210">Uma lista é mantida no seguinte artigo da base de dados de conhecimento.</span><span class="sxs-lookup"><span data-stu-id="74257-210">A list is maintained in the following knowledge base article.</span></span> <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

