---
title: Configurar um aplicativo de parceiro no local para Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Resumo: Configure um aplicativo de parceiro no local para Skype para Business Server.'
ms.openlocfilehash: fe80ae08a730ad4765c366a77fd0c44daaa18899
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878477"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a><span data-ttu-id="2b082-103">Configurar um aplicativo de parceiro no local para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="2b082-103">Configure an on-premises partner application for Skype for Business Server</span></span>
 
<span data-ttu-id="2b082-104">**Resumo:** Configure um aplicativo de parceiro no local para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="2b082-104">**Summary:** Configure an on-premises partner application for Skype for Business Server.</span></span>
  
<span data-ttu-id="2b082-105">Depois que você atribuiu o certificado OAuthTokenIssuer, em seguida, você deve configurar seu Skype para aplicativos de parceiros de negócios Server.</span><span class="sxs-lookup"><span data-stu-id="2b082-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Skype for Business Server partner applications.</span></span> <span data-ttu-id="2b082-106">(O procedimento prestes a ser abordadas configura tanto Microsoft Exchange Server 2013 e SharePoint para agir como aplicativos de parceiros, que é opcional.) Para configurar um aplicativo de parceiro no local, você deve iniciar o seguinte script do Windows PowerShell de copiando e colando o código no bloco de notas (ou qualquer outro editor de texto):</span><span class="sxs-lookup"><span data-stu-id="2b082-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and SharePoint to act as partner applications, which is optional.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>
  
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

<span data-ttu-id="2b082-107">Depois de copiar o código, salve o script usando a extensão de arquivo .PS1 (por exemplo, C:\Scripts\ServerToServerAuth.ps1).</span><span class="sxs-lookup"><span data-stu-id="2b082-107">After copying the code, save the script using a .PS1 file extension (for example, C:\Scripts\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="2b082-108">Observe que, antes de executar esse script, você deve substituir as URLs de metadados https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 e http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 com as URLs de metadados usadas pelos seus servidores Exchange 2013 e SharePoint, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="2b082-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="2b082-109">Consulte a documentação do produto para o Exchange 2013 e SharePoint para obter informações sobre como você pode identificar a URL de metadados do respectivo produto.</span><span class="sxs-lookup"><span data-stu-id="2b082-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>
  
<span data-ttu-id="2b082-110">Se você observar a última linha do script, perceberá que o cmdlet Set-CsOAuthConfiguration é chamado com o uso da sintaxe:</span><span class="sxs-lookup"><span data-stu-id="2b082-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="2b082-p103">Como o parâmetro Realm não foi usado para chamar Set-CsOAuthConfiguration, o realm automaticamente será definido como o FQDN (nome de domínio totalmente qualificado) de sua organização (por exemplo, litwareinc.com). Se o seu realm for diferente do nome da sua organização, inclua o nome do realm da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2b082-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

<span data-ttu-id="2b082-113">Depois de fazer essas alterações, em seguida, você pode executar o script e configure o Exchange 2013 e SharePoint como aplicativos de parceiros, executando-se o arquivo de script de dentro do Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="2b082-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="2b082-114">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2b082-114">For example:</span></span>
  
```
C:\Scripts\ServerToServerAuth.ps1
```

<span data-ttu-id="2b082-115">Observe que você pode executar esse script, mesmo se você não tem ambas Exchange 2013 e SharePoint Server instalado:, nenhum problema ocorrerá se você, digamos, configurar o SharePoint Server como um aplicativo de parceiro, embora você não tiver instalado o SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="2b082-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>
  
<span data-ttu-id="2b082-116">Ao executar esse script, você talvez receba uma mensagem de erro semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="2b082-116">When you run this script you might receive an error message similar to the following:</span></span>
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

<span data-ttu-id="2b082-p105">Essa mensagem de erro geralmente significa que: 1) uma das URLs especificadas no script não é válida (ou seja, uma das URLs de metadados não é realmente uma URL de metadados); ou 2) não foi possível acessar uma das URLs de metadados. Se isso acontecer, verifique se as URLs estão corretas e acessíveis e execute o script novamente.</span><span class="sxs-lookup"><span data-stu-id="2b082-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>
  
<span data-ttu-id="2b082-119">Depois de criar o aplicativo de parceiro do Skype para Business Server, você deve configurar então Skype para Business Server seja um aplicativo parceiro do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2b082-119">After creating the partner application for Skype for Business Server you must then configure Skype for Business Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="2b082-120">Você pode configurar aplicativos de parceiros para o Exchange 2013 executando o script Configure-EnterprisePartnerApplication.ps1; tudo o que você precisa fazer é especificar a URL de metadados de Skype para Business Server e indicar que o Skype para Business Server é o novo aplicativo de parceiro.</span><span class="sxs-lookup"><span data-stu-id="2b082-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Skype for Business Server and indicate that Skype for Business Server is the new partner application.</span></span> 
  
<span data-ttu-id="2b082-121">Para configurar o Skype para Business Server como um aplicativo de parceiro do Exchange, abra o Shell de gerenciamento do Exchange e execute um comando semelhante ao seguinte</span><span class="sxs-lookup"><span data-stu-id="2b082-121">To configure Skype for Business Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


