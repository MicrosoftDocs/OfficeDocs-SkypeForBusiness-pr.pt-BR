---
title: Mover usuários restantes
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Você pode mover os usuários para a nova implantação do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server. Você deve atender a alguns requisitos para garantir uma transição suave para o Skype for Business Server 2019. Para obter detalhes sobre os pré-requisitos para concluir os procedimentos deste tópico, consulte Configure clients for Migration. Para obter etapas detalhadas sobre como mover usuários, consulte fase 4: mover usuários de teste para o pool piloto.'
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753709"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="9e55b-106">Mover os usuários restantes para o Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="9e55b-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="9e55b-107">Você pode mover os usuários para a nova implantação do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server ou o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9e55b-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="9e55b-108">Você deve atender a alguns requisitos para garantir uma transição suave para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9e55b-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="9e55b-109">Para obter detalhes sobre os pré-requisitos para concluir os procedimentos deste tópico, consulte [Configure clients for Migration](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="9e55b-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="9e55b-110">Para obter etapas detalhadas sobre como mover usuários, consulte [fase 4: mover usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="9e55b-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9e55b-111">Você não pode usar o snap-in usuários e computadores do Active Directory ou as ferramentas administrativas herdadas para mover usuários do seu ambiente herdado para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9e55b-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="9e55b-112">Quando você mover um usuário para um pool do Skype for Business Server 2019, os dados do usuário serão movidos para o banco de dados back-end associado ao novo pool.</span><span class="sxs-lookup"><span data-stu-id="9e55b-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9e55b-113">Isso inclui as reuniões ativas criadas pelo usuário herdado.</span><span class="sxs-lookup"><span data-stu-id="9e55b-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="9e55b-114">Por exemplo, se um usuário herdado configurou uma conferência de **reunião** , essa conferência ainda estará disponível no novo pool do Skype for Business Server 2019 depois que o usuário tiver sido movido.</span><span class="sxs-lookup"><span data-stu-id="9e55b-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="9e55b-115">Os detalhes para acessar essa a reunião ainda terão a mesma **URL e ID da conferência**.</span><span class="sxs-lookup"><span data-stu-id="9e55b-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="9e55b-116">A única diferença é que a conferência agora está hospedada no pool do Skype for Business Server 2019 e não no pool herdado.</span><span class="sxs-lookup"><span data-stu-id="9e55b-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9e55b-117">A hospedagem de usuários no Skype for Business Server 2019 não requer a implantação de clientes atualizados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="9e55b-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="9e55b-118">A nova funcionalidade estará disponível aos usuários somente depois que eles atualizarem para o novo software cliente.</span><span class="sxs-lookup"><span data-stu-id="9e55b-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="9e55b-119">Tarefa de migração de pós-instalação</span><span class="sxs-lookup"><span data-stu-id="9e55b-119">Post migration task</span></span>

1. <span data-ttu-id="9e55b-120">Depois de mover os usuários, verifique a política de conferência atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="9e55b-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="9e55b-121">Para garantir que as reuniões organizadas pelos usuários hospedados no Skype for Business Server 2019 funcionem perfeitamente com os usuários federados hospedados na instalação herdada, a política de conferência atribuída aos usuários migrados deve permitir participantes anônimos.</span><span class="sxs-lookup"><span data-stu-id="9e55b-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="9e55b-122">As políticas de conferência que permitem que os participantes anônimos **permitam que os participantes convidem usuários anônimos** selecionados no painel de controle do Skype for Business Server 2019 e tenham o **AllowAnonymousParticipantsInMeetings** definido como **true** na saída do cmdlet **Get-CsConferencingPolicy** no Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9e55b-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

