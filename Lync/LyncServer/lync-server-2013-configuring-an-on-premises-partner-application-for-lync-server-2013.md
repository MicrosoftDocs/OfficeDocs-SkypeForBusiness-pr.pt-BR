---
title: Configurando um aplicativo de parceiro local para o Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c396415dd6bd3bda99254f30b0223f1ff672a01f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a><span data-ttu-id="1816e-102">Configurando um aplicativo de parceiro local para o Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1816e-102">Configuring an on-premises partner application for Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1816e-103">_**Tópico da última modificação:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="1816e-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="1816e-104">Depois de atribuir o certificado OAuthTokenIssuer, você deve configurar os aplicativos de parceiros do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1816e-104">After you have assigned the OAuthTokenIssuer certificate you must then configure your Microsoft Lync Server 2013 partner applications.</span></span> <span data-ttu-id="1816e-105">(O procedimento a ser discutido configura o Microsoft Exchange Server 2013 e o Microsoft SharePoint para atuar como aplicativos de parceiros.) Para configurar um aplicativo de parceiro local, você deve começar copiando o seguinte script do Windows PowerShell e colando o código no bloco de notas (ou em qualquer outro editor de texto):</span><span class="sxs-lookup"><span data-stu-id="1816e-105">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and Microsoft SharePoint to act as partner applications.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>

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
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="1816e-106">Depois de copiar o código, salve o script usando um. A extensão de arquivo PS1 (por exemplo,\\C\\: scripts ServerToServerAuth. ps1).</span><span class="sxs-lookup"><span data-stu-id="1816e-106">After copying the code, save the script using a .PS1 file extension (for example, C:\\Scripts\\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="1816e-107">Observe que, antes de executar esse script, você deve substituir as URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 de metadados http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx e as URLs de metadados usadas por seus servidores do Exchange 2013 e do SharePoint, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="1816e-107">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="1816e-108">Consulte a documentação do produto do Exchange 2013 e do SharePoint para obter informações sobre como você pode identificar a URL de metadados do respectivo produto.</span><span class="sxs-lookup"><span data-stu-id="1816e-108">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>

<span data-ttu-id="1816e-109">Se você observar a última linha do script, perceberá que o cmdlet Set-CsOAuthConfiguration é chamado com o uso da sintaxe:</span><span class="sxs-lookup"><span data-stu-id="1816e-109">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="1816e-p103">Como o parâmetro Realm não foi usado para chamar Set-CsOAuthConfiguration, o realm automaticamente será definido como o FQDN (nome de domínio totalmente qualificado) de sua organização (por exemplo, litwareinc.com). Se o seu realm for diferente do nome da sua organização, inclua o nome do realm da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1816e-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

<span data-ttu-id="1816e-112">Depois de fazer essas alterações, você pode executar o script e configurar o Exchange 2013 e o SharePoint como aplicativos de parceiros executando o arquivo de script de dentro do Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1816e-112">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="1816e-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1816e-113">For example:</span></span>

    C:\Scripts\ServerToServerAuth.ps1

<span data-ttu-id="1816e-114">Observe que você pode executar esse script mesmo se não tiver o Exchange 2013 e o SharePoint Server instalados:, nenhum problema ocorrerá se você, digamos, configurar o SharePoint Server como um aplicativo de parceiro, mesmo que você não tenha o SharePoint Server instalado.</span><span class="sxs-lookup"><span data-stu-id="1816e-114">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>

<span data-ttu-id="1816e-115">Ao executar esse script, você talvez receba uma mensagem de erro semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="1816e-115">When you run this script you might receive an error message similar to the following:</span></span>

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

<span data-ttu-id="1816e-p105">Essa mensagem de erro geralmente significa que: 1) uma das URLs especificadas no script não é válida (ou seja, uma das URLs de metadados não é realmente uma URL de metadados); ou 2) não foi possível acessar uma das URLs de metadados. Se isso acontecer, verifique se as URLs estão corretas e acessíveis e execute o script novamente.</span><span class="sxs-lookup"><span data-stu-id="1816e-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>

<span data-ttu-id="1816e-118">Depois de criar o aplicativo parceiro para o Lync Server 2013, você deve configurar o Lync Server para ser um aplicativo de parceiro do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="1816e-118">After creating the partner application for Lync Server 2013 you must then configure Lync Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="1816e-119">Você pode configurar aplicativos de parceiros para o Exchange 2013 executando o script Configure-EnterprisePartnerApplication. ps1; Tudo o que você precisa fazer é especificar a URL de metadados do Lync Server e indicar que o Lync Server é o novo aplicativo de parceiro.</span><span class="sxs-lookup"><span data-stu-id="1816e-119">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Lync Server and indicate that Lync Server is the new partner application.</span></span>

<span data-ttu-id="1816e-120">Para configurar o Lync Server como um aplicativo parceiro para Exchange, abra o Shell de gerenciamento do Exchange e execute um comando semelhante a este</span><span class="sxs-lookup"><span data-stu-id="1816e-120">To configure Lync Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

