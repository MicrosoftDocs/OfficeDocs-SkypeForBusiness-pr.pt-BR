---
title: 'Lync Server 2013: visão geral do recebimento de chamadas em grupo'
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
ms.openlocfilehash: d9001d3e89e07943915b923ec4bfa8abf2683c78
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="4a901-102">Visão geral do recebimento de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a901-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a901-103">_**Última modificação do tópico:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="4a901-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="4a901-104">Atendimento de chamadas em grupo, um novo recurso em atualizações cumulativas do Lync Server 2013:2013 de fevereiro, permite que os usuários respondam chamadas de entrada para seus colegas de seus próprios telefones.</span><span class="sxs-lookup"><span data-stu-id="4a901-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="4a901-105">Esse novo recurso aumenta a disponibilidade da linha de um usuário permitindo que outros usuários respondam a uma chamada de entrada discando um número de grupo de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="4a901-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="4a901-106">Quando o recebimento de chamadas em grupo é implantado, o número de chamadas de entrada que são roteadas para caixa postal pode ser significativamente reduzido, o que é particularmente útil para chamadas de clientes que são externos à sua organização.</span><span class="sxs-lookup"><span data-stu-id="4a901-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="4a901-107">O recurso de recebimento de chamadas de grupo é projetado especificamente para unidades de negócios em ambientes abertos do Office.</span><span class="sxs-lookup"><span data-stu-id="4a901-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="4a901-108">As chamadas de entrada não causam interrupções porque tocam apenas no destino desejado.</span><span class="sxs-lookup"><span data-stu-id="4a901-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="4a901-109">Outros usuários que ouvirem o toque, no entanto, ainda podem pegar a chamada simplesmente discando o número do grupo.</span><span class="sxs-lookup"><span data-stu-id="4a901-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="4a901-110">Em ambientes em que os usuários não estão localizados em um layout de escritório aberto ou onde os usuários que compartilham uma responsabilidade comum são distribuídos geograficamente, a chamada de equipe apresenta a solução mais adequada.</span><span class="sxs-lookup"><span data-stu-id="4a901-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="4a901-111">A principal diferença entre o recebimento de chamadas em grupo e a chamada de equipe é que, com o recebimento de chamadas de grupo, uma chamada de entrada tocará somente no destino desejado, mas qualquer pessoa ainda pode optar por respondê-la discando um número de grupo.</span><span class="sxs-lookup"><span data-stu-id="4a901-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="4a901-112">Com a chamada em equipe, a chamada toca em todos os telefones dos membros da equipe e qualquer usuário na equipe pode pegar o telefone para responder à chamada.</span><span class="sxs-lookup"><span data-stu-id="4a901-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="4a901-113">Uma diferença adicional entre o recebimento de chamadas em grupo e a chamada de equipe é que o recebimento de chamadas de grupo é gerenciado por um administrador, por meio do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a901-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="4a901-114">Com a chamada em equipe, os usuários finais gerenciam o recurso usando o cliente Lync.</span><span class="sxs-lookup"><span data-stu-id="4a901-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="4a901-115">Com o recebimento de chamadas em grupo, esse aspecto do gerenciamento de chamadas pode ser centralizado.</span><span class="sxs-lookup"><span data-stu-id="4a901-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="4a901-116">O recebimento de chamadas em grupo é criado no aplicativo de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="4a901-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="4a901-117">Ao implantar o recebimento de chamadas em grupo, você configura a tabela de órbita de estacionamento de chamada com intervalos separados de números de ramal designados como números de grupo de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="4a901-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="4a901-118">Como números de órbita de estacionamento de chamada, os números de grupo de recebimento de chamada devem ser extensões virtuais que não têm nenhum usuário ou telefone atribuído a eles.</span><span class="sxs-lookup"><span data-stu-id="4a901-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="4a901-119">Cada pool de front-ends onde você implanta o recebimento de chamadas em grupo pode ter um ou mais intervalos de números de grupo de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="4a901-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="4a901-120">Os intervalos de números de grupo devem ser globalmente exclusivos na implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a901-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a901-121">Os intervalos de números designados como números de recebimento de chamada em grupo na tabela de órbita de estacionamento de chamadas não podem ser gerenciados ou exibidos usando o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a901-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="4a901-122">A única maneira de ver todos os intervalos de números na tabela de órbita de estacionamento de chamada é usar o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a901-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="4a901-123">Da mesma forma, a única maneira de adicionar, modificar ou remover números de recebimento de chamadas de grupo é usar o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a901-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="4a901-124">Depois de configurar os números de grupo de recebimento de chamada, você atribui usuários a um grupo de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="4a901-124">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="4a901-125">Qualquer usuário atribuído a um grupo de recebimento de chamadas pode ter suas chamadas atendidas por outros usuários.</span><span class="sxs-lookup"><span data-stu-id="4a901-125">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="4a901-126">Quando uma chamada chega a um usuário atribuído a um grupo de recebimento de chamadas, qualquer outro usuário que observe a chamada pode respondê-la, discando manualmente o número do grupo de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="4a901-126">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="4a901-127">O usuário que escolhe a chamada não precisa ser um membro do grupo.</span><span class="sxs-lookup"><span data-stu-id="4a901-127">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="4a901-128">Quando uma chamada é selecionada por outro usuário, uma notificação é enviada para o número chamado originalmente.</span><span class="sxs-lookup"><span data-stu-id="4a901-128">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4a901-129">Um usuário pode ser um membro de apenas um grupo de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="4a901-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="4a901-130">Embora qualquer usuário na implantação do Lync Server possa atender a uma chamada para um membro do grupo de recebimento de chamadas, a pessoa que está respondendo à chamada deve saber o número correto do grupo de recebimento de chamadas para discar.</span><span class="sxs-lookup"><span data-stu-id="4a901-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="4a901-131">Se um usuário discar um número de grupo de recebimento de chamada para responder a uma chamada quando vários telefones no grupo estiverem tocando, o usuário responderá à chamada que está tocando o mais longo.</span><span class="sxs-lookup"><span data-stu-id="4a901-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="4a901-132">As configurações de toque simultâneo funcionarão para usuários que tenham o recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="4a901-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="4a901-133">Ou seja, uma chamada feita a um usuário que tenha o recebimento de chamadas de grupo tocará para todos os destinos configurados e outro usuário poderá atender à chamada.</span><span class="sxs-lookup"><span data-stu-id="4a901-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="4a901-134">A exceção a essa regra é quando o usuário configura o toque simultâneo para chamar todos os membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="4a901-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="4a901-135">O recebimento de chamadas em grupo não pode ser usado para atender os seguintes tipos de chamadas:</span><span class="sxs-lookup"><span data-stu-id="4a901-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="4a901-136">Chamadas para uma linha privada</span><span class="sxs-lookup"><span data-stu-id="4a901-136">Calls to a private line</span></span>

  - <span data-ttu-id="4a901-137">Chamadas de um contato que recebeu a relação de privacidade de amigos e familiares</span><span class="sxs-lookup"><span data-stu-id="4a901-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="4a901-138">Um usuário que seja membro de um grupo de recebimento de chamadas pode impedir que determinadas chamadas sejam recuperadas por meio do recebimento de chamadas em grupo, marcando o contato como um contato pessoal no cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="4a901-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="4a901-139">Para marcar um contato como contato pessoal, defina a relação de privacidade do contato como amigos e família.</span><span class="sxs-lookup"><span data-stu-id="4a901-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="4a901-140">Qualquer chamada de entrada de contatos com a relação de privacidade definida como amigos e família não pode ser recuperada usando o recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="4a901-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="4a901-141">Parte de vídeo de chamadas de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="4a901-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4a901-142">Se um usuário responder a uma chamada de áudio/vídeo, o usuário receberá apenas o áudio.</span><span class="sxs-lookup"><span data-stu-id="4a901-142">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="4a901-143">A pessoa que está ligando ou a pessoa que responde a chamada pode escalonar a chamada para adicionar vídeo.</span><span class="sxs-lookup"><span data-stu-id="4a901-143">Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="4a901-144">Chamadas de toque simultâneas roteadas para membros da chamada em equipe</span><span class="sxs-lookup"><span data-stu-id="4a901-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="4a901-145">Chamadas roteadas para um representante</span><span class="sxs-lookup"><span data-stu-id="4a901-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="4a901-146">Chamadas encaminhadas para um grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="4a901-146">Calls routed to a response group</span></span>

<span data-ttu-id="4a901-147">Os tipos de usuários a seguir não podem participar do recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="4a901-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="4a901-148">Ou seja, eles não devem ser incluídos em um grupo de recebimento de chamadas de grupo e não podem pegar chamadas para usuários que tenham o recebimento de chamadas de grupo habilitado.</span><span class="sxs-lookup"><span data-stu-id="4a901-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="4a901-149">Usuários hospedados online em uma implantação híbrida</span><span class="sxs-lookup"><span data-stu-id="4a901-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="4a901-150">Usuários que não estão hospedados em um pool do Lync Server 2013 com atualizações cumulativas do Lync Server 2013:2013 de fevereiro em uma implantação local</span><span class="sxs-lookup"><span data-stu-id="4a901-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="4a901-151">Se ninguém responder uma chamada para um membro de um grupo de recebimento de chamada, a chamada será roteada conforme especificado nas configurações do cliente.</span><span class="sxs-lookup"><span data-stu-id="4a901-151">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="4a901-152">Ou seja, a chamada vai para a caixa postal ou é encaminhada para um destino diferente, conforme especificado nas configurações do cliente.</span><span class="sxs-lookup"><span data-stu-id="4a901-152">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

