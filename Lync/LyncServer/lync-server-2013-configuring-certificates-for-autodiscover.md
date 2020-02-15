---
title: 'Lync Server 2013: Configurando certificados para descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d78aff761f1df9140bfc491e94ba98e1a0814f25
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="fce5f-102">Configurando certificados para descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce5f-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fce5f-103">_**Última modificação do tópico:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="fce5f-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="fce5f-104">Os certificados do seu pool de diretores, pool de front-ends e proxy reverso exigem entradas de nome alternativo de entidade adicional para dar suporte a conexões seguras com clientes Lync.</span><span class="sxs-lookup"><span data-stu-id="fce5f-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fce5f-105">Você pode usar o cmdlet <STRONG>Get-CsCertificate</STRONG> para exibir as informações sobre os certificados atualmente atribuídos.</span><span class="sxs-lookup"><span data-stu-id="fce5f-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="fce5f-106">No entanto, o modo padrão trunca as propriedades do certificado e não exibe todos os valores na propriedade SubjectAlternativeNames.</span><span class="sxs-lookup"><span data-stu-id="fce5f-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="fce5f-107">Você pode usar o <STRONG>Get-CsCertificate</STRONG> , o CsCertificate <STRONG>Request-</STRONG> e os cmdlets <STRONG>Set-CsCertificate</STRONG> para exibir alguma informação e para solicitar e atribuir certificados.</span><span class="sxs-lookup"><span data-stu-id="fce5f-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="fce5f-108">Porém, não é o melhor método a ser usado se você não conhece as propriedades do SAN (nomes alternativos da entidade) no certificado atual.</span><span class="sxs-lookup"><span data-stu-id="fce5f-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="fce5f-109">Para exibir o certificado e todos os membros de propriedade, é recomendável usar o snap-in de certificados no <EM>console de gerenciamento Microsoft (MMC)</EM> ou usar o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fce5f-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="fce5f-110">No assistente de implantação do Lync Server, você pode usar o assistente de certificado para exibir as propriedades do certificado.</span><span class="sxs-lookup"><span data-stu-id="fce5f-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="fce5f-111">Os procedimentos para exibir, solicitar e atribuir um certificado usando o Shell de gerenciamento do Lync Server e o <EM>MMC (console de gerenciamento Microsoft)</EM> são detalhados nos procedimentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="fce5f-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="fce5f-112">Para usar o assistente de implantação do Lync Server, confira detalhes aqui se você tiver implantado o diretor opcional ou o pool de diretores: <A href="lync-server-2013-configure-certificates-for-the-director.md">configure certificados para o diretor no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fce5f-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="fce5f-113">Para o servidor front-end ou o pool de front-ends, consulte os detalhes aqui: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure Certificates for Servers in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="fce5f-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="fce5f-114">As etapas iniciais nesse procedimento são de preparação para te orientar sobre a função do certificado atual.</span><span class="sxs-lookup"><span data-stu-id="fce5f-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="fce5f-115">Por padrão, os certificados não terão lyncdiscover. &lt;sipdomain&gt; ou lyncdiscoverinternal. &lt;entrada de nome&gt; de domínio interno, a menos que você tenha instalado os serviços de mobilidade anteriormente ou tenha preparado os certificados com antecedência.</span><span class="sxs-lookup"><span data-stu-id="fce5f-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="fce5f-116">Esse procedimento utiliza o exemplo do nome do domínio SIP ‘contoso.com’ e o exemplo do nome do domínio interno ‘contoso.net’.</span><span class="sxs-lookup"><span data-stu-id="fce5f-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="fce5f-117">A configuração de certificado padrão do Lync Server 2013 e do Lync Server 2010 é usar um único certificado (chamado "padrão") com o padrão de finalidades (para todos os fins, exceto para os serviços Web), WebServicesExternal e WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="fce5f-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="fce5f-118">Uma configuração opcional seria usar certificados separados para cada propósito.</span><span class="sxs-lookup"><span data-stu-id="fce5f-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="fce5f-119">Os certificados podem ser gerenciados usando o Shell de gerenciamento do Lync Server e os cmdlets do Windows PowerShell, ou usando o assistente de certificado no assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fce5f-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="fce5f-120">Para atualizar certificados com nomes alternativos de novos requerentes usando o Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="fce5f-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="fce5f-121">Faça logon no computador usando uma conta que tenha permissões e direitos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="fce5f-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="fce5f-122">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fce5f-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fce5f-p104">Descubra quais certificados foram atribuídos ao servidor e para qual tipo de uso. Você precisará dessas informações na próxima etapa para atribuir o certificado atualizado. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="fce5f-p104">Find out what certificates have been assigned to the server and for which type of use. You need this information in the next step to assign the updated certificate. At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="fce5f-p105">Examine o resultado da etapa anterior para ver se um único certificado foi atribuído a vários usos ou se um certificado diferente foi atribuído para cada uso. Examine o parâmetro Use para descobrir como um certificado é usado. Compare o parâmetro Thumbprint dos certificados exibidos para ver se o mesmo certificado tem vários usos.</span><span class="sxs-lookup"><span data-stu-id="fce5f-p105">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use. Look in the Use parameter to find out how a certificate is used. Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="fce5f-p106">Atualize o certificado. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="fce5f-p106">Update the certificate. At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="fce5f-131">Por exemplo, se o cmdlet **Get-CsCertificate** exibiu um certificado com Use de Default, outro com um Use de WebServicesInternal e outro com um Use de WebServicesExternal, e todos eles tinham o mesmo valor de Thumbprint, digite na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="fce5f-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="fce5f-132">**Importante:**</span><span class="sxs-lookup"><span data-stu-id="fce5f-132">**Important:**</span></span>
    
    <span data-ttu-id="fce5f-133">Quando é atribuído um certificado separado para cada uso (valor de Thumbprint é diferente para cada certificado), é importante que você não execute o cmdlet **Set-CsCertificate** com vários tipos.</span><span class="sxs-lookup"><span data-stu-id="fce5f-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="fce5f-134">Nesse caso, execute o cmdlet **Set-CsCertificate** separadamente para cada uso.</span><span class="sxs-lookup"><span data-stu-id="fce5f-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="fce5f-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fce5f-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="fce5f-p108">Para exibir o certificado, clique em **Iniciar**, clique em **Executar…**. Digite MMC para abrir o Console de Gerenciamento Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fce5f-p108">To view the certificate, click **Start**, click **Run…**. Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="fce5f-p109">No menu do MMC, selecione **Arquivo**, selecione**Adicionar/Remover snap-in…**, selecione Certificados. Clique em **Adicionar**. Quando lhe for solicitado, selecione **Conta do computador** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="fce5f-p109">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates. Click **Add**. When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="fce5f-141">Se o certificado estiver localizado no computador, selecione **computador local**.</span><span class="sxs-lookup"><span data-stu-id="fce5f-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="fce5f-142">Se o certificado estiver localizado em outro computador, selecione **outro computador**, digite o nome de domínio totalmente qualificado do computador ou clique em **procurar** em **Insira o nome do objeto a ser selecionado**, digite o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="fce5f-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="fce5f-143">Clique em **Verificar Nomes**.</span><span class="sxs-lookup"><span data-stu-id="fce5f-143">Click **Check Names**.</span></span> <span data-ttu-id="fce5f-144">Quando o nome do computador for resolvido, ele será sublinhado.</span><span class="sxs-lookup"><span data-stu-id="fce5f-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="fce5f-145">Clique em **OK**e em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="fce5f-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="fce5f-146">Clique em **OK** para confirmar a seleção e fechar a caixa de diálogo **Adicionar ou remover snap-ins** .</span><span class="sxs-lookup"><span data-stu-id="fce5f-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fce5f-147">Se o certificado não aparecer no console, verifique se você não selecionou o usuário ou serviço.</span><span class="sxs-lookup"><span data-stu-id="fce5f-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="fce5f-148">Você deve selecionar computador ou não será possível localizar o certificado probper.</span><span class="sxs-lookup"><span data-stu-id="fce5f-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="fce5f-p112">Para exibir as propriedades do certificado, expanda **Certificados**, expanda **Pessoal** e selecione **Certificados**. Selecione o certificado para exibição, clique com o botão direito do mouse em certificado e selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="fce5f-p112">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="fce5f-p113">Na exibição **Certificado**, selecione **Detalhes**. Aqui, você pode escolher o nome da entidade do certificado ao selecionar **Assunto** e o nome da entidade atribuída e as propriedades atribuídas serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="fce5f-p113">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="fce5f-153">Para exibir os nomes alternativos de entidades atribuídos, selecione**Nome Alternativo de Entidade**.</span><span class="sxs-lookup"><span data-stu-id="fce5f-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="fce5f-154">Todos os nomes alternativos de entidade atribuídos são exibidos.</span><span class="sxs-lookup"><span data-stu-id="fce5f-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="fce5f-155">Os nomes alternativos de entidade encontrados na propriedade são do tipo **Nome DNS** por padrão.</span><span class="sxs-lookup"><span data-stu-id="fce5f-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="fce5f-156">Você deve ver os seguintes membros (todos deveriam ser nomes de domínio completamente qualificados) como representado nos registros de host DNS (A ou, se IPv6, AAAA):</span><span class="sxs-lookup"><span data-stu-id="fce5f-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="fce5f-157">Nome do pool para esse pool ou um nome de servidor único se esse não for um pool</span><span class="sxs-lookup"><span data-stu-id="fce5f-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="fce5f-158">Nome do servidor ao qual o certificado está atribuído</span><span class="sxs-lookup"><span data-stu-id="fce5f-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="fce5f-159">Registros de URL Simples, normalmente reunir e discar</span><span class="sxs-lookup"><span data-stu-id="fce5f-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="fce5f-160">Nomes internos e externos de serviços Web (por exemplo, webpool01.contoso.net, webpool01.contoso.com), com base nas escolhas feitas no construtor de topologias e nas seleções de serviços Web do nas.</span><span class="sxs-lookup"><span data-stu-id="fce5f-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="fce5f-161">Se já tiver sido atribuído, o lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<sipdomain\> registros.</span><span class="sxs-lookup"><span data-stu-id="fce5f-161">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="fce5f-162">O último item é o mais interessante – se houver uma entrada SAN lyncdiscover e lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="fce5f-162">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="fce5f-163">Assim que obtiver essa informação, você pode fechar o certificado exibido e o MMC.</span><span class="sxs-lookup"><span data-stu-id="fce5f-163">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="fce5f-164">Se um serviço de descoberta automática, ou seja, o lyncdiscover. \>nome\> de domínio e lyncdiscoverinternal. \<nome\> do domínio (baseado em se este for um certificado externo ou interno) o nome alternativo da entidade estiver ausente e você estiver usando um único certificado padrão para os tipos padrão, WebServicesInternal e WebServiceExternal, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fce5f-164">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\> (based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="fce5f-165">No prompt da linha de comando do Shell de gerenciamento do Lync Server, digite:</span><span class="sxs-lookup"><span data-stu-id="fce5f-165">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="fce5f-166">Se você possui vários domínios SIP, não é possível usar o novo parâmetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="fce5f-166">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="fce5f-167">Em vez disso, você deve usar o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="fce5f-167">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="fce5f-168">Quando você usar o parâmetro DomainName, você deve definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="fce5f-168">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="fce5f-169">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fce5f-169">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="fce5f-170">Para atribuir o certificado, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fce5f-170">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="fce5f-171">Onde “Thumbprint” é o thumbprint exibido para o novo certificado emitido.</span><span class="sxs-lookup"><span data-stu-id="fce5f-171">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="fce5f-172">Para nomes alternativos de entidades de Descoberta Automática interna ausente quando usam certificados separados por Padrão, WebServicesInternale e WebServicesExternal, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fce5f-172">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="fce5f-173">No prompt da linha de comando do Shell de gerenciamento do Lync Server, digite:</span><span class="sxs-lookup"><span data-stu-id="fce5f-173">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="fce5f-p116">Se você possui vários domínios SIP, não é possível usar o novo parâmetro AllSipDomain. Ao invés, você deve usar o parâmetro DomainName. Quando utilizar o parâmetro DomainName, você deve usar um prefixo adequado para o FQDN de domínio SIP. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fce5f-p116">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="fce5f-178">Para obter um nome alternativo da entidade de Descoberta Automática externo, digite na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="fce5f-178">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="fce5f-p117">Se você possui vários domínios SIP, não é possível usar o novo parâmetro AllSipDomain. Ao invés, você deve usar o parâmetro DomainName. Quando utilizar o parâmetro DomainName, você deve usar um prefixo adequado para o FQDN de domínio SIP. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fce5f-p117">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="fce5f-183">Para atribuir os tipos de certificados individuais, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fce5f-183">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="fce5f-184">Onde “Thumbprint” é o thumbprint exibido para os novos certificados individuais emitidos.</span><span class="sxs-lookup"><span data-stu-id="fce5f-184">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

