---
title: 'Lync Server 2013: Configurar uma rota estática para controle de chamada remota'
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
ms.openlocfilehash: dfb825e51a9beec7010f9f46ed0fc649267897fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="d0aa8-102">Configurar uma rota estática para controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0aa8-102">Configure a static route for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0aa8-103">_**Tópico da última modificação:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="d0aa8-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="d0aa8-104">O controle de chamada remota requer que todos os pools do Lync Server estejam configurados com um caminho desse pool para o gateway SIP/CSTA que se conecta à agência de intercâmbio privada (PBX).</span><span class="sxs-lookup"><span data-stu-id="d0aa8-104">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="d0aa8-105">Esse caminho requer que cada pool tenha uma rota estática para cada gateway ao qual o pool irá fazer chamadas de proxy SIP de chamadas de controle de chamadas associadas a chamadas para o PBX.</span><span class="sxs-lookup"><span data-stu-id="d0aa8-105">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="d0aa8-106">Se você configurar uma rota estática global para controle de chamada remota, cada pool que não esteja configurado com uma rota estática no nível do pool usará a rota estática global.</span><span class="sxs-lookup"><span data-stu-id="d0aa8-106">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="d0aa8-107">Para configurar uma rota estática para o controle de chamada remota</span><span class="sxs-lookup"><span data-stu-id="d0aa8-107">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="d0aa8-108">Faça logon em um computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou uma função de controle de acesso baseado em função (RBAC) à qual você atribuiu o cmdlet **New-CsStaticRoute** .</span><span class="sxs-lookup"><span data-stu-id="d0aa8-108">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="d0aa8-109">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d0aa8-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d0aa8-110">Para criar uma rota estática e colocá-la na variável $TLSRoute ou $TCPRoute, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="d0aa8-110">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="d0aa8-111">Para fazer a correspondência entre domínios filho de um domínio, você pode especificar um valor curinga no parâmetro MatchUri.</span><span class="sxs-lookup"><span data-stu-id="d0aa8-111">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter.</span></span> <span data-ttu-id="d0aa8-112">Por exemplo, <STRONG>\*. contoso.net</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d0aa8-112">For example, <STRONG>\*.contoso.net</STRONG>.</span></span> <span data-ttu-id="d0aa8-113">Esse valor corresponde a qualquer domínio que termina com o sufixo <STRONG>contoso.net</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d0aa8-113">That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="d0aa8-114">Para uma conexão de TLS (Transport Layer Security), digite o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="d0aa8-114">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        <span data-ttu-id="d0aa8-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d0aa8-115">For example:</span></span>
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        <span data-ttu-id="d0aa8-116">Se UseDefaultCertificate estiver definido como false, você deve especificar os parâmetros TLSCertIssuer e TLSCertSerialNumber.</span><span class="sxs-lookup"><span data-stu-id="d0aa8-116">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="d0aa8-117">Esses parâmetros indicam o nome da autoridade de certificação (CA) que emitiu o certificado usado na rota estática e o número de série desse certificado TLS, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d0aa8-117">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="d0aa8-118">Para obter detalhes sobre esses parâmetros, consulte a ajuda do Shell de gerenciamento do Lync Server digitando o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="d0aa8-118">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - <span data-ttu-id="d0aa8-119">Para uma conexão TCP (Transmission Control Protocol), digite o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="d0aa8-119">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="d0aa8-120">Se você especificar um FQDN (nome de domínio totalmente qualificado), deverá configurar um registro de DNS (sistema de nomes de domínio) primeiro.</span><span class="sxs-lookup"><span data-stu-id="d0aa8-120">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        <span data-ttu-id="d0aa8-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d0aa8-121">For example:</span></span>
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        <span data-ttu-id="d0aa8-122">Estes são os valores padrão para parâmetros opcionais de rotas estáticas:</span><span class="sxs-lookup"><span data-stu-id="d0aa8-122">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="d0aa8-123">Habilitado = verdadeiro</span><span class="sxs-lookup"><span data-stu-id="d0aa8-123">Enabled = True</span></span>
        
          - <span data-ttu-id="d0aa8-124">MatchOnlyPhoneUri = false</span><span class="sxs-lookup"><span data-stu-id="d0aa8-124">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="d0aa8-125">ReplaceHostInRequestUri = false</span><span class="sxs-lookup"><span data-stu-id="d0aa8-125">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="d0aa8-126">É altamente recomendável que você não altere esses valores padrão.</span><span class="sxs-lookup"><span data-stu-id="d0aa8-126">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="d0aa8-127">No entanto, se você precisar alterar qualquer um desses parâmetros, consulte a ajuda do Shell de gerenciamento do Lync Server digitando o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="d0aa8-127">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  <span data-ttu-id="d0aa8-128">Para persistir uma rota estática recém-criada no repositório de gerenciamento central, execute um dos seguintes procedimentos, conforme apropriado:</span><span class="sxs-lookup"><span data-stu-id="d0aa8-128">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d0aa8-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="d0aa8-129">See Also</span></span>


[<span data-ttu-id="d0aa8-130">Configurar uma entrada de aplicativo confiável para controle de chamada remota no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0aa8-130">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="d0aa8-131">Definir um endereço SIP de gateway SIP/CSTA no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0aa8-131">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

