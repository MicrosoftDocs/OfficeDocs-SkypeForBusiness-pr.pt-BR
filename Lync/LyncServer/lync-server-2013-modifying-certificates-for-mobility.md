---
title: 'Lync Server 2013: Modificando certificados para mobilidade'
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
ms.openlocfilehash: 150dc8c7b4021e1e2c7ccab6ccc71823c01c388e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="daf7d-102">Modificando certificados para mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daf7d-102">Modifying certificates for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="daf7d-103">_**Tópico da última modificação:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="daf7d-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="daf7d-104">Para dar suporte a conexões seguras entre seu ambiente do Lync e seus clientes móveis, os certificados SSL (Secure Socket Layer) para seu pool de diretor, pool de front-end e proxy reverso precisarão ser atualizados com alguns nomes alternativos adicionais para o assunto ( SAN).</span><span class="sxs-lookup"><span data-stu-id="daf7d-104">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="daf7d-105">Se você precisar conferir mais detalhes sobre os requisitos de certificado para mobilidade, consulte a seção requisitos de certificado em [requisitos técnicos para mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), mas basicamente precisará obter novos certificados da autoridade de certificação com as entradas San adicionais incluídas e adicionar esses certificados usando as etapas deste artigo.</span><span class="sxs-lookup"><span data-stu-id="daf7d-105">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="daf7d-106">É claro que antes de começar, é uma boa ideia saber quais são os nomes alternativos de assunto que seus certificados já possuem.</span><span class="sxs-lookup"><span data-stu-id="daf7d-106">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="daf7d-107">Se você não tiver certeza de que já foi configurado, há várias maneiras de descobrir. Embora a opção de executar o **Get-CsCertificate** e outros comandos do PowerShell para exibir essas informações (que mostramos abaixo) por padrão, os dados serão truncados, portanto, você pode não conseguir ver todas as propriedades necessárias.</span><span class="sxs-lookup"><span data-stu-id="daf7d-107">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="daf7d-108">Para obter uma boa visão do certificado e de todas as suas propriedades, você pode ir para o console de gerenciamento Microsoft (MMC) e carregar o snap-in de certificados (que também percorremos abaixo), ou você pode simplesmente verificar o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="daf7d-108">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="daf7d-109">Conforme observado acima, as etapas a seguir vão orientá-lo na atualização dos certificados usando o Shell de gerenciamento do Lync Server e o MMC.</span><span class="sxs-lookup"><span data-stu-id="daf7d-109">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="daf7d-110">Se você tiver interesse em usar o assistente de certificado no assistente de implantação do Lync Server para isso, poderá verificar a opção [configurar certificados para o diretor no Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) para o diretor ou o pool do diretor, se você configurou um (você pode não ter).</span><span class="sxs-lookup"><span data-stu-id="daf7d-110">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="daf7d-111">Para o servidor front-end ou o pool de front-end, convém ver [configurar certificados para servidores no Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span><span class="sxs-lookup"><span data-stu-id="daf7d-111">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="daf7d-112">Uma última coisa a ter em mente é que você pode ter um único certificado padrão em seu ambiente do Lync Server 2013 ou pode ter certificados separados para o padrão (que é tudo, exceto os serviços Web), WebServicesExternal e WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="daf7d-112">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="daf7d-113">Seja qual for a sua configuração, essas etapas devem ajudá-lo.</span><span class="sxs-lookup"><span data-stu-id="daf7d-113">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="daf7d-114">Para atualizar certificados com nomes alternativos de novos assuntos usando o Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="daf7d-114">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="daf7d-115">Você precisa fazer logon no seu servidor do Lync Server 2013 usando uma conta com direitos e permissões de administrador local.</span><span class="sxs-lookup"><span data-stu-id="daf7d-115">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="daf7d-116">Além disso, se você estiver executando o **CsCertificate de solicitação** do PowerShell nas etapas 12 e posteriores, a conta precisará ter direitos para a autoridade de certificação (CA) especificada.</span><span class="sxs-lookup"><span data-stu-id="daf7d-116">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="daf7d-117">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="daf7d-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="daf7d-118">Antes de poder atribuir um certificado atualizado, você precisará descobrir quais certificados foram atribuídos ao servidor e para qual tipo de uso.</span><span class="sxs-lookup"><span data-stu-id="daf7d-118">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="daf7d-119">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="daf7d-119">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="daf7d-120">Examine a saída da etapa anterior para ver se um único certificado foi atribuído para vários usos ou se um certificado diferente está atribuído para cada uso.</span><span class="sxs-lookup"><span data-stu-id="daf7d-120">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="daf7d-121">Examine o parâmetro use para descobrir como um certificado está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="daf7d-121">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="daf7d-122">Compare o parâmetro de impressão digital para os certificados exibidos para ver se o mesmo certificado tem vários usos.</span><span class="sxs-lookup"><span data-stu-id="daf7d-122">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="daf7d-123">Fique de olho no parâmetro impressão digital.</span><span class="sxs-lookup"><span data-stu-id="daf7d-123">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="daf7d-124">Atualize o certificado.</span><span class="sxs-lookup"><span data-stu-id="daf7d-124">Update the certificate.</span></span> <span data-ttu-id="daf7d-125">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="daf7d-125">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="daf7d-126">Por exemplo, se o cmdlet **Get-CsCertificate** tiver exibido um certificado com uso do padrão, outro com um uso de WebServicesInternal e outro com um uso de WebServicesExternal, e todos tivessem o mesmo valor de impressão digital, na linha de comando, você deve digitar:</span><span class="sxs-lookup"><span data-stu-id="daf7d-126">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="daf7d-127">\*\*Importante: \*\*</span><span class="sxs-lookup"><span data-stu-id="daf7d-127">**Important:**</span></span>
    
    <span data-ttu-id="daf7d-128">Se um certificado separado for atribuído para cada uso (para que o valor de impressão digital que você verificou acima seja diferente para cada certificado), é fundamental que você **não** execute o cmdlet **set-CsCertificate** com vários tipos, como no exemplo acima.</span><span class="sxs-lookup"><span data-stu-id="daf7d-128">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="daf7d-129">Nesse caso, execute o cmdlet **set-CsCertificate** separadamente para cada uso.</span><span class="sxs-lookup"><span data-stu-id="daf7d-129">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="daf7d-130">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="daf7d-130">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="daf7d-131">Para exibir o certificado (ou certificados), clique em **Iniciar**, clique em **executar...**.</span><span class="sxs-lookup"><span data-stu-id="daf7d-131">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="daf7d-132">Digite MMC para abrir o console de gerenciamento Microsoft.</span><span class="sxs-lookup"><span data-stu-id="daf7d-132">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="daf7d-133">No menu MMC, selecione **arquivo**, selecione **Adicionar/remover snap-in..**., selecione certificados.</span><span class="sxs-lookup"><span data-stu-id="daf7d-133">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="daf7d-134">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="daf7d-134">Click **Add**.</span></span> <span data-ttu-id="daf7d-135">Quando solicitado, selecione **conta de computador**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="daf7d-135">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="daf7d-136">Se este for o servidor em que o certificado está localizado, selecione **computador local**.</span><span class="sxs-lookup"><span data-stu-id="daf7d-136">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="daf7d-137">Se o certificado estiver localizado em outro computador, você deve selecionar **outro computador**e, em seguida, pode digitar o nome de domínio totalmente qualificado do computador ou clicar em **procurar** , em **digite o nome do objeto a ser selecionado**e digitar o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="daf7d-137">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="daf7d-138">Clique em **verificar nomes**.</span><span class="sxs-lookup"><span data-stu-id="daf7d-138">Click **Check Names**.</span></span> <span data-ttu-id="daf7d-139">Quando o nome do computador resolver, ele estará sublinhado.</span><span class="sxs-lookup"><span data-stu-id="daf7d-139">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="daf7d-140">Clique em **OK**e, em seguida, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="daf7d-140">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="daf7d-141">Clique em **OK** para confirmar a seleção e fechar a caixa de diálogo **Adicionar ou remover snap-ins** .</span><span class="sxs-lookup"><span data-stu-id="daf7d-141">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="daf7d-142">Para exibir as propriedades do certificado, expanda **certificados**, expanda **pessoal**e selecione **certificados**.</span><span class="sxs-lookup"><span data-stu-id="daf7d-142">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="daf7d-143">Selecione o certificado a ser exibido, clique com o botão direito do mouse no certificado e selecione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="daf7d-143">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="daf7d-144">No modo de exibição de **certificado** , selecione **detalhes**.</span><span class="sxs-lookup"><span data-stu-id="daf7d-144">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="daf7d-145">Aqui, você pode selecionar o nome do assunto do certificado selecionando **assunto** e o nome da entidade atribuída e as propriedades associadas serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="daf7d-145">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="daf7d-146">Para exibir os nomes alternativos da entidade atribuída, selecione **nome alternativo do assunto**.</span><span class="sxs-lookup"><span data-stu-id="daf7d-146">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="daf7d-147">Todos os nomes alternativos de assunto atribuídos são exibidos aqui.</span><span class="sxs-lookup"><span data-stu-id="daf7d-147">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="daf7d-148">Os nomes alternativos de entidades encontrados aqui são do tipo **DNS Name** por padrão.</span><span class="sxs-lookup"><span data-stu-id="daf7d-148">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="daf7d-149">Você deve ver os membros a seguir (todos eles devem ter nomes de domínio totalmente qualificados, conforme representado nos registros do host DNS (A ou, se IPv6 AAAA):</span><span class="sxs-lookup"><span data-stu-id="daf7d-149">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="daf7d-150">Nome do pool para este pool ou o nome do servidor único se não for um pool</span><span class="sxs-lookup"><span data-stu-id="daf7d-150">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="daf7d-151">Nome do servidor ao qual o certificado está atribuído</span><span class="sxs-lookup"><span data-stu-id="daf7d-151">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="daf7d-152">Registros de URL simples, geralmente se encontram e se interligarem</span><span class="sxs-lookup"><span data-stu-id="daf7d-152">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="daf7d-153">Serviços Web internos e serviços Web nomes externos (por exemplo, webpool01.contoso.net, webpool01.contoso.com), com base nas opções feitas no construtor de topologias e nas seleções de serviços Web do ridden.</span><span class="sxs-lookup"><span data-stu-id="daf7d-153">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="daf7d-154">Se já foi atribuído, o lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<registros\> sipdomain.</span><span class="sxs-lookup"><span data-stu-id="daf7d-154">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="daf7d-155">O último item é o que você está mais interessado – se houver uma entrada de SAN lyncdiscover e lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="daf7d-155">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="daf7d-156">Repita essas etapas se você tiver vários certificados para verificar.</span><span class="sxs-lookup"><span data-stu-id="daf7d-156">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="daf7d-157">Depois que tiver essas informações, você poderá fechar o modo de exibição de certificado e o MMC.</span><span class="sxs-lookup"><span data-stu-id="daf7d-157">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="daf7d-158">Se um nome alternativo de requerente do serviço de descoberta automática estiver ausente, e você estiver usando um único certificado padrão para os tipos padrão, WebServicesInternal e WebServiceExternal, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="daf7d-158">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="daf7d-159">No prompt da linha de comando do Shell de gerenciamento do Lync Server Management, digite:</span><span class="sxs-lookup"><span data-stu-id="daf7d-159">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="daf7d-160">Se você tiver muitos domínios SIP, não poderá usar o novo parâmetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="daf7d-160">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="daf7d-161">Em vez disso, você precisa usar o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="daf7d-161">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="daf7d-162">Ao usar o parâmetro DomainName, você precisa definir o FQDN dos registros lyncdiscoverinternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="daf7d-162">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="daf7d-163">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="daf7d-163">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="daf7d-164">Para atribuir o certificado, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="daf7d-164">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="daf7d-165">Onde "impressão digital" é a impressão digital exibida para o certificado recém emitido.</span><span class="sxs-lookup"><span data-stu-id="daf7d-165">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="daf7d-166">Para obter uma SAN de descoberta automática interna ausente ao usar certificados separados para padrão, WebServicesInternal e WebServicesExternal, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="daf7d-166">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="daf7d-167">No prompt da linha de comando do Shell de gerenciamento do Lync Server Management, digite:</span><span class="sxs-lookup"><span data-stu-id="daf7d-167">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="daf7d-168">Se você tiver muitos domínios SIP, não poderá usar o novo parâmetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="daf7d-168">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="daf7d-169">Em vez disso, você precisa usar o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="daf7d-169">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="daf7d-170">Ao usar o parâmetro DomainName, você precisa usar um prefixo apropriado para o FQDN do domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="daf7d-170">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="daf7d-171">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="daf7d-171">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="daf7d-172">Para obter um nome alternativo de assunto de descoberta automática externo ausente, na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="daf7d-172">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="daf7d-173">Se você tiver muitos domínios SIP, não poderá usar o novo parâmetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="daf7d-173">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="daf7d-174">Em vez disso, você precisa usar o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="daf7d-174">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="daf7d-175">Ao usar o parâmetro DomainName, você precisa usar um prefixo apropriado para o FQDN do domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="daf7d-175">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="daf7d-176">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="daf7d-176">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="daf7d-177">Para atribuir os tipos de certificados individuais, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="daf7d-177">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="daf7d-178">Em que "impressão digital" é a impressão digital exibida para os certificados individuais emitidos recentemente.</span><span class="sxs-lookup"><span data-stu-id="daf7d-178">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="daf7d-179">Só para observar, as etapas 12 e 13 devem ser executadas somente se a conta que a executa tiver acesso à autoridade de certificação com as permissões apropriadas.</span><span class="sxs-lookup"><span data-stu-id="daf7d-179">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="daf7d-180">Se não for possível fazer logon com uma conta que tenha essas permissões ou se você estiver usando uma autoridade de certificação pública ou remota para seus certificados, você precisará solicitá-las por meio do assistente de implantação do Lync Server, que foi tocado na parte superior da correspondente.</span><span class="sxs-lookup"><span data-stu-id="daf7d-180">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

