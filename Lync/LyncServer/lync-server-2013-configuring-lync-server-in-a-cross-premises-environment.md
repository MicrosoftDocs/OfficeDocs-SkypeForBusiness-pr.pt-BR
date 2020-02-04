---
title: 'Lync Server 2013: Configurando o Lync Server em um ambiente de várias instalações'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02696b85921e2f408b7a7ec5531b0596aaef49ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="604c9-102">Configurando o Microsoft Lync Server 2013 em um ambiente de várias instalações</span><span class="sxs-lookup"><span data-stu-id="604c9-102">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="604c9-103">_**Tópico da última modificação:** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="604c9-103">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="604c9-104">Em uma configuração de vários locais, alguns dos seus usuários são hospedados em uma instalação local do Microsoft Lync Server 2013 enquanto outros usuários são hospedados na versão do Office 365 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="604c9-104">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Office 365 version of Lync Server.</span></span> <span data-ttu-id="604c9-105">Para configurar a autenticação do servidor para o servidor em um ambiente de várias instalações, você deve primeiro configurar a instalação local do Lync Server 2013 para confiar no servidor de autorização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="604c9-105">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Office 365 Authorization server.</span></span> <span data-ttu-id="604c9-106">A etapa inicial nesse processo pode ser executada executando o seguinte script do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="604c9-106">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

    $TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
    
    $sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue
            
       if ($sts -eq $null)
          {
             New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
          }
       else
          {
             if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
                {
                   Remove-CsOAuthServer microsoft.sts
                   New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
                }
            }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
                 New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
              }
           else
              {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
              }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="604c9-p102">Tenha em mente que o nome do realm de um locatário é normalmente diferente do nome da organização; na realidade, o nome do realm é quase sempre igual ao do ID do locatário. Por causa disso, a primeira linha do script é usada para retornar o valor da propriedade TenantId do locatário especificado (neste caso, fabrikam.com) e atribuir o nome à variável $TenantId:</span><span class="sxs-lookup"><span data-stu-id="604c9-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="604c9-109">Depois que o script é concluído, você deve configurar uma relação de confiança entre o Lync Server 2013 e o servidor de autorização e uma segunda relação de confiança entre o Exchange 2013 e o servidor de autorização.</span><span class="sxs-lookup"><span data-stu-id="604c9-109">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="604c9-110">Isso só pode ser feito usando cmdlets do Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="604c9-110">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="604c9-111">Se você não instalou os cmdlets do Microsoft Online Services, será necessário fazer duas coisas antes de prosseguir.</span><span class="sxs-lookup"><span data-stu-id="604c9-111">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="604c9-112">Primeiro, baixe e instale a versão de 64 bits do Assistente de Conexão do Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="604c9-112">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="604c9-113">Após a conclusão da instalação, baixe e instale a versão do 64 bits do módulo do Microsoft Online Services para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="604c9-113">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="604c9-114">Informações detalhadas sobre como instalar e usar o módulo do Microsoft Online Services podem ser encontradas no site do Office 365 na Web.</span><span class="sxs-lookup"><span data-stu-id="604c9-114">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="604c9-115">Estas instruções também informarão como configurar o logon único, a Federação e a sincronização entre o Office 365 e o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="604c9-115">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span><BR><span data-ttu-id="604c9-116">Se você não tiver instalado esses cmdlets, seu script falhará porque o cmdlet Get-CsTenant não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="604c9-116">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="604c9-117">Depois de configurar o Office 365 e, após a criação de entidades de serviço do Office 365 para o Lync Server 2013 e do Exchange 2013, será preciso registrar suas credenciais com essas entidades de serviço.</span><span class="sxs-lookup"><span data-stu-id="604c9-117">After you have configured Office 365, and after you have created Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="604c9-118">Para isso, primeiro você deve obter um certificado X.509 Base64 salvo como arquivo .CER.</span><span class="sxs-lookup"><span data-stu-id="604c9-118">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="604c9-119">Esse certificado será aplicado às entidades de serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="604c9-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="604c9-120">Quando você tiver obtido o certificado X. 509, inicie o módulo do Microsoft Online Services (clique em **Iniciar**, clique em **todos os programas**, em **Microsoft Online Services**e, em seguida, clique em **módulo do Microsoft Online Services para Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="604c9-120">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="604c9-121">Depois que o módulo serviços for aberto, digite o seguinte para importar o módulo Microsoft Online Windows PowerShell que contém os cmdlets que podem ser usados para gerenciar entidades de serviço:</span><span class="sxs-lookup"><span data-stu-id="604c9-121">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="604c9-122">Quando o módulo tiver sido importado, digite o seguinte comando e pressione ENTER para se conectar ao Office 365:</span><span class="sxs-lookup"><span data-stu-id="604c9-122">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

    Connect-MsolService

<span data-ttu-id="604c9-123">Depois de pressionar ENTER, uma caixa de diálogo de credenciais será exibida.</span><span class="sxs-lookup"><span data-stu-id="604c9-123">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="604c9-124">Insira seu nome de usuário e senha do Office 365 na caixa de diálogo e, em seguida, clique em OK.</span><span class="sxs-lookup"><span data-stu-id="604c9-124">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="604c9-125">Assim que estiver conectado ao Office 365, você poderá executar o seguinte comando para retornar informações sobre as entidades do serviço:</span><span class="sxs-lookup"><span data-stu-id="604c9-125">As soon as you are connected to Office 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="604c9-126">Você deverá obter informações semelhantes a estas para todas as entidades de serviço:</span><span class="sxs-lookup"><span data-stu-id="604c9-126">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="604c9-127">A próxima etapa é importar, codificar e atribuir o certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="604c9-127">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="604c9-128">Para importar e codificar o certificado, use os seguintes comandos do Windows PowerShell, certifique-se de especificar o caminho de arquivo completo para o seu. Arquivo CER quando você chamar o método de importação:</span><span class="sxs-lookup"><span data-stu-id="604c9-128">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="604c9-129">Depois que o certificado tiver sido importado e codificado, você poderá atribuir o certificado a seus dirigentes de serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="604c9-129">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="604c9-130">Para fazer isso, use o Get-MsolServicePrincipal para recuperar o valor da propriedade AppPrincipalId do Lync Server e das entidades de serviço do Microsoft Exchange; o valor da propriedade AppPrincipalId será usado para identificar a entidade de serviço ao qual o certificado está sendo atribuído.</span><span class="sxs-lookup"><span data-stu-id="604c9-130">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="604c9-131">Com o valor da propriedade AppPrincipalId para o Lync Server 2013 disponível, use o seguinte comando para atribuir o certificado à versão do Office 365 do Lync Server (as propriedades StartDate e EndDate devem corresponder ao período de validade do certificado):</span><span class="sxs-lookup"><span data-stu-id="604c9-131">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Office 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="604c9-132">Em seguida, você deve repetir o comando, desta vez usando o valor da propriedade AppPrincipalId para o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="604c9-132">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="604c9-133">Caso precise excluir o certificado posteriormente, faça isso recuperando KeyId do certificado primeiro:</span><span class="sxs-lookup"><span data-stu-id="604c9-133">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="604c9-134">O comando retornará dados como estes:</span><span class="sxs-lookup"><span data-stu-id="604c9-134">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="604c9-135">Você pode excluir o certificado usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="604c9-135">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="604c9-136">Além de atribuir um certificado, você também deve configurar a entidade de serviço do Office 365 para o Exchange Online adicionando o nome principal do servidor para a sua versão local do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="604c9-136">In addition to assigning a certificate you must also configure the Office 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="604c9-137">Isso pode ser feito executando-se as quatro linhas a seguir em uma sessão do PowerShell do Microsoft Online Services:</span><span class="sxs-lookup"><span data-stu-id="604c9-137">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

