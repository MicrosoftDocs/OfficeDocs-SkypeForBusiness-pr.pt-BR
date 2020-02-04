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
ms.openlocfilehash: c1f2a89cf317a0ea5bead4bb24eba1469ef1108e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="98090-102">Configurando certificados para descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98090-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98090-103">_**Tópico da última modificação:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="98090-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="98090-104">Os certificados para o seu pool de directors, o pool de front-end e o proxy reverso exigem entradas de nomes alternativos de entidades adicionais para dar suporte a conexões seguras com clientes do Lync.</span><span class="sxs-lookup"><span data-stu-id="98090-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98090-105">Você pode usar o cmdlet <STRONG>Get-CsCertificate</STRONG> para exibir informações sobre os certificados atribuídos no momento.</span><span class="sxs-lookup"><span data-stu-id="98090-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="98090-106">No entanto, o modo de exibição padrão trunca as propriedades do certificado e não exibe todos os valores na propriedade SubjectAlternativeNames.</span><span class="sxs-lookup"><span data-stu-id="98090-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="98090-107">Você pode usar os cmdlets <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate e <STRONG>set-CsCertificate</STRONG> para ver algumas informações e solicitar e atribuir certificados.</span><span class="sxs-lookup"><span data-stu-id="98090-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="98090-108">No entanto, esse não é o melhor método para usar se você não tiver certeza das propriedades dos nomes alternativos da entidade (SAN) no certificado atual.</span><span class="sxs-lookup"><span data-stu-id="98090-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="98090-109">Para exibir o certificado e todos os membros da propriedade, é recomendável usar o snap-in de certificados no <EM>console de gerenciamento Microsoft (MMC)</EM> ou usar o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98090-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="98090-110">No assistente de implantação do Lync Server, você pode usar o assistente de certificado para exibir as propriedades do certificado.</span><span class="sxs-lookup"><span data-stu-id="98090-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="98090-111">Os procedimentos para exibir, solicitar e atribuir um certificado usando o Shell de gerenciamento do Lync Server e o <EM>console de gerenciamento Microsoft (MMC)</EM> são detalhados nos procedimentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="98090-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="98090-112">Para usar o assistente de implantação do Lync Server, consulte os detalhes aqui se você implantou o director opcional ou o pool de directors: <A href="lync-server-2013-configure-certificates-for-the-director.md">configurar certificados para o diretor no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="98090-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="98090-113">Para o servidor front-end ou o pool de front-end, consulte os detalhes aqui: <A href="lync-server-2013-configure-certificates-for-servers.md">configurar certificados para servidores no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="98090-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="98090-114">As etapas iniciais deste procedimento são etapas de preparação, para orientar você sobre qual função os certificados atuais são reproduzidos.</span><span class="sxs-lookup"><span data-stu-id="98090-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="98090-115">Por padrão, os certificados não terão um lyncdiscover. &lt;sipdomain&gt; ou lyncdiscoverinternal. &lt;nome&gt; de domínio interno, a menos que você tenha instalado serviços de mobilidade anteriormente ou prepare seus certificados com antecedência.</span><span class="sxs-lookup"><span data-stu-id="98090-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="98090-116">Este procedimento usa o nome de domínio SIP ' contoso.com ' de exemplo e o nome de domínio interno ' contoso.net '.</span><span class="sxs-lookup"><span data-stu-id="98090-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="98090-117">A configuração de certificado padrão do Lync Server 2013 e do Lync Server 2010 é usar um único certificado (chamado ' default ') com o propósito padrão (para todas as finalidades, exceto para os serviços Web), WebServicesExternal e WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="98090-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="98090-118">Uma configuração opcional é usar certificados separados para cada finalidade.</span><span class="sxs-lookup"><span data-stu-id="98090-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="98090-119">Os certificados podem ser gerenciados usando o Shell de gerenciamento do Lync Server e cmdlets do Windows PowerShell ou usando o assistente de certificado no assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="98090-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="98090-120">Para atualizar certificados com nomes alternativos de novos assuntos usando o Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="98090-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="98090-121">Faça logon no computador usando uma conta que tenha direitos e permissões de administrador local.</span><span class="sxs-lookup"><span data-stu-id="98090-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="98090-122">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="98090-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="98090-123">Descubra quais certificados foram atribuídos ao servidor e para qual tipo de uso.</span><span class="sxs-lookup"><span data-stu-id="98090-123">Find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="98090-124">Você precisará destas informações na etapa seguinte para atribuir o certificado atualizado.</span><span class="sxs-lookup"><span data-stu-id="98090-124">You need this information in the next step to assign the updated certificate.</span></span> <span data-ttu-id="98090-125">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="98090-125">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="98090-126">Examine a saída da etapa anterior para ver se um único certificado está atribuído para vários usos ou se um certificado diferente está atribuído para cada uso.</span><span class="sxs-lookup"><span data-stu-id="98090-126">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="98090-127">Examine o parâmetro use para descobrir como um certificado é usado.</span><span class="sxs-lookup"><span data-stu-id="98090-127">Look in the Use parameter to find out how a certificate is used.</span></span> <span data-ttu-id="98090-128">Compare o parâmetro de impressão digital para os certificados exibidos para ver se o mesmo certificado tem vários usos.</span><span class="sxs-lookup"><span data-stu-id="98090-128">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="98090-129">Atualize o certificado.</span><span class="sxs-lookup"><span data-stu-id="98090-129">Update the certificate.</span></span> <span data-ttu-id="98090-130">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="98090-130">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="98090-131">Por exemplo, se o cmdlet **Get-CsCertificate** tiver exibido um certificado com uso do padrão, outro com um uso de WebServicesInternal e outro com um uso de WebServicesExternal, e todos tiverem o mesmo valor de impressão digital, na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="98090-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="98090-132">\*\*Importante: \*\*</span><span class="sxs-lookup"><span data-stu-id="98090-132">**Important:**</span></span>
    
    <span data-ttu-id="98090-133">Se um certificado separado for atribuído para cada uso (o valor de impressão digital for diferente para cada certificado), é importante que você não execute o cmdlet **set-CsCertificate** com vários tipos.</span><span class="sxs-lookup"><span data-stu-id="98090-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="98090-134">Nesse caso, execute o cmdlet **set-CsCertificate** separadamente para cada uso.</span><span class="sxs-lookup"><span data-stu-id="98090-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="98090-135">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="98090-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="98090-136">Para exibir o certificado, clique em **Iniciar**, clique em **executar..**..</span><span class="sxs-lookup"><span data-stu-id="98090-136">To view the certificate, click **Start**, click **Run…**.</span></span> <span data-ttu-id="98090-137">Digite MMC para abrir o console de gerenciamento Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98090-137">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="98090-138">No menu MMC, selecione **arquivo**, selecione **Adicionar/remover snap-in..**., selecione certificados.</span><span class="sxs-lookup"><span data-stu-id="98090-138">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="98090-139">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="98090-139">Click **Add**.</span></span> <span data-ttu-id="98090-140">Quando solicitado, selecione **conta de computador**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="98090-140">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="98090-141">Se o certificado estiver localizado neste computador, selecione **computador local**.</span><span class="sxs-lookup"><span data-stu-id="98090-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="98090-142">Se o certificado estiver localizado em outro computador, selecione **outro computador**, digite o nome de domínio totalmente qualificado do computador ou clique em **procurar** em **digite o nome do objeto a ser selecionado**, digite o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="98090-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="98090-143">Clique em **verificar nomes**.</span><span class="sxs-lookup"><span data-stu-id="98090-143">Click **Check Names**.</span></span> <span data-ttu-id="98090-144">Quando o nome do computador for resolvido, ele será sublinhado.</span><span class="sxs-lookup"><span data-stu-id="98090-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="98090-145">Clique em **OK**e, em seguida, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="98090-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="98090-146">Clique em **OK** para confirmar a seleção e fechar a caixa de diálogo **Adicionar ou remover snap-ins** .</span><span class="sxs-lookup"><span data-stu-id="98090-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="98090-147">Se o certificado não aparecer no console, verifique se você não selecionou o usuário ou o serviço.</span><span class="sxs-lookup"><span data-stu-id="98090-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="98090-148">Você deve selecionar computador ou não será possível localizar o certificado probper.</span><span class="sxs-lookup"><span data-stu-id="98090-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="98090-149">Para exibir as propriedades do certificado, expanda **certificados**, expanda **pessoal**e selecione **certificados**.</span><span class="sxs-lookup"><span data-stu-id="98090-149">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="98090-150">Selecione o certificado a ser exibido, clique com o botão direito do mouse no certificado e selecione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="98090-150">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="98090-151">No modo de exibição de **certificado** , selecione **detalhes**.</span><span class="sxs-lookup"><span data-stu-id="98090-151">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="98090-152">Aqui, você pode selecionar o nome do assunto do certificado selecionando **assunto** e o nome da entidade atribuída e as propriedades associadas serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="98090-152">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="98090-153">Para exibir os nomes alternativos da entidade atribuída, selecione **nome alternativo do assunto**.</span><span class="sxs-lookup"><span data-stu-id="98090-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="98090-154">Todos os nomes alternativos de assunto atribuídos são exibidos.</span><span class="sxs-lookup"><span data-stu-id="98090-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="98090-155">Os nomes alternativos de entidades encontrados na propriedade são do tipo **DNS Name** por padrão.</span><span class="sxs-lookup"><span data-stu-id="98090-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="98090-156">Você deve ver os membros a seguir (todos eles devem ter nomes de domínio totalmente qualificados, conforme representado nos registros do host DNS (A ou, se IPv6 AAAA):</span><span class="sxs-lookup"><span data-stu-id="98090-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="98090-157">Nome do pool para este pool ou o nome do servidor único se não for um pool</span><span class="sxs-lookup"><span data-stu-id="98090-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="98090-158">Nome do servidor ao qual o certificado está atribuído</span><span class="sxs-lookup"><span data-stu-id="98090-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="98090-159">Registros de URL simples, geralmente se encontram e se interligarem</span><span class="sxs-lookup"><span data-stu-id="98090-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="98090-160">Serviços Web internos e serviços Web nomes externos (por exemplo, webpool01.contoso.net, webpool01.contoso.com), com base nas opções feitas no construtor de topologias e nas seleções de serviços Web do ridden.</span><span class="sxs-lookup"><span data-stu-id="98090-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="98090-161">Se já foi atribuído, o lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<registros\> sipdomain.</span><span class="sxs-lookup"><span data-stu-id="98090-161">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="98090-162">O último item é o que você mais interessa – se houver uma entrada de SAN lyncdiscover e lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="98090-162">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="98090-163">Depois que tiver essas informações, você poderá fechar o modo de exibição de certificado e o MMC.</span><span class="sxs-lookup"><span data-stu-id="98090-163">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="98090-164">Se for um serviço de descoberta automática, ou seja, o lyncdiscover. \>nome\> de domínio e lyncdiscoverinternal. \<nome\> do domínio (com base em se este for um certificado externo ou interno) o nome alternativo do requerente estiver ausente, e você estiver usando um único certificado padrão para os tipos padrão, WebServicesInternal e WebServiceExternal, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="98090-164">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\> (based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="98090-165">No prompt da linha de comando do Shell de gerenciamento do Lync Server Management, digite:</span><span class="sxs-lookup"><span data-stu-id="98090-165">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="98090-166">Se você tiver muitos domínios SIP, não será possível usar o novo parâmetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="98090-166">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="98090-167">Em vez disso, você deve usar o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="98090-167">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="98090-168">Ao usar o parâmetro DomainName, você deve definir o FQDN dos registros lyncdiscoverinternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="98090-168">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="98090-169">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="98090-169">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="98090-170">Para atribuir o certificado, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="98090-170">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="98090-171">Onde "impressão digital" é a impressão digital exibida para o certificado recém emitido.</span><span class="sxs-lookup"><span data-stu-id="98090-171">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="98090-172">Para obter um nome alternativo de assunto da descoberta automática ausente ao usar certificados separados para padrão, WebServicesInternal e WebServicesExternal, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="98090-172">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="98090-173">No prompt da linha de comando do Shell de gerenciamento do Lync Server Management, digite:</span><span class="sxs-lookup"><span data-stu-id="98090-173">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="98090-174">Se você tiver muitos domínios SIP, não será possível usar o novo parâmetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="98090-174">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="98090-175">Em vez disso, você deve usar o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="98090-175">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="98090-176">Ao usar o parâmetro DomainName, você deve usar um prefixo apropriado para o FQDN do domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="98090-176">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="98090-177">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="98090-177">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="98090-178">Para obter um nome alternativo de assunto de descoberta automática externo ausente, na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="98090-178">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="98090-179">Se você tiver muitos domínios SIP, não será possível usar o novo parâmetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="98090-179">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="98090-180">Em vez disso, você deve usar o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="98090-180">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="98090-181">Ao usar o parâmetro DomainName, você deve usar um prefixo apropriado para o FQDN do domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="98090-181">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="98090-182">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="98090-182">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="98090-183">Para atribuir os tipos de certificados individuais, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="98090-183">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="98090-184">Em que "impressão digital" é a impressão digital exibida para os certificados individuais emitidos recentemente.</span><span class="sxs-lookup"><span data-stu-id="98090-184">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

