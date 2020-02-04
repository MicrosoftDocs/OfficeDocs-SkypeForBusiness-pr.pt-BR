---
title: 'Lync Server 2013: Requisitos de DNS para servidor Standard Edition'
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
ms.openlocfilehash: 3ab4280ca3ed329d0dc926756f6bfd933595ca08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="0a9f9-102">Requisitos de DNS para servidor Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a9f9-102">DNS requirements for a Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a9f9-103">_**Tópico da última modificação:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="0a9f9-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="0a9f9-104">Esta seção descreve os registros de sistema de nomes de domínio (DNS) necessários para a implantação de servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="0a9f9-105">Registros de DNS para servidores Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0a9f9-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="0a9f9-106">A tabela a seguir especifica requisitos de DNS para a implantação do servidor do Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a9f9-107">Cenário da implantação</span><span class="sxs-lookup"><span data-stu-id="0a9f9-107">Deployment scenario</span></span></th>
<th><span data-ttu-id="0a9f9-108">Requisitos de DNS</span><span class="sxs-lookup"><span data-stu-id="0a9f9-108">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a9f9-109">Servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0a9f9-109">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="0a9f9-110">Um registro A interno que resolve o nome de domínio totalmente qualificado (FQDN) do servidor para seu endereço IP.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-110">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a9f9-111">Entrada automática do cliente</span><span class="sxs-lookup"><span data-stu-id="0a9f9-111">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="0a9f9-112">Para cada domínio SIP compatível, um registro SRV para _sipinternaltls. _tcp. &lt;domínio&gt; na porta 5061 que mapeia para o FQDN do servidor Standard Edition que autentica e redireciona solicitações do cliente para entrar.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-112">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="0a9f9-113">Para obter detalhes, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisitos de DNS para entrada automática do cliente no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-113">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a9f9-114">Descoberta de serviços Web de atualização de dispositivo por dispositivos de comunicação unificada (UC)</span><span class="sxs-lookup"><span data-stu-id="0a9f9-114">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="0a9f9-115">Um registro interno de um com o nome ucupdates-r2. &lt;Domínio&gt; SIP que é resolvido para o endereço IP do servidor Standard Edition que hospeda o serviço Web de atualização de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-115">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="0a9f9-116">Na situação em que um dispositivo de comunicação unificada está ativado, mas um usuário nunca se conectou ao dispositivo, o registro a permite que o dispositivo descubra o serviço Web de Hospedagem de dispositivo de hospedagem do servidor e obtenha atualizações.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-116">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="0a9f9-117">Caso contrário, os dispositivos obtêm essas informações por meio do provisionamento em banda na primeira vez que o usuário faz logon.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-117">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span> <span data-ttu-id="0a9f9-118">Para obter detalhes, consulte <a href="lync-server-2013-device-update-web-service.md">serviço Web de atualização de dispositivo no Lync Server 2013</a> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-118">For details, see <a href="lync-server-2013-device-update-web-service.md">Device Update Web service in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a9f9-119">Um proxy reverso para dar suporte ao tráfego HTTP</span><span class="sxs-lookup"><span data-stu-id="0a9f9-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="0a9f9-120">Um registro externo que resolve o FQDN do Web farm externo para o endereço IP externo do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="0a9f9-121">Clientes e dispositivos UC usam esse registro para se conectar ao proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="0a9f9-122">Para obter detalhes, consulte <a href="lync-server-2013-determine-dns-requirements.md">determinar requisitos de DNS para o Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="0a9f9-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a9f9-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="0a9f9-123">See Also</span></span>


[<span data-ttu-id="0a9f9-124">Requisitos de DNS para entrada automática do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a9f9-124">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[<span data-ttu-id="0a9f9-125">Determinar requisitios de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a9f9-125">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="0a9f9-126">Serviço Web de Atualização de Dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a9f9-126">Device Update Web service in Lync Server 2013</span></span>](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

