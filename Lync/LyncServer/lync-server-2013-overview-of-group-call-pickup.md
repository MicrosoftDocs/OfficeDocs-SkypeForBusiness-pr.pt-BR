---
title: 'Lync Server 2013: visão geral do recurso de recebimento de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0efc85b28a689b43d024d9996211a70dcd91cee0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="23c67-102">Visão geral da retirada de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23c67-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23c67-103">_**Tópico da última modificação:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="23c67-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="23c67-104">Recebimento de chamadas em grupo, um novo recurso em atualizações cumulativas para o Lync Server 2013:2013 de fevereiro, permite que os usuários atendam às chamadas recebidas para seus colegas pelos próprios telefones.</span><span class="sxs-lookup"><span data-stu-id="23c67-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="23c67-105">Esse novo recurso aumenta a disponibilidade de uma linha de usuário permitindo que outros usuários atendam a uma chamada de entrada discando um número de grupo de recebimento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="23c67-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="23c67-106">Quando o recebimento de chamadas em grupo é implantado, o número de chamadas de entrada direcionadas para o correio de voz pode ser reduzido significativamente, o que é especialmente útil para chamadas de clientes externos à sua organização.</span><span class="sxs-lookup"><span data-stu-id="23c67-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="23c67-107">O recurso de recebimento de chamadas em grupo foi projetado especificamente para unidades de negócios em ambientes abertos do Office.</span><span class="sxs-lookup"><span data-stu-id="23c67-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="23c67-108">Chamadas de entrada não perturbam porque tocam somente no destino desejado.</span><span class="sxs-lookup"><span data-stu-id="23c67-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="23c67-109">Porém, outros usuários que escutam o toque podem atender a chamada simplesmente discando o número de grupo de atendimento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="23c67-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="23c67-110">Em ambientes em que os usuários não estão localizados em um layout de escritório aberto ou em que os usuários que compartilham uma responsabilidade comum estão espalhados geograficamente, a chamada em equipe apresenta-se como a solução mais adequada.</span><span class="sxs-lookup"><span data-stu-id="23c67-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="23c67-111">A principal diferença entre o recebimento de chamadas em grupo e a chamada de equipe é que, com o recebimento de chamadas em grupo, uma chamada de entrada tocará somente no destino pretendido, mas qualquer pessoa ainda poderá atendê-la ao discar um número de grupo.</span><span class="sxs-lookup"><span data-stu-id="23c67-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="23c67-112">Com chamada em equipe, a chamada toca nos telefones de todos os membros da equipe e qualquer usuário na equipe pode atender o telefone para responder à chamada.</span><span class="sxs-lookup"><span data-stu-id="23c67-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="23c67-113">Uma diferença adicional entre o recebimento de chamadas em grupo e a chamada de equipe é que o recebimento de chamadas em grupo é gerenciado por um administrador, por meio do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23c67-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="23c67-114">Com a chamada de equipe, os usuários finais gerenciam o recurso usando o cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="23c67-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="23c67-115">Com o recebimento de chamadas em grupo, esse aspecto do gerenciamento de chamadas pode ser centralizado.</span><span class="sxs-lookup"><span data-stu-id="23c67-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="23c67-116">O recebimento de chamadas em grupo foi criado no aplicativo de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="23c67-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="23c67-117">Ao implantar o recurso de recebimento de chamadas em grupo, configure a tabela órbita do estacionamento de chamada com intervalos separados de números de ramal designados como números de grupo de retirada de chamadas.</span><span class="sxs-lookup"><span data-stu-id="23c67-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="23c67-118">Como os números de órbita de estacionamento de chamadas, os números de grupo de atendimento de chamadas precisam ser extensões virtuais que não têm um usuário ou telefone atribuídos a elas.</span><span class="sxs-lookup"><span data-stu-id="23c67-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="23c67-119">Cada pool de front-ends onde você implanta o recebimento de chamadas em grupo pode ter um ou mais intervalos de números de grupo de recebimento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="23c67-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="23c67-120">Os intervalos de números de grupo devem ser globalmente exclusivos na implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23c67-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="23c67-121">Os intervalos de números que são designados como números de recebimento de chamadas em grupo na tabela órbita do parque de chamadas não podem ser gerenciados ou exibidos usando o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23c67-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="23c67-122">A única maneira de ver todos os intervalos de números na tabela órbita do estacionamento de chamada é usar o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23c67-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="23c67-123">Da mesma forma, a única maneira de adicionar, modificar ou remover números de recebimento de chamadas em grupo é usar o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="23c67-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="23c67-p106">Após você configurar os números de grupos de atendimento de chamadas, você atribui usuários a um grupo de atendimento de chamadas. Qualquer usuário que for atribuído a um grupo de atendimento de chamadas pode ter suas chamadas atendidas por outros usuários. Quando uma chamada chega para um usuário atribuído a um grupo de atendimento de chamadas, qualquer outro usuário que perceba a chamada pode atendê-la manualmente discando o número de grupo de atendimento de chamadas. O usuário que atender a chamada não precisa ser um membro do grupo. Quando uma chamada é atendida por outro usuário, uma notificação é enviada ao número que foi chamado originalmente.</span><span class="sxs-lookup"><span data-stu-id="23c67-p106">After you configure the call pickup group numbers, you assign users to a call pickup group. Any user who is assigned to a call pickup group can have their calls answered by other users. When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number. The user who picks up the call does not need to be a member of the group. When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="23c67-129">Um usuário pode ser membro de somente um grupo de atendimento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="23c67-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="23c67-130">Embora qualquer usuário na implantação do Lync Server possa atender a uma chamada para um membro do grupo de recebimento de chamadas, a pessoa que atende a chamada precisa saber o número correto de grupo de recebimento de chamadas para discar.</span><span class="sxs-lookup"><span data-stu-id="23c67-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="23c67-131">Se um usuário discar um número de grupo de atendimento de chamadas para atender uma chamada quando diversos telefones no grupo estiverem tocando, o usuário atenderá a chamada que estiver tocando a mais tempo.</span><span class="sxs-lookup"><span data-stu-id="23c67-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="23c67-132">Configurações de toque simultâneo funcionarão para usuários habilitados para atendimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="23c67-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="23c67-133">Ou seja, uma chamada feita para um usuário que tem o recurso de chamada em grupo tocará para todos os destinos configurados e outro usuário poderá atender a chamada.</span><span class="sxs-lookup"><span data-stu-id="23c67-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="23c67-134">A exceção para essa regra é quando o usuário configura toque simultâneo para todos os membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="23c67-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="23c67-135">Não é possível usar o recurso de recebimento de chamadas em grupo para atender aos seguintes tipos de chamadas:</span><span class="sxs-lookup"><span data-stu-id="23c67-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="23c67-136">Chamadas a uma linha privada</span><span class="sxs-lookup"><span data-stu-id="23c67-136">Calls to a private line</span></span>

  - <span data-ttu-id="23c67-137">Chamadas de um contato ao qual foi atribuída a política de privacidade Amigos e Família</span><span class="sxs-lookup"><span data-stu-id="23c67-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="23c67-138">Um usuário que é membro de um grupo de recebimento de chamadas pode impedir que determinadas chamadas sejam recuperadas por meio da passagem de chamadas em grupo, marcando o contato como um contato pessoal no cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="23c67-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="23c67-139">Para marcar um contato como seu contato pessoal, defina a Relação de Privacidade para o contato como Amigos e Família.</span><span class="sxs-lookup"><span data-stu-id="23c67-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="23c67-140">Qualquer chamada de entrada de contatos com a relação de privacidade definida como amigos e parentes não pode ser recuperada usando a retirada de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="23c67-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="23c67-141">Porção de vídeo de chamadas de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="23c67-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="23c67-p109">Se um usuário responde uma chamada de áudio/vídeo, ele recebe somente o áudio. Tanto a pessoa que realizou a chamada quanto a que está recebendo podem escalar a chamada para adicionar o vídeo.</span><span class="sxs-lookup"><span data-stu-id="23c67-p109">If a user answers an audio/video call, the user receives only the audio. Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="23c67-144">Chamadas de toque simultâneo que são direcionada para membros da equipe de atendimento de chamadas</span><span class="sxs-lookup"><span data-stu-id="23c67-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="23c67-145">Chamadas direcionadas a um representante</span><span class="sxs-lookup"><span data-stu-id="23c67-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="23c67-146">Chamadas direcionadas a um grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="23c67-146">Calls routed to a response group</span></span>

<span data-ttu-id="23c67-147">Os tipos de usuários a seguir não podem participar da retirada de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="23c67-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="23c67-148">Ou seja, eles não devem ser incluídos em um grupo de recebimento de chamadas em grupo e não podem atender chamadas para usuários que tenham o recurso de recebimento de chamadas em grupo habilitado.</span><span class="sxs-lookup"><span data-stu-id="23c67-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="23c67-149">Usuários que estão hospedados em uma implantação híbrida</span><span class="sxs-lookup"><span data-stu-id="23c67-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="23c67-150">Usuários que não são hospedados em um pool do Lync Server 2013 com atualizações cumulativas do Lync Server 2013:2013 de fevereiro em uma implantação local</span><span class="sxs-lookup"><span data-stu-id="23c67-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="23c67-p111">Se ninguém responder uma chamada destinada a um membro de um grupo de atendimento de chamadas, ela é direcionada conforme especificado nas configurações do cliente. Ou seja, a chamada vai para correio de voz e ou é direcionada para um outro destino, conforme estiver especificado nas configurações do cliente.</span><span class="sxs-lookup"><span data-stu-id="23c67-p111">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings. That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

