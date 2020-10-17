---
title: 'Lync Server 2013: configurar certificados para servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82d23410257db89ff0c7498aba879444a5be9707
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521058"
---
# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="4fa03-102">Configurar certificados para servidores no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fa03-102">Configure certificates for servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fa03-103">_**Última modificação do tópico:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="4fa03-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="4fa03-104">Para concluir com êxito este procedimento, você deve estar conectado como usuário membro do grupo RTCUniversalServerAdmins ou ter as permissões corretas delegadas.</span><span class="sxs-lookup"><span data-stu-id="4fa03-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="4fa03-105">Para obter detalhes sobre como delegar permissões, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4fa03-105">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="4fa03-106">Dependendo de sua organização e dos requisitos para a solicitação de certificados, podem ser necessárias outras associações de grupo.</span><span class="sxs-lookup"><span data-stu-id="4fa03-106">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="4fa03-107">Consulte o grupo que gerencia a autoridade de certificação (CA) da PKI (infraestrutura de chave pública).</span><span class="sxs-lookup"><span data-stu-id="4fa03-107">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4fa03-108">O Lync Server 2013 inclui suporte para o pacote SHA-2 (SHA-2 usa comprimentos de Resumo de 224, 256, 384 ou 512 bits) do hash de resumo e dos algoritmos de assinatura para conexões de clientes que executam os sistemas operacionais Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista ou Windows XP, além do Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="4fa03-108">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="4fa03-109">Para dar suporte ao acesso externo usando o pacote SHA-2, o certificado externo é emitido por uma AC pública que também pode emitir um certificado com o mesmo comprimento de bit Digest.</span><span class="sxs-lookup"><span data-stu-id="4fa03-109">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="4fa03-110">A seleção de qual o resumo de hash e o algoritmo de assinatura dependem dos clientes e dos servidores que usarão o certificado e outros computadores e dispositivos que os clientes e servidores irão se comunicar com quem também deve saber como usar os algoritmos usados no certificado.</span><span class="sxs-lookup"><span data-stu-id="4fa03-110">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="4fa03-111">Para obter informações sobre quais tamanhos de resumo são suportados no sistema operacional e em alguns aplicativos cliente, consulte <A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A> .</span><span class="sxs-lookup"><span data-stu-id="4fa03-111">For information on which digest lengths are supported in the operating system and some client applications, see<A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="4fa03-112">Cada servidor Standard Edition ou servidor front-end requer até quatro certificados: o certificado oAuthTokenIssuer, um certificado padrão, um certificado interno da Web e um certificado externo da Web.</span><span class="sxs-lookup"><span data-stu-id="4fa03-112">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="4fa03-113">No entanto, é possível solicitar e atribuir um único certificado padrão com entradas de nome alternativo de entidade apropriada, bem como o certificado oAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="4fa03-113">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="4fa03-114">Para obter detalhes sobre os requisitos de certificado, consulte [Certificate Requirements for Internal Servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="4fa03-114">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="4fa03-115">Para obter detalhes sobre como solicitar, atribuir e instalar o certificado oAuthTokenIssuer, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="4fa03-115">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="4fa03-116">Use o procedimento a seguir para solicitar, atribuir e instalar os certificados servidor Standard Edition ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="4fa03-116">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="4fa03-117">Repita o procedimento para cada servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="4fa03-117">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4fa03-118">O procedimento a seguir descreve como configurar certificados de uma PKI corporativa interna implantada pela sua organização e com o processamento de solicitação offline.</span><span class="sxs-lookup"><span data-stu-id="4fa03-118">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="4fa03-119">Para obter informações sobre como obter certificados de uma AC pública, consulte <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate Requirements for Internal Servers in Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="4fa03-119">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="4fa03-120">Além disso, este procedimento descreve como solicitar, atribuir e instalar certificados durante a configuração do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="4fa03-120">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="4fa03-121">Se você solicitou certificados com antecedência, conforme descrito na seção <A href="lync-server-2013-request-certificates-in-advance-optional.md">solicitar certificados com antecedência (opcional) para Lync Server 2013</A> desta documentação de implantação ou não usar uma PKI corporativa interna implantada em sua organização para obter certificados, você deve modificar esse procedimento conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="4fa03-121">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="4fa03-122">Para configurar certificados para um servidor front-end</span><span class="sxs-lookup"><span data-stu-id="4fa03-122">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="4fa03-123">No assistente de implantação do Lync Server, clique em **executar** ao lado de **etapa 3: solicitar, instalar ou atribuir certificados**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-123">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="4fa03-124">Na página **Assistente de Certificados**, clique em **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-124">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="4fa03-125">Na página **Solicitação de Certificado**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-125">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="4fa03-126">Na página **solicitações atrasadas ou imediatas** , você pode aceitar a opção padrão **enviar a solicitação imediatamente para uma autoridade de certificação online** clicando em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-126">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**.</span></span> <span data-ttu-id="4fa03-127">A autoridade de certificação interna com registro online automático deve estar disponível se você selecionar essa opção.</span><span class="sxs-lookup"><span data-stu-id="4fa03-127">The internal CA with automatic online enrollment must be available if you select this option.</span></span> <span data-ttu-id="4fa03-128">Se você escolher a opção para atrasar a solicitação, você será solicitado a fornecer um nome e um local para salvar o arquivo de solicitação de certificado.</span><span class="sxs-lookup"><span data-stu-id="4fa03-128">If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file.</span></span> <span data-ttu-id="4fa03-129">A solicitação de certificado deve ser apresentada e processada por uma autoridade de certificação dentro da sua organização ou por uma autoridade de certificação pública.</span><span class="sxs-lookup"><span data-stu-id="4fa03-129">The certificate request must be presented and processed by a CA either inside your organization, or by a public CA.</span></span> <span data-ttu-id="4fa03-130">Você precisará importar a resposta do certificado e atribuí-la à função de certificado adequada.</span><span class="sxs-lookup"><span data-stu-id="4fa03-130">You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="4fa03-131">Na página **escolher uma autoridade de certificação (CA)** , selecione a opção **selecionar uma autoridade de certificação na lista detectada em seu ambiente** e, em seguida, selecione uma autoridade de certificação conhecida (através de registro no Active Directory Domain Services) na lista.</span><span class="sxs-lookup"><span data-stu-id="4fa03-131">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="4fa03-132">Ou selecione a opção **especificar outra autoridade de certificação** , digite o nome de outra autoridade de certificação na caixa e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-132">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="4fa03-p109">Na página **Conta da Autoridade de Certificação**, são solicitadas credenciais para solicitar e processar a solicitação de certificado na AC. Você deve ter determinado se um nome de usuário e senha são necessários para solicitar um certificado antecipadamente. O administrador da sua AC terá a informação solicitada e pode ajudá-lo nesta etapa. Se for necessário fornecer credenciais alternativas, selecione a opção, forneça um nome de usuário e senha nas caixas de texto e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-p109">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA. You should have determined if a user name and password is necessary to request a certificate in advance. Your CA administrator will have the required information and may have to assist you in this step. If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="4fa03-137">Na página **Especificar Modelo de Certificado Alternativo**, para usar o modelo do Servidor Web padrão, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-137">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4fa03-p110">Se sua organização criou um modelo para uso como uma alternativa para o modelo padrão da AC do servidor Web, marque a caixa de seleção e insira o nome do modelo alternativo. Você precisará no nome de modelo conforme definido pelo administrador da AC.</span><span class="sxs-lookup"><span data-stu-id="4fa03-p110">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template. You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="4fa03-140">Na página **Nome e Configurações de Segurança**, especifique um **Nome Amigável** que o permita identificar o certificado e o objetivo.</span><span class="sxs-lookup"><span data-stu-id="4fa03-140">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose.</span></span> <span data-ttu-id="4fa03-141">Se deixá-lo em branco, um nome será gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4fa03-141">If you leave it blank, a name will be generated automatically.</span></span> <span data-ttu-id="4fa03-142">Defina o **Comprimento de bit** da chave ou aceite o padrão de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="4fa03-142">Set the **Bit length** of the key, or accept the default of 2048 bits.</span></span> <span data-ttu-id="4fa03-143">Selecione a **caixa de seleção marcar a chave privada do certificado como exportável** se você determinar que o certificado e a chave privada precisam ser movidos ou copiados para outros sistemas e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-143">Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4fa03-144">O Lync Server 2013 tem requisitos mínimos para uma chave privada exportável.</span><span class="sxs-lookup"><span data-stu-id="4fa03-144">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="4fa03-145">Um local está nos Servidores de Borda em um pool, onde o Serviço de Autenticação de Media Relay usa cópias do certificado, em vez dos certificados individuais para cada instância no pool.</span><span class="sxs-lookup"><span data-stu-id="4fa03-145">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="4fa03-146">Na página **informações da organização** , forneça, opcionalmente, as informações da organização e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-146">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="4fa03-147">Na página **informações geográficas** , forneça, opcionalmente, informações geográficas e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-147">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="4fa03-148">Na página **Nome da Entidade / Nomes Alternativos de Entidade**, veja os nomes alternativos de entidade que serão adicionados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-148">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="4fa03-149">Na página **configuração do domínio SIP** , selecione o **domínio SIP**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-149">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="4fa03-150">Na página **configurar nomes alternativos da entidade adicionais** , adicione quaisquer nomes alternativos de entidade adicionais necessários, incluindo qualquer um que possa ser necessário para domínios SIP adicionais no futuro e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-150">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="4fa03-151">Na página **Resumo da solicitação de certificado** , revise as informações no resumo.</span><span class="sxs-lookup"><span data-stu-id="4fa03-151">On the **Certificate Request Summary** page, review the information in the summary.</span></span> <span data-ttu-id="4fa03-152">Se as informações estiverem corretas, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-152">If the information is correct, click **Next**.</span></span> <span data-ttu-id="4fa03-153">Se você precisar corrigir ou modificar uma configuração, clique em **voltar** à página adequada para fazer a correção ou modificação.</span><span class="sxs-lookup"><span data-stu-id="4fa03-153">If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="4fa03-154">Na página **Executando Comandos**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-154">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="4fa03-155">Na página **status da solicitação de certificado online** , revise as informações retornadas.</span><span class="sxs-lookup"><span data-stu-id="4fa03-155">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="4fa03-156">Você deve observar que o certificado foi emitido e instalado no repositório de certificados local.</span><span class="sxs-lookup"><span data-stu-id="4fa03-156">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="4fa03-157">Se ele for relatado como tendo sido emitido e instalado, mas não for válido, verifique se o certificado raiz da autoridade de certificação foi instalado no repositório da autoridade de certificação raiz confiável do servidor.</span><span class="sxs-lookup"><span data-stu-id="4fa03-157">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="4fa03-158">Consulte a documentação da autoridade de certificação sobre como recuperar um certificado de autoridade de certificação raiz confiável.</span><span class="sxs-lookup"><span data-stu-id="4fa03-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="4fa03-159">Se você precisar exibir o certificado recuperado, clique em **Exibir detalhes do certificado**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="4fa03-160">Por padrão, a caixa de seleção para **atribuir o certificado aos usos de certificado do Lync Server** é verificada.</span><span class="sxs-lookup"><span data-stu-id="4fa03-160">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="4fa03-161">Se você deseja atribuir manualmente o certificado, desmarque a caixa de seleção e clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="4fa03-162">Se você desmarcou a caixa de seleção para **atribuir o certificado aos usos de certificado do Lync Server** na página anterior, será exibida a página **atribuição de certificado** .</span><span class="sxs-lookup"><span data-stu-id="4fa03-162">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page.</span></span> <span data-ttu-id="4fa03-163">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-163">Click **Next**.</span></span>

