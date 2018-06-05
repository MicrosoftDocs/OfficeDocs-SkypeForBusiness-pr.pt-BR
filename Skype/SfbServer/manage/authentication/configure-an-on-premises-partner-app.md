---
title: Configurar um aplicativo de parceiro local para o Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Resumo: Configure um aplicativo de parceiro no local para Skype para Business Server 2015.'
ms.openlocfilehash: 2f13196288fb7b609e5e3d39996c12eab04493dc
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569446"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server-2015"></a>Configurar um aplicativo de parceiro local para o Skype for Business Server 2015
 
**Resumo:** Configure um aplicativo de parceiro no local para Skype para Business Server 2015.
  
Depois que você atribuiu o certificado OAuthTokenIssuer, em seguida, você deve configurar seu Skype para aplicativos de parceiros de negócios Server 2015. (O procedimento prestes a ser abordadas configura tanto Microsoft Exchange Server 2013 e SharePoint para agir como aplicativos de parceiros, que é opcional.) Para configurar um aplicativo de parceiro no local, você deve iniciar o seguinte script do Windows PowerShell de copiando e colando o código no bloco de notas (ou qualquer outro editor de texto):
  
```
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

Depois de copiar o código, salve o script usando a extensão de arquivo .PS1 (por exemplo, C:\Scripts\ServerToServerAuth.ps1). Observe que, antes de executar esse script, você deve substituir as URLs de metadados https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 e http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 com as URLs de metadados usadas pelos seus servidores Exchange 2013 e SharePoint, respectivamente. Consulte a documentação do produto para o Exchange 2013 e SharePoint para obter informações sobre como você pode identificar a URL de metadados do respectivo produto.
  
Se você observar a última linha do script, perceberá que o cmdlet Set-CsOAuthConfiguration é chamado com o uso da sintaxe:
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Como o parâmetro Realm não foi usado para chamar Set-CsOAuthConfiguration, o realm automaticamente será definido como o FQDN (nome de domínio totalmente qualificado) de sua organização (por exemplo, litwareinc.com). Se o seu realm for diferente do nome da sua organização, inclua o nome do realm da seguinte maneira:
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

Depois de fazer essas alterações, em seguida, você pode executar o script e configure o Exchange 2013 e SharePoint como aplicativos de parceiros, executando-se o arquivo de script de dentro do Skype do Shell de gerenciamento do servidor de negócios. Por exemplo:
  
```
C:\Scripts\ServerToServerAuth.ps1
```

Observe que você pode executar esse script, mesmo se você não tem ambas Exchange 2013 e SharePoint Server instalado:, nenhum problema ocorrerá se você, digamos, configurar o SharePoint Server como um aplicativo de parceiro, embora você não tiver instalado o SharePoint Server.
  
Ao executar esse script, você talvez receba uma mensagem de erro semelhante à seguinte:
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

Essa mensagem de erro geralmente significa que: 1) uma das URLs especificadas no script não é válida (ou seja, uma das URLs de metadados não é realmente uma URL de metadados); ou 2) não foi possível acessar uma das URLs de metadados. Se isso acontecer, verifique se as URLs estão corretas e acessíveis e execute o script novamente.
  
Depois de criar o aplicativo de parceiro do Skype para Business Server 2015, em seguida, configure Skype para Business Server seja um aplicativo parceiro do Exchange 2013. Você pode configurar aplicativos de parceiros para o Exchange 2013 executando o script Configure-EnterprisePartnerApplication.ps1; tudo o que você precisa fazer é especificar a URL de metadados de Skype para Business Server e indicar que o Skype para Business Server é o novo aplicativo de parceiro. 
  
Para configurar o Skype para Business Server como um aplicativo de parceiro do Exchange, abra o Shell de gerenciamento do Exchange e execute um comando semelhante ao seguinte
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


