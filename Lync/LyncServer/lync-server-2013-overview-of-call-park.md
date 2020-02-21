---
title: 'Lync Server 2013: visão geral do estacionamento de chamada'
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
ms.openlocfilehash: 1624042b07bc024d837e55ffac402cb2f158922f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="219d5-102">Visão geral do estacionamento de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="219d5-102">Overview of Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="219d5-103">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="219d5-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="219d5-104">O aplicativo de estacionamento de chamada do Lync Server 2013 permite que os usuários do Enterprise Voice realizem qualquer um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="219d5-104">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="219d5-105">Colocar uma chamada em espera e, em seguida, recuperar a chamada do mesmo telefone ou de outro telefone.</span><span class="sxs-lookup"><span data-stu-id="219d5-105">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="219d5-106">Colocar uma chamada em espera para transferi-la para um departamento ou área geral (por exemplo, para um departamento de vendas ou um depósito onde há um telefone de área comum).</span><span class="sxs-lookup"><span data-stu-id="219d5-106">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="219d5-107">Colocar uma chamada em espera e manter o telefone de resposta original livre para outras chamadas.</span><span class="sxs-lookup"><span data-stu-id="219d5-107">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="219d5-108">Quando um usuário armazena uma chamada, o Lync Server transfere a chamada para um número temporário, chamado de *órbita*, onde a chamada é mantida até que seja recuperada ou o tempo limite se esgote. O Lync Server envia a órbita para o usuário que estaciona a chamada.</span><span class="sxs-lookup"><span data-stu-id="219d5-108">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="219d5-109">Para recuperar a chamada estacionada, o usuário pode discar o número de órbita ou clicar no botão ou link de órbita na janela de conversa.</span><span class="sxs-lookup"><span data-stu-id="219d5-109">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="219d5-110">O usuário que estaciona uma chamada pode notificar alguém para recuperar a chamada usando um mecanismo externo, como mensagens instantâneas (IM) ou um sistema de paginação, para comunicar o número de órbita a outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="219d5-110">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="219d5-111">O usuário que estacionau a chamada pode deixar a janela de conversa aberta para receber uma notificação quando a chamada é recuperada.</span><span class="sxs-lookup"><span data-stu-id="219d5-111">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="219d5-112">Como os intervalos de órbita são globalmente exclusivos, é possível recuperar chamadas de qualquer site do Lync Server ou telefone PBX se o roteamento for configurado adequadamente.</span><span class="sxs-lookup"><span data-stu-id="219d5-112">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="219d5-113">Se ninguém recuperar a chamada dentro de um período configurável, a chamada tocará de volta para a pessoa que o estacionasse.</span><span class="sxs-lookup"><span data-stu-id="219d5-113">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="219d5-114">Se essa pessoa não atender ao retorno de toque, a chamada será transferida para um destino de fallback, como um operador, se configurada.</span><span class="sxs-lookup"><span data-stu-id="219d5-114">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="219d5-115">Você pode configurar o número de vezes que a chamada toca antes de ser transferida de uma a dez vezes.</span><span class="sxs-lookup"><span data-stu-id="219d5-115">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="219d5-116">Se ninguém responder a uma chamada transferida, a chamada será desconectada.</span><span class="sxs-lookup"><span data-stu-id="219d5-116">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="219d5-117">A órbita é liberada quando a chamada é recuperada ou desconectada.</span><span class="sxs-lookup"><span data-stu-id="219d5-117">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="219d5-118">Ao implantar o estacionamento de chamadas, você precisa reservar intervalos de números de ramal para o estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="219d5-118">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="219d5-119">Essas extensões precisam ser extensões virtuais: extensões que não têm nenhum usuário ou telefone atribuído a elas.</span><span class="sxs-lookup"><span data-stu-id="219d5-119">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="219d5-120">Em seguida, você configura a tabela de órbita de estacionamento de chamada com os intervalos de números de ramal e especifica qual serviço de aplicativo hospeda o aplicativo de estacionamento de chamada que lida com cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="219d5-120">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="219d5-121">Cada pool de front-ends tem uma tabela de estacionamento de chamada no servidor back-end correspondente, que é usado para gerenciar chamadas estacionadas no pool.</span><span class="sxs-lookup"><span data-stu-id="219d5-121">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="219d5-122">A lista de intervalos de órbita é armazenada no repositório de gerenciamento central e é usada para rotear órbitas para o pool de destino.</span><span class="sxs-lookup"><span data-stu-id="219d5-122">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="219d5-123">Cada pool do Lync Server onde o aplicativo de estacionamento de chamada é implantado e configurado pode ter um ou mais intervalos de órbita.</span><span class="sxs-lookup"><span data-stu-id="219d5-123">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="219d5-124">Os intervalos de órbita devem ser globalmente exclusivos na implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="219d5-124">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="219d5-125">Você também define outras configurações de estacionamento de chamadas, como onde as chamadas são redirecionadas se o tempo limite se esgotarem e se a pessoa no telefone ouvirá música enquanto estacionada.</span><span class="sxs-lookup"><span data-stu-id="219d5-125">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="219d5-126">Você também pode especificar o arquivo de música a ser tocado enquanto a chamada está em espera.</span><span class="sxs-lookup"><span data-stu-id="219d5-126">You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="219d5-127">Arquivos de música em espera personalizados para estacionamento de chamadas não são incluídos no backup como parte do processo de recuperação de desastres do Lync Server 2013 e serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados.</span><span class="sxs-lookup"><span data-stu-id="219d5-127">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="219d5-128">Mantenha sempre uma cópia de backup separada dos arquivos de música em espera personalizados que você carregou para o estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="219d5-128">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="219d5-129">O aplicativo de estacionamento de chamada é um componente do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="219d5-129">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="219d5-130">Quando você implanta o Enterprise Voice, o aplicativo de estacionamento de chamada é instalado e ativado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="219d5-130">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="219d5-131">No entanto, antes de poder usar o estacionamento de chamada, o administrador do Enterprise Voice deve configurá-lo e habilitá-lo para os usuários por meio da política de voz.</span><span class="sxs-lookup"><span data-stu-id="219d5-131">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

