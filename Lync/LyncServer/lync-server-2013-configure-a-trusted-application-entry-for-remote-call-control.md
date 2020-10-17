---
title: Configurar uma entrada de aplicativo confiável para controle de chamada remota
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f8175a351d13675c048efce7a2f831af7ab2c31
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523058"
---
# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a>Configurar uma entrada de aplicativo confiável para controle de chamada remota no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-11-02_

O gateway SIP/CSTA deve ser configurado como um aplicativo confiável para que o Lync Server aplique uma rota estática para chamadas de roteamento para o gateway.

<div>


> [!IMPORTANT]
> Se você estiver migrando usuários de uma versão anterior da implantação do Lync Server, remova todas as entradas de aplicativos confiáveis existentes (anteriormente conhecidas como entradas de host autorizadas) que você criou para o gateway SIP/CSTA antes de seguir os procedimentos deste tópico. Para obter detalhes, consulte <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">remover um host autorizado herdado no Lync Server 2013 (opcional)</A>.<BR>Se você planeja implantar o novo controle de chamada remota usando uma conexão TCP (Transmission Control Protocol), será necessário verificar se o <STRONG>uso do serviço de limite para endereços IP selecionados</STRONG> deve ser definido em pools e aplicativos confiáveis existentes, se você quiser usar a mesma porta TCP para o novo aplicativo confiável.



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a>Para configurar uma entrada de aplicativo confiável para o gateway SIP/CSTA

1.  Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou de uma função RBAC (controle de acesso baseado em função) para a qual você atribuiu o cmdlet **New-CsTrustedApplicationPool** .

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Para criar uma entrada de aplicativo confiável, siga um destes procedimentos:
    
      - Para uma conexão TLS, digite o seguinte no prompt de comando:
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Por exemplo:
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - Para uma conexão TCP, digite o seguinte no prompt de comando:
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Por exemplo:
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  Para adicionar o aplicativo confiável para o pool, siga um destes procedimentos:
    
      - Para uma conexão TLS, digite o seguinte no prompt de comando:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        Por exemplo:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - Para uma conexão TCP, digite o seguinte no prompt de comando:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        Por exemplo:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  Para implementar as alterações publicadas efetuadas na topologia, digite o seguinte no prompt de comando:
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar uma rota estática para controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Definir um endereço IP de gateway SIP/CSTA no Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

