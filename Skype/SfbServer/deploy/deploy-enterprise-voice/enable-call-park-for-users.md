---
title: Habilitar o estacionamento de chamada para usuários no Skype para negócios
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Habilite usuários para o estacionamento de chamada no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 44e72cab776b08cbd0290bb15010d36d370d86b3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968220"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="3146c-103">Habilitar o estacionamento de chamada para usuários no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="3146c-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="3146c-104">Habilite usuários para o estacionamento de chamada no Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3146c-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="3146c-105">Por padrão, o estacionamento de chamadas está desabilitado para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="3146c-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="3146c-106">Os usuários não podem estacionar chamadas ou recuperar chamadas estacionadas até estarem habilitados para o estacionamento de chamadas na política de voz.</span><span class="sxs-lookup"><span data-stu-id="3146c-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="3146c-107">É possível habilitar o estacionamento de chamada no escopo global ou no escopo de site ou usuário.</span><span class="sxs-lookup"><span data-stu-id="3146c-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="3146c-108">O escopo do usuário tem precedência sobre o escopo do site e o escopo do site tem precedência sobre o escopo global.</span><span class="sxs-lookup"><span data-stu-id="3146c-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="3146c-109">Se você tiver várias políticas de voz, revise todas as diretivas para habilitar o estacionamento de chamada, não apenas a política global.</span><span class="sxs-lookup"><span data-stu-id="3146c-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="3146c-110">Usar Skype para painel de controle do Business Server para habilitar o estacionamento de chamada para usuários</span><span class="sxs-lookup"><span data-stu-id="3146c-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="3146c-111">Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="3146c-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="3146c-112">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="3146c-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3146c-113">Na barra de navegação esquerdo, clique em **Roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="3146c-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="3146c-114">Clique na guia **Política de Voz**.</span><span class="sxs-lookup"><span data-stu-id="3146c-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="3146c-115">Dê um duplo clique sobre uma política de voz existente para abrir a caixa de diálogo **Editar Política de Voz**.</span><span class="sxs-lookup"><span data-stu-id="3146c-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="3146c-116">Em **Recursos de Chamadas**, selecione **Habilitar o estacionamento de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="3146c-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="3146c-117">Clique em **OK** para salvar a política de voz</span><span class="sxs-lookup"><span data-stu-id="3146c-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="3146c-118">Para usar Cmdlets para habilitar o estacionamento de chamada para usuários</span><span class="sxs-lookup"><span data-stu-id="3146c-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="3146c-119">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função administrativa CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3146c-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="3146c-120">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="3146c-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3146c-121">Execute:</span><span class="sxs-lookup"><span data-stu-id="3146c-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="3146c-122">Por exemplo, para habilitar o estacionamento de chamadas para a política de voz global padrão:</span><span class="sxs-lookup"><span data-stu-id="3146c-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="3146c-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3146c-123">See also</span></span>



[<span data-ttu-id="3146c-124">Criar ou modificar uma política de voz e configurar registros de uso PSTN no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="3146c-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

