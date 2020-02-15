---
title: 'Lync Server 2013: usando ligar para mim com um telefone habilitado para Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c94820ea7f72b0a2a7afc60b6736c02d96695ea0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a><span data-ttu-id="c4e46-102">Usando ligar para mim com um telefone habilitado para Lync e o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4e46-102">Using Call Me At with a Lync-enabled phone and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4e46-103">_**Última modificação do tópico:** 2013-08-09_</span><span class="sxs-lookup"><span data-stu-id="c4e46-103">_**Topic Last Modified:** 2013-08-09_</span></span>

<span data-ttu-id="c4e46-104">O recurso ligar para mim no Lync oferece uma maneira de os usuários ingressarem na parte de áudio de uma conferência usando um telefone celular, "linha de terreno" ou outro dispositivo conectado à rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="c4e46-104">The Call Me At feature in Lync provides a way for users to join the audio portion of a conference by using a cell phone, “land line,” or other device connected to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="c4e46-105">Ao tentar ingressar em uma reunião usando o Lync, você normalmente verá a caixa de diálogo **ingressar em áudio de reunião** :</span><span class="sxs-lookup"><span data-stu-id="c4e46-105">When you attempt to join a meeting by using Lync, you will typically be presented with the **Join Meeting Audio** dialog box:</span></span>

<span data-ttu-id="c4e46-106">![Usar o Lync para participar da captura de tela da janela de áudio da reunião](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Usar o Lync para participar da captura de tela da janela de áudio da reunião")</span><span class="sxs-lookup"><span data-stu-id="c4e46-106">![Use Lync to join meeting audio window screenshot](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Use Lync to join meeting audio window screenshot")</span></span>

<span data-ttu-id="c4e46-107">Se você selecionar **ligar para mim**, poderá escolher um número de telefone na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="c4e46-107">If you select **Call me at**, you can then pick a phone number from the dropdown list.</span></span> <span data-ttu-id="c4e46-108">O Lync Server 2013 fará uma chamada telefônica para o número selecionado e você poderá usar esse telefone para participar da parte de áudio da conferência.</span><span class="sxs-lookup"><span data-stu-id="c4e46-108">Lync Server 2013 will place a phone call to the selected number, and you can then use that phone to participate in the audio portion of the conference.</span></span>

<span data-ttu-id="c4e46-109">A lista suspensa é preenchida pelos números de telefone (para celular, telefone residencial ou outro telefone) digitado na guia **telefones** da caixa de diálogo **Lync – opções** :</span><span class="sxs-lookup"><span data-stu-id="c4e46-109">The dropdown list is populated by the phone numbers (for mobile phone, home phone, or other phone) that you have entered on the **Phones** tab in the **Lync – Options** dialog box:</span></span>

<span data-ttu-id="c4e46-110">![Captura de tela de opções de configuração do Lync phones](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Captura de tela de opções de configuração do Lync phones")</span><span class="sxs-lookup"><span data-stu-id="c4e46-110">![Lync Phones set up options screenshot](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Lync Phones set up options screenshot")</span></span>

<span data-ttu-id="c4e46-111">Se você não tiver inserido números de telefone na guia **telefones** , não haverá números disponíveis na caixa suspensa.</span><span class="sxs-lookup"><span data-stu-id="c4e46-111">If you have not entered any phone numbers on the **Phones** tab then you will not have any numbers available in the dropdown box.</span></span> <span data-ttu-id="c4e46-112">No entanto, você sempre pode clicar em **novo número** e fazer o Lync Server discar para qualquer número de telefone que desejar:</span><span class="sxs-lookup"><span data-stu-id="c4e46-112">However, you can always click **New Number** and have Lync Server dial out to any phone number you wish:</span></span>

<span data-ttu-id="c4e46-113">![Captura de tela do Lync ingressar em áudio de reuniões](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Captura de tela do Lync ingressar em áudio de reuniões")</span><span class="sxs-lookup"><span data-stu-id="c4e46-113">![Lync join meeting audio call me window screenshot](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Lync join meeting audio call me window screenshot")</span></span>

<span data-ttu-id="c4e46-114">O recurso ligar para mim funciona muito bem, desde que você o use da forma como era destinado: fazendo com que o Lync Server chame um número de telefone PSTN.</span><span class="sxs-lookup"><span data-stu-id="c4e46-114">The Call Me At feature works extremely well provided that you use it in the way it was intended: by having Lync Server call a PSTN phone number.</span></span> <span data-ttu-id="c4e46-115">No entanto, você pode executar uma experiência inferior à ideal se solicitar que o Lync Server chame você em um ponto de extremidade habilitado para Lync (por exemplo, um telefone em uma sala de conferência).</span><span class="sxs-lookup"><span data-stu-id="c4e46-115">However, you can run into a less-than-optimal experience if you ask Lync Server to call you at a Lync-enabled endpoint (for example, a phone in a conference room).</span></span> <span data-ttu-id="c4e46-116">Veja a seguir o problema que você pode executar, além de duas maneiras de contornar o problema.</span><span class="sxs-lookup"><span data-stu-id="c4e46-116">Following is the issue you might run into, as well as two ways to work around the problem.</span></span>

