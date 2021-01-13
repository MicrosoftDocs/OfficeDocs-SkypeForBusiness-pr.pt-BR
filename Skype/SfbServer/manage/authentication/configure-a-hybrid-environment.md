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
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configure a autenticação de servidor para servidor para um ambiente híbrido do Skype for Business Server.

**Resumo:** Configure a autenticação de servidor para servidor para o ambiente híbrido do Skype for Business Server.

Em uma configuração híbrida, alguns de seus usuários estão em uma instalação local do Skype for Business Server enquanto outros usuários estão na versão Microsoft 365 ou Office 365 do Skype for Business Server. Para configurar a autenticação de servidor para servidor em um ambiente híbrido, você deve primeiro configurar sua instalação local do Skype for Business Server para confiar no servidor de autorização. A etapa inicial desse processo pode ser realizada executando o seguinte script do Shell de Gerenciamento do Skype for Business Server:

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

Para executar esse script, você deve ter instalado o módulo PowerShell do Skype for Business Online e se conectar ao seu locatário com este módulo. Se você não tiver instalado esses cmdlets, seu script falhará porque o Get-CsTenant cmdlet não estará disponível. Após a conclusão do script, você deve configurar uma relação de confiança entre o Skype for Business Server e o servidor de autorização e uma segunda relação de confiança entre o Exchange 2013/2016 e o servidor de autorização. Isso só pode ser feito usando os cmdlets do Microsoft Online Services.

> [!NOTE]
> Se você não tiver instalado os cmdlets do Microsoft Online Services, precisará instalá-lo no repositório do PowerShell com o `install-module MSOnline` cmdlet. Informações detalhadas para instalar e usar o Módulo do Microsoft Online Services podem ser encontradas no site do Microsoft 365. Essas instruções também explicam como configurar o single sign-on, a federação e a sincronização entre o Microsoft 365 ou o Office 365 e o Active Directory. 



Depois de configurar o Microsoft 365 ou o Office 365 e depois de criar entidades de serviço do Microsoft 365 ou Office 365 para o Skype for Business Server e o Exchange 2013, você precisará registrar suas credenciais com essas entidades de serviço. Para fazer isso, primeiro você deve obter um certificado Base64 X.509 salvo como um . Arquivo CER. Esse certificado será aplicado às entidades de serviço do Microsoft 365 ou Office 365.

Quando você tiver obtido o certificado X.509, abra o console do PowerShell e importe o módulo do Windows PowerShell do Microsoft Online que contém os cmdlets que podem ser usados para gerenciar entidades de serviço:

```PowerShell
Import-Module MSOnline
```

Quando o módulo tiver sido importado, digite o seguinte comando e pressione ENTER:

```PowerShell
Connect-MsolService
```

Depois de pressionar ENTER, uma caixa de diálogo de credenciais será exibida. Insira seu nome de usuário e senha do Microsoft 365 ou Office 365 na caixa de diálogo e clique em OK.

Assim que estiver conectado ao Microsoft 365 ou Ao Office 365, você poderá executar o seguinte comando para retornar informações sobre suas entidades de serviço:

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

A próxima etapa é importar, codificar e atribuir o certificado X.509. Para importar e codificar o certificado, use os seguintes comandos do Windows PowerShell, certificando-se de especificar o caminho completo do arquivo para o seu . Arquivo CER ao chamar o método Import:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

Depois que o certificado tiver sido importado e codificado, você poderá atribuir o certificado às entidades de serviço do Microsoft 365 ou Office 365. Para fazer isso, primeiro use o Get-MsolServicePrincipal para recuperar o valor da propriedade AppPrincipalId para o Skype for Business Server e as entidades de serviço do Microsoft Exchange; o valor da propriedade AppPrincipalId será usado para identificar a entidade de serviço que está sendo atribuída ao certificado. Com o valor da propriedade AppPrincipalId do Skype for Business Server em mãos, use o seguinte comando para atribuir o certificado à versão do Skype for Business Online:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Em seguida, você deve repetir o comando, desta vez usando o valor da propriedade AppPrincipalId para o Exchange 2013.

Se, mais tarde, você precisar excluir esse certificado, por exemplo, se ele tiver expirado, poderá fazer isso recuperando primeiro a KeyId do certificado:

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

Além de atribuir um certificado, você também deve configurar a Entidade de Serviço do Exchange Online e configurar sua versão local de URLs de serviços Web externos do Skype for Business Server como uma entidade de serviço do Microsoft 365 ou Office 365. Isso pode ser feito realizando os dois comandos a seguir. 

No exemplo a seguir, Pool1ExternalWebFQDN.contoso.com é a URL de serviços Web externos para o pool do Skype for Business Server. Você deve repetir essas etapas para adicionar todas as URLs de serviços Web externos na implantação.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
