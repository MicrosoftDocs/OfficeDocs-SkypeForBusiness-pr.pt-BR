---
title: Gerenciar comunicados de saída e ingressar em conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Resumo: Saiba como gerenciar anúncios de ingressar e deixar conferências no Skype for Business Server.'
ms.openlocfilehash: 9ca73d3d32ce03a8119d805b5e7260c0a871eb27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828101"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="c89f8-103">Gerenciar comunicados de saída e ingressar em conferência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c89f8-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="c89f8-104">**Resumo:** Saiba como gerenciar comunicados de saída e ingressar em conferência no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c89f8-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="c89f8-105">Quando os usuários discados in unem ou saem de uma conferência, o aplicativo Comunicado de Conferência pode anunciar sua entrada ou saída, tocando um tom ou dizendo seus nomes.</span><span class="sxs-lookup"><span data-stu-id="c89f8-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="c89f8-106">Você pode alterar como os anúncios funcionam usando o Shell de Gerenciamento do Skype for Business Server e o cmdlet **Set-CsDialinConferencing** com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="c89f8-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="c89f8-107">EnableNameRecording - Determina se os participantes anônimos são solicitados a registrar seu nome antes de entrar na conferência.</span><span class="sxs-lookup"><span data-stu-id="c89f8-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="c89f8-108">O valor padrão é "$true", que significa que os participantes receberão essa solicitação.</span><span class="sxs-lookup"><span data-stu-id="c89f8-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="c89f8-109">(Os participantes autenticados não registram seus nomes, pois em vez disso exibem seus nomes de exibição.)</span><span class="sxs-lookup"><span data-stu-id="c89f8-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="c89f8-110">EntryExitAnnouncementsEnabledByDefault - Indica se os anúncios estão ligado ou desligados por padrão.</span><span class="sxs-lookup"><span data-stu-id="c89f8-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="c89f8-111">O valor padrão é "$false", que significa que, por padrão, não anúncios quando os participantes ingressam ou saem de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="c89f8-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="c89f8-112">O organizador da reunião pode substituir essa configuração ao agendar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="c89f8-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="c89f8-113">EntryExitAnnouncementsType - Indica a ação tomada sempre que um participante participa ou sai de uma conferência para a qual os anúncios estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="c89f8-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="c89f8-114">O valor padrão é "UseNames", que significa que há um anúncio parecido com o seguinte: "Ken Myer ingressou na conferência" quando os anúncios estão ativados.</span><span class="sxs-lookup"><span data-stu-id="c89f8-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="c89f8-p105">É possível definir essas configurações no escopo global ou no escopo do site. As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global.</span><span class="sxs-lookup"><span data-stu-id="c89f8-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="c89f8-117">Para modificar o comportamento de anúncio de ingresso e saída de conferência</span><span class="sxs-lookup"><span data-stu-id="c89f8-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="c89f8-118">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função Cs-ServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c89f8-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="c89f8-119">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="c89f8-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c89f8-120">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="c89f8-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="c89f8-121">Este cmdlet recupera informações sobre se os participantes precisam registrar seus nomes ao ingressar em uma conferência e como o Skype for Business Server responde quando os participantes in unem ou saem de uma conferência discada.</span><span class="sxs-lookup"><span data-stu-id="c89f8-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="c89f8-122">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="c89f8-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="c89f8-123">No exemplo a seguir, as configurações são configuradas no escopo do site para Redmond.</span><span class="sxs-lookup"><span data-stu-id="c89f8-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="c89f8-124">Os anúncios estão ativados, mas os participantes não recebem uma solicitação para inserir seus nomes quando ingressam em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="c89f8-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="c89f8-125">Um tom é tocado quando os participantes entram ou saem de uma conferência:</span><span class="sxs-lookup"><span data-stu-id="c89f8-125">A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="c89f8-126">Para obter mais informações, incluindo sintaxe e uma lista completa de parâmetros, consulte [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c89f8-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

