---
title: 'Lync Server 2013: visão geral do parque de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5deeff873b37c0056bf03c598c39e448cba4379
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="7a3d3-102">Visão geral do estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a3d3-102">Overview of Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a3d3-103">_**Tópico da última modificação:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="7a3d3-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="7a3d3-104">O aplicativo do Lync Server 2013 Call Park permite que os usuários do Enterprise Voice realizem qualquer um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7a3d3-104">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="7a3d3-105">Colocar uma chamada em espera e recuperá-la no mesmo telefone ou em outro.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-105">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="7a3d3-106">Colocar uma chamada em espera para transferi-la para um departamento ou área geral, por exemplo, um departamento de vendas ou um depósito onde há um telefone de área comum.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-106">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="7a3d3-107">Colocar uma chamada em espera e manter o telefone original livre para outras chamadas.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-107">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="7a3d3-108">Quando um usuário representa uma chamada, o Lync Server transfere a chamada para um número temporário, chamado de *órbita*, em que a chamada é mantida até ser recuperada ou expirada. O Lync Server envia a órbita para o usuário que estaciona a chamada.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-108">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="7a3d3-109">Para recuperar a chamada estacionada, o usuário pode discar o número de órbita ou clicar no link de órbita ou na janela de Conversação.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-109">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="7a3d3-p102">O usuário que estacionou uma chamada pode notificar alguém para recuperar a chamada usando um mecanismo externo, como mensagens instantâneas ou um sistema de paginação, para comunicar o número de órbita para outra pessoa. O usuário que estacionou a chamada pode deixar a janela de Conversação aberta para receber notificações quando a chamada for recuperada.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-p102">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="7a3d3-112">Como os intervalos de órbita são globalmente exclusivos, é possível recuperar chamadas de qualquer site do Lync Server ou de um telefone PBX se o roteamento estiver configurado apropriadamente.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-112">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="7a3d3-113">Se ninguém recuperar a chamada dentro do tempo configurável, a chamada tocará novamente para a pessoa que a estacionou.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-113">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="7a3d3-114">Se essa pessoa não atender, a chamada será transferida para um destino de fallback, como um operador, se assim estiver configurado.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-114">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="7a3d3-115">Você pode configurar o número de vezes que a chamada toca antes de ser transferida, entre uma a dez vezes.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-115">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="7a3d3-116">Se ninguém atender a chamada transferida, ela será desconectada.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-116">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="7a3d3-117">A órbita é liberada quando a chamada é recebida ou desconectada.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-117">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="7a3d3-118">Quando você implanta o Estacionamento de Chamada, precisa reservar intervalos de números de extensão para estacionar as chamadas.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-118">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="7a3d3-119">Essas extensões precisam ser extensões virtuais: extensões que não têm nenhum usuário ou telefone atribuído.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-119">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="7a3d3-120">Você configura a tabela de órbitas do estacionamento de chamada com os intervalos de números de extensões e especifica qual serviço de Aplicativo hospeda o aplicativo de Estacionamento de Chamada que lida com cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-120">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="7a3d3-121">Cada pool de front-ends tem uma tabela parque de chamadas no servidor back-end correspondente usado para gerenciar chamadas estacionadas no pool.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-121">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="7a3d3-122">A lista de intervalos de órbita é armazenada no repositório de gerenciamento central e é usada para rotear órbitas para o pool de destino.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-122">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="7a3d3-123">Cada pool do Lync Server onde o aplicativo de estacionamento de chamada é implantado e configurado pode ter um ou mais intervalos de órbita.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-123">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="7a3d3-124">As faixas órbitas devem ser globalmente exclusivas entre a implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-124">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="7a3d3-p105">Você também define outras configurações de Estacionamento de Chamada, como para onde as chamadas são redirecionadas quando atingem o tempo limite e se a pessoa ao telefone ouve música enquanto aguarda. Você também pode especificar o arquivo de música a ser reproduzido enquanto a chamada está em espera.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-p105">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a3d3-127">Os arquivos personalizados de música em espera para o estacionamento de chamadas não fazem backup como parte do processo de recuperação de desastres do Lync Server 2013 e serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-127">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="7a3d3-128">Mantenha sempre uma cópia de backup separada dos arquivos de música de espera personalizados que você enviar ao Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-128">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="7a3d3-129">O aplicativo Estacionamento de Chamada é um componente do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-129">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="7a3d3-130">Ao implantar o Enterprise Voice, o aplicativo de estacionamento de chamada é instalado e ativado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-130">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="7a3d3-131">No entanto, antes de poder usar o parque de chamadas, o administrador do Enterprise Voice deve configurá-lo e habilitá-lo para os usuários por meio da política de voz.</span><span class="sxs-lookup"><span data-stu-id="7a3d3-131">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

