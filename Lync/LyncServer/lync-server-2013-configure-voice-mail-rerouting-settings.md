---
title: 'Lync Server 2013: definir configurações de reencaminhamento de caixa postal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa98050e026c90438b1df0811daa4b5235c9732
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a><span data-ttu-id="21bb6-102">Definir configurações de reencaminhamento de caixa postal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21bb6-102">Configure voice mail rerouting settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21bb6-103">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="21bb6-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="21bb6-104">Os aparelhos de filial persistente e servidores de filial persistente podem fornecer sustentabilidade da caixa postal para usuários de filial durante uma interrupção da WAN, se o Unificação de mensagens (UM) do Exchange estiver instalado no site central e um atendedor automático de mensagem de UM do Exchange estiver implantado.</span><span class="sxs-lookup"><span data-stu-id="21bb6-104">Survivable Branch Appliances and Survivable Branch Servers can provide voice mail survivability for branch users during a WAN outage, if Exchange Unified Messaging (UM) is installed at the central site and an Exchange UM Message Auto Attendant (AA) is deployed.</span></span> <span data-ttu-id="21bb6-105">Recomendamos que o seu administrador do Exchange configure o AA para aceitar somente mensagens, o que desabilitará outra funcionalidade genérica, como a transferência para um usuário ou a transferência para uma telefonista.</span><span class="sxs-lookup"><span data-stu-id="21bb6-105">We recommend that your Exchange administrator configure the AA to accept messages only, which disables other generic functionality, such as transfer to a user or transfer to an operator.</span></span> <span data-ttu-id="21bb6-106">Como alternativa, você poderia usar um AA genérico ou um AA personalizado para rotear a chamada.</span><span class="sxs-lookup"><span data-stu-id="21bb6-106">Alternatively, you might use a generic AA or an AA customized to route the call.</span></span>

<span data-ttu-id="21bb6-107">Para obter detalhes, consulte a seção "preparando para a persistência de caixa postal" de [requisitos de resiliência de site de filial para o Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="21bb6-107">For details, see the “Preparing for Voice Mail Survivability” section of [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="to-configure-voice-mail-survivability"></a><span data-ttu-id="21bb6-108">Para configurar a sustentabilidade da caixa postal</span><span class="sxs-lookup"><span data-stu-id="21bb6-108">To configure voice mail survivability</span></span>

1.  <span data-ttu-id="21bb6-109">Peça ao administrador do Exchange para configurar o AA para aceitar apenas mensagens (no Shell do Exchange Use o seguinte cmdlet: **set- \<UMAutoAttendant AA\> Name-CallSomeoneEnabled $false**.</span><span class="sxs-lookup"><span data-stu-id="21bb6-109">Ask your Exchange administrator to configure the AA to accept messages only (in the Exchange Shell use the following cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span></span> <span data-ttu-id="21bb6-110">O parâmetro que especifica que se permita deixar mensagens ( *SendVoiceMsgEnabled*) é verdadeiro por padrão.</span><span class="sxs-lookup"><span data-stu-id="21bb6-110">The parameter that specifies to allow leaving messages (*SendVoiceMsgEnabled*) is true by default.</span></span>

2.  <span data-ttu-id="21bb6-111">No Shell de gerenciamento do Lync Server, use o cmdlet **New-CSVoiceMailReroutingConfiguration** para definir o número de telefone AA como o número de telefone do atendedor automático da um do Exchange na configuração de reencaminhamento de caixa postal no aparelho de filial persistente ou servidor de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="21bb6-111">In the Lync Server Management Shell, use the **New-CSVoiceMailReroutingConfiguration** cmdlet to set the AA phone number as the Exchange UM Auto Attendant phone number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21bb6-112">Se você precisar modificar a configuração do roteamento da caixa postal posteriormente, use o cmdlet <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="21bb6-112">If you need to modify the voice mail rerouting setting later, use the <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet to do so.</span></span> <span data-ttu-id="21bb6-113">Para obter detalhes, sobre <STRONG>New-</STRONG> e <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, nos tópicos da Ajuda do Shell.</span><span class="sxs-lookup"><span data-stu-id="21bb6-113">For details, about <STRONG>New-</STRONG> and <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, in the Shell Help topics.</span></span>

    
    </div>

3.  <span data-ttu-id="21bb6-114">Defina o número de acesso do assinante da UM do Exchange que corresponde ao plano de discagem de UM do usuário da filial como o número de acesso do assinante do UM do Exchange na configuração de reencaminhamento de caixa postal no aparelho de filial persistente ou servidor de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="21bb6-114">Set the Exchange UM subscriber access number that corresponds to the branch user’s Exchange UM dial plan as the Exchange UM subscriber access number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21bb6-115">Configure o plano de discagem dos usuários de UM do Exchange para que haja apenas um plano de discagem associado a todos os usuários da filial que precisam acessar a funcionalidade obter caixa postal durante uma interrupção da WAN.</span><span class="sxs-lookup"><span data-stu-id="21bb6-115">Configure the Exchange UM users’ dial plan so that there is only one dial plan associated with all branch users who need access to the Get Voice Mail functionality during a WAN outage.</span></span>

    
    </div>

<span data-ttu-id="21bb6-116">**Próxima etapa** para aparelhos de filial persistente ou servidores de filial persistente: [usuários domésticos em um aparelho de filial persistente ou servidor no Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="21bb6-116">**Next step** for Survivable Branch Appliances or Survivable Branch Servers: [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

