---
title: 'Lync Server 2013: configurar uma rota estática para controle de chamada remota'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535574a47a9ea77b5db20e45dcdcbb62fab2e4b9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Configurar uma rota estática para controle de chamada remota no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-22_

O controle de chamada remota exige que todos os pools do Lync Server estejam configurados com um caminho desse pool para o gateway SIP/CSTA que se conecta ao PBX (Private Branch Exchange). Esse caminho exige que cada pool tenha um roteamento estático para cada gateway no qual o pool usará uma mensagem de controle de chamada de SIP proxy associada às chamadas feitas para o PBX. Se você configurar um roteamento estático global para controle de chamada remota, cada pool não configurado com um roteamento estático no nível do pool usará o roteamento estático global.

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>Para configurar uma rota estática para o controle de chamada remota

1.  Faça logon em um computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou de uma função RBAC (controle de acesso baseado em função) para a qual você atribuiu o cmdlet **New-CsStaticRoute** .

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Para criar um roteamento estático e colocá-lo na variável $TLSRoute ou $TCPRoute, siga um destes procedimentos:
    
    <div class="">
    

    > [!TIP]  
    > Para corresponder a domínios filhos de um domínio, é possível especificar um valor curinga no parâmetro MatchUri. Por exemplo, <STRONG>*. contoso.net </STRONG>. O valor corresponde a qualquer domínio que termina com o sufixo <STRONG>contoso.net </STRONG>.

    
    </div>
    
      - Para uma conexão TLS (Transport Layer Security), digite o seguinte no prompt de comando:
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        Por exemplo:
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        Se UseDefaultCertificate for definido como Falso, você deve especificar os parâmetros TLSCertIssuer e TLSCertSerialNumber. Esses parâmetros indicam o nome da autoridade de certificação (CA) que emitiu o certificado usado no roteamento estático e o número de série do certificado TLS, respectivamente. Para obter detalhes sobre esses parâmetros, consulte a ajuda do Shell de gerenciamento do Lync Server digitando o seguinte no prompt de comando:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - Para uma conexão TCP (Transmission Control Protocol), digite o seguinte no prompt de comando:
        
        <div class="">
        

        > [!NOTE]  
        > Se especificar um nome de domínio totalmente qualificado (FQDN), você deve configurar um registro A de DNS primeiro.

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        Por exemplo:
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        Estes são os valores padrões para parâmetros opcionais de roteamento estático:
        
          - Habilitado = Verdadeiro
        
          - MatchOnlyPhoneUri = Falso
        
          - ReplaceHostInRequestUri = Falso
        
        Recomendamos que você não altere esses valores padrões. No entanto, se você precisar alterar qualquer um desses parâmetros, consulte a ajuda do Shell de gerenciamento do Lync Server digitando o seguinte no prompt de comando:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  Para manter uma rota estática recentemente criada no repositório de gerenciamento central, execute um dos seguintes procedimentos, conforme apropriado:
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>Confira Também


[Configurar uma entrada de aplicativo confiável para controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Definir um endereço IP de gateway SIP/CSTA no Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

