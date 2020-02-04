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
ms.openlocfilehash: 755bff84b8902e346135139d1c8c5b26c55605c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="b95b7-102">Planejar a aparência de uma linha compartilhada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b95b7-102">Plan for Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b95b7-103">_**Tópico da última modificação:** 2016-03-21_</span><span class="sxs-lookup"><span data-stu-id="b95b7-103">_**Topic Last Modified:** 2016-03-21_</span></span>

<span data-ttu-id="b95b7-104">Leia este tópico para aprender a planejar a aparência de uma linha compartilhada (SLA) no Lync Server 2013, atualização cumulativa de abril de 2016.</span><span class="sxs-lookup"><span data-stu-id="b95b7-104">Read this topic to learn how to plan for Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="b95b7-105">A aparência da linha compartilhada é um recurso do Lync Server 2013, atualização cumulativa de abril de 2016 para manipular várias chamadas em um número específico chamado de número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="b95b7-105">Shared Line Appearance is a feature in Lync Server 2013, Cumulative Update April 2016 for handling multiple calls on a specific number called a shared number.</span></span> <span data-ttu-id="b95b7-106">O SLA pode configurar qualquer usuário do Lync habilitado para Enterprise Voice como um número compartilhado com várias linhas para responder a várias chamadas.</span><span class="sxs-lookup"><span data-stu-id="b95b7-106">SLA can configure any enterprise voice enabled Lync user as a shared number with multiple lines to respond to multiple calls.</span></span> <span data-ttu-id="b95b7-107">As chamadas não serão realmente recebidas no número compartilhado, em vez disso, elas serão encaminhadas para os usuários que atuam como representantes para o número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="b95b7-107">The calls are not actually received on the shared number, instead they are forwarded to users that act as delegates for the shared number.</span></span> <span data-ttu-id="b95b7-108">Qualquer um dos representantes pode atender a chamada enquanto o restante dos representantes recebe uma notificação no telefone sobre quem obteve o convite e que linha ficou ocupada como resultado.</span><span class="sxs-lookup"><span data-stu-id="b95b7-108">Any one of the delegates can pick up the call while the rest of the delegates get a notification on their phone about who picked up the call and which line has become busy as a result.</span></span> <span data-ttu-id="b95b7-109">Tanto o número de linhas quanto os representantes são configuráveis para um número compartilhado no SLA.</span><span class="sxs-lookup"><span data-stu-id="b95b7-109">Both the number of lines and the delegates are configurable for a shared number in SLA.</span></span> <span data-ttu-id="b95b7-110">Além disso, as opções avançadas, como BusyOption (o que acontece em uma situação quando todas as linhas estão ocupadas) e MissedCallOption (caso em que nenhum dos representantes atende uma chamada), também podem ser configuradas para um número compartilhado.</span><span class="sxs-lookup"><span data-stu-id="b95b7-110">In addition, advanced options, such as BusyOption (what happens in a situation when all lines are busy) and MissedCallOption (the case in which none of the delegates pick up a call), can also be configured for a shared number.</span></span>

<span data-ttu-id="b95b7-111">O SLA só tem suporte nos seguintes dispositivos telefônicos (não há suporte para clientes do Lync em computadores, telefones celulares ou outros dispositivos):</span><span class="sxs-lookup"><span data-stu-id="b95b7-111">SLA is supported only on the following phone devices (it is not supported for Lync clients on computers, mobile phones, or other devices):</span></span>

  - <span data-ttu-id="b95b7-112">Polycom VVX300 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="b95b7-112">Polycom VVX300 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="b95b7-113">Polycom VVX400 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="b95b7-113">Polycom VVX400 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="b95b7-114">Polycom VVX500 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="b95b7-114">Polycom VVX500 with firmware update 5.4.1</span></span>

  - <span data-ttu-id="b95b7-115">Polycom VVX600 com atualização de firmware 5.4.1</span><span class="sxs-lookup"><span data-stu-id="b95b7-115">Polycom VVX600 with firmware update 5.4.1</span></span>

<span data-ttu-id="b95b7-116">O SLA é um novo recurso do Lync Server 2013, atualização cumulativa de abril de 2016.</span><span class="sxs-lookup"><span data-stu-id="b95b7-116">SLA is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span>

<span data-ttu-id="b95b7-117">Para obter informações sobre a implantação do SLA, consulte [implantar a aparência da linha compartilhada no Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="b95b7-117">For information about deploying SLA, see [Deploy Shared Line Appearance in Lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).</span></span>

<div>

## <a name="feature-list"></a><span data-ttu-id="b95b7-118">Lista de recursos</span><span class="sxs-lookup"><span data-stu-id="b95b7-118">Feature List</span></span>

<span data-ttu-id="b95b7-119">Configuração de um grupo de SLA permite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b95b7-119">Setting up an SLA group enables the following:</span></span>

  - <span data-ttu-id="b95b7-p102">Todos os representantes do grupo podem atender chamadas de entrada para o mesmo número compartilhado. As chamadas podem ser baseadas em PSTN ou em SIP.</span><span class="sxs-lookup"><span data-stu-id="b95b7-p102">All delegates in the group can answer inbound calls to the same shared number. The calls can be PSTN-based or SIP-based.</span></span>

  - <span data-ttu-id="b95b7-122">Os representantes podem reter e atender chamadas.</span><span class="sxs-lookup"><span data-stu-id="b95b7-122">Delegates can hold and pick up calls.</span></span>

  - <span data-ttu-id="b95b7-123">Os representantes podem transferir chamadas para um número externo do grupo SLA.</span><span class="sxs-lookup"><span data-stu-id="b95b7-123">Delegates can transfer calls to a number outside of the SLA group.</span></span>

  - <span data-ttu-id="b95b7-124">Os representantes podem ver quantas chamadas estão atualmente no número compartilhado e ver o estado de cada uma delas.</span><span class="sxs-lookup"><span data-stu-id="b95b7-124">Delegates can see how many calls are currently on the shared number, and view the status of each of those calls.</span></span>

  - <span data-ttu-id="b95b7-p103">Você pode configurar um número máximo de chamadas simultâneas para o número compartilhado. Você também pode definir como deseja que as chamadas adicionais sejam manipuladas depois que esse máximo for atingido. As chamadas em excesso podem ser rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou encaminhadas para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="b95b7-p103">You can configure a maximum number of concurrent calls for the shared number. You can also set how you want additional calls to be handled after this maximum is reached. Excess calls can be rejected with a busy signal, forwarded to an alternate number, or forwarded to voice mail.</span></span>

  - <span data-ttu-id="b95b7-p104">Você pode configurar como você deseja que as chamadas não atendidas (chamadas não atendidas após um determinado período de tempo) sejam tratadas. Se você ativar o correio de voz para a identidade do grupo, as chamadas não atendidas automaticamente irão para o correio de voz. Se você não tiver correio de voz habilitado para a identidade do grupo (número compartilhado), você poderá escolher que as chamadas perdidas sejam rejeitadas com um sinal de ocupado, encaminhadas para um número alternativo ou desconectadas.</span><span class="sxs-lookup"><span data-stu-id="b95b7-p104">You can configure how you want missed calls (calls not picked up after a certain time) to be handled. If you enable voice mail for the group identity, missed calls automatically go to voice mail. If you do not have voice mail enabled for the group identity (shared number), you can choose for missed calls to be rejected with a busy signal, forwarded to an alternate number, or disconnected.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

