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
description: 'Resumo: configurar a autenticação de servidor para servidor para um ambiente híbrido do Skype for Business Server.'
ms.openlocfilehash: ed82e72c04d6fca0702a37819778d880b45ef617
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818833"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configurar a autenticação de servidor para servidor para um ambiente híbrido do Skype for Business Server.

**Resumo:** Configurar a autenticação de servidor para servidor para o ambiente híbrido do Skype for Business Server.

Em uma configuração híbrida, alguns dos seus usuários são hospedados em uma instalação local do Skype for Business Server enquanto outros usuários são hospedados na versão do Office 365 do Skype for Business Server. Para configurar a autenticação de servidor para servidor em um ambiente híbrido, você deve primeiro configurar a instalação local do Skype for Business Server para confiar no servidor de autorização do Office 365. A etapa inicial nesse processo pode ser executada executando o seguinte script do Shell de gerenciamento do Skype for Business Server:

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

Para executar esse script, você deve ter instalado o módulo do PowerShell do Skype for Business Online e conectar-se ao seu locatário com este módulo. Se você não tiver instalado esses cmdlets, seu script falhará porque o cmdlet Get-CsTenant não estará disponível. Depois que o script é concluído, você deve configurar uma relação de confiança entre o Skype for Business Server e o servidor de autorização e uma segunda relação de confiança entre o Exchange 2013/2016 e o servidor de autorização. Isso só pode ser feito usando cmdlets do Microsoft Online Services.

> [!NOTE]
> Se você não instalou os cmdlets do Microsoft Online Services, será necessário instalá-lo a partir do repositório do PowerShell com o `install-module MSOnline`cmdlet. Informações detalhadas sobre como instalar e usar o módulo do Microsoft Online Services podem ser encontradas no site do Office 365 na Web. Estas instruções também informarão como configurar o logon único, a Federação e a sincronização entre o Office 365 e o Active Directory. 



Depois de configurar o Office 365 e, após a criação de entidades de serviço do Office 365 para o Skype for Business Server e do Exchange 2013, será necessário registrar suas credenciais com essas entidades de serviço. Para fazer isso, primeiro você deve obter um certificado de base64 X. 509 salvo como um. Arquivo CER. Esse certificado será aplicado às entidades de serviço do Office 365.

Quando você tiver obtido o certificado X. 509, abra o console do PowerShell e importe o módulo Microsoft Online do Windows PowerShell que contém os cmdlets que podem ser usados para gerenciar as entidades do serviço:

```PowerShell
Import-Module MSOnline
```

Quando o módulo tiver sido importado, digite o seguinte comando e pressione ENTER para se conectar ao Office 365:

```PowerShell
Connect-MsolService
```

Depois de pressionar ENTER, uma caixa de diálogo de credenciais será exibida. Insira seu nome de usuário e senha do Office 365 na caixa de diálogo e, em seguida, clique em OK.

Assim que estiver conectado ao Office 365, você poderá executar o seguinte comando para retornar informações sobre as entidades do serviço:

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

A próxima etapa é importar, codificar e atribuir o certificado X.509. Para importar e codificar o certificado, use os seguintes comandos do Windows PowerShell, certifique-se de especificar o caminho de arquivo completo para o seu. Arquivo CER quando você chamar o método de importação:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

Depois que o certificado tiver sido importado e codificado, você poderá atribuir o certificado a seus dirigentes de serviço do Office 365. Para fazer isso, use o Get-MsolServicePrincipal para recuperar o valor da propriedade AppPrincipalId tanto para o Skype for Business Server quanto para as entidades de serviço do Microsoft Exchange; o valor da propriedade AppPrincipalId será usado para identificar a entidade de serviço ao qual o certificado está sendo atribuído. Com o valor da propriedade AppPrincipalId para o Skype for Business Server em mãos, use o seguinte comando para atribuir o certificado à versão do Skype for Business Online:

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Em seguida, você deve repetir o comando, desta vez usando o valor da propriedade AppPrincipalId para o Exchange 2013.

Se, posteriormente, você precisar excluir esse certificado, por exemplo, se ele tiver expirado, você pode fazê-lo primeiro recuperando o KeyId para o certificado:

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

Além de atribuir um certificado, você também deve configurar a entidade de serviço do Exchange Online e configurar sua versão local do Skype for Business Server URLs de serviços Web externos como uma entidade de serviço do Office 365. Isso pode ser feito executando os dois comandos a seguir: 

No exemplo a seguir, Pool1ExternalWebFQDN.contoso.com é a URL de serviços Web externos do pool do servidor do Skype for Business. Você deve repetir essas etapas para adicionar todas as URLs de serviços Web externos na implantação.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
