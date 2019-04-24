---
title: Configurar a autenticação de servidor-para-servidor para um Skype para um ambiente híbrido do Business Server
ms.reviewer: ''
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
ms.openlocfilehash: d8ba920d516368d1931097e5e31b738a0d271bcf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211015"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>Configure a autenticação de servidor-para-servidor para um Skype para um ambiente híbrido do Business Server.

**Resumo:** Configure a autenticação de servidor-para-servidor para Skype para um ambiente híbrido do Business Server.

Em uma configuração híbrida, alguns dos usuários hospedados em uma instalação local do Skype para Business Server enquanto outros usuários estão hospedados na versão do Office 365 do Skype para Business Server. Para configurar uma autenticação servidor-para-servidor em um ambiente híbrido, você deve primeiro configurar sua instalação do local do Skype para Business Server confiar no servidor de autorização do Office 365. A etapa inicial nesse processo pode ser realizada executando a seguinte Skype para script do Shell de gerenciamento do servidor de negócios:

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

Tenha em mente que o nome do realm de um locatário é normalmente diferente do nome da organização; na realidade, o nome do realm é quase sempre igual ao do ID do locatário. Por causa disso, a primeira linha do script é usada para retornar o valor da propriedade TenantId do locatário especificado (neste caso, fabrikam.com) e atribuir o nome à variável $TenantId:

```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

Para executar esse script, você deve ter instalado o Skype para o módulo de Powershell Online de negócios e conecte-se ao seu locatário com esse módulo. Se você não tiver instalado esses cmdlets, seu script falhará porque o cmdlet Get-CsTenant não estará disponível. Quando o script for concluída, em seguida, você deve configurar uma relação de confiança entre Skype para Business Server e o servidor de autorização e uma segunda relação de confiança entre o Exchange 2013/2016 e o servidor de autorização. Isso só pode ser feito usando os cmdlets do Microsoft Online Services.

> [!NOTE]
> Se você não tiver instalado os cmdlets do Microsoft Online Services, você precisará instalá-lo do repositório do powershell com o cmdlet install-módulo MSOnline. Informações detalhadas sobre como instalar e usar o módulo do Microsoft Online Services podem ser encontradas no site do Office 365. Estas instruções também informará como configurar o serviço single sign-on, Federação e a sincronização entre o Office 365 e o Active Directory. 



Depois que você configurou o Office 365 e depois de ter criado Office 365 entidades de serviço para Skype para Business Server e o Exchange 2013, será necessário registrar suas credenciais com essas entidades de serviço. Para isso, primeiro você deve obter um certificado X.509 Base64 salvo como arquivo .CER. Esse certificado, em seguida, será aplicado para as entidades de serviço do Office 365.

Quando você tiver obtido o certificado x. 509, abra o console do Powershell e importar o módulo do Microsoft Online Windows PowerShell que contém os cmdlets que pode ser usados para gerenciar as entidades de serviço:

```
Import-Module MSOnline
```

Quando o módulo foi importado, digite o seguinte comando e pressione ENTER para conectar ao Office 365:

```
Connect-MsolService
```

Depois de pressionar ENTER, uma caixa de diálogo de credenciais será exibida. Insira seu nome de usuário do Office 365 e a senha na caixa de diálogo e clique em Okey.

Assim que você estiver conectado ao Office 365, você pode, em seguida, execute o seguinte comando para retornar informações sobre as entidades de serviço:

```
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

A próxima etapa é importar, codificar e atribuir o certificado X.509. Para importar e codificar o certificado, use os seguintes comandos do Windows PowerShell, certificando-se de especificar o caminho completo do arquivo para sua. Arquivo CER quando você chama o método Import:

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

Depois que o certificado foi importado e codificado, você pode atribuir o certificado para as entidades de serviço do Office 365. Para fazer isso, primeiro usar o Get-MsolServicePrincipal para recuperar o valor da propriedade AppPrincipalId para o Skype para Business Server e as entidades de serviço do Microsoft Exchange; o valor da propriedade AppPrincipalId será usado para identificar a entidade de serviço que está sendo atribuída o certificado. Com o AppPrincipalId propriedade valor do Skype para Business Server lado, use o seguinte comando para atribuir o certificado para a versão Skype para Business Online:

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

Você deve repetir o comando, desta vez usando o valor da propriedade AppPrincipalId para o Exchange 2013.

Se você precisar excluir o certificado, por exemplo, se ele tiver expirado, posteriormente, você pode fazer isso primeiro recuperando KeyId do certificado:

```
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

```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

Além de atribuir um certificado, você também deve configurar a entidade de serviço Online do Exchange e configurar sua versão do local do Skype para URLs de serviços Web externos Business Server como uma entidade de serviço do Office 365. Isso pode ser feito executando os dois comandos a seguir: 

No exemplo a seguir, Pool1ExternalWebFQDN.contoso.com é a URL externa de serviços Web para o Skype para pool de servidores de negócios. Você deve repetir essas etapas para adicionar todas as Web services URLs externas na implantação.

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
