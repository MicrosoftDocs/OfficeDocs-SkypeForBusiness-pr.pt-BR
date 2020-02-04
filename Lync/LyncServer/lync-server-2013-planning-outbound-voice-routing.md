---
title: 'Lync Server 2013: Planejando roteamento de voz de saída'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d33fbe8d15b78bed9dd651cd7facf35a8249f64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a><span data-ttu-id="026de-102">Planejando roteamento de voz de saída no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="026de-102">Planning outbound voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="026de-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="026de-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="026de-104">O encaminhamento de chamadas de saída aplica-se a chamadas destinadas a um gateway PSTN (rede telefônica pública comutada), tronco ou PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="026de-104">Outbound call routing applies to calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX).</span></span> <span data-ttu-id="026de-105">Quando um usuário faz uma chamada, o servidor normaliza o número de telefone para o formato E. 164, se necessário, e tenta fazer a correspondência com um URI de SIP.</span><span class="sxs-lookup"><span data-stu-id="026de-105">When a user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="026de-106">Se o servidor não conseguir fazer a correspondência, ele aplicará a lógica de roteamento de chamadas de saída com base na cadeia de caracteres de discagem fornecida.</span><span class="sxs-lookup"><span data-stu-id="026de-106">If the server cannot make the match, it applies outbound call routing logic based on the supplied dial string.</span></span> <span data-ttu-id="026de-107">Especifique essa lógica definindo as configurações do servidor descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="026de-107">You define that logic by configuring the server settings that are described in the following table.</span></span>

### <a name="lync-server-outbound-call-routing-settings"></a><span data-ttu-id="026de-108">Configurações de roteamento de chamadas de saída do Lync Server</span><span class="sxs-lookup"><span data-stu-id="026de-108">Lync Server Outbound Call Routing Settings</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="026de-109">Objeto</span><span class="sxs-lookup"><span data-stu-id="026de-109">Object</span></span></th>
<th><span data-ttu-id="026de-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="026de-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="026de-111">Plano de discagem</span><span class="sxs-lookup"><span data-stu-id="026de-111">Dial Plan</span></span></p></td>
<td><p><span data-ttu-id="026de-112">Um plano de discagem é um conjunto nomeado de regras de normalização que converte números de telefone de um local nomeado, usuário individual ou objeto de contato em um único formato padrão (E.164) para fins de roteamento de chamadas e autorização de telefones.</span><span class="sxs-lookup"><span data-stu-id="026de-112">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="026de-113">Regra de normalização</span><span class="sxs-lookup"><span data-stu-id="026de-113">Normalization rule</span></span></p></td>
<td><p><span data-ttu-id="026de-p102">As regras de normalização definem como os números de telefone expressos em vários formatos são roteados para cada local, usuário ou objeto de contato especificado. A mesma cadeia de caracteres de discagem pode ser interpretada e convertida de maneira diferente, dependendo do local do qual é discada e da pessoa ou do objeto de contato que está fazendo a chamada. Um conjunto de regras de normalização associadas a um local específico constitui um plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="026de-p102">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object that makes the call. A set of normalization rules associated with a particular location constitutes a dial plan.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="026de-117">Política de voz</span><span class="sxs-lookup"><span data-stu-id="026de-117">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="026de-p103">Uma política de voz associa um ou mais registros de uso de PSTN a um usuário ou grupo de usuários. Também fornece uma lista de recursos de chamada que você pode ativar ou desativar.</span><span class="sxs-lookup"><span data-stu-id="026de-p103">A voice policy associates one or more PSTN usage records with one user or a group of users. A voice policy also provides a list of calling features that you can enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="026de-120">Registro de uso de PSTN</span><span class="sxs-lookup"><span data-stu-id="026de-120">PSTN usage record</span></span></p></td>
<td><p><span data-ttu-id="026de-121">Um registro de uso de PSTN especifica uma classe de chamada (por exemplo, interna, local ou interurbana) que pode ser feita por vários usuários ou grupos de usuários em uma organização.</span><span class="sxs-lookup"><span data-stu-id="026de-121">A PSTN usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users, or groups of users, in an organization.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="026de-122">Rota de chamada</span><span class="sxs-lookup"><span data-stu-id="026de-122">Call Route</span></span></p></td>
<td><p><span data-ttu-id="026de-p104">Uma rota de chamada associa os números de telefone de destino com troncos específicos e registros de uso de PSTN. Um gateway PSTN é considerado um tronco.</span><span class="sxs-lookup"><span data-stu-id="026de-p104">A call route associates destination phone numbers with particular trunks and PSTN usage records. A PSTN gateway is considered a trunk.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="026de-125">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="026de-125">In This Section</span></span>

<span data-ttu-id="026de-126">Esta seção fornece diretrizes para configurar as seguintes configurações de servidor de roteamento de chamadas de saída:</span><span class="sxs-lookup"><span data-stu-id="026de-126">This section provides guidelines for configuring the following outbound call routing server settings:</span></span>

  - <span></span>  
    [<span data-ttu-id="026de-127">Planos de discagem e regras de normalização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="026de-127">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [<span data-ttu-id="026de-128">Políticas de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="026de-128">Voice policies in Lync Server 2013</span></span>](lync-server-2013-voice-policies.md)

  - <span></span>  
    [<span data-ttu-id="026de-129">Registros de uso de PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="026de-129">PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [<span data-ttu-id="026de-130">Rotas de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="026de-130">Voice routes in Lync Server 2013</span></span>](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="026de-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="026de-131">See Also</span></span>


[<span data-ttu-id="026de-132">Entroncamento SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="026de-132">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)  
[<span data-ttu-id="026de-133">Conexões SIP diretas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="026de-133">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

