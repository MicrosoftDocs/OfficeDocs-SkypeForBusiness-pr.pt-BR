---
title: 'Lync Server 2013: configurar números de acesso de conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83c7069db95d36e79d74cea81faf3aa98685832f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504768"
---
# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="b9826-102">Configurar números de acesso de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9826-102">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9826-103">_**Última modificação do tópico:** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="b9826-103">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="b9826-p101">Ao implantar uma conferência discada, você precisa configurar números de telefone que os usuários poderão discar da PSTN para participar da parte de áudio das conferências. Esses números de acesso de discagem aparecem nos convites de reunião e na página Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="b9826-p101">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="b9826-106">Antes de criar números de acesso discado, primeiro você precisa planejar as regiões de conferência discada e, em seguida, configurar os planos de discagem nas regiões.</span><span class="sxs-lookup"><span data-stu-id="b9826-106">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="b9826-107">Para obter detalhes sobre regiões, consulte [requisitos de conferência discada no Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="b9826-107">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="b9826-108">Para obter detalhes sobre como configurar planos de discagem para conferência discada, consulte [configurar planos de discagem para conferência discada no Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="b9826-108">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9826-109">Você não pode usar um novo número de acesso de discagem até que a replicação dos serviços de domínio do Active Directory (AD &nbsp; DS) desse número de acesso esteja concluída.</span><span class="sxs-lookup"><span data-stu-id="b9826-109">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="b9826-110">A replicação pode demorar algumas horas para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="b9826-110">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b9826-111">Após a criação dos números de acesso discado, é possível modificar o nome de exibição dos objetos de contato do Active Directory de modo que os usuários possam identificar com mais facilidade o número de acesso correto.</span><span class="sxs-lookup"><span data-stu-id="b9826-111">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="b9826-112">Use o cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> para modificar o nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="b9826-112">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="b9826-113">Não modifique os objetos do Active Directory manualmente.</span><span class="sxs-lookup"><span data-stu-id="b9826-113">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="b9826-114">Para obter detalhes sobre como modificar um número de acesso, consulte Lync Server Management Shell Documentation for the <STRONG>set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b9826-114">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b9826-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b9826-115">In This Section</span></span>

[<span data-ttu-id="b9826-116">Criar ou modificar um número de acesso de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9826-116">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b9826-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="b9826-117">See Also</span></span>


[<span data-ttu-id="b9826-118">Requisitos de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9826-118">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="b9826-119">Configurar planos de discagem para conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9826-119">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

