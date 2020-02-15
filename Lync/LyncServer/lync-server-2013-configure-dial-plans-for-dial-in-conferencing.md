---
title: 'Lync Server 2013: configurar planos de discagem para conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial plans for dial-in conferencing
ms:assetid: a3e0958e-384f-43e5-b4c9-686b6ecac7ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412768(v=OCS.15)
ms:contentKeyID: 48185051
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e28dd2ddb0633a45d19f1a7bb7638d86e042658b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="d6a1e-102">Configurar planos de discagem para conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6a1e-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6a1e-103">_**Última modificação do tópico:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="d6a1e-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="d6a1e-p101">Quando você implanta a conferência discada, precisa criar ou modificar um ou mais planos de discagem para o roteamento de números de telefone de acesso de discagem. Verifique se pelo menos uma regra de normalização em cada plano de discagem converte ramais telefônicos em números de telefone completos no formato E.164. Os usuários da conferência discada ingressam em conferências como usuários corporativos autenticados, digitando seu PIN (número de identificação pessoal) e seu número de telefone. Você precisa de uma regra de normalização para converter ramais em números de telefone completos, de forma que os usuários possam ser autenticados ao inserir somente um ramal telefônico.</span><span class="sxs-lookup"><span data-stu-id="d6a1e-p101">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers. Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format. Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="d6a1e-108">Para configurar planos de discagem para conferência discada, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="d6a1e-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="d6a1e-109">Quer você implante ou não o Enterprise Voice, modifique o plano de discagem global para adicionar uma região de conferência discada e para garantir que uma regra de normalização converta precisamente seus números de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="d6a1e-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="d6a1e-110">Para obter instruções detalhadas, consulte [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="d6a1e-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="d6a1e-111">Se você não implantou o Enterprise Voice, crie planos de discagem para seus números de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="d6a1e-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="d6a1e-112">Certifique-se de incluir uma região de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="d6a1e-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="d6a1e-113">Para obter instruções detalhadas, consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="d6a1e-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="d6a1e-114">Se você implantou o Enterprise Voice, modifique os planos de discagem do Enterprise Voice conforme necessário para incluir regiões e usar regras de normalização apropriadas para números de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="d6a1e-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="d6a1e-115">Para obter instruções detalhadas, consulte [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="d6a1e-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="d6a1e-116">Você também pode criar planos de discagem dedicados, usados somente para números de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="d6a1e-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="d6a1e-117">Para obter instruções detalhadas, consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="d6a1e-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="d6a1e-118">Para obter detalhes sobre as regiões de planejamento, confira [requisitos de conferência discada no Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="d6a1e-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d6a1e-119">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d6a1e-119">In This Section</span></span>

  - [<span data-ttu-id="d6a1e-120">Exibir informações do plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6a1e-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="d6a1e-121">Criar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6a1e-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="d6a1e-122">Modificar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6a1e-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="d6a1e-123">Definindo regras de normalização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6a1e-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

