---
title: 'Lync Server 2013: requisitos de DNS para servidores Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3132ec1e18d27564f0077e83d411c5b3930c241b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="baebf-102">Requisitos de DNS para servidores de edição padrão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="baebf-102">DNS requirements for Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="baebf-103">_**Tópico da última modificação:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="baebf-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="baebf-104">Esta seção descreve os registros de sistema de nomes de domínio (DNS) necessários para a implantação de servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="baebf-104">This section describes the Domain Name System (DNS) records that are required for deployment of Standard Edition servers.</span></span>

<div>

## <a name="dns-records-for-standard-edition-servers"></a><span data-ttu-id="baebf-105">Registros de DNS para servidores Standard Edition</span><span class="sxs-lookup"><span data-stu-id="baebf-105">DNS Records for Standard Edition Servers</span></span>

<span data-ttu-id="baebf-106">A tabela a seguir especifica requisitos de DNS para a implantação do servidor do Lync Server 2013 Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="baebf-106">The following table specifies DNS requirements for Lync Server 2013 Standard Edition server deployment.</span></span>

### <a name="dns-requirements-for-a-standard-edition-server"></a><span data-ttu-id="baebf-107">Requisitos de DNS para um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="baebf-107">DNS Requirements for a Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="baebf-108">Cenário da implantação</span><span class="sxs-lookup"><span data-stu-id="baebf-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="baebf-109">Requisitos de DNS</span><span class="sxs-lookup"><span data-stu-id="baebf-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="baebf-110">Servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="baebf-110">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="baebf-111">Um registro A interno que resolve o nome de domínio totalmente qualificado (FQDN) do servidor para seu endereço IP.</span><span class="sxs-lookup"><span data-stu-id="baebf-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="baebf-112">Entrada automática do cliente</span><span class="sxs-lookup"><span data-stu-id="baebf-112">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="baebf-113">Para cada domínio SIP compatível, um registro SRV para _sipinternaltls. _tcp. &lt;domínio&gt; na porta 5061 que mapeia para o FQDN do servidor Standard Edition que autentica e redireciona solicitações do cliente para entrar.</span><span class="sxs-lookup"><span data-stu-id="baebf-113">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Standard Edition server that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="baebf-114">Para obter detalhes, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisitos de DNS para entrada automática do cliente no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="baebf-114">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="baebf-115">Descoberta de serviços Web de atualização de dispositivo por dispositivos de comunicação unificada (UC)</span><span class="sxs-lookup"><span data-stu-id="baebf-115">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="baebf-116">Um registro interno de um com o nome ucupdates-r2. &lt;Domínio&gt; SIP que é resolvido para o endereço IP do servidor Standard Edition que hospeda o serviço Web de atualização de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="baebf-116">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Standard Edition server hosting Device Update Web service.</span></span> <span data-ttu-id="baebf-117">Na situação em que um dispositivo de comunicação unificada está ativado, mas um usuário nunca se conectou ao dispositivo, o registro a permite que o dispositivo descubra o serviço Web de Hospedagem de dispositivo de hospedagem do servidor e obtenha atualizações.</span><span class="sxs-lookup"><span data-stu-id="baebf-117">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the server hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="baebf-118">Caso contrário, os dispositivos obtêm essas informações por meio do provisionamento em banda na primeira vez que o usuário faz logon.</span><span class="sxs-lookup"><span data-stu-id="baebf-118">Otherwise, devices obtain the server information though in-band provisioning the first time a user logs in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="baebf-119">Um proxy reverso para dar suporte ao tráfego HTTP</span><span class="sxs-lookup"><span data-stu-id="baebf-119">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="baebf-120">Um registro externo que resolve o FQDN do Web farm externo para o endereço IP externo do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="baebf-120">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="baebf-121">Clientes e dispositivos UC usam esse registro para se conectar ao proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="baebf-121">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="baebf-122">Para obter detalhes, consulte <a href="lync-server-2013-determine-dns-requirements.md">determinar requisitos de DNS para o Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="baebf-122">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

