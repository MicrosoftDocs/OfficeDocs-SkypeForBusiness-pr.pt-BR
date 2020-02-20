---
title: 'Lync Server 2013: atribuindo políticas de presença por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4ae464e37c7d4061c9a7311d7df427b7a66db1c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="099ef-102">Atribuindo políticas de presença por usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="099ef-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="099ef-103">_**Última modificação do tópico:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="099ef-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="099ef-104">Uma política de presença é um conjunto de limites e restrições que afetam a presença.</span><span class="sxs-lookup"><span data-stu-id="099ef-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="099ef-105">A tabela a seguir descreve as configurações de política de presença disponíveis no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="099ef-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="099ef-106">Configurações da Política de Presença</span><span class="sxs-lookup"><span data-stu-id="099ef-106">Presence Policy Settings</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="099ef-107">Nome XML</span><span class="sxs-lookup"><span data-stu-id="099ef-107">XML name</span></span></th>
<th><span data-ttu-id="099ef-108">Nome de exibição</span><span class="sxs-lookup"><span data-stu-id="099ef-108">Display name</span></span></th>
<th><span data-ttu-id="099ef-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="099ef-109">Description</span></span></th>
<th><span data-ttu-id="099ef-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="099ef-110">Type</span></span></th>
<th><span data-ttu-id="099ef-111">Valor</span><span class="sxs-lookup"><span data-stu-id="099ef-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="099ef-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="099ef-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="099ef-113">Número máximo de inscrições de categoria do assinante</span><span class="sxs-lookup"><span data-stu-id="099ef-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="099ef-p102">Limita o número de inscrições de categoria do assinante. Por exemplo, quando o Communicator se inscreve para a presença de um usuário, ele obtém uma inscrição de categoria para cada cartão de contato, dados de calendário, notas, serviços e categorias de estado.</span><span class="sxs-lookup"><span data-stu-id="099ef-p102">Limits the number of subscriber category subscriptions. For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="099ef-116">Uma configuração 0 significa que o objeto de usuário ou contato não pode ser inscrito por outros.</span><span class="sxs-lookup"><span data-stu-id="099ef-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="099ef-117">Essa configuração pode ter um impacto significativo no desempenho se for definida para um número alto e o usuário médio tem um grande número de usuários inscrevendo para sua presença.</span><span class="sxs-lookup"><span data-stu-id="099ef-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="099ef-118">Inteiro</span><span class="sxs-lookup"><span data-stu-id="099ef-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="099ef-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="099ef-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="099ef-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="099ef-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="099ef-121">Número máximo de alertas de inscrição de presença na fila</span><span class="sxs-lookup"><span data-stu-id="099ef-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="099ef-p103">Limita o número de entradas na tabela de inscritos solicitados. Essa configuração determina o número máximo de solicitações que podem ser enfileiradas para um determinado usuário. Por exemplo, quando um usuário A se inscreve para a presença do usuário B, o usuário B recebe um prompt de que o usuário A agora está inscrito para o usuário B e um prompt de confirmação é criado na tabela de inscritos solicitados do usuário B. Após o usuário B aceitar ou confirmar a inscrição, o prompt de confirmação é removido da tabela de inscritos solicitados do usuário B.</span><span class="sxs-lookup"><span data-stu-id="099ef-p103">Limits the number of entries in the prompted subscribers table. This setting determines the maximum number of prompts that can be queued for a given user. For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table. After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="099ef-126">Uma configuração 0 significa que o usuário não é solicitado quando alguém se inscreve para sua presença.</span><span class="sxs-lookup"><span data-stu-id="099ef-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="099ef-127">Inteiro ou símbolo</span><span class="sxs-lookup"><span data-stu-id="099ef-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="099ef-128">0-500</span><span class="sxs-lookup"><span data-stu-id="099ef-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="099ef-129">Por padrão, a **política** e o serviço padrão: as políticas de presença **médias** são instaladas quando você implanta o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="099ef-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="099ef-130">A tabela a seguir descreve as configurações específicas de duas políticas de presença.</span><span class="sxs-lookup"><span data-stu-id="099ef-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="099ef-131">Políticas de presença</span><span class="sxs-lookup"><span data-stu-id="099ef-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="099ef-132">Nome da política</span><span class="sxs-lookup"><span data-stu-id="099ef-132">Policy name</span></span></th>
<th><span data-ttu-id="099ef-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="099ef-133">Description</span></span></th>
<th><span data-ttu-id="099ef-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="099ef-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="099ef-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="099ef-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="099ef-136">Política padrão</span><span class="sxs-lookup"><span data-stu-id="099ef-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="099ef-p105">Política para usuários comuns. Esta é a política de presença padrão.</span><span class="sxs-lookup"><span data-stu-id="099ef-p105">Policy for typical users. This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="099ef-139">1000</span><span class="sxs-lookup"><span data-stu-id="099ef-139">1000</span></span></p></td>
<td><p><span data-ttu-id="099ef-140">200</span><span class="sxs-lookup"><span data-stu-id="099ef-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="099ef-141">Serviço: Médio</span><span class="sxs-lookup"><span data-stu-id="099ef-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="099ef-142">Política para aplicativos que exigem mais usuários para se inscrever na presença do objeto.</span><span class="sxs-lookup"><span data-stu-id="099ef-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="099ef-143">1000</span><span class="sxs-lookup"><span data-stu-id="099ef-143">1000</span></span></p></td>
<td><p><span data-ttu-id="099ef-144">,0</span><span class="sxs-lookup"><span data-stu-id="099ef-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

