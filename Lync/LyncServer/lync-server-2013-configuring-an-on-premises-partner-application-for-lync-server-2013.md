---
title: Configurando um aplicativo de parceiro local para o Lync Server 2013
description: Configurando um aplicativo de parceiro local para o Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0401634c6cb7afc451652ffbaf55cdc01a7ca89
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570917"
---
# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a>Configurando um aplicativo de parceiro local para o Microsoft Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-04_

Após ter atribuído o certificado OAuthTokenIssuer, você deve configurar seus aplicativos de parceiro do Microsoft Lync Server 2013. (O procedimento a ser discutido configura o Microsoft Exchange Server 2013 e o Microsoft SharePoint para atuar como aplicativos de parceiros.) Para configurar um aplicativo de parceiro local, você deve começar copiando o seguinte script do Windows PowerShell e colando o código no bloco de notas (ou qualquer outro editor de texto):

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

Depois de copiar o código, salve o script usando um. A extensão de arquivo PS1 (por exemplo, C: \\ Scripts \\ServerToServerAuth.ps1). Observe que, antes de executar esse script, você deve substituir as URLs de metadados https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 e http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx com as URLs de metadados usadas pelos seus servidores do Exchange 2013 e do SharePoint, respectivamente. Consulte a documentação do produto do Exchange 2013 e do SharePoint para obter informações sobre como você pode identificar a URL de metadados do respectivo produto.

Se você observar a última linha do script, perceberá que o cmdlet Set-CsOAuthConfiguration é chamado com o uso da sintaxe:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Como o parâmetro Realm não foi usado para chamar Set-CsOAuthConfiguration, o realm automaticamente será definido como o FQDN (nome de domínio totalmente qualificado) de sua organização (por exemplo, litwareinc.com). Se o seu realm for diferente do nome da sua organização, inclua o nome do realm da seguinte maneira:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

Depois de fazer essas alterações, você pode executar o script e configurar o Exchange 2013 e o SharePoint como aplicativos de parceiro executando o arquivo de script de dentro do Shell de gerenciamento do Lync Server 2013. Por exemplo:

    C:\Scripts\ServerToServerAuth.ps1

Observe que você pode executar esse script mesmo se não tiver o Exchange 2013 e o SharePoint Server instalados:, nenhum problema ocorrerá se você, diga, configure o SharePoint Server como um aplicativo parceiro, mesmo que você não tenha o SharePoint Server instalado.

Ao executar esse script, você talvez receba uma mensagem de erro semelhante à seguinte:

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

Essa mensagem de erro geralmente significa que: 1) uma das URLs especificadas no script não é válida (ou seja, uma das URLs de metadados não é realmente uma URL de metadados); ou 2) não foi possível acessar uma das URLs de metadados. Se isso acontecer, verifique se as URLs estão corretas e acessíveis e execute o script novamente.

Depois de criar o aplicativo parceiro para o Lync Server 2013, você deve configurar o Lync Server para ser um aplicativo parceiro para o Exchange 2013. Você pode configurar aplicativos parceiros para o Exchange 2013 executando o script Configure-EnterprisePartnerApplication.ps1; Tudo o que você precisa fazer é especificar a URL de metadados para o Lync Server e indicar que o Lync Server é o novo aplicativo de parceiro.

Para configurar o Lync Server como um aplicativo parceiro para o Exchange, abra o Shell de gerenciamento do Exchange e execute um comando semelhante a este

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

