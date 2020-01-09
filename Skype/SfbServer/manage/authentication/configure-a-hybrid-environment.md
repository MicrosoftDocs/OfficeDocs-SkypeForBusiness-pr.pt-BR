---
title: Configurar a autenticação de servidor para servidor para um ambiente híbrido do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Resumo: configurar a autenticação de servidor para servidor para um ambiente híbrido do Skype for Business Server.'
ms.openlocfilehash: 5d56f098589355b85f942a6b1eb80d8ab6c03225
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992348"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="d4b6b-103">Configurar a autenticação de servidor para servidor para um ambiente híbrido do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="d4b6b-104">**Resumo:** Configurar a autenticação de servidor para servidor para o ambiente híbrido do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="d4b6b-105">Em uma configuração híbrida, alguns dos seus usuários são hospedados em uma instalação local do Skype for Business Server enquanto outros usuários são hospedados na versão do Office 365 do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="d4b6b-106">Para configurar a autenticação de servidor para servidor em um ambiente híbrido, você deve primeiro configurar a instalação local do Skype for Business Server para confiar no servidor de autorização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the Office 365 authorization server.</span></span> <span data-ttu-id="d4b6b-107">A etapa inicial nesse processo pode ser executada executando o seguinte script do Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="d4b6b-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

```PowerShell
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
```

<span data-ttu-id="d4b6b-p102">Tenha em mente que o nome do realm de um locatário é normalmente diferente do nome da organização; na realidade, o nome do realm é quase sempre igual ao do ID do locatário. Por causa disso, a primeira linha do script é usada para retornar o valor da propriedade TenantId do locatário especificado (neste caso, fabrikam.com) e atribuir o nome à variável $TenantId:</span><span class="sxs-lookup"><span data-stu-id="d4b6b-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="d4b6b-110">Para executar esse script, você deve ter instalado o módulo do PowerShell do Skype for Business Online e conectar-se ao seu locatário com este módulo.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="d4b6b-111">Se você não tiver instalado esses cmdlets, seu script falhará porque o cmdlet Get-CsTenant não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="d4b6b-112">Depois que o script é concluído, você deve configurar uma relação de confiança entre o Skype for Business Server e o servidor de autorização e uma segunda relação de confiança entre o Exchange 2013/2016 e o servidor de autorização.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="d4b6b-113">Isso só pode ser feito usando cmdlets do Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="d4b6b-114">Se você não instalou os cmdlets do Microsoft Online Services, será necessário instalá-lo a partir do repositório do PowerShell com o `install-module MSOnline`cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="d4b6b-115">Informações detalhadas sobre como instalar e usar o módulo do Microsoft Online Services podem ser encontradas no site do Office 365 na Web.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="d4b6b-116">Estas instruções também informarão como configurar o logon único, a Federação e a sincronização entre o Office 365 e o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 



<span data-ttu-id="d4b6b-117">Depois de configurar o Office 365 e, após a criação de entidades de serviço do Office 365 para o Skype for Business Server e do Exchange 2013, será necessário registrar suas credenciais com essas entidades de serviço.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-117">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="d4b6b-118">Para fazer isso, primeiro você deve obter um certificado de base64 X. 509 salvo como um. Arquivo CER.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="d4b6b-119">Esse certificado será aplicado às entidades de serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="d4b6b-120">Quando você tiver obtido o certificado X. 509, abra o console do PowerShell e importe o módulo Microsoft Online do Windows PowerShell que contém os cmdlets que podem ser usados para gerenciar as entidades do serviço:</span><span class="sxs-lookup"><span data-stu-id="d4b6b-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="d4b6b-121">Quando o módulo tiver sido importado, digite o seguinte comando e pressione ENTER para se conectar ao Office 365:</span><span class="sxs-lookup"><span data-stu-id="d4b6b-121">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="d4b6b-122">Depois de pressionar ENTER, uma caixa de diálogo de credenciais será exibida.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="d4b6b-123">Insira seu nome de usuário e senha do Office 365 na caixa de diálogo e, em seguida, clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-123">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="d4b6b-124">Assim que estiver conectado ao Office 365, você poderá executar o seguinte comando para retornar informações sobre as entidades do serviço:</span><span class="sxs-lookup"><span data-stu-id="d4b6b-124">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="d4b6b-125">Você deverá obter informações semelhantes a estas para todas as entidades de serviço:</span><span class="sxs-lookup"><span data-stu-id="d4b6b-125">You should get back information similar to this for all your service principals:</span></span>

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

<span data-ttu-id="d4b6b-126">A próxima etapa é importar, codificar e atribuir o certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="d4b6b-127">Para importar e codificar o certificado, use os seguintes comandos do Windows PowerShell, certifique-se de especificar o caminho de arquivo completo para o seu. Arquivo CER quando você chamar o método de importação:</span><span class="sxs-lookup"><span data-stu-id="d4b6b-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="d4b6b-128">Depois que o certificado tiver sido importado e codificado, você poderá atribuir o certificado a seus dirigentes de serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-128">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="d4b6b-129">Para fazer isso, use o Get-MsolServicePrincipal para recuperar o valor da propriedade AppPrincipalId tanto para o Skype for Business Server quanto para as entidades de serviço do Microsoft Exchange; o valor da propriedade AppPrincipalId será usado para identificar a entidade de serviço ao qual o certificado está sendo atribuído.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="d4b6b-130">Com o valor da propriedade AppPrincipalId para o Skype for Business Server em mãos, use o seguinte comando para atribuir o certificado à versão do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="d4b6b-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="d4b6b-131">Em seguida, você deve repetir o comando, desta vez usando o valor da propriedade AppPrincipalId para o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="d4b6b-132">Se, posteriormente, você precisar excluir esse certificado, por exemplo, se ele tiver expirado, você pode fazê-lo primeiro recuperando o KeyId para o certificado:</span><span class="sxs-lookup"><span data-stu-id="d4b6b-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="d4b6b-133">O comando retornará dados como estes:</span><span class="sxs-lookup"><span data-stu-id="d4b6b-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="d4b6b-134">Você pode excluir o certificado usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="d4b6b-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="d4b6b-135">Além de atribuir um certificado, você também deve configurar a entidade de serviço do Exchange Online e configurar sua versão local do Skype for Business Server URLs de serviços Web externos como uma entidade de serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="d4b6b-136">Isso pode ser feito executando os dois comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="d4b6b-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="d4b6b-137">No exemplo a seguir, Pool1ExternalWebFQDN.contoso.com é a URL de serviços Web externos do pool do servidor do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="d4b6b-138">Você deve repetir essas etapas para adicionar todas as URLs de serviços Web externos na implantação.</span><span class="sxs-lookup"><span data-stu-id="d4b6b-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
