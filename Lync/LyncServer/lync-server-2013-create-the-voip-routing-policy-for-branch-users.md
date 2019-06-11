---
title: 'Lync Server 2013: Criar a política de roteamento VoIP para usuários de filiais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f53e69069bc1f39f84c057f1e90882d5ae0d65d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a><span data-ttu-id="19e25-102">Criar a política de roteamento VoIP para usuários de filiais no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19e25-102">Create the VoIP routing policy for branch users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19e25-103">_**Tópico da última modificação:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="19e25-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="19e25-104">Recomendamos a criação de uma política de voz sobre IP (VoIP) separada para os usuários em sites de filiais.</span><span class="sxs-lookup"><span data-stu-id="19e25-104">We recommend creating a separate voice over IP (VoIP) policy for users at branch sites.</span></span> <span data-ttu-id="19e25-105">Essa política deve conter rotas para egresso do gateway de Appliance da ramificação sobreviventes ou do gateway externo do servidor de ramificação sobreviventes e rotas de backup para egresso de um gateway no site central.</span><span class="sxs-lookup"><span data-stu-id="19e25-105">This policy should contain routes to egress from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway and backup routes to egress from a gateway at the central site.</span></span> <span data-ttu-id="19e25-106">Independentemente de onde o usuário estiver registrado, seja no registrador do aplicativo de ramificação sobreviventes ou no servidor de ramificação sobreviventes ou no cluster de registrador de backup no site central, a política de VoIP do usuário estará sempre em vigor.</span><span class="sxs-lookup"><span data-stu-id="19e25-106">Regardless of where the user is registered, either on the Registrar on the Survivable Branch Appliance or Survivable Branch Server or on the backup Registrar cluster at the central site, the user’s VoIP policy is always in effect.</span></span>

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a><span data-ttu-id="19e25-107">Para configurar a política de roteamento de VoIP para usuários de filiais</span><span class="sxs-lookup"><span data-stu-id="19e25-107">To configure the VoIP routing policy for branch users</span></span>

1.  <span data-ttu-id="19e25-108">Crie um plano de discagem de nível de usuário e atribua-o a usuários da ramificação.</span><span class="sxs-lookup"><span data-stu-id="19e25-108">Create a user-level dial plan and assign it to branch users.</span></span> <span data-ttu-id="19e25-109">(Consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md) na documentação de operações.)</span><span class="sxs-lookup"><span data-stu-id="19e25-109">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

2.  <span data-ttu-id="19e25-110">Atribua regras de normalização correspondentes aos hábitos de discagem dos usuários nesse site.</span><span class="sxs-lookup"><span data-stu-id="19e25-110">Assign normalization rules corresponding to the dialing habits of users at that site.</span></span> <span data-ttu-id="19e25-111">Se o aplicativo de ramificação sobreviventes ou o usuário do servidor de ramificação sobreviventes passar no pool de registrador de backup no site central, o mesmo plano de discagem estará em vigor.</span><span class="sxs-lookup"><span data-stu-id="19e25-111">If the Survivable Branch Appliance or Survivable Branch Server user fails over to the backup Registrar pool at the central site, the same dial plan will be in effect.</span></span> <span data-ttu-id="19e25-112">(Consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md) na documentação de operações.)</span><span class="sxs-lookup"><span data-stu-id="19e25-112">(See [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in the Operations documentation.)</span></span>

3.  <span data-ttu-id="19e25-113">Configure uma rota de voz que egresso do gateway de equipamento de ramificação sobreviventes ou do gateway externo do servidor de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="19e25-113">Configure a voice route that egresses from the Survivable Branch Appliance gateway or the Survivable Branch Server external gateway.</span></span> <span data-ttu-id="19e25-114">(Consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md) na documentação de operações.)</span><span class="sxs-lookup"><span data-stu-id="19e25-114">(See [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in the Operations documentation.)</span></span>

4.  <span data-ttu-id="19e25-115">Defina uma rota de chamada de backup no aparelho de ramificação sobreviventes ou gateway de servidor de ramificação sobreviventes para apontar para o pool de registrador de backup (posicionado com o servidor de mediação) no site central.</span><span class="sxs-lookup"><span data-stu-id="19e25-115">Set a backup call route on the Survivable Branch Appliance or Survivable Branch Server gateway to point to the backup Registrar pool (collocated with Mediation Server) at the central site.</span></span> <span data-ttu-id="19e25-116">(Consulte o seu aparelho de ramificação sobreviventes ou a documentação do fornecedor do servidor de ramificação sobreviventes.)</span><span class="sxs-lookup"><span data-stu-id="19e25-116">(See your Survivable Branch Appliance or Survivable Branch Server vendor documentation.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="19e25-117">Esta configuração de rota de chamada de backup ajuda a garantir que as chamadas de entrada para o usuário da ramificação funcionarão quando o aplicativo Ramificable ou o servidor de ramificação sobreviventes não estiver disponível (por exemplo, se estiver inoperante para manutenção).</span><span class="sxs-lookup"><span data-stu-id="19e25-117">This backup call route setup helps ensure that inbound calls to the branch user will work when the Survivable Branch Appliance or Survivable Branch Server is not available (for example, if it is down for maintenance).</span></span> <span data-ttu-id="19e25-118">Se o servidor de registrador e mediação na ramificação da ramificação sobreviventes ou no servidor de ramificação sobreviventes não estiver disponível, e o usuário estiver registrado no pool de registradores de backup no site central, as chamadas recebidas ainda poderão ser encaminhadas para o usuário.</span><span class="sxs-lookup"><span data-stu-id="19e25-118">If the Registrar and Mediation Server on the Survivable Branch Appliance or Survivable Branch Server are not available, and the user is registered with the backup Registrar pool at the central site, inbound calls can still be routed to the user.</span></span>

    
    </div>

<span data-ttu-id="19e25-119">**Próxima etapa**: [Configurar o recurso configurações de redirecionamento de caixa postal no Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span><span class="sxs-lookup"><span data-stu-id="19e25-119">**Next step**: [Configure voice mail rerouting settings in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

