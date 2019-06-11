---
title: 'Lync Server 2013: Definir configurações de reroteamento de caixa postal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73aa16f7c18665c0b74c1e31e2ce888abdbe1c5a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a><span data-ttu-id="1692c-102">Definir configurações de reroteamento de caixa postal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1692c-102">Configure voice mail rerouting settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1692c-103">_**Tópico da última modificação:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="1692c-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="1692c-104">Os aparelhos de ramificação sobreviventes e os servidores de filiais sobreviventes podem fornecer impossibilitação da caixa postal para os usuários da filial durante uma interrupção da WAN, se o Exchange Unified Messaging (UM) estiver instalado no site central e um assistente de troca automática de mensagem do Exchange (AA) estiver implantado.</span><span class="sxs-lookup"><span data-stu-id="1692c-104">Survivable Branch Appliances and Survivable Branch Servers can provide voice mail survivability for branch users during a WAN outage, if Exchange Unified Messaging (UM) is installed at the central site and an Exchange UM Message Auto Attendant (AA) is deployed.</span></span> <span data-ttu-id="1692c-105">Recomendamos que o administrador do Exchange configure o AA para aceitar somente mensagens, o que desabilita outras funcionalidades genéricas, como transferência para um usuário ou transferência para um operador.</span><span class="sxs-lookup"><span data-stu-id="1692c-105">We recommend that your Exchange administrator configure the AA to accept messages only, which disables other generic functionality, such as transfer to a user or transfer to an operator.</span></span> <span data-ttu-id="1692c-106">Você também pode usar um AA genérico ou um AA personalizado para encaminhar a chamada.</span><span class="sxs-lookup"><span data-stu-id="1692c-106">Alternatively, you might use a generic AA or an AA customized to route the call.</span></span>

<span data-ttu-id="1692c-107">Para obter detalhes, consulte a seção "preparando a imsustentabilidade da caixa postal" dos [requisitos de resiliência de site para o Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="1692c-107">For details, see the “Preparing for Voice Mail Survivability” section of [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md) in the Planning documentation.</span></span>

<div>

## <a name="to-configure-voice-mail-survivability"></a><span data-ttu-id="1692c-108">Para configurar a imsustentabilidade da caixa postal</span><span class="sxs-lookup"><span data-stu-id="1692c-108">To configure voice mail survivability</span></span>

1.  <span data-ttu-id="1692c-109">Peça ao administrador do Exchange para configurar o AA para aceitar somente mensagens (no Shell do Exchange Use o seguinte cmdlet: **set- \<UMAutoAttendant AA\> nome-CallSomeoneEnabled $false**.</span><span class="sxs-lookup"><span data-stu-id="1692c-109">Ask your Exchange administrator to configure the AA to accept messages only (in the Exchange Shell use the following cmdlet: **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**.</span></span> <span data-ttu-id="1692c-110">O parâmetro que especifica a permissão para deixar mensagens (*SendVoiceMsgEnabled*) é verdadeiro por padrão.</span><span class="sxs-lookup"><span data-stu-id="1692c-110">The parameter that specifies to allow leaving messages (*SendVoiceMsgEnabled*) is true by default.</span></span>

2.  <span data-ttu-id="1692c-111">No Shell de gerenciamento do Lync Server, use o cmdlet **New-CSVoiceMailReroutingConfiguration** para definir o número de telefone AA como o número de telefone do atendedor automático do Exchange na caixa de entrada de redirecionamento de correio de voz na ramificação da ramificação sobreviventes ou Servidor de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="1692c-111">In the Lync Server Management Shell, use the **New-CSVoiceMailReroutingConfiguration** cmdlet to set the AA phone number as the Exchange UM Auto Attendant phone number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1692c-112">Se você precisar modificar a configuração de redirecionamento de caixa postal mais tarde, use o cmdlet <STRONG>set-CsVoiceMailReRoutingConfiguration</STRONG> para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="1692c-112">If you need to modify the voice mail rerouting setting later, use the <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet to do so.</span></span> <span data-ttu-id="1692c-113">Para obter detalhes, sobre <STRONG>novo-</STRONG> e <STRONG>set-CSVoiceMailReroutingConfiguration</STRONG>, nos tópicos da ajuda do Shell.</span><span class="sxs-lookup"><span data-stu-id="1692c-113">For details, about <STRONG>New-</STRONG> and <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG>, in the Shell Help topics.</span></span>

    
    </div>

3.  <span data-ttu-id="1692c-114">Defina o número de acesso do assinante do Exchange UM que corresponda ao plano de discagem de UM do usuário da filial como o número de acesso do assinante do Exchange na configuração de redirecionamento de caixa postal para o aparelho de ramificação sobreviventes ou o servidor de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="1692c-114">Set the Exchange UM subscriber access number that corresponds to the branch user’s Exchange UM dial plan as the Exchange UM subscriber access number in the voice mail rerouting configuration on the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1692c-115">Configure o plano de discagem dos usuários do Exchange UM para que haja apenas um plano de discagem associado a todos os usuários da filial que precisam acessar a funcionalidade obter caixa postal durante uma falha de WAN.</span><span class="sxs-lookup"><span data-stu-id="1692c-115">Configure the Exchange UM users’ dial plan so that there is only one dial plan associated with all branch users who need access to the Get Voice Mail functionality during a WAN outage.</span></span>

    
    </div>

<span data-ttu-id="1692c-116">**Próxima etapa** para aparelhos de ramificação sobreviventes ou servidores de filiais sobreviventes: [usuários domésticos em um aplicativo ou aplicativo de ramificação sobreviventes no Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="1692c-116">**Next step** for Survivable Branch Appliances or Survivable Branch Servers: [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

