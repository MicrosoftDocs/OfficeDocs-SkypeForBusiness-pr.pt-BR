---
title: Políticas de conferência do modo de exibição do Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Resumo: Saiba como exibir políticas de conferência no Skype para Business Server.'
ms.openlocfilehash: 161b9f172af935b105e01bda88c1c3dbef2e3a9f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992333"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="59c27-103">Políticas de conferência do modo de exibição do Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="59c27-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="59c27-104">**Resumo:** Saiba como exibir políticas de conferência no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="59c27-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="59c27-105">Você pode exibir as políticas de conferência usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="59c27-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="59c27-106">Exibir políticas de conferência usando Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="59c27-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="59c27-107">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="59c27-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="59c27-108">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="59c27-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="59c27-109">Na barra de navegação esquerda, clique em **Conferência** e, em seguida, clique em **Política de Conferência**.</span><span class="sxs-lookup"><span data-stu-id="59c27-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="59c27-110">Na página de **Política de Conferência**, dê um clique duplo na política de conferência que você deseja visualizar.</span><span class="sxs-lookup"><span data-stu-id="59c27-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="59c27-111">Em **Editar Filtro de Arquivo**, marque a caixa de seleção **Mostrar Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="59c27-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="59c27-112">**Editar a política de conferência - \<política\> ** abre exibindo as configurações para a política selecionada.</span><span class="sxs-lookup"><span data-stu-id="59c27-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="59c27-113">Para obter detalhes sobre como definir as configurações, consulte [criar políticas de conferência no Skype para Business Server](create-policies.md).</span><span class="sxs-lookup"><span data-stu-id="59c27-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="59c27-114">Exibir políticas de conferência usando Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="59c27-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="59c27-115">Para visualizar as políticas de conferência, use o cmdlet **Get-CsConferencingPolicy**:</span><span class="sxs-lookup"><span data-stu-id="59c27-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```
Get-CsConferencingPolicy
```

<span data-ttu-id="59c27-116">O cmdlet retorna informações como as seguintes:</span><span class="sxs-lookup"><span data-stu-id="59c27-116">The cmdlet returns information such as the following:</span></span>
  
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

<span data-ttu-id="59c27-117">Para obter mais informações, incluindo uma descrição de sintaxe completa e a lista de parâmetros, consulte [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="59c27-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

