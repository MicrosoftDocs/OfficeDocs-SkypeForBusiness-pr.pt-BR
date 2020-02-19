---
title: 'Lync Server 2013: planejar a aparência da linha compartilhada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c7b8d66370ef542351f15bdd5f577f29c3a7251
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="60d77-102">Planejar a aparência de uma linha compartilhada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60d77-102">Plan for Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60d77-103">_**Última modificação do tópico:** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="60d77-103">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="60d77-104">Leia este tópico para saber como planejar a aparência da linha compartilhada (SLA) no Lync Server 2013, atualização cumulativa de abril de 2016.</span><span class="sxs-lookup"><span data-stu-id="60d77-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="60d77-105">A aparência de linha compartilhada é um recurso no Lync Server 2013, atualização cumulativa de abril de 2016 para lidar com várias chamadas em um número específico chamado de número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="60d77-105">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="60d77-106">O SLA pode configurar qualquer usuário do Lync habilitado para o Enterprise Voice como um número compartilhado com várias linhas para responder a várias chamadas.</span><span class="sxs-lookup"><span data-stu-id="60d77-106">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="60d77-107">As chamadas não são realmente recebidas no número compartilhado, em vez disso são encaminhadas para os usuários que atuam como delegados para o número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="60d77-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="60d77-108">Qualquer um dos representantes pode pegar a chamada enquanto o restante dos representantes Obtém uma notificação em seu telefone sobre quem selecionou a chamada e qual linha ficou ocupada como resultado.</span><span class="sxs-lookup"><span data-stu-id="60d77-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="60d77-109">O número de linhas e os representantes são configuráveis para um número compartilhado no SLA.</span><span class="sxs-lookup"><span data-stu-id="60d77-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="60d77-110">Além disso, as opções avançadas, como BusyOption (o que acontece em uma situação quando todas as linhas estão ocupadas) e MissedCallOption (o caso em que nenhum dos representantes pega uma chamada), também pode ser configurado para um número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="60d77-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="60d77-111">Só há suporte para o SLA nos seguintes dispositivos de telefone (não há suporte para clientes do Lync em computadores, telefones celulares ou outros dispositivos):</span><span class="sxs-lookup"><span data-stu-id="60d77-111">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="60d77-112">Polycom VVX300 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="60d77-112">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="60d77-113">Polycom VVX400 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="60d77-113">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="60d77-114">Polycom VVX500 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="60d77-114">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="60d77-115">Polycom VVX600 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="60d77-115">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="60d77-116">SLA é um novo recurso no Lync Server 2013, atualização cumulativa de abril de 2016.</span><span class="sxs-lookup"><span data-stu-id="60d77-116">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="60d77-117">Para obter informações sobre como implantar o SLA, consulte [implantar aparência de linha compartilhada no Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="60d77-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="60d77-118">Lista de recursos</span><span class="sxs-lookup"><span data-stu-id="60d77-118">Feature List</span></span>

<span data-ttu-id="60d77-119">A configuração de um grupo de SLA permite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="60d77-119">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="60d77-120">Todos os representantes no grupo podem responder chamadas de entrada para o mesmo número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="60d77-120">All delegates in the group can answer inbound calls to the same shared number.</span></span> <span data-ttu-id="60d77-121">As chamadas podem ser baseadas em PSTN ou em SIP.</span><span class="sxs-lookup"><span data-stu-id="60d77-121">The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="60d77-122">Os representantes podem manter e pegar chamadas.</span><span class="sxs-lookup"><span data-stu-id="60d77-122">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="60d77-123">Os representantes podem transferir chamadas para um número fora do grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="60d77-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="60d77-124">Os representantes podem ver quantas chamadas estão no número compartilhado no momento e exibir o status de cada uma dessas chamadas.</span><span class="sxs-lookup"><span data-stu-id="60d77-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="60d77-125">Você pode configurar um número máximo de chamadas simultâneas para o número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="60d77-125">You can configure a maximum number of concurrent calls for the shared number.</span></span> <span data-ttu-id="60d77-126">Você também pode definir como deseja que as chamadas adicionais sejam tratadas depois que esse máximo for atingido.</span><span class="sxs-lookup"><span data-stu-id="60d77-126">You can also set how you want additional calls to be handled after this maximum is reached.</span></span> <span data-ttu-id="60d77-127">As chamadas em excesso podem ser rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou encaminhadas para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="60d77-127">Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="60d77-128">Você pode configurar como deseja que as chamadas perdidas (chamadas não selecionadas após um determinado tempo) sejam tratadas.</span><span class="sxs-lookup"><span data-stu-id="60d77-128">You can configure how you want missed calls (calls not picked up after a certain time) to be handled.</span></span> <span data-ttu-id="60d77-129">Se você habilitar a caixa postal para a identidade do grupo, as chamadas perdidas vão automaticamente para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="60d77-129">If you enable voice mail for the group identity, missed calls automatically go to voice mail.</span></span> <span data-ttu-id="60d77-130">Se você não tiver a caixa postal habilitada para a identidade do grupo (número compartilhado), você pode escolher para que as chamadas perdidas sejam rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou desconectadas.</span><span class="sxs-lookup"><span data-stu-id="60d77-130">If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

