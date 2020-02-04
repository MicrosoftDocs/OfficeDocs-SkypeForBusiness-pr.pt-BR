---
title: 'Lync Server 2013: Configurar planos de discagem para conferência discada'
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
ms.openlocfilehash: 544c431257dea20db729e80dd1d9acc565da8201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-plans-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="fb05b-102">Configurar planos de discagem para conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb05b-102">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb05b-103">_**Tópico da última modificação:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="fb05b-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="fb05b-104">Ao implantar a conferência discada, você precisa criar ou modificar um ou mais planos de discagem para o roteamento de números de telefone de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="fb05b-104">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="fb05b-105">Certifique-se de que pelo menos uma regra de normalização em cada plano de discagem converte ramais de telefone em números de telefone completos no formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="fb05b-105">Make sure that at least one normalization rule in each dial plan converts telephone extensions into complete phone numbers in E.164 format.</span></span> <span data-ttu-id="fb05b-106">Os usuários da conferência discada participam de conferências como usuários corporativos autenticados, digitando seu número de identificação pessoal (PIN) e seu número de telefone.</span><span class="sxs-lookup"><span data-stu-id="fb05b-106">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number.</span></span> <span data-ttu-id="fb05b-107">Você precisa de uma regra de normalização para converter ramais em números de telefone completos, de forma que os usuários possam ser autenticados ao inserir somente um ramal telefônico.</span><span class="sxs-lookup"><span data-stu-id="fb05b-107">You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>

<span data-ttu-id="fb05b-108">Para configurar planos de discagem para conferência discada, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fb05b-108">To set up dial plans for dial-in conferencing, do the following:</span></span>

  - <span data-ttu-id="fb05b-109">Independente de implantar o Enterprise Voice, modifique o plano de discagem global para adicionar uma região de conferência discada e para garantir que uma regra de normalização converta seus números de acesso discado de modo preciso.</span><span class="sxs-lookup"><span data-stu-id="fb05b-109">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="fb05b-110">Para obter instruções detalhadas, consulte [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="fb05b-110">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

  - <span data-ttu-id="fb05b-111">Se você não implantou o Enterprise Voice, crie planos de discagem para todos os seus números de acesso de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="fb05b-111">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="fb05b-112">Certifique-se de incluir uma região de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="fb05b-112">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="fb05b-113">Para obter instruções detalhadas, consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="fb05b-113">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

  - <span data-ttu-id="fb05b-114">Se você implantou o Enterprise Voice, modifique os planos de discagem do Enterprise Voice conforme necessário para incluir regiões e usar regras de normalização apropriadas para números de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="fb05b-114">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="fb05b-115">Para obter instruções detalhadas, consulte [modificar um plano de discagem no Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="fb05b-115">For detailed instructions, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span> <span data-ttu-id="fb05b-116">Você também pode criar planos de discagem dedicados, usados somente para números de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="fb05b-116">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="fb05b-117">Para obter instruções detalhadas, consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="fb05b-117">For detailed instructions, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<span data-ttu-id="fb05b-118">Para obter detalhes sobre regiões de planejamento, consulte [requisitos de conferência discada no Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="fb05b-118">For details about planning regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fb05b-119">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="fb05b-119">In This Section</span></span>

  - [<span data-ttu-id="fb05b-120">Exibir informações do plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb05b-120">View dial plan information in Lync Server 2013</span></span>](lync-server-2013-view-dial-plan-information.md)

  - [<span data-ttu-id="fb05b-121">Criar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb05b-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)

  - [<span data-ttu-id="fb05b-122">Modificar um plano de discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb05b-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)

  - [<span data-ttu-id="fb05b-123">Definindo regras de normalização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb05b-123">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

