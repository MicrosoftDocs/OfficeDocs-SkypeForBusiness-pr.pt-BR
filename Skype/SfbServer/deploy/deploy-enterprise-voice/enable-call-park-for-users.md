---
title: Habilitar Estacionamento de Chamada para usuários no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Habilitar usuários para Estacionamento de Chamada no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: e9bbc42f5940af0cfc94ab83eae981dd023c9fcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830951"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="82e2e-103">Habilitar Estacionamento de Chamada para usuários no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="82e2e-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="82e2e-104">Habilitar usuários para Estacionamento de Chamada no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="82e2e-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="82e2e-105">Por padrão, o Estacionamento de Chamada está desabilitado para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="82e2e-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="82e2e-106">Os usuários não podem estacionar chamadas ou recuperar chamadas estacionadas até que sejam habilitadas para Estacionamento de Chamada na política de voz.</span><span class="sxs-lookup"><span data-stu-id="82e2e-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="82e2e-107">Você pode habilitar o Estacionamento de Chamada no escopo global ou no escopo do site ou do usuário.</span><span class="sxs-lookup"><span data-stu-id="82e2e-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="82e2e-108">O escopo do usuário tem precedência sobre o escopo do site e o escopo do site tem precedência sobre o escopo global.</span><span class="sxs-lookup"><span data-stu-id="82e2e-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="82e2e-109">Se você tiver várias políticas de voz, revise todas as políticas para habilitar o Estacionamento de Chamadas, não apenas a política global.</span><span class="sxs-lookup"><span data-stu-id="82e2e-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="82e2e-110">Para usar o Painel de Controle do Skype for Business Server para habilitar o Estacionamento de Chamadas para Usuários</span><span class="sxs-lookup"><span data-stu-id="82e2e-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="82e2e-111">Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="82e2e-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="82e2e-112">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="82e2e-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="82e2e-113">Na barra de navegação à esquerda, clique em **Roteamento de Voz**.</span><span class="sxs-lookup"><span data-stu-id="82e2e-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="82e2e-114">Clique na guia **Política de Voz**.</span><span class="sxs-lookup"><span data-stu-id="82e2e-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="82e2e-115">Dê um duplo clique sobre uma política de voz existente para abrir a caixa de diálogo **Editar Política de Voz**.</span><span class="sxs-lookup"><span data-stu-id="82e2e-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="82e2e-116">Sob **Recursos de Chamadas**, selecione **Habilitar o estacionamento de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="82e2e-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="82e2e-117">Clique em **OK** para salvar a política de voz</span><span class="sxs-lookup"><span data-stu-id="82e2e-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="82e2e-118">Para usar cmdlets para habilitar o estacionamento de chamada para usuários</span><span class="sxs-lookup"><span data-stu-id="82e2e-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="82e2e-119">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função administrativa CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="82e2e-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="82e2e-120">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="82e2e-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="82e2e-121">Execute:</span><span class="sxs-lookup"><span data-stu-id="82e2e-121">Run:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="82e2e-122">Por exemplo, para habilitar o Estacionamento de Chamada para a política de voz global padrão:</span><span class="sxs-lookup"><span data-stu-id="82e2e-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="82e2e-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="82e2e-123">See also</span></span>



[<span data-ttu-id="82e2e-124">Criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="82e2e-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

