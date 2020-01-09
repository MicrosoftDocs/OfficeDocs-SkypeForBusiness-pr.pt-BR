---
title: Gerenciar o ingresso em conferência e deixar comunicados no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Resumo: saiba como gerenciar o ingresso em conferência e deixar comunicados no Skype for Business Server.'
ms.openlocfilehash: 5c2bc7175f99ee50e94bee26ef0e6d54a6a8db5a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991826"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="613de-103">Gerenciar o ingresso em conferência e deixar comunicados no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="613de-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="613de-104">**Resumo:** Saiba como gerenciar o ingresso em conferência e deixar comunicados no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="613de-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="613de-105">Quando os usuários de discagem entram ou deixam uma conferência, o aplicativo de anúncio de conferência pode anunciar a entrada ou a saída tocando um tom ou dizendo seus nomes.</span><span class="sxs-lookup"><span data-stu-id="613de-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="613de-106">Você pode alterar a forma como os comunicados funcionam usando o Shell de gerenciamento do Skype for Business Server e o cmdlet **set-CsDialinConferencing** com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="613de-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="613de-p102">EnableNameRecording  - Determina se os participantes anônimos devem receber uma solicitação para registrar seus nomes antes de entrar na conferência. O valor padrão é "$true", que significa que os participantes receberão essa solicitação. (Os participantes autenticados não registram seus nomes porque seu nome de exibição é utilizado.)</span><span class="sxs-lookup"><span data-stu-id="613de-p102">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference. The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference. (Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="613de-p103">EntryExitAnnouncementsEnabledByDefault - Indica se os anúncios estão ativados ou desativados por padrão. O valor padrão é "$false", o que significa que, por padrão, não há anúncios quando os participantes participam ou saem de uma conferência. O organizador da reunião pode substituir essa configuração ao agendar uma reunião.</span><span class="sxs-lookup"><span data-stu-id="613de-p103">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default. The default value is "$false," which means that by default there are no announcements when participants join or leave a conference. The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="613de-p104">EntryExitAnnouncementsType - Indica a ação a ser executada sempre que um participante participa ou sai de uma conferência para a qual os anúncios estão habilitados. O valor padrão é "UseNames", que significa que há um anúncio parecido com o seguinte: "Ken Myer está participando da conferência" quando os anúncios são ativados.</span><span class="sxs-lookup"><span data-stu-id="613de-p104">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled. The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="613de-p105">É possível definir essas configurações no escopo global ou no escopo do site. As configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global.</span><span class="sxs-lookup"><span data-stu-id="613de-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="613de-117">Para modificar o comportamento de anúncio de ingresso e saída de conferência</span><span class="sxs-lookup"><span data-stu-id="613de-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="613de-118">Faça logon no computador como membro do grupo  RTCUniversalServerAdmins  ou como membro da função  Cs-ServerAdministrator  ou  CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="613de-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="613de-119">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="613de-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="613de-120">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="613de-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="613de-121">Esse cmdlet recupera informações sobre a necessidade de os participantes gravarem o nome ao ingressar em uma conferência e como o Skype for Business Server responde quando os participantes se unem ou deixam uma conferência discada.</span><span class="sxs-lookup"><span data-stu-id="613de-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="613de-122">Execute o seguinte no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="613de-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="613de-p106">Neste exemplo, as configurações estão definidas no escopo do site para Redmond. Os anúncios estão ativados, mas os participantes não recebem uma solicitação para inserir seus nomes quando ingressam em uma conferência. Um tom é reproduzido quando os participantes entram e saem de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="613de-p106">In the following example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="613de-126">Para obter mais informações, incluindo a sintaxe e uma lista completa de parâmetros, consulte [set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="613de-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

