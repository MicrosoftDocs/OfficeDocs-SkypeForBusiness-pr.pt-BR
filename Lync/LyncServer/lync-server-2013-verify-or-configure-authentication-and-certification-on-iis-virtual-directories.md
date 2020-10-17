---
title: 'Lync Server 2013: verificar ou configurar autenticação e certificação nos diretórios virtuais do IIS'
description: 'Lync Server 2013: verificar ou configurar autenticação e certificação nos diretórios virtuais do IIS.'
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
ms.openlocfilehash: 5e4d583eda7f0c7fb32b51dd5df6eb48af9b20d9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560207"
---
# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="20fb7-103">Verificar ou configurar a autenticação e certificação nos diretórios virtuais do IIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20fb7-103">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20fb7-104">_**Última modificação do tópico:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="20fb7-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="20fb7-105">Use o procedimento a seguir para configurar o certificado nos diretórios virtuais dos serviços de informações da Internet (IIS) ou verificar se o certificado está configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="20fb7-105">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="20fb7-106">Execute o procedimento a seguir em cada servidor que executa o IIS em seu pool do Lync Server interno e no diretor opcional ou servidores do pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="20fb7-106">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20fb7-107">O procedimento a seguir define um procedimento para solicitar um certificado combinado que é usado para todas as finalidades do Lync Server, site interno e site externo no IIS.</span><span class="sxs-lookup"><span data-stu-id="20fb7-107">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="20fb7-108">O Lync Server 2010 introduziu um conjunto de cmdlets do Windows PowerShell do Shell de gerenciamento do Lync Server &nbsp; para o propósito expresso de gerenciamento de solicitação de certificado, importação e atribuição.</span><span class="sxs-lookup"><span data-stu-id="20fb7-108">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="20fb7-109">O procedimento assume que há uma autoridade de certificação (CA) implantada internamente que pode processar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="20fb7-109">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="20fb7-110">Se você usar certificados públicos para fins do Lync Server ou sua autoridade de certificação exigir uma solicitação offline, consulte a sintaxe detalhada neste tópico para obter informações sobre o parâmetro – output.</span><span class="sxs-lookup"><span data-stu-id="20fb7-110">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="20fb7-111"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="20fb7-111"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="20fb7-112">Para configurar autenticação e certificados em diretórios virtuais de ISS</span><span class="sxs-lookup"><span data-stu-id="20fb7-112">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="20fb7-113">Para concluir com êxito o seguinte, você deve estar conectado ao computador (servidor de front-end ou diretor) onde os serviços Web estão instalados e ser um administrador local.</span><span class="sxs-lookup"><span data-stu-id="20fb7-113">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="20fb7-114">Você deve ter as permissões de **leitura** e **registrar** na autoridade de certificação que você estará solicitando certificados, caso a autoridade de certificação seja a sua organização.</span><span class="sxs-lookup"><span data-stu-id="20fb7-114">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="20fb7-115">Você não precisa de permissões da autoridade de certificação se for configurar e enviar solicitações de certificado offline.</span><span class="sxs-lookup"><span data-stu-id="20fb7-115">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="20fb7-116">Clique em **Iniciar**, selecione **Todos os programas**, selecione **Ferramentas administrativas** e, então, clique em **Gerenciador do Serviços de Informações da Internet (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="20fb7-116">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="20fb7-p104">Em **Gerenciador do Serviços de Informações da Internet (IIS)**, selecione **ServerName**. Em **Exibição de recursos**, selecione **Certificados do servidor**, clique com o botão direito e selecione **Abrir recurso**.</span><span class="sxs-lookup"><span data-stu-id="20fb7-p104">In **Internet Information Services (IIS) Manager**, select **ServerName**. In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="20fb7-p105">Na Exibição de recursos dos Certificados do servidor, caso haja certificados atribuídos ao servidor, eles aparecerão aí. Caso exista um certificado que corresponda aos requisitos para o External Web Site no IIS, você pode reutilizar tal certificado. Para visualizar um certificado, clique com o botão direito no certificado e selecione <STRONG>Visualizar…</STRONG></span><span class="sxs-lookup"><span data-stu-id="20fb7-p105">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here. If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate. To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="20fb7-122">No servidor de front-ends ou diretor que você está solicitando o certificado, clique em **Iniciar**, selecione **todos os programas**, selecione **Microsoft Lync Server 2013**e clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="20fb7-122">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="20fb7-123">No Shell de gerenciamento do Lync Server, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="20fb7-123">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="20fb7-p106">A saída é uma lista dos certificados que estão atualmente no servidor, no repositório de certificados do Pessoal do Computador. Observe que, no certificado combinado (isto é, onde por padrão os serviços da web internos e externos estão utilizando o mesmo certificado), você verá que a propriedade Uso estará populado com Padrão, WebServicesInternal and WebServicesExternal. Além disso, a propriedade Thumbprint será a mesma para cada um dos tipos de Uso. Um exemplo de saída de Get-CsCertificate é exibido neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="20fb7-p106">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store. Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal. Also, the Thumbprint property will be the same for each of the Use types. An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="20fb7-128">![Get-CsCertificate informações sobre o status atual do scert](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Informações de Get-CsCertificate sobre o status atual do scert")</span><span class="sxs-lookup"><span data-stu-id="20fb7-128">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="20fb7-129">No Shell de gerenciamento do Lync Server, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="20fb7-129">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="20fb7-130">Onde o comando completo se parecerá com o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="20fb7-130">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="20fb7-p107">Por padrão, o Request-CsCertificate irá popular o nome da entidade com o nome do pool ou servidor e irá popular entradas no nome de entidade alternativo com o servidor FQDN, o pool FQDN, Simple URL FQDNs e serviços da web internos e externos FQDNs. Isso é feito ao referenciar ao documento de topologia na sua implantação. Caso exista um valor faltando e você tenha especificado o parâmetro –Verbose, você será notificado de que os valores atuais e computados para os nomes alternativos são diferentes, mas não informará qual valor está faltando. É fornecido apenas o valor computado completo que o cmdlet referencia. Utilize a string de nomes alternativos computados na saída para solicitar novamente um novo certificado que incluirá todos os valores.</span><span class="sxs-lookup"><span data-stu-id="20fb7-p107">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs. It does this by referencing to the topology document in your deployment. If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing. It does supply you with the entire computed value that the cmdlet references. Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="20fb7-136">![Saída da solicitação de CERT usando Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Saída da solicitação de certificado usando Request-CsCertifica")</span><span class="sxs-lookup"><span data-stu-id="20fb7-136">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="20fb7-137">No Shell de gerenciamento do Lync Server, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="20fb7-137">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="20fb7-138">Onde o comando completo se parecerá com o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="20fb7-138">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="20fb7-139">A saída do cmdlet Set-CsCertificate mostrará que o mesmo certificado (identificado pelo thumbprint do certificado) é atribuído para utilização Padrão, WebServicesExternal e WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="20fb7-139">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="20fb7-140">![Saída de Set-CsCertificate no IIS WebEx](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Saída de Set-CsCertificate no IIS WebEx")</span><span class="sxs-lookup"><span data-stu-id="20fb7-140">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="20fb7-141">Para verificar ou configurar a autenticação e certificados em diretórios virtuais do IIS</span><span class="sxs-lookup"><span data-stu-id="20fb7-141">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="20fb7-142">Clique em **Iniciar**, selecione **Todos os programas**, selecione **Ferramentas administrativas** e clique em **Gerenciador dos Serviços de Informações da Internet (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="20fb7-142">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="20fb7-143">No **Gerenciador dos serviços de informações da Internet (IIS)**, expanda **ServerName**e expanda **sites**.</span><span class="sxs-lookup"><span data-stu-id="20fb7-143">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="20fb7-144">Clique com o botão direito do mouse em **Lync Server External Web Site** e clique em **Editar Ligações**</span><span class="sxs-lookup"><span data-stu-id="20fb7-144">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="20fb7-145">Verifique se o https está associado à porta 4443 e clique em **https**.</span><span class="sxs-lookup"><span data-stu-id="20fb7-145">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="20fb7-146">Selecione a entrada HTTPS, clique em **Editar**e verifique se a WebServicesExternalCertificate do Lync Server está associada a esse protocolo.</span><span class="sxs-lookup"><span data-stu-id="20fb7-146">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="20fb7-147">Compare o thumbprint do cmdlet Set-CsCertificate para garantir que o certificado esperado está corretamente associado ao HTTPS.</span><span class="sxs-lookup"><span data-stu-id="20fb7-147">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="20fb7-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="20fb7-148">See Also</span></span>


[<span data-ttu-id="20fb7-149">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="20fb7-149">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="20fb7-150">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="20fb7-150">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

