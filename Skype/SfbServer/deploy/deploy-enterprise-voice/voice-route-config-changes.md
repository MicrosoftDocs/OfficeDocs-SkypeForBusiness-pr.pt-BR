---
title: Publicar alterações pendentes na configuração de roteamento de voz no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Resumo: saiba como revisar, publicar ou cancelar alterações de configuração de roteamento de voz no Skype for Business Server usando o painel de controle do Skype for Business Server.'
ms.openlocfilehash: 1ff33dee1518581e4a94aac56ecae34d9bfd1159
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300884"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a><span data-ttu-id="fa3fa-103">Publicar alterações pendentes na configuração de roteamento de voz no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fa3fa-103">Publish pending changes to the voice routing configuration in Skype for Business</span></span>
 
<span data-ttu-id="fa3fa-104">**Resumo:** Saiba como revisar, publicar ou cancelar alterações de configuração de roteamento de voz no Skype for Business Server usando o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-104">**Summary:** Learn how to review, publish, or cancel voice routing configuration changes in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="fa3fa-105">Após fazer alterações em qualquer uma das definições de configuração nas páginas do grupo **Roteamento de Voz**, execute este procedimento para examinar, publicar ou cancelar as alterações pendentes.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-105">After you make changes to any of the configuration settings in pages in the **Voice Routing** group, perform this procedure to review, publish, or cancel the pending changes.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fa3fa-106">Certifique-se de que somente um usuário por vez modifique as definições de configurações do Roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-106">Be sure that only one user at a time modifies the Voice Routing configuration settings.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fa3fa-p101">Todas as alterações pendentes devem ser publicadas ao mesmo tempo, executando o comando **Confirmar todos**. Não é possível publicar seletivamente as alterações pendentes. Antes de publicar as alterações pendentes, execute o comando **Revisar alterações não confirmadas** e cancele qualquer alteração de configuração que não deseja publicar.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-p101">All pending changes must be published at the same time by running the **Commit all** command. You cannot selectively publish pending changes. Before you publish pending changes, run the **Review uncommitted changes** command and cancel any configuration changes that you do not want to publish.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fa3fa-110">Se você navegar longe das páginas do grupo **Roteamento de voz** antes de confirmar as alterações pendentes, todas as alterações pendentes serão perdida.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-110">If you navigate away from the pages in the **Voice Routing** group before committing pending changes, all pending changes will be lost.</span></span> <span data-ttu-id="fa3fa-111">No entanto, é possível exportar a configuração atual (incluindo quaisquer alterações pendentes) para um arquivo de configuração de voz e, em seguida, importar e publicar a configuração atualizada.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-111">However, you can export the current configuration (including any pending changes) to a voice configuration file, and then import and publish the updated configuration.</span></span> <span data-ttu-id="fa3fa-112">Para obter detalhes, consulte [exportar ou importar um arquivo de configuração de rota de voz no Skype for Business](voice-route-configuration-import-export.md).</span><span class="sxs-lookup"><span data-stu-id="fa3fa-112">For details, see [Export or import a voice route configuration file in Skype for Business](voice-route-configuration-import-export.md).</span></span> 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a><span data-ttu-id="fa3fa-113">Para revisar, publicar ou cancelar as alterações de configuração do roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="fa3fa-113">To review, publish, or cancel voice routing configuration changes</span></span>

1. <span data-ttu-id="fa3fa-114">Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="fa3fa-115">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-115">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fa3fa-116">Na barra de navegação esquerda, clique em **Roteamento de Voz**.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-116">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="fa3fa-117">Faça as alterações de configuração que deseja para as configurações em cada página do grupo **Roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-117">Make the configuration changes you want to the settings on each page of the **Voice Routing** group.</span></span>
    
5. <span data-ttu-id="fa3fa-118">Para revisar as alterações pendentes sem publicá-las, selecione **Revisar alterações não confirmadas** no menu **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-118">To review pending changes without publishing them, select **Review uncommitted changes** from the **Commit** menu.</span></span>
    
6. <span data-ttu-id="fa3fa-119">Se você deseja cancelar qualquer alteração pendente, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="fa3fa-119">If you want to cancel any of the pending changes, do one of the following:</span></span>
    
   - <span data-ttu-id="fa3fa-120">Selecione **Cancelar todas as alterações não confirmadas** no menu **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-120">Select **Cancel all uncommitted changes** from the **Commit** menu.</span></span>
    
   - <span data-ttu-id="fa3fa-121">Navegue até a guia da página **Roteamento de voz** que possui as alterações pendente que deseja cancelar, selecione o item com as alterações pendentes, clique em **Confirmar** e em **Cancelar alterações selecionadas**.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-121">Navigate to the tab of the **Voice Routing** page that has pending changes you want to cancel, select the item with the pending changes, click **Commit**, and then click **Cancel selected changes**.</span></span>
    
7. <span data-ttu-id="fa3fa-122">Após revisar todas as alterações pendentes e cancelar qualquer uma que não deseja publicar, clique em **Confirmar** e em **Confirmar todas**.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-122">After you have reviewed all pending changes and canceled any that you do not want to publish, click **Commit**, and then click **Commit all**.</span></span>
    
8. <span data-ttu-id="fa3fa-123">Na caixa de diálogo **Definições da configuração de voz não confirmadas** que exibe uma lista de todas as alterações pendentes, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa3fa-123">In the **Uncommitted Voice Configuration Settings** dialog box, which displays a list of all of the pending changes, click **OK**.</span></span> 
    
    <span data-ttu-id="fa3fa-124">Quando o painel de controle do Skype for Business Server tiver confirmado as alterações, será exibida a mensagem de **configuração de roteamento de voz publicada com êxito** .</span><span class="sxs-lookup"><span data-stu-id="fa3fa-124">When Skype for Business Server Control Panel has committed the changes, the **Successfully published voice routing configuration** message appears.</span></span>
    

