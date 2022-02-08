---
title: Configurar a autenticação de servidor para servidor para um ambiente Skype for Business Server híbrido
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Resumo: Configure a autenticação de servidor para servidor para um ambiente Skype for Business Server híbrido.'
ms.openlocfilehash: f07c5f9fb930910422c264d1ca61f992c84f1600
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391173"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configure a autenticação de servidor para servidor para um ambiente Skype for Business Server híbrido.

**Resumo:** Configure a autenticação de servidor para servidor para Skype for Business Server ambiente híbrido.

Em uma configuração híbrida, alguns de seus usuários estão instalados em uma instalação local do Skype for Business Server enquanto outros usuários estão em casa na versão Microsoft 365 ou Office 365 do Skype for Business Server. Para configurar a autenticação de servidor para servidor em um ambiente híbrido, você deve primeiro configurar sua instalação local do Skype for Business Server para confiar no servidor de autorização. A etapa inicial desse processo pode ser executada executando o seguinte script Skype for Business Server Shell de Gerenciamento:

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

Tenha em mente que o nome do realm de um locatário é normalmente diferente do nome da organização; na realidade, o nome do realm é quase sempre igual ao do ID do locatário. Por causa disso, a primeira linha do script é usada para retornar o valor da propriedade TenantId do locatário especificado (neste caso, fabrikam.com) e atribuir o nome à variável $TenantId:

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

Para executar esse script, você deve ter instalado o módulo Skype for Business PowerShell Online e se conectar ao seu locatário com esse módulo. Se você não tiver instalado esses cmdlets, seu script falhará porque o cmdlet Get-CsTenant não estará disponível. Após a conclusão do script, você deve configurar uma relação de confiança entre o Skype for Business Server e o servidor de autorização e uma segunda relação de confiança entre o Exchange 2013/2016 e o servidor de autorização. Isso só pode ser feito usando Microsoft Online Services cmdlets.

> [!NOTE]
> Se você não tiver instalado os cmdlets Microsoft Online Services, precisará instalá-lo do repositório do PowerShell com o cmdlet `install-module MSOnline`. Informações detalhadas para instalar e usar o módulo Microsoft Online Services podem ser encontradas no site Microsoft 365 web. Essas instruções também lhe dirá como configurar o login único, a federação e a sincronização entre o Microsoft 365 ou Office 365 e o Active Directory. 



Depois de configurar Microsoft 365 ou Office 365 e depois de criar entidades de serviço Microsoft 365 ou Office 365 para Skype for Business Server e Exchange  2013, você precisará registrar suas credenciais com essas entidades de serviço. Para fazer isso, você deve primeiro obter um certificado X.509 Base64 salvo como um . Arquivo CER. Esse certificado será aplicado às entidades Microsoft 365 ou Office 365 de serviço.

Quando você tiver obtido o certificado X.509, abra o console do PowerShell e importe o módulo de Windows PowerShell do Microsoft Online contendo os cmdlets que podem ser usados para gerenciar entidades de serviço:

```PowerShell
Import-Module MSOnline
```

Quando o módulo tiver sido importado, digite o seguinte comando e pressione ENTER:

```PowerShell
Connect-MsolService
```

Depois de pressionar ENTER, uma caixa de diálogo de credenciais será exibida. Insira seu Microsoft 365 ou Office 365 nome de usuário e senha na caixa de diálogo e clique em OK.

Assim que você estiver conectado a Microsoft 365 ou Office 365, você poderá executar o seguinte comando para retornar informações sobre suas entidades de serviço:

```PowerShell
Get-MsolServicePrincipal
```

Você deverá obter informações semelhantes a estas para todas as entidades de serviço:

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

A próxima etapa é importar, codificar e atribuir o certificado X.509. Para importar e codificar o certificado, use os comandos Windows PowerShell a seguir, certificando-se de especificar o caminho completo do arquivo para o seu . Arquivo CER quando você chama o método Import:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

Depois que o certificado tiver sido importado e codificado, você poderá atribuir o certificado às entidades Microsoft 365 ou Office 365 de serviço. Para fazer isso, primeiro use o Get-MsolServicePrincipal para recuperar o valor da propriedade AppPrincipalId para as entidades de serviço do Skype for Business Server e do Microsoft Exchange; o valor da propriedade AppPrincipalId será usado para identificar a entidade de serviço que está sendo atribuída ao certificado. Com o valor da propriedade AppPrincipalId para Skype for Business Server em mãos, use o comando a seguir para atribuir o certificado Skype versão para Empresas Online:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Em seguida, repita o comando, desta vez usando o valor da propriedade AppPrincipalId para Exchange 2013.

Se você precisar excluir esse certificado posteriormente, por exemplo, se ele tiver expirado, você poderá fazer isso recuperando primeiro o KeyId do certificado:

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

O comando retornará dados como estes:

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

Você pode excluir o certificado usando um comando semelhante a este:

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

Além de atribuir um certificado, você também deve configurar a Entidade de Serviço Exchange Online e configurar sua versão local de URL Skype for Business Server s de serviços Web externos como uma entidade de serviço Microsoft 365 ou Office 365 local. Isso pode ser feito realizando os dois comandos a seguir. 

No exemplo a seguir, Pool1ExternalWebFQDN.contoso.com é a URL de serviços Web externos para o pool Skype for Business Server web. Você deve repetir essas etapas para adicionar todas as URLs de serviços Web externos na implantação.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
