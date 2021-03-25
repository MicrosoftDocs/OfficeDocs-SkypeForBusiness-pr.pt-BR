---
title: Exibir políticas de conferência no Skype for Business Server
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
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Resumo: Saiba como exibir políticas de conferência no Skype for Business Server.'
ms.openlocfilehash: afe86f0a77e73c3fa7bf96339c4865598a7bc609
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119400"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="f9426-103">Exibir políticas de conferência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f9426-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="f9426-104">**Resumo:** Saiba como exibir políticas de conferência no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f9426-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="f9426-105">Você pode exibir políticas de conferência usando o Painel de Controle do Skype for Business Server ou usando o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f9426-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f9426-106">Exibir políticas de conferência usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f9426-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f9426-107">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f9426-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="f9426-108">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f9426-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f9426-109">Na barra de navegação esquerda, clique **em Conferência** e em Política **de Conferência.**</span><span class="sxs-lookup"><span data-stu-id="f9426-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="f9426-110">Na página de **Política de Conferência**, dê um clique duplo na política de conferência que você deseja visualizar.</span><span class="sxs-lookup"><span data-stu-id="f9426-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="f9426-111">Em **Editar Filtro de Arquivo,** marque a caixa de seleção Mostrar **Detalhes.**</span><span class="sxs-lookup"><span data-stu-id="f9426-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="f9426-112">**Editar Política de \<policy\> Conferência -** abre exibindo as configurações da política selecionada.</span><span class="sxs-lookup"><span data-stu-id="f9426-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="f9426-113">Para obter detalhes sobre como configurar as configurações, consulte [Create conferencing policies in Skype for Business Server](create-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f9426-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f9426-114">Exibir políticas de conferência usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f9426-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f9426-115">Para exibir políticas de conferência, use o cmdlet **Get-CsConferencingPolicy:**</span><span class="sxs-lookup"><span data-stu-id="f9426-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```PowerShell
Get-CsConferencingPolicy
```

<span data-ttu-id="f9426-116">O cmdlet retorna informações como:</span><span class="sxs-lookup"><span data-stu-id="f9426-116">The cmdlet returns information such as the following:</span></span>
  
<pre>
Identity                                  : Global
AllowIPAudio                              : True
AllowIPVideo                              : True
AllowMultiView                            : True
Description                               :
AllowParticipantControl                   : True
AllowAnnotations                          : True
DisablePowerPointAnnotations              : False
AllowUserToScheduleMeetingsWithAppSharing : True
AllowNonEnterpriseVoiceUsersToDialOut     : False
AllowAnonymousUsersToDialOut              : False
AllowAnonymousParticipantsInMeetings      : True
AllowExternalUsersToSaveContent           : True
AllowExternalUserControl                  : False
AllowExternalUsersToRecordMeeting         : False
AllowPolls                                : True
AllowSharedNotes                          : True
EnableDialInConferencing                  : True
EnableAppDesktopSharing                   : Desktop
AllowConferenceRecording                  : False
EnableP2PRecording                        : False
EnableFileTransfer                        : True
EnableP2PFileTransfer                     : True
EnableP2PVideo                            : True
AllowLargeMeetings                        : False
EnableDataCollaboration                   : True
MaxVideoConferenceResolution              : VGA
MaxMeetingSize                            : 250
AudioBitRateKb                            : 200
VideoBitRateKb                            : 50000
AppSharingBitRateKb                       : 50000
FileTransferBitRateKb                     : 50000
TotalReceiveVideoBitRateKb                : 6000
EnableMultiViewJoin                       : True
</pre>

<span data-ttu-id="f9426-117">Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f9426-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
