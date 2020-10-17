---
title: Opcion Habilitar e desabilitar comunicados de ingresso e saída de conferência
description: Opcion Habilitar e desabilitar comunicados de ingresso e saída de conferência.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70cd6b452a44d7d40f23d5ca96b6e4b7b063d2ec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565777"
---
# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="ca372-103">Opcion Habilitar e desabilitar comunicados de ingresso e saída de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca372-103">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca372-104">_**Última modificação do tópico:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="ca372-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="ca372-105">Quando usuários de discagem ingressam ou saem de uma conferência, o aplicativo comunicado de conferência pode anunciar sua entrada ou saída tocando um tom ou dizendo seus nomes.</span><span class="sxs-lookup"><span data-stu-id="ca372-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="ca372-106">Você pode alterar o funcionamento de comunicados executando cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ca372-106">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="ca372-107">Esta etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="ca372-107">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="ca372-108">Para modificar o comportamento de anúncio de ingresso e saída de conferência</span><span class="sxs-lookup"><span data-stu-id="ca372-108">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="ca372-109">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-ServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="ca372-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="ca372-110">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ca372-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ca372-111">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="ca372-111">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="ca372-112">Este cmdlet recupera as informações sobre se os participantes precisam registrar seus nomes ao ingressar em uma conferência e como o Lync Server responde quando os participantes ingressam ou saem de uma conferência discada.</span><span class="sxs-lookup"><span data-stu-id="ca372-112">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="ca372-113">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="ca372-113">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="ca372-114">**EnableNameRecording**     Determina se os participantes anônimos serão solicitados a gravar seu nome antes de entrar na conferência.</span><span class="sxs-lookup"><span data-stu-id="ca372-114">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="ca372-115">O valor padrão é "$true", que significa que os participantes receberão essa solicitação.</span><span class="sxs-lookup"><span data-stu-id="ca372-115">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="ca372-116">(Os participantes autenticados não registram seus nomes, pois em vez disso exibem seus nomes de exibição.)</span><span class="sxs-lookup"><span data-stu-id="ca372-116">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="ca372-117">**EntryExitAnnouncementsEnabledByDefault**     Indica se os comunicados estão ativados ou desativados por padrão.</span><span class="sxs-lookup"><span data-stu-id="ca372-117">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="ca372-118">O valor padrão é "$false", que significa que, por padrão, não anúncios quando os participantes ingressam ou saem de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="ca372-118">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="ca372-119">O organizador da reunião pode substituir essa configuração ao agendar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="ca372-119">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="ca372-120">**EntryExitAnnouncementsType**     Indica a ação tomada sempre que um participante entra ou sai de uma conferência para a qual os comunicados estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="ca372-120">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="ca372-121">O valor padrão é "UseNames", que significa que há um anúncio parecido com o seguinte: "Ken Myer ingressou na conferência" quando os anúncios estão ativados.</span><span class="sxs-lookup"><span data-stu-id="ca372-121">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="ca372-p105">É possível definir essas configurações no escopo global ou no escopo do site. As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global.</span><span class="sxs-lookup"><span data-stu-id="ca372-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="ca372-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ca372-124">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="ca372-p106">Neste exemplo, as configurações estão definidas no escopo do site para Redmond. Os anúncios estão ativados, mas os participantes não recebem uma solicitação para inserir seus nomes quando ingressam em uma conferência. Um tom é reproduzido quando os participantes entram e saem de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="ca372-p106">In this example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