<span data-ttu-id="c4e46-117">Para começar, veja o que acontece quando você fornece o recurso ligar para mim com o número de telefone de um telefone habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="c4e46-117">To begin, here’s what happens when you provide the Call Me At feature with the phone number of a Lync-enabled phone.</span></span> <span data-ttu-id="c4e46-118">Suponha que Ken Myer tente ingressar em uma reunião com o Lync Server chamá-lo em 1-206-555-1219, um número de telefone habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4e46-118">Suppose Ken Myer tries to join a meeting by having Lync Server call him at 1-206-555-1219, a Lync Server-enabled phone number.</span></span> <span data-ttu-id="c4e46-119">Ken será inicialmente conectado à reunião, mas, após alguns segundos, o Lync exibirá a chamada de mensagem **não foi concluída ou terminou**, e Ken parecerá ter sido descartado da reunião:</span><span class="sxs-lookup"><span data-stu-id="c4e46-119">Ken will initially be connected to the meeting, but after a few seconds Lync will display the message **Call was not completed or has ended**, and Ken will appear to have been dropped from the meeting:</span></span>

<span data-ttu-id="c4e46-120">![Captura de tela da janela de conferência de chamada do Lync](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Captura de tela da janela de conferência de chamada do Lync")</span><span class="sxs-lookup"><span data-stu-id="c4e46-120">![Screen shot of Lync call conferencing window](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Screen shot of Lync call conferencing window")</span></span>

<span data-ttu-id="c4e46-121">No entanto, observe que há uma discrepância dentro da janela de conversa do Lync.</span><span class="sxs-lookup"><span data-stu-id="c4e46-121">Notice, however, that there is a discrepancy within the Lync conversation window.</span></span> <span data-ttu-id="c4e46-122">Ken Myer é o único nome listado no título dos **participantes** .</span><span class="sxs-lookup"><span data-stu-id="c4e46-122">Ken Myer is the only name listed under the **Participants** heading.</span></span> <span data-ttu-id="c4e46-123">No entanto, se você procurar na barra de título da janela, verá que a conferência contém um total de quatro participantes.</span><span class="sxs-lookup"><span data-stu-id="c4e46-123">However, if you look in the title bar of the window, you’ll see that the conference contains a total of 4 participants.</span></span>

<span data-ttu-id="c4e46-124">Da mesma forma, se você examinar a janela de conversa de qualquer um dos outros participantes da conferência, não verá Ken Myer listado em qualquer lugar:</span><span class="sxs-lookup"><span data-stu-id="c4e46-124">Likewise, if you look in the conversation window of any of the other conference participants you will not see Ken Myer listed anywhere:</span></span>

<span data-ttu-id="c4e46-125">![Captura de tela da janela de lista de participantes do Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Captura de tela da janela de lista de participantes do Lync")</span><span class="sxs-lookup"><span data-stu-id="c4e46-125">![Lync participant list window screenshot](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Lync participant list window screenshot")</span></span>

<span data-ttu-id="c4e46-126">E ainda, ao mesmo tempo, Ken Myer poderá participar da parte de áudio da chamada usando o telefone habilitado para Lync.</span><span class="sxs-lookup"><span data-stu-id="c4e46-126">And yet, at the same time, Ken Myer will be able to participate in the audio portion of the call by using his Lync-enabled phone.</span></span> <span data-ttu-id="c4e46-127">Na verdade, o recurso ligar para mim funcionou, mas a experiência do usuário é inferior à ideal.</span><span class="sxs-lookup"><span data-stu-id="c4e46-127">The Call Me At feature has actually worked, but the user experience is less than optimal.</span></span>

<span data-ttu-id="c4e46-128">Há pelo menos duas maneiras de contornar esse problema.</span><span class="sxs-lookup"><span data-stu-id="c4e46-128">There are at least two ways to work around this problem.</span></span> <span data-ttu-id="c4e46-129">Se você já tiver ingressado em uma conferência dessa maneira (como Ken Myer DID), normalmente poderá resolver o problema ao envolver uma modalidade diferente.</span><span class="sxs-lookup"><span data-stu-id="c4e46-129">If you have already joined a conference in this fashion (like Ken Myer did), you can typically resolve the issue by engaging in a different modality.</span></span> <span data-ttu-id="c4e46-130">Por exemplo, se você enviar uma mensagem instantânea, a janela de conversa agora mostrará todos os participantes da conferência, incluindo você mesmo:</span><span class="sxs-lookup"><span data-stu-id="c4e46-130">For example, if you send an instant message the conversation window will now show all the conference participants, including yourself:</span></span>

