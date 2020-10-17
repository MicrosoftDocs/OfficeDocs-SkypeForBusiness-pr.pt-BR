---
title: 'Lync Server 2013: configurar uma rota estática para controle de chamada remota'
description: 'Lync Server 2013: configurar uma rota estática para controle de chamada remota.'
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
ms.openlocfilehash: 8ecf6478d4fb7ab4f04f8a452d4837b327ba254a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551687"
---
# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="ea8c1-103">Configurar uma rota estática para controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea8c1-103">Configure a static route for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea8c1-104">_**Última modificação do tópico:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="ea8c1-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="ea8c1-105">O controle de chamada remota exige que todos os pools do Lync Server estejam configurados com um caminho desse pool para o gateway SIP/CSTA que se conecta ao PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="ea8c1-105">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="ea8c1-106">Esse caminho exige que cada pool tenha um roteamento estático para cada gateway no qual o pool usará uma mensagem de controle de chamada de SIP proxy associada às chamadas feitas para o PBX.</span><span class="sxs-lookup"><span data-stu-id="ea8c1-106">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="ea8c1-107">Se você configurar um roteamento estático global para controle de chamada remota, cada pool não configurado com um roteamento estático no nível do pool usará o roteamento estático global.</span><span class="sxs-lookup"><span data-stu-id="ea8c1-107">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="ea8c1-108">Para configurar uma rota estática para o controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="ea8c1-108">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="ea8c1-109">Faça logon em um computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou de uma função RBAC (controle de acesso baseado em função) para a qual você atribuiu o cmdlet **New-CsStaticRoute** .</span><span class="sxs-lookup"><span data-stu-id="ea8c1-109">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="ea8c1-110">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ea8c1-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ea8c1-111">Para criar um roteamento estático e colocá-lo na variável $TLSRoute ou $TCPRoute, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="ea8c1-111">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="ea8c1-p102">Para corresponder a domínios filhos de um domínio, é possível especificar um valor curinga no parâmetro MatchUri. Por exemplo, <STRONG>\*. contoso.net </STRONG>. O valor corresponde a qualquer domínio que termina com o sufixo <STRONG>contoso.net </STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ea8c1-p102">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter. For example, <STRONG>\*.contoso.net</STRONG>. That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="ea8c1-115">Para uma conexão TLS (Transport Layer Security), digite o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="ea8c1-115">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        <span data-ttu-id="ea8c1-116">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ea8c1-116">For example:</span></span>
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        <span data-ttu-id="ea8c1-117">Se UseDefaultCertificate for definido como Falso, você deve especificar os parâmetros TLSCertIssuer e TLSCertSerialNumber.</span><span class="sxs-lookup"><span data-stu-id="ea8c1-117">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="ea8c1-118">Esses parâmetros indicam o nome da autoridade de certificação (CA) que emitiu o certificado usado no roteamento estático e o número de série do certificado TLS, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ea8c1-118">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="ea8c1-119">Para obter detalhes sobre esses parâmetros, consulte a ajuda do Shell de gerenciamento do Lync Server digitando o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="ea8c1-119">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - <span data-ttu-id="ea8c1-120">Para uma conexão TCP (Transmission Control Protocol), digite o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="ea8c1-120">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="ea8c1-121">Se especificar um nome de domínio totalmente qualificado (FQDN), você deve configurar um registro A de DNS primeiro.</span><span class="sxs-lookup"><span data-stu-id="ea8c1-121">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        <span data-ttu-id="ea8c1-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ea8c1-122">For example:</span></span>
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        <span data-ttu-id="ea8c1-123">Estes são os valores padrões para parâmetros opcionais de roteamento estático:</span><span class="sxs-lookup"><span data-stu-id="ea8c1-123">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="ea8c1-124">Habilitado = Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="ea8c1-124">Enabled = True</span></span>
        
          - <span data-ttu-id="ea8c1-125">MatchOnlyPhoneUri = Falso</span><span class="sxs-lookup"><span data-stu-id="ea8c1-125">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="ea8c1-126">ReplaceHostInRequestUri = Falso</span><span class="sxs-lookup"><span data-stu-id="ea8c1-126">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="ea8c1-127">Recomendamos que você não altere esses valores padrões.</span><span class="sxs-lookup"><span data-stu-id="ea8c1-127">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="ea8c1-128">No entanto, se você precisar alterar qualquer um desses parâmetros, consulte a ajuda do Shell de gerenciamento do Lync Server digitando o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="ea8c1-128">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  <span data-ttu-id="ea8c1-129">Para manter uma rota estática recentemente criada no repositório de gerenciamento central, execute um dos seguintes procedimentos, conforme apropriado:</span><span class="sxs-lookup"><span data-stu-id="ea8c1-129">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea8c1-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="ea8c1-130">See Also</span></span>


[<span data-ttu-id="ea8c1-131">Configurar uma entrada de aplicativo confiável para controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea8c1-131">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="ea8c1-132">Definir um endereço IP de gateway SIP/CSTA no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea8c1-132">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

