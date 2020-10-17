---
title: 'Lync Server 2013: configurar planos de discagem para conferência discada'
description: 'Lync Server 2013: configurar planos de discagem para conferência discada.'
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
ms.openlocfilehash: 28123f905288ce35b6f470168962a3d8e6faa22b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567577"
---
# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="fb02e-103">Configurar planos de discagem para conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb02e-103">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb02e-104">_**Última modificação do tópico:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="fb02e-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="fb02e-p101">Quando você implanta a conferência discada, precisa criar ou modificar um ou mais planos de discagem para o roteamento de números de telefone de acesso de discagem. Verifique se pelo menos uma regra de normalização em cada plano de discagem converte ramais telefônicos em números de telefone completos no formato E.164. Os usuários da conferência discada ingressam em conferências como usuários corporativos autenticados, digitando seu PIN (número de identificação pessoal) e seu número de telefone. Você precisa de uma regra de normalização para converter ramais em números de telefone completos, de forma que os usuários possam ser autenticados ao inserir somente um ramal telefônico.</span><span class="sxs-lookup"><span data-stu-id="fb02e-p101">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers. Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format. Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="fb02e-109">Para configurar planos de discagem para conferência discada, execute o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="fb02e-109">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="fb02e-110">Quer você implante ou não o Enterprise Voice, modifique o plano de discagem global para adicionar uma região de conferência discada e para garantir que uma regra de normalização converta precisamente seus números de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="fb02e-110">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="fb02e-111">Para obter instruções detalhadas, consulte [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="fb02e-111">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="fb02e-112">Se você não implantou o Enterprise Voice, crie planos de discagem para seus números de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="fb02e-112">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="fb02e-113">Certifique-se de incluir uma região de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="fb02e-113">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="fb02e-114">Para obter instruções detalhadas, consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="fb02e-114">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="fb02e-115">Se você implantou o Enterprise Voice, modifique os planos de discagem do Enterprise Voice conforme necessário para incluir regiões e usar regras de normalização apropriadas para números de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="fb02e-115">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="fb02e-116">Para obter instruções detalhadas, consulte [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="fb02e-116">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="fb02e-117">Você também pode criar planos de discagem dedicados, usados somente para números de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="fb02e-117">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="fb02e-118">Para obter instruções detalhadas, consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="fb02e-118">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="fb02e-119">Para obter detalhes sobre as regiões de planejamento, confira [requisitos de conferência discada no Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="fb02e-119">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fb02e-120">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="fb02e-120">In This Section</span></span>

  - [<span data-ttu-id="fb02e-121">Exibir informações do plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb02e-121">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="fb02e-122">Criar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb02e-122">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="fb02e-123">Modificar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb02e-123">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="fb02e-124">Definindo regras de normalização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb02e-124">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