<span data-ttu-id="c4e46-131">![Captura de tela de conversa do Lync e lista de participantes](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Captura de tela de conversa do Lync e lista de participantes")</span><span class="sxs-lookup"><span data-stu-id="c4e46-131">![Lync conversation and participant list screenshot](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Lync conversation and participant list screenshot")</span></span>

<span data-ttu-id="c4e46-132">Neste ponto, você deve ser capaz de participar da reunião no modo esperado.</span><span class="sxs-lookup"><span data-stu-id="c4e46-132">At this point you should be able to participate in the meeting in the expected fashion.</span></span>

<span data-ttu-id="c4e46-133">Como alternativa, você pode evitar esse problema completamente alterando a forma como ingressar na reunião.</span><span class="sxs-lookup"><span data-stu-id="c4e46-133">Alternatively, you can avoid this issue altogether by changing the way you join the meeting.</span></span> <span data-ttu-id="c4e46-134">Se você precisar que a chamada do Lync Server seja um telefone habilitado para Lync Server, comece a ingressar na reunião sem uma conexão de áudio.</span><span class="sxs-lookup"><span data-stu-id="c4e46-134">If you need to have Lync Server call a Lync Server-enabled phone, you should begin by joining the meeting without an audio connection.</span></span> <span data-ttu-id="c4e46-135">Para fazer isso, selecione não ingressar no áudio quando aparecer a caixa de diálogo ingressar em áudio da reunião:</span><span class="sxs-lookup"><span data-stu-id="c4e46-135">To do that, select Don’t join audio when presented with the Join Meeting Audio dialog box:</span></span>

<span data-ttu-id="c4e46-136">![Lync não ingressar na tela de áudio da janela](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync não ingressar na tela de áudio da janela")</span><span class="sxs-lookup"><span data-stu-id="c4e46-136">![Lync don't join meeting audio window screenshot](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync don't join meeting audio window screenshot")</span></span>

<span data-ttu-id="c4e46-137">Após a conexão com êxito à reunião, agora você pode "convidar" o telefone habilitado para Lync Server para ingressar na reunião também.</span><span class="sxs-lookup"><span data-stu-id="c4e46-137">After you have successfully connected to the meeting, you can now “invite” the Lync Server-enabled phone to join the meeting as well.</span></span> <span data-ttu-id="c4e46-138">Para fazer isso, coloque o mouse sobre o ícone de pessoas e clique em **convidar mais pessoas**:</span><span class="sxs-lookup"><span data-stu-id="c4e46-138">To do that, place the mouse over the People icon and then click **Invite More People**:</span></span>

<span data-ttu-id="c4e46-139">![Captura de tela da janela de convite mais participantes do Lync](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Captura de tela da janela de convite mais participantes do Lync")</span><span class="sxs-lookup"><span data-stu-id="c4e46-139">![Lync invite more participants window screenshot](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Lync invite more participants window screenshot")</span></span>

<span data-ttu-id="c4e46-140">Isso exibirá a caixa de diálogo **Enviar uma mensagem instantânea** .</span><span class="sxs-lookup"><span data-stu-id="c4e46-140">That will bring up the **Send an IM** dialog box.</span></span> <span data-ttu-id="c4e46-141">Ignore o título da caixa de diálogo (você não está realmente enviando uma mensagem instantânea) e digite o número de telefone do telefone habilitado para Lync:</span><span class="sxs-lookup"><span data-stu-id="c4e46-141">Ignore the dialog box title (you’re not actually sending an instant message) and type the phone number of the Lync-enabled phone:</span></span>

<span data-ttu-id="c4e46-142">![Enviar uma captura de tela de caixa de diálogo de IM](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Enviar uma captura de tela de caixa de diálogo de IM")</span><span class="sxs-lookup"><span data-stu-id="c4e46-142">![Send an IM dialog box screenshot](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Send an IM dialog box screenshot")</span></span>

<span data-ttu-id="c4e46-143">Depois que você clicar em **OK**, o Lync Server chamará o número inserido na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c4e46-143">After you click **OK**, Lync Server will call the number entered in the dialog box.</span></span> <span data-ttu-id="c4e46-144">Quando a conexão for feita, você terá recursos de áudio completo por meio do telefone habilitado para Lync e poderá ver e interagir com a lista completa de conferência.</span><span class="sxs-lookup"><span data-stu-id="c4e46-144">When the connection is made, you will have full audio capabilities through the Lync-enabled phone, and you will be able to see and interact with the full conference roster.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

