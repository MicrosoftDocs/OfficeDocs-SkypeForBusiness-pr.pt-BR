---
title: 'Lync Server 2013: Configurar certificados para servidores'
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
ms.openlocfilehash: 303724fa705fa94e9bbacacb4764bba7b918c460
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="593d9-102">Configurar certificados para servidores no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="593d9-102">Configure certificates for servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="593d9-103">_**Tópico da última modificação:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="593d9-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="593d9-104">Para concluir esse procedimento com êxito, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins ou ter as permissões corretas delegadas.</span><span class="sxs-lookup"><span data-stu-id="593d9-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="593d9-105">Para obter detalhes sobre como delegar permissões, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="593d9-105">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="593d9-106">Dependendo da sua organização e dos requisitos para solicitar certificados, você pode exigir outras associações de grupo.</span><span class="sxs-lookup"><span data-stu-id="593d9-106">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="593d9-107">Consulte o grupo que gerencia sua autoridade de certificação (PKI) da infraestrutura de chave pública (PKI).</span><span class="sxs-lookup"><span data-stu-id="593d9-107">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="593d9-108">O Lync Server 2013 inclui suporte para o pacote SHA-2 (SHA-2 usa os comprimentos de resumo dos bits do 224, 256, 384 ou 512) do hash de resumo e dos algoritmos de assinatura para conexões de clientes que executam o Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista ou Sistemas operacionais Windows XP, além do Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="593d9-108">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="593d9-109">Para suportar o acesso externo usando o pacote do SHA-2, o certificado externo é emitido por uma AC pública que também pode emitir um certificado com a mesma extensão de disco.</span><span class="sxs-lookup"><span data-stu-id="593d9-109">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="593d9-110">A seleção do resumo do hash e do algoritmo de assinatura dependerá do cliente e dos servidores que utilizarão o certificado, e de outros computadores e dispositivos que os clientes e servidores comunicarão a quem também deve saber como usar os algoritmos usados no certificado.</span><span class="sxs-lookup"><span data-stu-id="593d9-110">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="593d9-111">Para obter informações sobre quais tamanhos de resumo são compatíveis com o sistema operacional e alguns aplicativos cliente,<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>consulte.</span><span class="sxs-lookup"><span data-stu-id="593d9-111">For information on which digest lengths are supported in the operating system and some client applications, see<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="593d9-112">Cada servidor de front-end ou servidor Standard Edition requer até quatro certificados: o certificado oAuthTokenIssuer, um certificado padrão, um certificado interno da Web e um certificado externo da Web.</span><span class="sxs-lookup"><span data-stu-id="593d9-112">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="593d9-113">No entanto, é possível solicitar e atribuir um único certificado padrão com entradas de nome alternativo de assunto apropriado, bem como o certificado oAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="593d9-113">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="593d9-114">Para obter detalhes sobre os requisitos de certificado, consulte [requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="593d9-114">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="593d9-115">Para obter detalhes sobre como solicitar, atribuir e instalar o certificado oAuthTokenIssuer, consulte [Gerenciando a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="593d9-115">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="593d9-116">Use o procedimento a seguir para solicitar, atribuir e instalar os certificados do servidor Standard Edition ou do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="593d9-116">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="593d9-117">Repita o procedimento para cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="593d9-117">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="593d9-118">O procedimento a seguir descreve como configurar certificados de uma PKI corporativa interna implantada pela sua organização e com o processamento de solicitações offline.</span><span class="sxs-lookup"><span data-stu-id="593d9-118">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="593d9-119">Para obter informações sobre como obter certificados de uma autoridade de certificação pública, consulte <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">requisitos de certificado para servidores internos no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="593d9-119">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="593d9-120">Além disso, esse procedimento descreve como solicitar, atribuir e instalar certificados durante a configuração do servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="593d9-120">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="593d9-121">Se você solicitou certificados antecipadamente, conforme descrito na seção <A href="lync-server-2013-request-certificates-in-advance-optional.md">solicitar certificados na seção Avançado (opcional) do Lync Server 2013</A> desta documentação de implantação, ou se não usar uma PKI corporativa interna implantada em sua organização para obter certificados, você deve modificar esse procedimento conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="593d9-121">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="593d9-122">Para configurar certificados para um servidor front-end</span><span class="sxs-lookup"><span data-stu-id="593d9-122">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="593d9-123">No assistente de implantação do Lync Server, clique em **executar** ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**.</span><span class="sxs-lookup"><span data-stu-id="593d9-123">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="593d9-124">Na página **Assistente de Certificados**, clique em **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="593d9-124">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="593d9-125">Na página **solicitação de certificado** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="593d9-125">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="593d9-p107">Na página **Solicitações Atrasadas ou Imediatas**, é possível aceitar a opção padrão **Enviar a solicitação imediatamente para uma autoridade de certificação online** clicando em **Avançar**. A AC interna com inscrição online automática precisa estar disponível se você selecionar essa opção. Se você escolher a opção para atrasar a solicitação, receberá uma solicitação para fornecer um nome e local para salvar o arquivo de solicitação do certificado. A solicitação de certificado precisa ser apresentada a processada por uma AC dentro de sua organização ou por uma AC pública. Em seguida, será necessário importar a resposta do certificado e atribuí-la à função de certificado apropriada.</span><span class="sxs-lookup"><span data-stu-id="593d9-p107">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**. The internal CA with automatic online enrollment must be available if you select this option. If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file. The certificate request must be presented and processed by a CA either inside your organization, or by a public CA. You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="593d9-131">Na página **escolher uma CA (autoridade** de certificação), selecione a opção **selecionar uma autoridade de certificação na lista detectada em seu ambiente** e, em seguida, selecione uma autoridade de certificação conhecida (por meio de registro nos serviços de domínio Active Directory) na lista.</span><span class="sxs-lookup"><span data-stu-id="593d9-131">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="593d9-132">Como alternativa, selecione a opção **Especificar outra autoridade de certificação**, digite o nome de outra AC na caixa e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="593d9-132">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="593d9-133">Na página **Conta da Autoridade de Certificação**, você deve informar as credenciais para solicitar e processar a solicitação de certificado na AC.</span><span class="sxs-lookup"><span data-stu-id="593d9-133">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA.</span></span> <span data-ttu-id="593d9-134">Você deve determinar com antecedência se um nome de usuário e uma senha são necessários para solicitar um certificado.</span><span class="sxs-lookup"><span data-stu-id="593d9-134">You should have determined if a user name and password is necessary to request a certificate in advance.</span></span> <span data-ttu-id="593d9-135">O administrador da sua CA terá as informações necessárias e poderá ter que ajudá-lo nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="593d9-135">Your CA administrator will have the required information and may have to assist you in this step.</span></span> <span data-ttu-id="593d9-136">Se precisar fornecer credenciais alternativas, marque a caixa de seleção, digite um nome de usuário e uma senha nas caixas de texto e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="593d9-136">If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="593d9-137">Na página **Especificar Modelo de Certificado Alternativo**, para usar o modelo de Servidor da web padrão, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="593d9-137">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="593d9-p110">Se sua organização tiver criado um modelo para ser usado como uma alternativa para o modelo de AC padrão do Servidor da web, marque a caixa de seleção, e digite o nome do modelo alternativo. Você precisará do nome do modelo, conforme definido pelo administrador de AC.</span><span class="sxs-lookup"><span data-stu-id="593d9-p110">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template. You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="593d9-140">Na página **configurações de nome e segurança** , especifique um **nome amigável** que deve permitir a identificação do certificado e da finalidade.</span><span class="sxs-lookup"><span data-stu-id="593d9-140">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose.</span></span> <span data-ttu-id="593d9-141">Se você deixá-lo em branco, um nome será gerado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="593d9-141">If you leave it blank, a name will be generated automatically.</span></span> <span data-ttu-id="593d9-142">Defina o **comprimento do bit** da chave ou aceite o padrão de 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="593d9-142">Set the **Bit length** of the key, or accept the default of 2048 bits.</span></span> <span data-ttu-id="593d9-143">Selecione a **chave privada do certificado como exportável** se você determinar que o certificado e a chave privada precisam ser movidos ou copiados para outros sistemas e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="593d9-143">Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="593d9-144">O Lync Server 2013 tem requisitos mínimos para uma chave privada exportável.</span><span class="sxs-lookup"><span data-stu-id="593d9-144">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="593d9-145">Um exemplo disso são os Servidores de Borda em um pool, onde o Serviço de Autenticação de Media Relay usa cópias do certificado, em vez de certificados individuais para cada instância no pool.</span><span class="sxs-lookup"><span data-stu-id="593d9-145">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="593d9-146">Na página **Informações da Organização**, forneça, opcionalmente, as informações da organização e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="593d9-146">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="593d9-147">Na página **Informações Geográficas**, forneça, opcionalmente, informações geográficas e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="593d9-147">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="593d9-148">Na página **Nome da Entidade/Nomes Alternativos da Entidade**, revise os nomes alternativos da entidade que serão adicionados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="593d9-148">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="593d9-149">Na página **Configuração do Domínio SIP**, selecione o **Domínio SIP** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="593d9-149">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="593d9-150">Na página **Configurar Nomes Alternativos da Entidade Adicionais**, adicione quaisquer nomes alternativos da entidade adicionais necessários, incluindo qualquer um que possa ser exigido para domínios SIP adicionais no futuro, e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="593d9-150">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="593d9-p113">Na página **Resumo da Solicitação de Certificado**, revise as informações no resumo. Se as informações estiverem corretas, clique em **Avançar**. Se você precisar corrigir ou modificar uma configuração, clique em **Voltar** para a página apropriada a fim de fazer a correção ou modificação.</span><span class="sxs-lookup"><span data-stu-id="593d9-p113">On the **Certificate Request Summary** page, review the information in the summary. If the information is correct, click **Next**. If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="593d9-154">Na página **Executando Comandos**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="593d9-154">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="593d9-155">On the **Online Certificate Request Status** page, review the information returned.</span><span class="sxs-lookup"><span data-stu-id="593d9-155">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="593d9-156">You should note that the certificate was issued and installed into the local certificate store.</span><span class="sxs-lookup"><span data-stu-id="593d9-156">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="593d9-157">Se for reportado como tendo sido emitido e instalado, mas não for válido, verifique se o certificado raiz da CA foi instalado no repositório da CA raiz confiável do servidor.</span><span class="sxs-lookup"><span data-stu-id="593d9-157">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="593d9-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span><span class="sxs-lookup"><span data-stu-id="593d9-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="593d9-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span><span class="sxs-lookup"><span data-stu-id="593d9-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="593d9-160">Por padrão, a caixa de seleção para **atribuir o certificado a usos de certificado do Lync Server** está marcada.</span><span class="sxs-lookup"><span data-stu-id="593d9-160">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="593d9-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span><span class="sxs-lookup"><span data-stu-id="593d9-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="593d9-162">Se você desmarcou a caixa de seleção para **atribuir o certificado aos usos de certificado do Lync Server** na página anterior, você será apresentado à página **atribuição de certificado** .</span><span class="sxs-lookup"><span data-stu-id="593d9-162">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page.</span></span> <span data-ttu-id="593d9-163">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="593d9-163">Click **Next**.</span></span>

18. <span data-ttu-id="593d9-p116">Na página **Repositório de Certificados**, selecione o certificado que você solicitou. Se você quiser ver o certificado, clique em **Exibir Detalhes do Certificado** e clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="593d9-p116">On the **Certificate Store** page, select the certificate that you requested. If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="593d9-166">Se a página <STRONG>status da solicitação de certificado online</STRONG> relatou um problema com o certificado, como o certificado que não é válido, a exibição do certificado real pode ajudar a solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="593d9-166">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue.</span></span> <span data-ttu-id="593d9-167">Dois problemas específicos que podem fazer com que um certificado seja inválido são a ausência o certificado AC raiz confiável, mencionada anteriormente, e a ausência de uma chave privada associada ao certificado.</span><span class="sxs-lookup"><span data-stu-id="593d9-167">Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate.</span></span> <span data-ttu-id="593d9-168">Consulte a documentação da AC para resolver esses dois problemas.</span><span class="sxs-lookup"><span data-stu-id="593d9-168">Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="593d9-169">Na página **Resumo de Atribuição de Certificado**, examine as informações apresentadas a fim de assegurar que esse certificado deve ser atribuído e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="593d9-169">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="593d9-p118">Na página **Executando Comandos**, revise a saída do comando. Clique em **Exibir Log** se você quiser revisar o processo de atribuição ou se houver um erro ou aviso. Após a conclusão da revisão, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="593d9-p118">On the **Executing Commands** page, review the output of the command. Click **View Log** if you want to review the assignment process or if there was an error or warning issued. When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="593d9-173">Na página do **Assistente de certificado** , verifique se o **status** do certificado é "atribuído" e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="593d9-173">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="593d9-174">Confira também</span><span class="sxs-lookup"><span data-stu-id="593d9-174">See Also</span></span>


[<span data-ttu-id="593d9-175">Requisitos de infraestrutura de certificado para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="593d9-175">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

