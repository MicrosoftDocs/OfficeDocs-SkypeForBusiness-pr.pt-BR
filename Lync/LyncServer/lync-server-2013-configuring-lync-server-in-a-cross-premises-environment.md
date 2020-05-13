---
title: 'Lync Server 2013: Configurando o Lync Server em um ambiente entre locais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dcbdb7ac12dcb8fc768a1f9e537622d01191b8f
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>Configurando o Microsoft Lync Server 2013 em um ambiente entre locais

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2017-02-21_

Em uma configuração entre instalações, alguns dos seus usuários são hospedados em uma instalação local do Microsoft Lync Server 2013 enquanto outros usuários são hospedados na versão Microsoft 365 ou Office 365 do Lync Server. Para configurar a autenticação de servidor para servidor em um ambiente entre locais, primeiro você deve configurar a instalação local do Lync Server 2013 para confiar no servidor de autorização da Microsoft 365. A etapa inicial desse processo pode ser executada executando o seguinte script do Shell de gerenciamento do Lync Server:

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

Tenha em mente que o nome do realm de um locatário é normalmente diferente do nome da organização; na realidade, o nome do realm é quase sempre igual ao do ID do locatário. Por causa disso, a primeira linha do script é usada para retornar o valor da propriedade TenantId do locatário especificado (neste caso, fabrikam.com) e atribuir o nome à variável $TenantId:

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

Após a conclusão do script, você deve configurar uma relação de confiança entre o Lync Server 2013 e o servidor de autorização e uma segunda relação de confiança entre o Exchange 2013 e o servidor de autorização. Isso só pode ser feito usando os cmdlets do Microsoft Online Services.

<div>


> [!NOTE]  
> Caso não tenha instalado os cmdlets do Microsoft Online Services, será necessário fazer duas coisas antes de continuar. Primeiro, baixe e instale a versão de 64 bits do Assistente de Conexão do Microsoft Online Services. Após a conclusão da instalação, baixe e instale a versão de 64 bits do módulo do Microsoft Online Services para Windows PowerShell. Informações detalhadas sobre a instalação e o uso do módulo do Microsoft Online Services podem ser encontradas no site do Microsoft 365 ou do Office 365. Essas instruções também informarão como configurar o logon único, a Federação e a sincronização entre o Microsoft 365 ou o Office 36 e o Active Directory.<BR>Se você não tiver instalado esses cmdlets, seu script falhará porque o cmdlet Get-CsTenant não estará disponível.



</div>

Depois de ter configurado o Microsoft 365 e depois de ter criado as entidades de serviço do Microsoft 365 ou do Office 365 para Lync Server 2013 e Exchange 2013, você precisará registrar suas credenciais com essas entidades de serviço. Para isso, primeiro você deve obter um certificado X.509 Base64 salvo como um arquivo .CER. Esse certificado será então aplicado às entidades de serviço do Microsoft 365 ou do Office 365.

Quando tiver obtido o certificado X. 509, inicie o módulo do Microsoft Online Services (clique em **Iniciar**, em **todos os programas**, em **Microsoft Online Services**e em **Microsoft Online Services Module for Windows PowerShell**). Depois que o módulo de serviços for aberto, digite o seguinte para importar o módulo Microsoft Online Windows PowerShell contendo os cmdlets que podem ser usados para gerenciar entidades de serviço:

    Import-Module MSOnlineExtended

Após a importação do módulo, digite o seguinte comando e pressione ENTER para se conectar ao Microsoft 365:

    Connect-MsolService

Depois de pressionar ENTER, uma caixa de diálogo de credenciais será exibida. Insira seu nome de usuário e senha do Microsoft 365 ou do Office 365 na caixa de diálogo e clique em OK.

Assim que estiver conectado ao Microsoft 365, você poderá executar o comando a seguir para retornar informações sobre as entidades de serviço:

    Get-MsolServicePrincipal

Você deverá obter informações semelhantes a estas para todas as entidades de serviço:

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

A próxima etapa é importar, codificar e atribuir o certificado X.509. Para importar e codificar o certificado, use os seguintes comandos do Windows PowerShell, certifique-se de especificar o caminho completo do arquivo para o. Arquivo CER ao chamar o método Import:

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

Após o certificado ter sido importado e codificado, você poderá atribuí-lo às suas entidades de serviço do Microsoft 365. Para isso, use primeiro Get-MsolServicePrincipal a fim de recuperar o valor da propriedade AppPrincipalId para as entidades de serviço do Lync Server e do Microsoft Exchange; o valor da propriedade AppPrincipalId será usado para identificar a entidade de serviço atribuída ao certificado. Com o valor da propriedade AppPrincipalId para o Lync Server 2013 disponível, use o comando a seguir para atribuir o certificado à versão 365 da Microsoft do Lync Server (as propriedades StartDate e EndDate devem corresponder ao período de validade do certificado):

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

Em seguida, você deve repetir o comando, desta vez usando o valor da propriedade AppPrincipalId para o Exchange 2013.

Caso precise excluir o certificado posteriormente, faça isso recuperando KeyId do certificado primeiro:

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

O comando retornará dados como estes:

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

Você pode excluir o certificado usando um comando semelhante a este:

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

Além de atribuir um certificado, você também deve configurar o Microsoft 365 Service principal para o Exchange Online adicionando o nome principal do servidor para sua versão local do Lync Server 2013. Isso pode ser feito executando as quatro linhas a seguir em uma sessão do Microsoft Online Services PowerShell:

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

