---
title: Configurar um aplicativo parceiro local para o Skype for Business Server
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
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Resumo: Configurar um aplicativo parceiro local para o Skype for Business Server.'
ms.openlocfilehash: 82db666dbbd94fdae8a99bca13954d33d6d5805f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828431"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>Configurar um aplicativo parceiro local para o Skype for Business Server
 
**Resumo:** Configurar um aplicativo parceiro local para o Skype for Business Server.
  
Depois de ter atribuído o certificado OAuthTokenIssuer, você deve configurar seus aplicativos parceiros do Skype for Business Server. (O procedimento a ser discutido configura o Microsoft Exchange Server 2013 e o SharePoint para agir como aplicativos parceiros, o que é opcional.) Para configurar um aplicativo parceiro local, você deve começar copiando o seguinte script do Windows PowerShell e copiando o código no Bloco de Notas (ou em qualquer outro editor de texto):
  
```PowerShell
if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
   {
       Remove-CsPartnerApplication app
   }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
        
if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
           }
     }

$shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
        
if ($shp -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
    }
else
    {
       if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.sharepoint
  
             New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl https://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
            }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Depois de copiar o código, salve o script usando a extensão de arquivo .PS1 (por exemplo, C:\Scripts\ServerToServerAuth.ps1). Observe que, antes de executar esse script, você deve substituir as URLs de metadados e as URLs de metadados usadas pelos servidores https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 do Exchange 2013 e do SharePoint, respectivamente. Consulte a documentação do produto para o Exchange 2013 e o SharePoint para obter informações sobre como identificar a URL de metadados do respectivo produto.
  
Se você observar a última linha do script, perceberá que o cmdlet Set-CsOAuthConfiguration é chamado com o uso da sintaxe:
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Como o parâmetro Realm não foi usado para chamar Set-CsOAuthConfiguration, o realm automaticamente será definido como o FQDN (nome de domínio totalmente qualificado) de sua organização (por exemplo, litwareinc.com). Se o seu realm for diferente do nome da sua organização, inclua o nome do realm da seguinte maneira:
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

Depois de fazer essas alterações, você poderá executar o script e configurar o Exchange 2013 e o SharePoint como aplicativos parceiros executando o arquivo de script de dentro do Shell de Gerenciamento do Skype for Business Server. Por exemplo:
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

Observe que você pode executar esse script mesmo se não tiver o Exchange 2013 e o SharePoint Server instalados:, nenhum problema ocorrerá se você, digamos, configurar o SharePoint Server como um aplicativo parceiro, mesmo que você não tenha o SharePoint Server instalado.
  
Ao executar esse script, você talvez receba uma mensagem de erro semelhante à seguinte:
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

Essa mensagem de erro geralmente significa que: 1) uma das URLs especificadas no script não é válida (ou seja, uma das URLs de metadados não é realmente uma URL de metadados); ou 2) não foi possível acessar uma das URLs de metadados. Se isso acontecer, verifique se as URLs estão corretas e acessíveis e execute o script novamente.
  
Depois de criar o aplicativo parceiro para o Skype for Business Server, você deve configurar o Skype for Business Server para ser um aplicativo parceiro do Exchange 2013. Você pode configurar aplicativos parceiros para o Exchange 2013 executando o script Configure-EnterprisePartnerApplication.ps1; Tudo o que você precisa fazer é especificar a URL de metadados do Skype for Business Server e indicar que o Skype for Business Server é o novo aplicativo parceiro. 
  
Para configurar o Skype for Business Server como um aplicativo parceiro do Exchange, abra o Shell de Gerenciamento do Exchange e execute um comando semelhante a este
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


