---
title: Habilitar o estacionamento de chamadas para usuários no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Habilite os usuários para o parque de chamadas no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 797b17cb3d9482d9059bedcbbc347c3dd592e478
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240372"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="3a6b1-103">Habilitar o estacionamento de chamadas para usuários no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3a6b1-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="3a6b1-104">Habilite os usuários para o parque de chamadas no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3a6b1-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="3a6b1-105">Por padrão, o estacionamento de chamadas está desabilitado para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="3a6b1-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="3a6b1-106">Os usuários não podem estacionar chamadas nem recuperar chamadas estacionadas até que elas sejam habilitadas para estacionamento de chamadas na política de voz.</span><span class="sxs-lookup"><span data-stu-id="3a6b1-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="3a6b1-107">Você pode habilitar o estacionamento de chamadas no escopo global ou no escopo do site ou no escopo do usuário.</span><span class="sxs-lookup"><span data-stu-id="3a6b1-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="3a6b1-108">O escopo do usuário tem precedência sobre o escopo do site e o escopo do site tem precedência sobre o escopo global.</span><span class="sxs-lookup"><span data-stu-id="3a6b1-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="3a6b1-109">Se você tiver várias políticas de voz, examine todas as políticas para habilitar o estacionamento de chamadas, não apenas a política global.</span><span class="sxs-lookup"><span data-stu-id="3a6b1-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="3a6b1-110">Para usar o painel de controle do Skype for Business Server para habilitar o estacionamento de chamadas para usuários</span><span class="sxs-lookup"><span data-stu-id="3a6b1-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="3a6b1-111">Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="3a6b1-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="3a6b1-112">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a6b1-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="3a6b1-113">Na barra de navegação esquerdo, clique em **Roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="3a6b1-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="3a6b1-114">Clique na guia **Política de Voz**.</span><span class="sxs-lookup"><span data-stu-id="3a6b1-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="3a6b1-115">Dê um duplo clique sobre uma política de voz existente para abrir a caixa de diálogo **Editar Política de Voz**.</span><span class="sxs-lookup"><span data-stu-id="3a6b1-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="3a6b1-116">Em **Recursos de Chamadas**, selecione **Habilitar o estacionamento de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="3a6b1-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="3a6b1-117">Clique em **OK** para salvar a política de voz</span><span class="sxs-lookup"><span data-stu-id="3a6b1-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="3a6b1-118">Para usar cmdlets para habilitar o estacionamento de chamadas para usuários</span><span class="sxs-lookup"><span data-stu-id="3a6b1-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="3a6b1-119">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função administrativa CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3a6b1-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="3a6b1-120">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="3a6b1-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3a6b1-121">Execute:</span><span class="sxs-lookup"><span data-stu-id="3a6b1-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="3a6b1-122">Por exemplo, para habilitar o estacionamento de chamadas para a política de voz global padrão:</span><span class="sxs-lookup"><span data-stu-id="3a6b1-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="3a6b1-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="3a6b1-123">See also</span></span>



[<span data-ttu-id="3a6b1-124">Criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3a6b1-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

