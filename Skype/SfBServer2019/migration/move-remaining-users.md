---
title: Mover usuários restantes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Você pode mover usuários para o novo Skype para implantação Business Server 2019 usando qualquer um dos Skype para painel de controle do Business Server ou Skype do Shell de gerenciamento do servidor de negócios. Alguns requisitos para garantir uma transição suave para o Skype para Business Server 2019 devem ser atendidos. Para obter detalhes sobre os pré-requisitos para concluir os procedimentos neste tópico, consulte Configure clientes para migração. Para obter etapas detalhadas sobre como mover usuários, consulte a fase 4: mover usuários de teste para o pool piloto.'
ms.openlocfilehash: 9f984b7fac919decce521c6dafc587a4ac86de50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231585"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="f88d0-106">Mover usuários restantes para Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="f88d0-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="f88d0-107">Você pode mover usuários para o novo Skype para implantação Business Server 2019 usando qualquer um dos Skype para painel de controle do Business Server ou Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="f88d0-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="f88d0-108">Alguns requisitos para garantir uma transição suave para o Skype para Business Server 2019 devem ser atendidos.</span><span class="sxs-lookup"><span data-stu-id="f88d0-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="f88d0-109">Para obter detalhes sobre os pré-requisitos para concluir os procedimentos neste tópico, consulte [Configure clientes para migração](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="f88d0-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="f88d0-110">Para obter instruções detalhadas sobre como mover usuários, consulte [fase 4: mover usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="f88d0-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f88d0-111">Você não pode usar o snap-in de computadores e usuários do Active Directory ou as ferramentas administrativas herdadas para mover usuários de seu ambiente herdado para Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f88d0-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="f88d0-112">Quando você mover um usuário para um Skype para Business Server 2019 pool, os dados para o usuário são movidos para o banco de dados de back-end associado ao novo pool.</span><span class="sxs-lookup"><span data-stu-id="f88d0-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f88d0-113">Isso inclui as reuniões ativas criadas pelo usuário herdado.</span><span class="sxs-lookup"><span data-stu-id="f88d0-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="f88d0-114">Por exemplo, se um usuário herdado tiver configurado uma conferência de **Minha reunião** , conferência continuará disponível no novo Skype para Business Server 2019 pool depois que o usuário foi movido.</span><span class="sxs-lookup"><span data-stu-id="f88d0-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="f88d0-115">Os detalhes para acessar essa reunião ainda será a mesma **URL de conferência e a ID de conferência**.</span><span class="sxs-lookup"><span data-stu-id="f88d0-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="f88d0-116">A única diferença é que a conferência agora está hospedada no Skype para Business Server 2019 pool e não no pool herdado.</span><span class="sxs-lookup"><span data-stu-id="f88d0-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f88d0-117">A hospedagem de usuários em Skype para Business Server 2019 não exige que você implante clientes atualizados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f88d0-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="f88d0-118">Nova funcionalidade estará disponível para os usuários somente quando eles tem atualizado para o novo software cliente.</span><span class="sxs-lookup"><span data-stu-id="f88d0-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="f88d0-119">Tarefas pós-migração</span><span class="sxs-lookup"><span data-stu-id="f88d0-119">Post migration task</span></span>

1. <span data-ttu-id="f88d0-120">Depois de mover usuários, verifique se a política de conferência atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="f88d0-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="f88d0-121">Para garantir que as reuniões organizadas pelos usuários hospedagem no Skype Business Server 2019 trabalho perfeitamente com os usuários federados hospedados no install herdado, a política de conferência atribuída aos usuários migrados deve permitir participantes anônimos.</span><span class="sxs-lookup"><span data-stu-id="f88d0-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="f88d0-122">Políticas de conferência que permitem participantes anônimos tem **Permitir que os participantes convidem usuários anônimos** selecionados no Skype para painel de controle do Business Server 2019 e tem **AllowAnonymousParticipantsInMeetings** definem como **True** no saída do cmdlet **Get-CsConferencingPolicy** no Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="f88d0-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

