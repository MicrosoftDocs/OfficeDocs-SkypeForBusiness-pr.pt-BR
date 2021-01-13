---
title: Configurar a autenticação de servidor para servidor para um ambiente híbrido do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Resumo: Configure a autenticação de servidor para servidor para um ambiente híbrido do Skype for Business Server.'
ms.openlocfilehash: 6f4e11b54f0292b1ccb91ab486e2e638a4dcceb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828481"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="0c4a4-103">Configure a autenticação de servidor para servidor para um ambiente híbrido do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="0c4a4-104">**Resumo:** Configure a autenticação de servidor para servidor para o ambiente híbrido do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="0c4a4-105">Em uma configuração híbrida, alguns de seus usuários estão em uma instalação local do Skype for Business Server enquanto outros usuários estão na versão Microsoft 365 ou Office 365 do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Microsoft 365 or Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="0c4a4-106">Para configurar a autenticação de servidor para servidor em um ambiente híbrido, você deve primeiro configurar sua instalação local do Skype for Business Server para confiar no servidor de autorização.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the authorization server.</span></span> <span data-ttu-id="0c4a4-107">A etapa inicial desse processo pode ser realizada executando o seguinte script do Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="0c4a4-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

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

<span data-ttu-id="0c4a4-p102">Tenha em mente que o nome do realm de um locatário é normalmente diferente do nome da organização; na realidade, o nome do realm é quase sempre igual ao do ID do locatário. Por causa disso, a primeira linha do script é usada para retornar o valor da propriedade TenantId do locatário especificado (neste caso, fabrikam.com) e atribuir o nome à variável $TenantId:</span><span class="sxs-lookup"><span data-stu-id="0c4a4-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="0c4a4-110">Para executar esse script, você deve ter instalado o módulo PowerShell do Skype for Business Online e se conectar ao seu locatário com este módulo.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="0c4a4-111">Se você não tiver instalado esses cmdlets, seu script falhará porque o Get-CsTenant cmdlet não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="0c4a4-112">Após a conclusão do script, você deve configurar uma relação de confiança entre o Skype for Business Server e o servidor de autorização e uma segunda relação de confiança entre o Exchange 2013/2016 e o servidor de autorização.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="0c4a4-113">Isso só pode ser feito usando os cmdlets do Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="0c4a4-114">Se você não tiver instalado os cmdlets do Microsoft Online Services, precisará instalá-lo no repositório do PowerShell com o `install-module MSOnline` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="0c4a4-115">Informações detalhadas para instalar e usar o Módulo do Microsoft Online Services podem ser encontradas no site do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 web site.</span></span> <span data-ttu-id="0c4a4-116">Essas instruções também explicam como configurar o single sign-on, a federação e a sincronização entre o Microsoft 365 ou o Office 365 e o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 365 and Active Directory.</span></span> 



<span data-ttu-id="0c4a4-117">Depois de configurar o Microsoft 365 ou o Office 365 e depois de criar entidades de serviço do Microsoft 365 ou Office 365 para o Skype for Business Server e o Exchange 2013, você precisará registrar suas credenciais com essas entidades de serviço.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-117">After you have configured Microsoft 365 or Office 365, and after you have created Microsoft 365 or Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="0c4a4-118">Para fazer isso, primeiro você deve obter um certificado Base64 X.509 salvo como um . Arquivo CER.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="0c4a4-119">Esse certificado será aplicado às entidades de serviço do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-119">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="0c4a4-120">Quando você tiver obtido o certificado X.509, abra o console do PowerShell e importe o módulo do Windows PowerShell do Microsoft Online que contém os cmdlets que podem ser usados para gerenciar entidades de serviço:</span><span class="sxs-lookup"><span data-stu-id="0c4a4-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="0c4a4-121">Quando o módulo tiver sido importado, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="0c4a4-121">When the module has been imported, type the following command and then press ENTER:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="0c4a4-122">Depois de pressionar ENTER, uma caixa de diálogo de credenciais será exibida.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="0c4a4-123">Insira seu nome de usuário e senha do Microsoft 365 ou Office 365 na caixa de diálogo e clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-123">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="0c4a4-124">Assim que estiver conectado ao Microsoft 365 ou Ao Office 365, você poderá executar o seguinte comando para retornar informações sobre suas entidades de serviço:</span><span class="sxs-lookup"><span data-stu-id="0c4a4-124">As soon as you are connected to Microsoft 365 or Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="0c4a4-125">Você deverá obter informações semelhantes a estas para todas as entidades de serviço:</span><span class="sxs-lookup"><span data-stu-id="0c4a4-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="0c4a4-126">A próxima etapa é importar, codificar e atribuir o certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="0c4a4-127">Para importar e codificar o certificado, use os seguintes comandos do Windows PowerShell, certificando-se de especificar o caminho completo do arquivo para o seu . Arquivo CER ao chamar o método Import:</span><span class="sxs-lookup"><span data-stu-id="0c4a4-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

<span data-ttu-id="0c4a4-128">Depois que o certificado tiver sido importado e codificado, você poderá atribuir o certificado às entidades de serviço do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-128">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 or Office 365 service principals.</span></span> <span data-ttu-id="0c4a4-129">Para fazer isso, primeiro use o Get-MsolServicePrincipal para recuperar o valor da propriedade AppPrincipalId para o Skype for Business Server e as entidades de serviço do Microsoft Exchange; o valor da propriedade AppPrincipalId será usado para identificar a entidade de serviço que está sendo atribuída ao certificado.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="0c4a4-130">Com o valor da propriedade AppPrincipalId do Skype for Business Server em mãos, use o seguinte comando para atribuir o certificado à versão do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="0c4a4-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="0c4a4-131">Em seguida, você deve repetir o comando, desta vez usando o valor da propriedade AppPrincipalId para o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="0c4a4-132">Se, mais tarde, você precisar excluir esse certificado, por exemplo, se ele tiver expirado, poderá fazer isso recuperando primeiro a KeyId do certificado:</span><span class="sxs-lookup"><span data-stu-id="0c4a4-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="0c4a4-133">O comando retornará dados como estes:</span><span class="sxs-lookup"><span data-stu-id="0c4a4-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="0c4a4-134">Você pode excluir o certificado usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="0c4a4-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="0c4a4-135">Além de atribuir um certificado, você também deve configurar a Entidade de Serviço do Exchange Online e configurar sua versão local de URLs de serviços Web externos do Skype for Business Server como uma entidade de serviço do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as a Microsoft 365 or Office 365 service principal.</span></span> <span data-ttu-id="0c4a4-136">Isso pode ser feito realizando os dois comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="0c4a4-137">No exemplo a seguir, Pool1ExternalWebFQDN.contoso.com é a URL de serviços Web externos para o pool do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="0c4a4-138">Você deve repetir essas etapas para adicionar todas as URLs de serviços Web externos na implantação.</span><span class="sxs-lookup"><span data-stu-id="0c4a4-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
