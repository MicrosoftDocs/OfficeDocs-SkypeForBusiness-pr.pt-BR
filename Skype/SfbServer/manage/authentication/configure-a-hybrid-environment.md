---
title: Configurar a autenticação de servidor para servidor para um ambiente híbrido do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 6cc408677af4629d36b577da4ae38cd420195483
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221675"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configure a autenticação de servidor para servidor para um ambiente híbrido do Skype for Business Server.

**Resumo:** Configurar a autenticação de servidor para servidor para o ambiente híbrido do Skype for Business Server.

Em uma configuração híbrida, alguns dos seus usuários estão hospedados em uma instalação local do Skype for Business Server enquanto outros usuários estão hospedados na versão do Microsoft 365 ou do Office 365 do Skype for Business Server. Para configurar a autenticação de servidor para servidor em um ambiente híbrido, primeiro você deve configurar a instalação local do Skype for Business Server para confiar no servidor de autorização. A etapa inicial desse processo pode ser executada executando o seguinte script do Shell de gerenciamento do Skype for Business Server:

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

Para executar esse script, você deve ter instalado o módulo PowerShell do Skype for Business Online e se conectar ao seu locatário com este módulo. Se você não tiver instalado esses cmdlets, seu script falhará porque o cmdlet Get-CsTenant não estará disponível. Após a conclusão do script, você deve configurar uma relação de confiança entre o Skype for Business Server e o servidor de autorização e uma segunda relação de confiança entre o Exchange 2013/2016 e o servidor de autorização. Isso só pode ser feito usando os cmdlets do Microsoft Online Services.

> [!NOTE]
> Se você não tiver instalado os cmdlets do Microsoft Online Services, será necessário instalá-lo no repositório do PowerShell com o cmdlet `install-module MSOnline` . Informações detalhadas sobre a instalação e o uso do módulo do Microsoft Online Services podem ser encontradas no site da Microsoft 365. Essas instruções também informarão como configurar o logon único, a Federação e a sincronização entre o Microsoft 365 ou o Office 365 e o Active Directory. 



Depois de ter configurado o Microsoft 365 ou o Office 365, e depois de ter criado as entidades de serviço do Microsoft 365 ou do Office 365 para o Skype for Business Server e o Exchange 2013, você precisará registrar suas credenciais com essas entidades de serviço. Para fazer isso, primeiro você deve obter um certificado de base64 X. 509 salvo como um. Arquivo CER. Esse certificado será então aplicado às entidades de serviço do Microsoft 365 ou do Office 365.

Quando você tiver obtido o certificado X. 509, abra o console do PowerShell e importe o módulo Microsoft Online Windows PowerShell contendo os cmdlets que podem ser usados para gerenciar entidades de serviço:

```PowerShell
Import-Module MSOnline
```

Após a importação do módulo, digite o seguinte comando e pressione ENTER:

```PowerShell
Connect-MsolService
```

Depois de pressionar ENTER, uma caixa de diálogo de credenciais será exibida. Insira seu nome de usuário e senha do Microsoft 365 ou do Office 365 na caixa de diálogo e clique em OK.

Assim que estiver conectado ao Microsoft 365 ou ao Office 365, você poderá executar o comando a seguir para retornar informações sobre as entidades de serviço:

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

A próxima etapa é importar, codificar e atribuir o certificado X.509. Para importar e codificar o certificado, use os seguintes comandos do Windows PowerShell, certifique-se de especificar o caminho completo do arquivo para o. Arquivo CER ao chamar o método Import:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

Após o certificado ter sido importado e codificado, você pode atribuir o certificado à sua entidade de serviço do Microsoft 365 ou do Office 365. Para fazer isso, primeiro use o Get-MsolServicePrincipal para recuperar o valor da propriedade AppPrincipalId para o Skype for Business Server e as entidades de serviço do Microsoft Exchange; o valor da propriedade AppPrincipalId será usado para identificar a entidade de serviço à qual o certificado está sendo atribuído. Com o valor da propriedade AppPrincipalId para o Skype for Business Server em mãos, use o comando a seguir para atribuir o certificado à versão do Skype for Business Online:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Em seguida, você deve repetir o comando, desta vez usando o valor da propriedade AppPrincipalId para o Exchange 2013.

Se, posteriormente, você precisar excluir esse certificado, por exemplo, se ele tiver expirado, você pode fazer isso recuperando o KeyId para o certificado:

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

Além de atribuir um certificado, você também deve configurar a entidade de serviço do Exchange Online e configurar sua versão local de URLs de serviços Web externos do Skype for Business Server como uma entidade de serviço do Microsoft 365 ou do Office 365. Isso pode ser feito executando os dois comandos a seguir. 

No exemplo a seguir, Pool1ExternalWebFQDN.contoso.com é a URL de serviços Web externos para o pool do Skype for Business Server. Você deve repetir essas etapas para adicionar todas as URLs de serviços Web externos na implantação.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
