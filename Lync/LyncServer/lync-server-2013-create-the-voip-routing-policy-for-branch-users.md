---
title: 'Lync Server 2013: criar a política de roteamento VoIP para usuários de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cc958e5f643a18c45989d5835fd786c001899db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="06ed2-102">Criar a política de roteamento VoIP para usuários de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06ed2-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06ed2-103">_**Última modificação do tópico:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="06ed2-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="06ed2-104">É recomendável criar uma política VoIP separada para os usuários de locais de filial.</span><span class="sxs-lookup"><span data-stu-id="06ed2-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="06ed2-105">Essa política deve conter rotas para saída do gateway de aparelho de filial persistente ou gateway externo de servidor de filial persistente e rotas de backup para saída de um gateway no site central.</span><span class="sxs-lookup"><span data-stu-id="06ed2-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="06ed2-106">Independentemente de onde o usuário está registrado, seja no registrador de aplicativos de filial persistente ou servidor de filial persistente ou no cluster de registradores de backup no site central, a política de VoIP do usuário está sempre em vigor.</span><span class="sxs-lookup"><span data-stu-id="06ed2-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="06ed2-107">Para configurar a política de roteamento do VoIP para usuários de filiais</span><span class="sxs-lookup"><span data-stu-id="06ed2-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="06ed2-108">Criar um plano de discagem de nível de usuário e atribuí-lo aos usuários da filial.</span><span class="sxs-lookup"><span data-stu-id="06ed2-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="06ed2-109">(Consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md) na documentação de operações.)</span><span class="sxs-lookup"><span data-stu-id="06ed2-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="06ed2-110">Atribua regras de normalização que correspondam aos hábitos de discagem dos usuários nesse site.</span><span class="sxs-lookup"><span data-stu-id="06ed2-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="06ed2-111">Se o aparelho de filial persistente ou o usuário do servidor de filial persistente passar o pool de registradores de backup no site central, o mesmo plano de discagem estará em vigor.</span><span class="sxs-lookup"><span data-stu-id="06ed2-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="06ed2-112">(Consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md) na documentação de operações.)</span><span class="sxs-lookup"><span data-stu-id="06ed2-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="06ed2-113">Configure uma rota de voz que se egresso do gateway de aparelho de filial persistente ou do gateway externo do servidor de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="06ed2-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="06ed2-114">(Consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md) na documentação de operações.)</span><span class="sxs-lookup"><span data-stu-id="06ed2-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="06ed2-115">Defina uma rota de chamada de backup no aparelho de filial persistente ou gateway de servidor de filial persistente para apontar para o pool de registrador de backup (colocado com o servidor de mediação) no site central.</span><span class="sxs-lookup"><span data-stu-id="06ed2-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="06ed2-116">(Consulte seu aparelho de filial persistente ou documentação do fornecedor do servidor de filial persistente.)</span><span class="sxs-lookup"><span data-stu-id="06ed2-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="06ed2-117">Essa configuração de rota de chamada de backup ajuda a garantir que as chamadas de entrada para o usuário da filial funcionem quando o aparelho de filial persistente ou servidor de filial persistente não estiver disponível (por exemplo, se estiver desativado para manutenção).</span><span class="sxs-lookup"><span data-stu-id="06ed2-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="06ed2-118">Se o servidor de registrador e mediação no aparelho de filial persistente ou servidor de filial persistente não estiverem disponíveis e o usuário estiver registrado com o pool de registradores de backup no site central, as chamadas de entrada ainda poderão ser encaminhadas para o usuário.</span><span class="sxs-lookup"><span data-stu-id="06ed2-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="06ed2-119">**Próxima etapa**: [definir configurações de reencaminhamento de caixa postal no Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="06ed2-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

