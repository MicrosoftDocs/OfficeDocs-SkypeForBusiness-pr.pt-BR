---
title: Configurar a autenticação de servidor-para-servidor para um Skype para um ambiente híbrido do Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Resumo: Configure a autenticação de servidor-para-servidor para um Skype para um ambiente híbrido do Business Server.'
ms.openlocfilehash: 02412c152e017da95c82ff6f8ad6f08db1a105ef
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375947"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="e6937-103">Configure a autenticação de servidor-para-servidor para um Skype para um ambiente híbrido do Business Server.</span><span class="sxs-lookup"><span data-stu-id="e6937-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="e6937-104">**Resumo:** Configure a autenticação de servidor-para-servidor para Skype para um ambiente híbrido do Business Server.</span><span class="sxs-lookup"><span data-stu-id="e6937-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="e6937-105">Em uma configuração híbrida, alguns dos usuários hospedados em uma instalação local do Skype para Business Server enquanto outros usuários estão hospedados na versão do Office 365 do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e6937-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="e6937-106">Para configurar uma autenticação servidor-para-servidor em um ambiente híbrido, você deve primeiro configurar sua instalação do local do Skype para Business Server confiar no servidor de autorização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6937-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the Office 365 authorization server.</span></span> <span data-ttu-id="e6937-107">A etapa inicial nesse processo pode ser realizada executando a seguinte Skype para script do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="e6937-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

