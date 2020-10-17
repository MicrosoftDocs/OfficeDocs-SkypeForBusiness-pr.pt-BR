---
title: Habilitar o Exchange 2013 Outlook Web App e integração de IM
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da6866565df12ff4484124836f9164d2bf8c35c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502878"
---
# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Habilitar o Exchange 2013 Outlook Web App e integração de IM

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Para habilitar o Exchange 2013 Outlook Web Access (OWA) e a integração de mensagens instantâneas (IM) com o Lync Server 2013, você deve adicionar o servidor do Exchange 2013 servidor de acesso para cliente (CAS) à topologia 2013 do Lync Server como um servidor de aplicativos confiável.

<div>

## <a name="to-create-a-trusted-application-pool"></a>Para criar um pool de aplicativos confiáveis

1.  Inicie o Shell de gerenciamento do Lync Server 2013.

2.  Execute o seguinte cmdlet:
    
        Get-CsSite
    
    Isso retorna siteID para o siteName no qual você está criando o pool. Para obter detalhes, consulte [Get-cssite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) na documentação do Shell de gerenciamento do Lync Server 2013.

3.  Execute o seguinte cmdlet:
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Para obter detalhes, consulte [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) na documentação do Shell de gerenciamento do Lync Server 2013.
    
    O Exchange Server FQDN deve ser configurado como o certificado Exchange OWA do Nome da Entidade (SN) ou Nome Alternativo de Entidade (SAN).
    
    No Exchange OWA, verifique se o pool do FQDN também é confiável.
    
    <div>
    

    > [!IMPORTANT]  
    > Se o servidor CAS <EM>não</EM> estiver posicionado no mesmo servidor que está executando a Unificação de mensagens (um) do Exchange 2013, pule as etapas restantes deste procedimento e execute o procedimento "criar um aplicativo confiável para o servidor do Exchange 2013 CAS" mais adiante neste tópico. Se o servidor CAS estiver posicionado no mesmo servidor que está executando a Unificação de mensagens (UM) do Exchange 2013, conclua as etapas deste procedimento e não execute o procedimento "criar um aplicativo confiável para o servidor do Exchange 2013 CAS" mais adiante neste tópico.

    
    </div>

4.  Execute **Enable-CsTopology**.

5.  Abra o Construtor de Topologia e baixe a topologia existente.

6.  No painel à esquerda, expanda a árvore até chegar em **Servidores de aplicativos confiáveis**.

7.  Expanda o nó **Servidores de aplicativo confiáveis**.

8.  Agora você deve ver o servidor CAS do Exchange 2013 listado como um servidor de aplicativos confiável.

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>Para criar um aplicativo confiável para o servidor CAS do Exchange 2013

1.  Inicie o Shell de gerenciamento do Lync Server 2013.

2.  Se o servidor CAS *não* estiver posicionado no mesmo servidor que está executando a Unificação de mensagens (um) do Exchange 2013, execute o seguinte cmdlet:
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Para obter detalhes, consulte o tópico [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) na documentação do Shell de gerenciamento do Lync Server 2013.

3.  Execute **Enable-CsTopology**.

4.  Do Construtor de Topologia, no painel à esquerda, expanda a árvore até chegar em **Servidores de aplicativos confiáveis**.

5.  Expanda o nó **Servidores de aplicativos confiáveis**.

6.  Agora você deve ver o servidor CAS do Exchange 2013 listado como um servidor de aplicativos confiável.

</div>

</div>

<span> </span>

</div>

</div>

</div>

