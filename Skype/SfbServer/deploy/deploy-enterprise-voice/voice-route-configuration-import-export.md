---
title: Exportar ou importar um arquivo de configuração de rota de voz no Skype para negócios
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Resumo: Saiba como exportar ou importar um arquivo de configuração de roteamento de voz no Skype para Business Server usando o Skype para painel de controle do servidor de negócios.'
ms.openlocfilehash: 8f0d8f4e221cbe23ac37c4126a9d26aac46e6d53
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874840"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="ab13b-103">Exportar ou importar um arquivo de configuração de rota de voz no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="ab13b-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="ab13b-104">**Resumo:** Saiba como exportar ou importar um arquivo de configuração de roteamento de voz no Skype para Business Server usando o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="ab13b-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="ab13b-105">Se quiser salvar sua configuração de roteamento de voz sem publicá-la, siga estas etapas para salvar e recuperar um instantâneo da sua configuração de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="ab13b-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="ab13b-106">Quando você importa um arquivo de configuração roteamento voz (.vcfg), mas tiver sofrido alterações à configuração de voz roteamento no servidor enquanto isso, as páginas do grupo de **Roteamento de voz** no Skype para painel de controle do Business Server indicará que existe foram feitas alterações não confirmadas roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="ab13b-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="ab13b-107">Essas alterações não confirmadas são as diferenças entre as duas configurações que exigem reconciliação.</span><span class="sxs-lookup"><span data-stu-id="ab13b-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="ab13b-108">Se você tiver feito as alterações não confirmadas às configurações em qualquer página dentro do grupo, as alterações são salvas no arquivo de configuração de voz exportado (.vcfg).</span><span class="sxs-lookup"><span data-stu-id="ab13b-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="ab13b-109">Isso permite que você faça alterações na configuração de roteamento durante várias sessões antes de publicar as alterações de voz.</span><span class="sxs-lookup"><span data-stu-id="ab13b-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="ab13b-110">Para exportar uma configuração de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="ab13b-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="ab13b-111">Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ab13b-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="ab13b-112">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="ab13b-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ab13b-113">Na barra de navegação esquerdo, clique em **Roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="ab13b-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="ab13b-114">No menu **Ações**, clique em **Exportar configuração**.</span><span class="sxs-lookup"><span data-stu-id="ab13b-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="ab13b-115">Especifique um local e nome de arquivo e então clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ab13b-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="ab13b-116">Para importar uma configuração de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="ab13b-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="ab13b-117">Faça logon no computador como membro do grupo **RTCUniversalServerAdmins** ou como membro da função administrativa **CsVoiceAdministrator**, **CsServerAdministrator**, ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ab13b-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="ab13b-118">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="ab13b-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ab13b-119">Na barra de navegação esquerda, clique em **Roteamento de Voz**.</span><span class="sxs-lookup"><span data-stu-id="ab13b-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="ab13b-120">No menu **Ações**, clique em **Importar Configuração**.</span><span class="sxs-lookup"><span data-stu-id="ab13b-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="ab13b-121">Localize o arquivo de configuração que você deseja importar e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="ab13b-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="ab13b-122">Clique em **Confirmar** e, em seguida, clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="ab13b-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ab13b-123">Sempre que importar um arquivo de configuração de voz, você deve executar o comando **Confirmar tudo** para publicar a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="ab13b-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="ab13b-124">Para obter detalhes, consulte [Publish alterações pendentes para a configuração de roteamento de voz no Skype para negócios](voice-route-config-changes.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="ab13b-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