```
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

<span data-ttu-id="e6937-p102">Tenha em mente que o nome do realm de um locatário é normalmente diferente do nome da organização; na realidade, o nome do realm é quase sempre igual ao do ID do locatário. Por causa disso, a primeira linha do script é usada para retornar o valor da propriedade TenantId do locatário especificado (neste caso, fabrikam.com) e atribuir o nome à variável $TenantId:</span><span class="sxs-lookup"><span data-stu-id="e6937-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

<span data-ttu-id="e6937-110">Quando o script for concluída, em seguida, você deve configurar uma relação de confiança entre Skype para Business Server e o servidor de autorização e uma segunda relação de confiança entre o Exchange 2013 e o servidor de autorização.</span><span class="sxs-lookup"><span data-stu-id="e6937-110">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="e6937-111">Isso só pode ser feito usando os cmdlets do Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="e6937-111">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="e6937-112">Caso não tenha instalado os cmdlets do Microsoft Online Services, será necessário fazer duas coisas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e6937-112">If you have not installed the Microsoft Online Services cmdlets, you will need to do two things before proceeding.</span></span> <span data-ttu-id="e6937-113">Primeiro, baixe e instale a versão de 64 bits do Assistente de Conexão do Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="e6937-113">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="e6937-114">Após a instalação estiver concluída, baixe e instale a versão de 64 bits do Microsoft Online Services Module for Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6937-114">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="e6937-115">Informações detalhadas sobre como instalar e usar o módulo do Microsoft Online Services podem ser encontradas no site do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6937-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="e6937-116">Estas instruções também informará como configurar o serviço single sign-on, Federação e a sincronização entre o Office 365 e o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e6937-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 

<span data-ttu-id="e6937-117">Se você não tiver instalado esses cmdlets, seu script falhará porque o cmdlet Get-CsTenant não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="e6937-117">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>

<span data-ttu-id="e6937-118">Depois que você configurou o Office 365 e depois de ter criado Office 365 entidades de serviço para Skype para Business Server e o Exchange 2013, será necessário registrar suas credenciais com essas entidades de serviço.</span><span class="sxs-lookup"><span data-stu-id="e6937-118">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="e6937-119">Para isso, primeiro você deve obter um certificado X.509 Base64 salvo como arquivo .CER.</span><span class="sxs-lookup"><span data-stu-id="e6937-119">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="e6937-120">Esse certificado, em seguida, será aplicado para as entidades de serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6937-120">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="e6937-121">Quando você tiver obtido o certificado x. 509, inicie o módulo do Microsoft Online Services (clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Online Services**e clique em **Microsoft Online Services Module for Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="e6937-121">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="e6937-122">Depois que o módulo de serviços abrir, digite o seguinte procedimento para importar o módulo do Microsoft Online Windows PowerShell que contém os cmdlets que pode ser usados para gerenciar as entidades de serviço:</span><span class="sxs-lookup"><span data-stu-id="e6937-122">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```
Import-Module MSOnlineExtended
```

<span data-ttu-id="e6937-123">Quando o módulo foi importado, digite o seguinte comando e pressione ENTER para conectar ao Office 365:</span><span class="sxs-lookup"><span data-stu-id="e6937-123">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

```
Connect-MsolService
```

<span data-ttu-id="e6937-124">Depois de pressionar ENTER, uma caixa de diálogo de credenciais será exibida.</span><span class="sxs-lookup"><span data-stu-id="e6937-124">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="e6937-125">Insira seu nome de usuário do Office 365 e a senha na caixa de diálogo e clique em Okey.</span><span class="sxs-lookup"><span data-stu-id="e6937-125">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="e6937-126">Assim que você estiver conectado ao Office 365, você pode, em seguida, execute o seguinte comando para retornar informações sobre as entidades de serviço:</span><span class="sxs-lookup"><span data-stu-id="e6937-126">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```
Get-MsolServicePrincipal
```

<span data-ttu-id="e6937-127">Você deverá obter informações semelhantes a estas para todas as entidades de serviço:</span><span class="sxs-lookup"><span data-stu-id="e6937-127">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="e6937-128">A próxima etapa é importar, codificar e atribuir o certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="e6937-128">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="e6937-129">Para importar e codificar o certificado, use os seguintes comandos do Windows PowerShell, certificando-se de especificar o caminho completo do arquivo para sua. Arquivo CER quando você chama o método Import:</span><span class="sxs-lookup"><span data-stu-id="e6937-129">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="e6937-130">Depois que o certificado foi importado e codificado, você pode atribuir o certificado para as entidades de serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6937-130">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="e6937-131">Para fazer isso, primeiro usar o Get-MsolServicePrincipal para recuperar o valor da propriedade AppPrincipalId para o Skype para Business Server e as entidades de serviço do Microsoft Exchange; o valor da propriedade AppPrincipalId será usado para identificar a entidade de serviço que está sendo atribuída o certificado.</span><span class="sxs-lookup"><span data-stu-id="e6937-131">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="e6937-132">Com o AppPrincipalId propriedade valor do Skype para Business Server lado, use o seguinte comando para atribuir o certificado para a versão do Office 365 do Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="e6937-132">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to the Office 365 version of Skype for Business Server:</span></span>

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="e6937-133">Você deve repetir o comando, desta vez usando o valor da propriedade AppPrincipalId para o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="e6937-133">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="e6937-134">Caso precise excluir o certificado posteriormente, faça isso recuperando KeyId do certificado primeiro:</span><span class="sxs-lookup"><span data-stu-id="e6937-134">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="e6937-135">O comando retornará dados como estes:</span><span class="sxs-lookup"><span data-stu-id="e6937-135">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="e6937-136">Você pode excluir o certificado usando um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="e6937-136">You can then delete the certificate by using a command similar to this:</span></span>

```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="e6937-137">Além de atribuir um certificado, você também deve configurar a entidade de serviço Online do Exchange e configurar sua versão do local do Skype para URLs de serviços Web externos Business Server como uma entidade de serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6937-137">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="e6937-138">Isso pode ser feito executando os dois comandos a seguir:</span><span class="sxs-lookup"><span data-stu-id="e6937-138">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="e6937-139">No exemplo a seguir, lync.contoso.com é a URL externa de serviços Web para o Skype para pool de servidores de negócios.</span><span class="sxs-lookup"><span data-stu-id="e6937-139">In the following example, lync.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="e6937-140">Você deve repetir essas etapas para adicionar todas as Web services URLs externas na implantação.</span><span class="sxs-lookup"><span data-stu-id="e6937-140">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```