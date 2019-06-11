---
title: 'Lync Server 2013: Configurar número de acesso da conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d42d8fbe6d3f507d0cadb7dc879b940191c04603
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="485f6-102">Configurar número de acesso da conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="485f6-102">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="485f6-103">_**Tópico da última modificação:** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="485f6-103">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="485f6-104">Ao implantar uma conferência discada, você precisa configurar números de telefone que os usuários poderão discar da PSTN para participar da parte de áudio das conferências.</span><span class="sxs-lookup"><span data-stu-id="485f6-104">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="485f6-105">Esses números de acesso de discagem aparecem nos convites de reunião e na página Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="485f6-105">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="485f6-106">Antes de criar números de acesso discado, primeiro você precisa planejar as regiões de conferência discada e, em seguida, configurar os planos de discagem nas regiões.</span><span class="sxs-lookup"><span data-stu-id="485f6-106">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="485f6-107">Para obter detalhes sobre regiões, consulte [requisitos de conferência discada no Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="485f6-107">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="485f6-108">Para obter detalhes sobre como configurar planos de discagem para conferência discada, consulte [configurar planos de discagem para conferência discada no Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="485f6-108">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="485f6-109">Você não pode usar um novo número de acesso discada até que a duplicação dos&nbsp;serviços de domínio Active Directory (AD DS) desse número de acesso seja concluída.</span><span class="sxs-lookup"><span data-stu-id="485f6-109">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="485f6-110">A replicação pode demorar algumas horas para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="485f6-110">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="485f6-111">Após a criação dos números de acesso discado, é possível modificar o nome de exibição dos objetos de contato do Active Directory de modo que os usuários possam identificar com mais facilidade o número de acesso correto.</span><span class="sxs-lookup"><span data-stu-id="485f6-111">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="485f6-112">Use o cmdlet <STRONG>set-CsDialInConferencingAccessNumber</STRONG> para modificar o nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="485f6-112">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="485f6-113">Não modifique os objetos do Active Directory manualmente.</span><span class="sxs-lookup"><span data-stu-id="485f6-113">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="485f6-114">Para obter detalhes sobre como modificar um número de acesso, consulte documentação do Shell de gerenciamento do Lync Server para o cmdlet <STRONG>set-CsDialInConferencingAccessNumber</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="485f6-114">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="485f6-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="485f6-115">In This Section</span></span>

[<span data-ttu-id="485f6-116">Criar ou modificar um número de acesso de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="485f6-116">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="485f6-117">Confira também</span><span class="sxs-lookup"><span data-stu-id="485f6-117">See Also</span></span>


[<span data-ttu-id="485f6-118">Requisitos de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="485f6-118">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="485f6-119">Configurar planos de discagem para conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="485f6-119">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

