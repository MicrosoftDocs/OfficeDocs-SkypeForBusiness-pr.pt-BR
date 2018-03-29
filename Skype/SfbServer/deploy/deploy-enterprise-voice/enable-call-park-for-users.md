---
title: Habilitar Estacionamento de Chamada para usuários no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Habilite usuários para o estacionamento de chamada no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 3af13e59541799a75c58f6e796bf07e7a978065e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-park-for-users-in-skype-for-business-2015"></a><span data-ttu-id="c1d40-103">Habilitar Estacionamento de Chamada para usuários no Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="c1d40-103">Enable Call Park for users in Skype for Business 2015</span></span>
 
<span data-ttu-id="c1d40-104">Habilite usuários para o estacionamento de chamada no Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c1d40-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="c1d40-105">Por padrão, o estacionamento de chamadas está desabilitado para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="c1d40-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="c1d40-106">Os usuários não podem estacionar chamadas ou recuperar chamadas estacionadas até estarem habilitados para o estacionamento de chamadas na política de voz.</span><span class="sxs-lookup"><span data-stu-id="c1d40-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="c1d40-107">É possível habilitar o estacionamento de chamada no escopo global ou no escopo de site ou usuário.</span><span class="sxs-lookup"><span data-stu-id="c1d40-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="c1d40-108">O escopo do usuário tem precedência sobre o escopo do site e o escopo do site tem precedência sobre o escopo global.</span><span class="sxs-lookup"><span data-stu-id="c1d40-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="c1d40-109">Se você tiver várias políticas de voz, revise todas as diretivas para habilitar o estacionamento de chamada, não apenas a política global.</span><span class="sxs-lookup"><span data-stu-id="c1d40-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="c1d40-110">Usar Skype para painel de controle do Business Server para habilitar o estacionamento de chamada para usuários</span><span class="sxs-lookup"><span data-stu-id="c1d40-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="c1d40-111">Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="c1d40-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="c1d40-112">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="c1d40-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c1d40-113">Na barra de navegação esquerdo, clique em **Roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="c1d40-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="c1d40-114">Clique na guia **Política de Voz**.</span><span class="sxs-lookup"><span data-stu-id="c1d40-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="c1d40-115">Dê um duplo clique sobre uma política de voz existente para abrir a caixa de diálogo **Editar Política de Voz**.</span><span class="sxs-lookup"><span data-stu-id="c1d40-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="c1d40-116">Em **Recursos de Chamadas**, selecione **Habilitar o estacionamento de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="c1d40-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="c1d40-117">Clique em **OK** para salvar a política de voz</span><span class="sxs-lookup"><span data-stu-id="c1d40-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="c1d40-118">Para usar Cmdlets para habilitar o estacionamento de chamada para usuários</span><span class="sxs-lookup"><span data-stu-id="c1d40-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="c1d40-119">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função administrativa CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c1d40-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="c1d40-120">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c1d40-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c1d40-121">Execute:</span><span class="sxs-lookup"><span data-stu-id="c1d40-121">Run:</span></span>
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="c1d40-122">Por exemplo, para habilitar o estacionamento de chamadas para a política de voz global padrão:</span><span class="sxs-lookup"><span data-stu-id="c1d40-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="c1d40-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c1d40-123">See also</span></span>

#### 

[<span data-ttu-id="c1d40-124">Criar ou modificar uma política de voz e configurar registros de uso PSTN no Skype para negócios 2015</span><span class="sxs-lookup"><span data-stu-id="c1d40-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)

