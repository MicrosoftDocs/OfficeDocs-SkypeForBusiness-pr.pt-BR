---
title: 'Lync Server 2013: Configurando o Lync Server em um ambiente entre locais'
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
ms.openlocfilehash: 7dcbdb7ac12dcb8fc768a1f9e537622d01191b8f
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="d5d78-102">Configurando o Microsoft Lync Server 2013 em um ambiente entre locais</span><span class="sxs-lookup"><span data-stu-id="d5d78-102">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5d78-103">_**Última modificação do tópico:** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="d5d78-103">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="d5d78-104">Em uma configuração entre instalações, alguns dos seus usuários são hospedados em uma instalação local do Microsoft Lync Server 2013 enquanto outros usuários são hospedados na versão Microsoft 365 ou Office 365 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5d78-104">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Microsoft 365 or Office 365 version of Lync Server.</span></span> <span data-ttu-id="d5d78-105">Para configurar a autenticação de servidor para servidor em um ambiente entre locais, primeiro você deve configurar a instalação local do Lync Server 2013 para confiar no servidor de autorização da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d5d78-105">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Microsoft 365 Authorization server.</span></span> <span data-ttu-id="d5d78-106">A etapa inicial desse processo pode ser executada executando o seguinte script do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="d5d78-106">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

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

<span data-ttu-id="d5d78-p102">Tenha em mente que o nome do realm de um locatário é normalmente diferente do nome da organização; na realidade, o nome do realm é quase sempre igual ao do ID do locatário. Por causa disso, a primeira linha do script é usada para retornar o valor da propriedade TenantId do locatário especificado (neste caso, fabrikam.com) e atribuir o nome à variável $TenantId:</span><span class="sxs-lookup"><span data-stu-id="d5d78-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="d5d78-109">Após a conclusão do script, você deve configurar uma relação de confiança entre o Lync Server 2013 e o servidor de autorização e uma segunda relação de confiança entre o Exchange 2013 e o servidor de autorização.</span><span class="sxs-lookup"><span data-stu-id="d5d78-109">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="d5d78-110">Isso só pode ser feito usando os cmdlets do Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="d5d78-110">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5d78-111">Caso não tenha instalado os cmdlets do Microsoft Online Services, será necessário fazer duas coisas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d5d78-111">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="d5d78-112">Primeiro, baixe e instale a versão de 64 bits do Assistente de Conexão do Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="d5d78-112">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="d5d78-113">Após a conclusão da instalação, baixe e instale a versão de 64 bits do módulo do Microsoft Online Services para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5d78-113">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="d5d78-114">Informações detalhadas sobre a instalação e o uso do módulo do Microsoft Online Services podem ser encontradas no site do Microsoft 365 ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d5d78-114">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 or Office 365 web site.</span></span> <span data-ttu-id="d5d78-115">Essas instruções também informarão como configurar o logon único, a Federação e a sincronização entre o Microsoft 365 ou o Office 36 e o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d5d78-115">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 36 and Active Directory.</span></span><BR><span data-ttu-id="d5d78-116">Se você não tiver instalado esses cmdlets, seu script falhará porque o cmdlet Get-CsTenant não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="d5d78-116">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="d5d78-117">Depois de ter configurado o Microsoft 365 e depois de ter criado as entidades de serviço do Microsoft 365 ou do Office 365 para Lync Server 2013 e Exchange 2013, você precisará registrar suas credenciais com essas entidades de serviço.</span><span class="sxs-lookup"><span data-stu-id="d5d78-117">After you have configured Microsoft 365, and after you have created Microsoft 365 or Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="d5d78-118">Para isso, primeiro você deve obter um certificado X.509 Base64 salvo como um arquivo .CER.</span><span class="sxs-lookup"><span data-stu-id="d5d78-118">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="d5d78-119">Esse certificado será então aplicado às entidades de serviço do Microsoft 365 ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d5d78-119">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="d5d78-120">Quando tiver obtido o certificado X. 509, inicie o módulo do Microsoft Online Services (clique em **Iniciar**, em **todos os programas**, em **Microsoft Online Services**e em **Microsoft Online Services Module for Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="d5d78-120">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="d5d78-121">Depois que o módulo de serviços for aberto, digite o seguinte para importar o módulo Microsoft Online Windows PowerShell contendo os cmdlets que podem ser usados para gerenciar entidades de serviço:</span><span class="sxs-lookup"><span data-stu-id="d5d78-121">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="d5d78-122">Após a importação do módulo, digite o seguinte comando e pressione ENTER para se conectar ao Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="d5d78-122">When the module has been imported, type the following command and then press ENTER in order to connect to Microsoft 365:</span></span>

    Connect-MsolService

