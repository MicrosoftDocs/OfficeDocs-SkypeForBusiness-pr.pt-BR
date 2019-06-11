---
title: Habilitar o Exchange 2013 o Outlook Web App e a integração de mensagens instantâneas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69df3f33f0671d3014e90859fd39cc2b85f9558b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Habilitar o Exchange 2013 o Outlook Web App e a integração de mensagens instantâneas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Para habilitar o Exchange 2013 o Outlook Web Access (OWA) e a integração de mensagens instantâneas (IM) do Exchange com o Lync Server 2013, você deve adicionar o servidor Exchange 2013 cliente Access Server (CAS) à topologia do Lync Server 2013 como um servidor de aplicativos confiável.

<div>

## <a name="to-create-a-trusted-application-pool"></a>Para criar um pool de aplicativos confiável

1.  Inicie o Shell de gerenciamento do Lync Server 2013.

2.  Execute o seguinte cmdlet:
    
        Get-CsSite
    
    Isso retorna o siteid para o siteName no qual você está criando o pool. Para obter detalhes, consulte [Get-cssite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) na documentação do Shell de gerenciamento do Lync Server 2013.

3.  Execute o seguinte cmdlet:
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Para obter detalhes, consulte [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) na documentação do Shell de gerenciamento do Lync Server 2013.
    
    O FQDN do servidor Exchange deve ser configurado como o nome do requerente do certificado do OWA do Exchange (SN) ou o nome alternativo do assunto (SAN).
    
    Em Exchange OWA, verifique se o FQDN do pool também é confiável.
    
    <div>
    

    > [!IMPORTANT]  
    > Se o servidor CAS <EM>não</EM> estiver posicionado no mesmo servidor que está executando o Exchange 2013 Unified Messaging (um), pule as etapas restantes deste procedimento e execute o procedimento "criar um aplicativo confiável para o servidor Exchange 2013 CAS" mais adiante neste tópico. Se o servidor de CAS estiver posicionado no mesmo servidor que está executando o Exchange 2013 Unified Messaging (UM), conclua as etapas neste procedimento e não execute o procedimento "criar um aplicativo confiável para o servidor Exchange 2013 CAS" mais adiante neste tópico.

    
    </div>

4.  Execute **Enable-CsTopology**.

5.  Abra o construtor de topologias e baixe a topologia existente.

6.  No painel esquerdo, expanda a árvore até chegar a **servidores de aplicativos confiáveis**.

7.  Expanda o nó **servidores de aplicativos confiáveis** .

8.  Agora você deve ver o servidor CAS do Exchange 2013 listado como um servidor de aplicativos confiável.

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>Para criar um aplicativo confiável para o servidor CAS do Exchange 2013

1.  Inicie o Shell de gerenciamento do Lync Server 2013.

2.  Se o servidor CAS *não* estiver posicionado no mesmo servidor que está executando o Exchange 2013 Unified Messaging (um), execute o seguinte cmdlet:
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Para obter detalhes, consulte o tópico [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) na documentação do Shell de gerenciamento do Lync Server 2013.

3.  Execute **Enable-CsTopology**.

4.  No construtor de topologias, no painel esquerdo, expanda a árvore até chegar a **servidores de aplicativos confiáveis**.

5.  Expanda o nó **servidores de aplicativos confiáveis** .

6.  Agora você deve ver o servidor CAS do Exchange 2013 listado como um servidor de aplicativos confiável.

</div>

</div>

<span> </span>

</div>

</div>

</div>

