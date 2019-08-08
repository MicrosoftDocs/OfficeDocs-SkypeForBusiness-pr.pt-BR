---
title: Exportar ou importar um arquivo de configuração de rota de voz no Skype for Business
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Resumo: saiba como exportar ou importar um arquivo de configuração de roteamento de voz no Skype for Business Server usando o painel de controle do Skype for Business Server.'
ms.openlocfilehash: ec5a3d0c7f14d85a7b64eaad1edc73ebe4e24cd2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239912"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="0b253-103">Exportar ou importar um arquivo de configuração de rota de voz no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0b253-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="0b253-104">**Resumo:** Saiba como exportar ou importar um arquivo de configuração de roteamento de voz no Skype for Business Server usando o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0b253-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="0b253-105">Se quiser salvar sua configuração de roteamento de voz sem publicá-la, siga estas etapas para salvar e recuperar um instantâneo da sua configuração de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="0b253-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="0b253-106">Quando você importa um arquivo de configuração de roteamento de voz (. vcfg), mas foram feitas alterações na configuração de roteamento de voz no servidor enquanto isso, as páginas no grupo de **Roteamento de voz** no painel de controle do Skype for Business Server indicam que, são alterações não confirmadas no roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="0b253-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="0b253-107">Essas alterações não confirmadas são as diferenças entre as duas configurações que exigem reconciliação.</span><span class="sxs-lookup"><span data-stu-id="0b253-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="0b253-108">Se você tiver feito alterações não confirmadas nas configurações de qualquer página do grupo, as alterações serão salvas no arquivo de configuração de voz exportado (. vcfg).</span><span class="sxs-lookup"><span data-stu-id="0b253-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="0b253-109">Isso permite que você faça alterações de configuração de roteamento de voz durante várias sessões antes de publicar as alterações.</span><span class="sxs-lookup"><span data-stu-id="0b253-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="0b253-110">Para exportar uma configuração de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="0b253-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="0b253-111">Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0b253-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="0b253-112">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0b253-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0b253-113">Na barra de navegação esquerdo, clique em **Roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="0b253-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="0b253-114">No menu **Ações**, clique em **Exportar configuração**.</span><span class="sxs-lookup"><span data-stu-id="0b253-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="0b253-115">Especifique um local e nome de arquivo e então clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0b253-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="0b253-116">Para importar uma configuração de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="0b253-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="0b253-117">Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0b253-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="0b253-118">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0b253-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0b253-119">Na barra de navegação esquerda, clique em **Roteamento de Voz**.</span><span class="sxs-lookup"><span data-stu-id="0b253-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="0b253-120">No menu **Ações**, clique em **Importar Configuração**.</span><span class="sxs-lookup"><span data-stu-id="0b253-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="0b253-121">Localize o arquivo de configuração que você deseja importar e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="0b253-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="0b253-122">Clique em **Confirmar** e, em seguida, clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="0b253-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0b253-123">Sempre que importar um arquivo de configuração de voz, você deve executar o comando **Confirmar tudo** para publicar a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="0b253-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="0b253-124">Para obter detalhes, consulte [publicar alterações pendentes na configuração de roteamento de voz no Skype for Business](voice-route-config-changes.md) na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="0b253-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