<span data-ttu-id="d5d78-123">Depois de pressionar ENTER, uma caixa de diálogo de credenciais será exibida.</span><span class="sxs-lookup"><span data-stu-id="d5d78-123">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="d5d78-124">Insira seu nome de usuário e senha do Microsoft 365 ou do Office 365 na caixa de diálogo e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d5d78-124">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="d5d78-125">Assim que estiver conectado ao Microsoft 365, você poderá executar o comando a seguir para retornar informações sobre as entidades de serviço:</span><span class="sxs-lookup"><span data-stu-id="d5d78-125">As soon as you are connected to Microsoft 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="d5d78-126">Você deverá obter informações semelhantes a estas para todas as entidades de serviço:</span><span class="sxs-lookup"><span data-stu-id="d5d78-126">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="d5d78-127">A próxima etapa é importar, codificar e atribuir o certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="d5d78-127">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="d5d78-128">Para importar e codificar o certificado, use os seguintes comandos do Windows PowerShell, certifique-se de especificar o caminho completo do arquivo para o. Arquivo CER ao chamar o método Import:</span><span class="sxs-lookup"><span data-stu-id="d5d78-128">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="d5d78-129">Após o certificado ter sido importado e codificado, você poderá atribuí-lo às suas entidades de serviço do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d5d78-129">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 service principals.</span></span> <span data-ttu-id="d5d78-130">Para isso, use primeiro Get-MsolServicePrincipal a fim de recuperar o valor da propriedade AppPrincipalId para as entidades de serviço do Lync Server e do Microsoft Exchange; o valor da propriedade AppPrincipalId será usado para identificar a entidade de serviço atribuída ao certificado.</span><span class="sxs-lookup"><span data-stu-id="d5d78-130">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="d5d78-131">Com o valor da propriedade AppPrincipalId para o Lync Server 2013 disponível, use o comando a seguir para atribuir o certificado à versão 365 da Microsoft do Lync Server (as propriedades StartDate e EndDate devem corresponder ao período de validade do certificado):</span><span class="sxs-lookup"><span data-stu-id="d5d78-131">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Microsoft 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="d5d78-132">Em seguida, você deve repetir o comando, desta vez usando o valor da propriedade AppPrincipalId para o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d5d78-132">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="d5d78-133">Caso precise excluir o certificado posteriormente, faça isso recuperando KeyId do certificado primeiro:</span><span class="sxs-lookup"><span data-stu-id="d5d78-133">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="d5d78-134">O comando retornará dados como estes:</span><span class="sxs-lookup"><span data-stu-id="d5d78-134">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="d5d78-135">Você pode excluir o certificado usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="d5d78-135">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="d5d78-136">Além de atribuir um certificado, você também deve configurar o Microsoft 365 Service principal para o Exchange Online adicionando o nome principal do servidor para sua versão local do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5d78-136">In addition to assigning a certificate you must also configure the Microsoft 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="d5d78-137">Isso pode ser feito executando as quatro linhas a seguir em uma sessão do Microsoft Online Services PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d5d78-137">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

