---
title: 'Lync Server 2013: Configurar uma rota estática para controle de chamada remota'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a11b24fc8d4be54f5645853c050891d3821945e4
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Configurar uma rota estática para controle de chamada remota no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-22_

O controle de chamada remota requer que todos os pools do Lync Server estejam configurados com um caminho desse pool para o gateway SIP/CSTA que se conecta à agência de intercâmbio privada (PBX). Esse caminho requer que cada pool tenha uma rota estática para cada gateway ao qual o pool irá fazer chamadas de proxy SIP de chamadas de controle de chamadas associadas a chamadas para o PBX. Se você configurar uma rota estática global para controle de chamada remota, cada pool que não esteja configurado com uma rota estática no nível do pool usará a rota estática global.

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>Para configurar uma rota estática para o controle de chamada remota

1.  Faça logon em um computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou uma função de controle de acesso baseado em função (RBAC) à qual você atribuiu o cmdlet **New-CsStaticRoute** .

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Para criar uma rota estática e colocá-la na variável $TLSRoute ou $TCPRoute, siga um destes procedimentos:
    
    <div class="">
    

    > [!TIP]  
    > Para fazer a correspondência entre domínios filho de um domínio, você pode especificar um valor curinga no parâmetro MatchUri. Por exemplo, <STRONG>*. contoso.net</STRONG>. Esse valor corresponde a qualquer domínio que termina com o sufixo <STRONG>contoso.net</STRONG>.

    
    </div>
    
      - Para uma conexão de TLS (Transport Layer Security), digite o seguinte no prompt de comando:
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        Por exemplo:
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        Se UseDefaultCertificate estiver definido como false, você deve especificar os parâmetros TLSCertIssuer e TLSCertSerialNumber. Esses parâmetros indicam o nome da autoridade de certificação (CA) que emitiu o certificado usado na rota estática e o número de série desse certificado TLS, respectivamente. Para obter detalhes sobre esses parâmetros, consulte a ajuda do Shell de gerenciamento do Lync Server digitando o seguinte no prompt de comando:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - Para uma conexão TCP (Transmission Control Protocol), digite o seguinte no prompt de comando:
        
        <div class="">
        

        > [!NOTE]  
        > Se você especificar um FQDN (nome de domínio totalmente qualificado), deverá configurar um registro de DNS (sistema de nomes de domínio) primeiro.

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        Por exemplo:
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        Estes são os valores padrão para parâmetros opcionais de rotas estáticas:
        
          - Habilitado = verdadeiro
        
          - MatchOnlyPhoneUri = false
        
          - ReplaceHostInRequestUri = false
        
        É altamente recomendável que você não altere esses valores padrão. No entanto, se você precisar alterar qualquer um desses parâmetros, consulte a ajuda do Shell de gerenciamento do Lync Server digitando o seguinte no prompt de comando:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  Para persistir uma rota estática recém-criada no repositório de gerenciamento central, execute um dos seguintes procedimentos, conforme apropriado:
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar uma entrada de aplicativo confiável para controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Definir um endereço SIP de gateway SIP/CSTA no Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

