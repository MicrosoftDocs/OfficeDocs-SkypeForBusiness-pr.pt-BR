---
title: 'Lync Server 2013: modificando certificados para mobilidade'
description: 'Lync Server 2013: modificando certificados para mobilidade.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 099122b1773c3f15d8ae0034ee5fa404225cdfd2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555847"
---
# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="6f313-103">Modificando certificados para mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f313-103">Modifying certificates for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f313-104">_**Última modificação do tópico:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="6f313-104">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="6f313-105">Para dar suporte a conexões seguras entre seu ambiente do Lync e seus clientes móveis, os certificados SSL (Secure Socket Layer) para seu pool de diretores, pool de front-ends e proxy reverso precisarão ser atualizados com algumas entradas adicionais de nome alternativo de entidade (SAN).</span><span class="sxs-lookup"><span data-stu-id="6f313-105">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="6f313-106">Se você precisar fazer o check-out de mais detalhes sobre os requisitos de certificado para mobilidade, confira a seção requisitos de certificado em [requisitos técnicos para mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), mas, basicamente, você precisará obter novos certificados da autoridade de certificação com as entradas San adicionais incluídas e, em seguida, adicionar esses certificados usando as etapas deste artigo.</span><span class="sxs-lookup"><span data-stu-id="6f313-106">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="6f313-107">Naturalmente, antes de começar, é uma boa ideia saber quais nomes alternativos de entidade seus certificados já têm.</span><span class="sxs-lookup"><span data-stu-id="6f313-107">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="6f313-108">Se você não tiver certeza sobre o que já foi configurado, há várias maneiras de descobrir. Enquanto a opção para executar o **Get-CsCertificate** e outros comandos do PowerShell para exibir essas informações, (que percorremos abaixo) por padrão, esses dados serão truncados, portanto, você pode não ver todas as propriedades necessárias.</span><span class="sxs-lookup"><span data-stu-id="6f313-108">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="6f313-109">Para obter uma boa visão do certificado e de todas as suas propriedades, você pode ir para o console de gerenciamento Microsoft (MMC) e carregar o snap-in de certificados (que também percorremos abaixo), ou você pode simplesmente verificar o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f313-109">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="6f313-110">Conforme observado acima, as etapas a seguir vão orientá-lo na atualização dos certificados usando o Shell de gerenciamento do Lync Server e o MMC.</span><span class="sxs-lookup"><span data-stu-id="6f313-110">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="6f313-111">Se você estiver interessado em usar o assistente de certificado no assistente de implantação do Lync Server para isso, você pode verificar [configurar certificados para o diretor no Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) para o diretor ou pool de diretor, se você configurou um (talvez você não tenha).</span><span class="sxs-lookup"><span data-stu-id="6f313-111">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="6f313-112">Para o servidor front-end ou o pool de front-ends, convém ver [configurar certificados para servidores no Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span><span class="sxs-lookup"><span data-stu-id="6f313-112">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="6f313-113">Uma última coisa a ter em mente é que você pode ter um único certificado padrão no seu ambiente do Lync Server 2013 ou pode ter certificados separados para o padrão (que é tudo, exceto os serviços Web), WebServicesExternal e WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="6f313-113">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="6f313-114">Seja qual for a configuração, essas etapas devem ajudá-lo.</span><span class="sxs-lookup"><span data-stu-id="6f313-114">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="6f313-115">Para atualizar certificados com nomes alternativos de novos requerentes usando o Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="6f313-115">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="6f313-116">Você precisa fazer logon no seu servidor do Lync Server 2013 usando uma conta que tenha direitos e permissões de administrador local.</span><span class="sxs-lookup"><span data-stu-id="6f313-116">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="6f313-117">Além disso, se você estiver executando o PowerShell **Request-CsCertificate** nas etapas 12 e posteriores, a conta precisará ter direitos para a CA (autoridade de certificação) especificada.</span><span class="sxs-lookup"><span data-stu-id="6f313-117">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="6f313-118">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6f313-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6f313-119">Antes de poder atribuir um certificado atualizado, você precisará descobrir quais certificados foram atribuídos ao servidor e para qual tipo de uso.</span><span class="sxs-lookup"><span data-stu-id="6f313-119">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="6f313-120">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="6f313-120">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="6f313-121">Revise a saída da etapa anterior para ver se um único certificado foi atribuído para vários usos ou se um certificado diferente foi atribuído para cada uso.</span><span class="sxs-lookup"><span data-stu-id="6f313-121">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="6f313-122">Procure no parâmetro use para descobrir como o certificado está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="6f313-122">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="6f313-123">Compare o parâmetro Thumbprint dos certificados exibidos para ver se o mesmo certificado tem vários usos.</span><span class="sxs-lookup"><span data-stu-id="6f313-123">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="6f313-124">Mantenha seus olhos no parâmetro Thumbprint.</span><span class="sxs-lookup"><span data-stu-id="6f313-124">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="6f313-125">Atualize o certificado.</span><span class="sxs-lookup"><span data-stu-id="6f313-125">Update the certificate.</span></span> <span data-ttu-id="6f313-126">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="6f313-126">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="6f313-127">Por exemplo, se o cmdlet **Get-CsCertificate** exibiu um certificado com o uso de Default, outro com um uso de WebServicesInternal e outro com um uso de WebServicesExternal e todos tinham o mesmo valor de impressão digital, na linha de comando, você deverá digitar:</span><span class="sxs-lookup"><span data-stu-id="6f313-127">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="6f313-128">**Importante:**</span><span class="sxs-lookup"><span data-stu-id="6f313-128">**Important:**</span></span>
    
    <span data-ttu-id="6f313-129">Se um certificado separado for atribuído para cada uso (de modo que o valor de impressão digital que você verificou acima seja diferente para cada certificado), é vital que você **não** execute o cmdlet **set-CsCertificate** com vários tipos, como no exemplo acima.</span><span class="sxs-lookup"><span data-stu-id="6f313-129">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="6f313-130">Nesse caso, execute o cmdlet **Set-CsCertificate** separadamente para cada uso.</span><span class="sxs-lookup"><span data-stu-id="6f313-130">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="6f313-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6f313-131">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="6f313-132">Para exibir o certificado (ou certificados), clique em **Iniciar**, clique em **executar...**.</span><span class="sxs-lookup"><span data-stu-id="6f313-132">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="6f313-133">Digite MMC para abrir o Console de Gerenciamento Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6f313-133">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="6f313-134">No menu do MMC, selecione **Arquivo**, selecione**Adicionar/Remover snap-in…**, selecione Certificados.</span><span class="sxs-lookup"><span data-stu-id="6f313-134">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="6f313-135">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6f313-135">Click **Add**.</span></span> <span data-ttu-id="6f313-136">Quando lhe for solicitado, selecione **Conta do computador** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6f313-136">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="6f313-137">Se este for o servidor onde o certificado está localizado, selecione **computador local**.</span><span class="sxs-lookup"><span data-stu-id="6f313-137">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="6f313-138">Se o certificado estiver localizado em outro computador, selecione **outro computador**e, em seguida, digite o nome de domínio totalmente qualificado do computador ou clique em **procurar** em **Insira o nome do objeto a ser selecionado**e digite o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="6f313-138">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="6f313-139">Clique em **Verificar Nomes**.</span><span class="sxs-lookup"><span data-stu-id="6f313-139">Click **Check Names**.</span></span> <span data-ttu-id="6f313-140">Quando o nome do computador resolver, ele será sublinhado.</span><span class="sxs-lookup"><span data-stu-id="6f313-140">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="6f313-141">Clique em **OK**e em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="6f313-141">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="6f313-142">Clique em **OK** para confirmar a seleção e fechar a caixa de diálogo **Adicionar ou remover snap-ins** .</span><span class="sxs-lookup"><span data-stu-id="6f313-142">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="6f313-p113">Para exibir as propriedades do certificado, expanda **Certificados**, expanda **Pessoal** e selecione **Certificados**. Selecione o certificado para exibição, clique com o botão direito do mouse em certificado e selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="6f313-p113">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="6f313-p114">Na exibição **Certificado**, selecione **Detalhes**. Aqui, você pode escolher o nome da entidade do certificado ao selecionar **Assunto** e o nome da entidade atribuída e as propriedades atribuídas serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="6f313-p114">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="6f313-147">Para exibir os nomes alternativos de entidades atribuídos, selecione**Nome Alternativo de Entidade**.</span><span class="sxs-lookup"><span data-stu-id="6f313-147">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="6f313-148">Todos os nomes alternativos de entidade atribuídos são exibidos aqui.</span><span class="sxs-lookup"><span data-stu-id="6f313-148">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="6f313-149">Os nomes alternativos da entidade encontrados aqui são do tipo **nome DNS** por padrão.</span><span class="sxs-lookup"><span data-stu-id="6f313-149">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="6f313-150">Você deve ver os seguintes membros (todos deveriam ser nomes de domínio completamente qualificados) como representado nos registros de host DNS (A ou, se IPv6, AAAA):</span><span class="sxs-lookup"><span data-stu-id="6f313-150">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="6f313-151">Nome do pool para este pool ou o nome do servidor único se não for um pool</span><span class="sxs-lookup"><span data-stu-id="6f313-151">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="6f313-152">Nome do servidor ao qual o certificado está atribuído</span><span class="sxs-lookup"><span data-stu-id="6f313-152">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="6f313-153">Registros de URL Simples, normalmente reunir e discar</span><span class="sxs-lookup"><span data-stu-id="6f313-153">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="6f313-154">Nomes internos e externos de serviços Web (por exemplo, webpool01.contoso.net, webpool01.contoso.com), com base nas escolhas feitas no construtor de topologias e nas seleções de serviços Web do nas.</span><span class="sxs-lookup"><span data-stu-id="6f313-154">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="6f313-155">Se já tiver sido atribuído, o lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="6f313-155">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="6f313-156">e lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="6f313-156">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="6f313-157">relatórios.</span><span class="sxs-lookup"><span data-stu-id="6f313-157">records.</span></span>
    
    <span data-ttu-id="6f313-158">O último item é o que você está mais interessado, se houver uma entrada de SAN do lyncdiscover e do lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="6f313-158">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="6f313-159">Repita essas etapas se você tiver vários certificados para verificar.</span><span class="sxs-lookup"><span data-stu-id="6f313-159">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="6f313-160">Assim que obtiver essa informação, você pode fechar o certificado exibido e o MMC.</span><span class="sxs-lookup"><span data-stu-id="6f313-160">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="6f313-161">Se um nome alternativo de entidade do serviço Descoberta Automática estiver ausente, e você está usando um certificado Padrão para os tipos Padrão, WebServicesInternal e WebServiceExternal, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6f313-161">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="6f313-162">No prompt da linha de comando do Shell de gerenciamento do Lync Server, digite:</span><span class="sxs-lookup"><span data-stu-id="6f313-162">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="6f313-163">Se você tiver vários domínios SIP, não poderá usar o novo parâmetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="6f313-163">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="6f313-164">Em vez disso, você precisa usar o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="6f313-164">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="6f313-165">Quando você usa o parâmetro DomainName, você precisa definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="6f313-165">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="6f313-166">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6f313-166">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="6f313-167">Para atribuir o certificado, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6f313-167">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="6f313-168">Onde “Thumbprint” é o thumbprint exibido para o novo certificado emitido.</span><span class="sxs-lookup"><span data-stu-id="6f313-168">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="6f313-169">Para uma SAN interna de descoberta automática ausente ao usar certificados separados para padrão, WebServicesInternal e WebServicesExternal, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6f313-169">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="6f313-170">No prompt da linha de comando do Shell de gerenciamento do Lync Server, digite:</span><span class="sxs-lookup"><span data-stu-id="6f313-170">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="6f313-171">Se você tiver vários domínios SIP, não poderá usar o novo parâmetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="6f313-171">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="6f313-172">Em vez disso, você precisa usar o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="6f313-172">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="6f313-173">Quando você usa o parâmetro DomainName, você precisa usar um prefixo apropriado para o FQDN do domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="6f313-173">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="6f313-174">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6f313-174">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="6f313-175">Para obter um nome alternativo da entidade de Descoberta Automática externo, digite na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="6f313-175">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="6f313-176">Se você tiver vários domínios SIP, não poderá usar o novo parâmetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="6f313-176">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="6f313-177">Em vez disso, você precisa usar o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="6f313-177">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="6f313-178">Quando você usa o parâmetro DomainName, você precisa usar um prefixo apropriado para o FQDN do domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="6f313-178">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="6f313-179">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6f313-179">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="6f313-180">Para atribuir os tipos de certificados individuais, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6f313-180">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="6f313-181">Onde “Thumbprint” é o thumbprint exibido para os novos certificados individuais emitidos.</span><span class="sxs-lookup"><span data-stu-id="6f313-181">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6f313-182">Apenas para observar, as etapas 12 e 13 devem ser executadas somente se a conta que a executa tiver acesso à autoridade de certificação com as permissões apropriadas.</span><span class="sxs-lookup"><span data-stu-id="6f313-182">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="6f313-183">Se você não conseguir fazer logon com uma conta que tenha essas permissões ou se estiver usando uma autoridade de certificação pública ou remota para seus certificados, precisará solicitá-las por meio do assistente de implantação do Lync Server, que foi tocado na parte superior do artigo.</span><span class="sxs-lookup"><span data-stu-id="6f313-183">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