18. <span data-ttu-id="4fa03-164">Na página **repositório de certificados** , selecione o certificado que você solicitou.</span><span class="sxs-lookup"><span data-stu-id="4fa03-164">On the **Certificate Store** page, select the certificate that you requested.</span></span> <span data-ttu-id="4fa03-165">Se quiser exibir o certificado, clique em **Exibir detalhes do certificado**e clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="4fa03-165">If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4fa03-166">Se a página <STRONG>status da solicitação de certificado online</STRONG> relatou um problema com o certificado, como o certificado não é válido, a exibição do certificado real pode ajudar a resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="4fa03-166">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue.</span></span> <span data-ttu-id="4fa03-167">Dois problemas específicos que podem fazer com que um certificado não seja válido é o certificado de autoridade de certificação raiz confiável ausente mencionado anteriormente e uma chave privada ausente associada ao certificado.</span><span class="sxs-lookup"><span data-stu-id="4fa03-167">Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate.</span></span> <span data-ttu-id="4fa03-168">Consulte a documentação da autoridade de certificação para resolver esses dois problemas.</span><span class="sxs-lookup"><span data-stu-id="4fa03-168">Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="4fa03-169">Na página **Resumo de atribuição de certificado** , revise as informações apresentadas para certificar-se de que esse é o certificado que deve ser atribuído e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-169">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="4fa03-170">Na página **executando comandos** , revise a saída do comando.</span><span class="sxs-lookup"><span data-stu-id="4fa03-170">On the **Executing Commands** page, review the output of the command.</span></span> <span data-ttu-id="4fa03-171">Clique em **Exibir log** se quiser revisar o processo de atribuição ou se houve um erro ou aviso emitido.</span><span class="sxs-lookup"><span data-stu-id="4fa03-171">Click **View Log** if you want to review the assignment process or if there was an error or warning issued.</span></span> <span data-ttu-id="4fa03-172">Após concluir a revisão, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-172">When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="4fa03-173">Na página **Assistente de certificado** , verifique se o **status** do certificado é "atribuído" e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="4fa03-173">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4fa03-174">Confira também</span><span class="sxs-lookup"><span data-stu-id="4fa03-174">See Also</span></span>


[<span data-ttu-id="4fa03-175">Requisitos de infraestrutura de certificado para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4fa03-175">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

