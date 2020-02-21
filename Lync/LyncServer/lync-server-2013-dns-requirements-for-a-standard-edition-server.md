---
title: 'Lync Server 2013: requisitos de DNS para um servidor Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12a4d87f0ffa1ab7d6e857a40c2440d35d0b38aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="8811c-102">Requisitos de DNS para um servidor Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8811c-102">DNS requirements for a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8811c-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="8811c-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="8811c-104">Esta seção descreve os registros DNS necessários para a implantação de servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8811c-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="8811c-105">Registros DNS para servidores Standard Edition</span><span class="sxs-lookup"><span data-stu-id="8811c-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="8811c-106">A tabela a seguir especifica os requisitos de DNS para a implantação do servidor do Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="8811c-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8811c-107">Cenário da implantação</span><span class="sxs-lookup"><span data-stu-id="8811c-107">Deployment scenario</span></span></th>
<th><span data-ttu-id="8811c-108">Requisito de DNS</span><span class="sxs-lookup"><span data-stu-id="8811c-108">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8811c-109">Servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="8811c-109">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="8811c-110">Um registro A interno que resolva o FQDN (nome de domínio totalmente qualificado) do servidor como o respectivo endereço IP.</span><span class="sxs-lookup"><span data-stu-id="8811c-110">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8811c-111">Entrada automática do cliente</span><span class="sxs-lookup"><span data-stu-id="8811c-111">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="8811c-112">Para cada domínio SIP com suporte, um registro SRV para _sipinternaltls. _tcp. &lt;domínio&gt; sobre a porta 5061 que mapeia para o FQDN do servidor Standard Edition que autentica e redireciona as solicitações do cliente para entrada.</span><span class="sxs-lookup"><span data-stu-id="8811c-112">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="8811c-113">Para obter detalhes, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS Requirements for Automatic Client Sign-in in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8811c-113">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8811c-114">Descoberta do serviço Web de Atualização de Dispositivo por dispositivos de UC (comunicações unificadas)</span><span class="sxs-lookup"><span data-stu-id="8811c-114">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="8811c-115">Um registro A interno com o nome ucupdates-r2. &lt;Domínio&gt; SIP que resolve para o endereço IP do servidor Standard Edition que hospeda o serviço Web de atualização de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8811c-115">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="8811c-116">Na situação em que um dispositivo de UC esteja ativado, mas um usuário nunca tenha feito logon no dispositivo, o registro A permite que o dispositivo descubra o servidor que hospeda o serviço Web de Atualização de Dispositivo e obtenha atualizações.</span><span class="sxs-lookup"><span data-stu-id="8811c-116">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="8811c-117">Caso contrário, os dispositivos obtêm as informações do servidor através do provisionamento em banda na primeira vez que um usuário faz logon.</span><span class="sxs-lookup"><span data-stu-id="8811c-117">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span> <span data-ttu-id="8811c-118">Para obter detalhes, consulte <a href="lync-server-2013-device-update-web-service.md">Device Update Web Service in Lync Server 2013</a> na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="8811c-118">For details, see <a href="lync-server-2013-device-update-web-service.md">Device Update Web service in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8811c-119">Um proxy reverso para dar suporte ao tráfego HTTP</span><span class="sxs-lookup"><span data-stu-id="8811c-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="8811c-120">Um registro A externo que resolva o FQDN da Web farm externa como o endereço IP externo do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="8811c-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="8811c-121">Os clientes e os dispositivos de UC usam esse registro para se conectar ao proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="8811c-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="8811c-122">Para obter detalhes, consulte <a href="lync-server-2013-determine-dns-requirements.md">determine DNS Requirements for Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="8811c-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8811c-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="8811c-123">See Also</span></span>


[<span data-ttu-id="8811c-124">Requisitos de DNS para entrada de cliente automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8811c-124">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[<span data-ttu-id="8811c-125">Determinar requisitos de DNS para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8811c-125">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="8811c-126">Serviço Web de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8811c-126">Device Update Web service in Lync Server 2013</span></span>](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

