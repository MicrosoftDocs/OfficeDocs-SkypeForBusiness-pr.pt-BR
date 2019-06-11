---
title: (Opcional) Habilitar e desabilitar comunicados de ingresso e saída de conferência
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 778969dfa5ed6b84fdbcd2b204e497f8d649f1a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="1c2ea-102">(Opcional) Habilitar e desabilitar comunicados de ingresso e saída de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c2ea-102">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c2ea-103">_**Tópico da última modificação:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="1c2ea-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="1c2ea-104">Quando os usuários de discagem entram ou deixam uma conferência, o aplicativo de anúncio de conferência pode anunciar a entrada ou a saída tocando um tom ou dizendo seus nomes.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-104">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="1c2ea-105">Você pode alterar como os comunicados funcionam Executando cmdlets.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-105">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="1c2ea-106">Esta etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-106">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="1c2ea-107">Para modificar o comportamento de anúncio de ingresso e saída de conferência</span><span class="sxs-lookup"><span data-stu-id="1c2ea-107">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="1c2ea-108">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **cs-ServerAdministrator** ou **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="1c2ea-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="1c2ea-109">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1c2ea-110">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="1c2ea-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="1c2ea-111">Esse cmdlet recupera informações sobre a necessidade de os participantes gravarem o nome ao ingressar em uma conferência e como o Lync Server responde quando os participantes ingressam ou deixam uma conferência discada.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-111">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="1c2ea-112">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="1c2ea-112">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="1c2ea-113">**O EnableNameRecording**   determina se os participantes anônimos devem gravar o nome antes de entrar na conferência.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-113">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="1c2ea-114">O valor padrão é "$true", que significa que os participantes receberão essa solicitação.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-114">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="1c2ea-115">(Os participantes autenticados não registram seus nomes porque seu nome de exibição é utilizado.)</span><span class="sxs-lookup"><span data-stu-id="1c2ea-115">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="1c2ea-116">**EntryExitAnnouncementsEnabledByDefault**   indica se os comunicados estão ativados ou desativados por padrão.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-116">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="1c2ea-117">O valor padrão é "$false", o que significa que, por padrão, não há anúncios quando os participantes participam ou saem de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-117">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="1c2ea-118">O organizador da reunião pode substituir essa configuração ao agendar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-118">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="1c2ea-119">**EntryExitAnnouncementsType**   indica a ação tomada sempre que um participante entra ou sai de uma conferência para a qual os comunicados são habilitados.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-119">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="1c2ea-120">O valor padrão é "UseNames", que significa que há um anúncio parecido com o seguinte: "Ken Myer está participando da conferência" quando os anúncios são ativados.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-120">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="1c2ea-p105">É possível definir essas configurações no escopo global ou no escopo do site. As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="1c2ea-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1c2ea-123">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="1c2ea-124">Neste exemplo, as configurações são configuradas no escopo do site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-124">In this example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="1c2ea-125">Os anúncios estão ativados, mas os participantes não recebem uma solicitação para inserir seus nomes quando ingressam em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-125">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="1c2ea-126">Um tom é tocado quando os participantes entram ou deixam uma conferência.</span><span class="sxs-lookup"><span data-stu-id="1c2ea-126">A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

