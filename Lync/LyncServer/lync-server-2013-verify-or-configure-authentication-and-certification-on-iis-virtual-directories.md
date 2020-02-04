---
title: 'Lync Server 2013: Verificar ou configurar autenticação e certificação nos diretórios virtuais de IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48399ed2a6eba53707218295adcd1cbd11a5e32c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="fd427-102">Verificar ou configurar autenticação e certificação nos diretórios virtuais de IIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd427-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd427-103">_**Tópico da última modificação:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="fd427-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="fd427-104">Use o procedimento a seguir para configurar o certificado nos diretórios virtuais dos serviços de informações da Internet (IIS) ou verificar se o certificado está configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="fd427-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="fd427-105">Execute o procedimento a seguir em cada servidor que executa o IIS em seu pool interno do Lync Server e no director opcional. ou servidores do pool do diretor.</span><span class="sxs-lookup"><span data-stu-id="fd427-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd427-106">O procedimento a seguir define um procedimento para solicitar um certificado combinado que é usado para todas as finalidades do Lync Server, site interno e site externo no IIS.</span><span class="sxs-lookup"><span data-stu-id="fd427-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="fd427-107">O Lync Server 2010 introduziu um conjunto de cmdlets&nbsp;do shell do shell do Shell de gerenciamento do Lync Server para a finalidade expressa de gerenciamento de solicitação, importação e atribuição de certificado.</span><span class="sxs-lookup"><span data-stu-id="fd427-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="fd427-108">O procedimento pressupõe que há uma autoridade de certificação (CA) implantada internamente que pode processar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="fd427-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="fd427-109">Se você usar certificados públicos para fins do Lync Server ou a autoridade de certificação exigir uma solicitação offline, consulte a sintaxe detalhada neste tópico para obter informações sobre o parâmetro – output.</span><span class="sxs-lookup"><span data-stu-id="fd427-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="fd427-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Solicitação-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="fd427-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="fd427-111">Para configurar a autenticação e certificados em diretórios virtuais do IIS</span><span class="sxs-lookup"><span data-stu-id="fd427-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="fd427-112">Para concluir com êxito o seguinte, você deve estar conectado ao computador (servidor front-end ou diretor) em que os serviços Web estão instalados e ser um administrador local.</span><span class="sxs-lookup"><span data-stu-id="fd427-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="fd427-113">Você deve ter as permissões de **leitura** e **registro** na autoridade de certificação da qual você solicitará certificados, se a autoridade de certificação for a autoridade de certificação da sua organização.</span><span class="sxs-lookup"><span data-stu-id="fd427-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="fd427-114">Você não precisa de permissões para a autoridade de certificação se você irá configurar e enviar uma solicitação de certificado offline.</span><span class="sxs-lookup"><span data-stu-id="fd427-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="fd427-115">Clique em **Iniciar**, selecione **todos os programas**, selecione **Ferramentas administrativas**e clique em **Gerenciador dos serviços de informações da Internet (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="fd427-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="fd427-116">No **Gerenciador dos serviços de informações da Internet (IIS)**, selecione **nomedoservidor**.</span><span class="sxs-lookup"><span data-stu-id="fd427-116">In **Internet Information Services (IIS) Manager**, select **ServerName**.</span></span> <span data-ttu-id="fd427-117">No **modo de exibição recursos**, selecione **certificados de servidor**, clique com o botão direito do mouse e selecione **abrir recurso**.</span><span class="sxs-lookup"><span data-stu-id="fd427-117">In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="fd427-118">No modo de exibição de recursos de certificados do servidor, se houver certificados atribuídos ao servidor, eles serão exibidos aqui.</span><span class="sxs-lookup"><span data-stu-id="fd427-118">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here.</span></span> <span data-ttu-id="fd427-119">Se houver um certificado que corresponda aos requisitos do site externo no IIS, você poderá reutilizar esse certificado.</span><span class="sxs-lookup"><span data-stu-id="fd427-119">If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate.</span></span> <span data-ttu-id="fd427-120">Para exibir um certificado, clique com o botão direito do mouse no certificado e selecione <STRONG>Exibir...</STRONG></span><span class="sxs-lookup"><span data-stu-id="fd427-120">To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="fd427-121">No servidor ou diretor de front-end para o qual você está solicitando o certificado, clique em **Iniciar**, selecione **todos os programas**, selecione **Microsoft Lync Server 2013**e clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fd427-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="fd427-122">No Shell de gerenciamento do Lync Server, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fd427-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="fd427-123">A saída é uma lista dos certificados que estão atualmente no servidor no repositório de certificados do computador pessoal.</span><span class="sxs-lookup"><span data-stu-id="fd427-123">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store.</span></span> <span data-ttu-id="fd427-124">Observe que, no certificado combinado (ou seja, em que o padrão, os serviços Web internos e os serviços Web externos estão usando o mesmo certificado), você verá que a propriedade use será preenchida com default, WebServicesInternal e WebServicesExternal.</span><span class="sxs-lookup"><span data-stu-id="fd427-124">Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal.</span></span> <span data-ttu-id="fd427-125">Além disso, a propriedade Thumbprint será a mesma para cada um dos tipos de uso.</span><span class="sxs-lookup"><span data-stu-id="fd427-125">Also, the Thumbprint property will be the same for each of the Use types.</span></span> <span data-ttu-id="fd427-126">Um exemplo de saída de Get-CsCertificate é mostrado neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="fd427-126">An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="fd427-127">![Informações de Get-CsCertificate sobre o status atual do scert](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Informações de Get-CsCertificate sobre o status atual do scert")</span><span class="sxs-lookup"><span data-stu-id="fd427-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="fd427-128">No Shell de gerenciamento do Lync Server, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fd427-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="fd427-129">Onde o comando completo seria exibido, como exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="fd427-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="fd427-130">Por padrão, a solicitação-CsCertificate preencherá o nome do requerente com o nome do servidor ou do pool e preencherá as entradas no nome alternativo do requerente com o FQDN do servidor, FQDN do pool, FQDNs de URL simples e FQDNs de serviços Web internos e externos.</span><span class="sxs-lookup"><span data-stu-id="fd427-130">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs.</span></span> <span data-ttu-id="fd427-131">Isso faz referência ao documento de topologia na sua implantação.</span><span class="sxs-lookup"><span data-stu-id="fd427-131">It does this by referencing to the topology document in your deployment.</span></span> <span data-ttu-id="fd427-132">Se houver um valor ausente e você tiver especificado o parâmetro – Verbose, você será notificado de que os valores calculados e reais para nomes alternativos são diferentes, mas ele não informa quais valores estão ausentes.</span><span class="sxs-lookup"><span data-stu-id="fd427-132">If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing.</span></span> <span data-ttu-id="fd427-133">Ele fornece o valor total calculado que o cmdlet referencia.</span><span class="sxs-lookup"><span data-stu-id="fd427-133">It does supply you with the entire computed value that the cmdlet references.</span></span> <span data-ttu-id="fd427-134">Use a cadeia de caracteres de nomes alternativos calculados na saída para resolicitar um novo certificado que incluirá todos os valores.</span><span class="sxs-lookup"><span data-stu-id="fd427-134">Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="fd427-135">![Saída da solicitação de certificado usando Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Saída da solicitação de certificado usando Request-CsCertifica")</span><span class="sxs-lookup"><span data-stu-id="fd427-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="fd427-136">No Shell de gerenciamento do Lync Server, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fd427-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="fd427-137">Onde o comando completo seria exibido, como exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="fd427-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="fd427-138">A saída do cmdlet Set-CsCertificate mostrará que o mesmo certificado (identificado pela impressão digital do certificado) é atribuído para o uso padrão, WebServicesExternal e WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="fd427-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="fd427-139">![Saída de Set-CsCertificate no IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Saída de Set-CsCertificate no IIS WebExt")</span><span class="sxs-lookup"><span data-stu-id="fd427-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="fd427-140">Para verificar ou configurar a autenticação e os certificados nos diretórios virtuais do IIS</span><span class="sxs-lookup"><span data-stu-id="fd427-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="fd427-141">Clique em **Iniciar**, selecione **todos os programas**, selecione **Ferramentas administrativas**e clique em **Gerenciador dos serviços de informações da Internet (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="fd427-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="fd427-142">No **Gerenciador dos serviços de informações da Internet (IIS)**, expanda **ServerName**e, em seguida, expanda **sites**.</span><span class="sxs-lookup"><span data-stu-id="fd427-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="fd427-143">Clique com o botão direito do mouse **no site externo do Lync Server**e clique em **Editar associações**</span><span class="sxs-lookup"><span data-stu-id="fd427-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="fd427-144">Verifique se HTTPS está associado à porta 4443 e clique em **https**.</span><span class="sxs-lookup"><span data-stu-id="fd427-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="fd427-145">Selecione a entrada HTTPS, clique em **Editar**e verifique se o Lync Server WebServicesExternalCertificate está associado a esse protocolo.</span><span class="sxs-lookup"><span data-stu-id="fd427-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="fd427-146">Compare a impressão digital do cmdlet Set-CsCertificate para garantir que o certificado esperado seja corretamente associado à associação HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fd427-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fd427-147">Confira também</span><span class="sxs-lookup"><span data-stu-id="fd427-147">See Also</span></span>


[<span data-ttu-id="fd427-148">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="fd427-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="fd427-149">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="fd427-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

