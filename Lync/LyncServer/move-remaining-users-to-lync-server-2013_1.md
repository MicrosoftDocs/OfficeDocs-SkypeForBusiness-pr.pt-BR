---
title: Mover os usuários restantes para o Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81d74c9cc578909061d098d349e685817b71e4d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500168"
---
# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="f9308-102">Mover os usuários restantes para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9308-102">Move remaining users to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9308-103">_**Última modificação do tópico:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="f9308-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="f9308-104">Você pode mover os usuários para a nova implantação do Lync Server 2013 usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f9308-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="f9308-105">Você deve atender a alguns requisitos para garantir uma transição suave para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9308-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="f9308-106">Para obter detalhes sobre os pré-requisitos para concluir os procedimentos deste tópico, consulte [Configure clients for Migration](configure-clients-for-migration_1.md).</span><span class="sxs-lookup"><span data-stu-id="f9308-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration_1.md).</span></span> <span data-ttu-id="f9308-107">Para obter etapas detalhadas sobre como mover usuários, consulte [fase 6: mover usuários para o pool piloto](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="f9308-107">For detailed steps about moving users, see [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f9308-108">Você não pode usar o snap-in usuários e computadores do Active Directory ou as ferramentas administrativas do Microsoft Office Communications Server 2007 R2 para mover usuários do seu ambiente herdado para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f9308-108">You cannot use the Active Directory Users and Computers snap-in or the Microsoft Office Communications Server 2007 R2 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f9308-p102">O cmdlet <STRONG>Move-CsLegacyUser</STRONG> exige que os nomes de usuários sejam formados adequadamente e não tenham espaços à esquerda ou direita. Você não pode mover uma conta de usuário usando o cmdlet <STRONG>Move-CsLegacyUser</STRONG> se ele tiver espaços à esquerda ou direita.</span><span class="sxs-lookup"><span data-stu-id="f9308-p102">The <STRONG>Move-CsLegacyUser</STRONG> cmdlet requires that user names are properly formed and do not have leading or trailing spaces. You cannot move a user account using the <STRONG>Move-CsLegacyUser</STRONG> cmdlet if it contains leading or trailing spaces.</span></span>



</div>

<span data-ttu-id="f9308-111">Quando você mover um usuário para um pool do Lync Server 2013, os dados do usuário serão movidos para o banco de dados back-end associado ao novo pool.</span><span class="sxs-lookup"><span data-stu-id="f9308-111">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f9308-112">Isso inclui as reuniões ativas criadas pelo usuário herdado.</span><span class="sxs-lookup"><span data-stu-id="f9308-112">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="f9308-113">Por exemplo, se um usuário herdado configurou uma conferência de <STRONG>reunião</STRONG> , essa conferência ainda estará disponível no novo pool do Lync Server 2013, depois que o usuário tiver sido movido.</span><span class="sxs-lookup"><span data-stu-id="f9308-113">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool, after the user has been moved.</span></span> <span data-ttu-id="f9308-114">Os detalhes para acessar essa a reunião ainda terão a mesma <STRONG>URL e ID da conferência</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="f9308-114">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="f9308-115">A única diferença é que a conferência agora está hospedada no pool do Lync Server 2013 e não no pool do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f9308-115">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in Office Communications Server 2007 R2 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f9308-116">A hospedagem de usuários no Lync Server 2013 não requer a implantação de clientes atualizados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f9308-116">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="f9308-117">A nova funcionalidade estará disponível para os usuários apenas quando eles tiverem o novo software cliente.</span><span class="sxs-lookup"><span data-stu-id="f9308-117">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="f9308-118">Tarefa pós-migração</span><span class="sxs-lookup"><span data-stu-id="f9308-118">Post Migration Task</span></span>

1.  <span data-ttu-id="f9308-119">Depois de mover os usuários, verifique a política de conferência atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="f9308-119">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="f9308-120">Para garantir que as reuniões organizadas pelos usuários hospedados no Lync Server 2013 funcionem perfeitamente com usuários federados hospedados no Office Communications Server 2007 R2, a política de conferência atribuída aos usuários migrados deve permitir participantes anônimos.</span><span class="sxs-lookup"><span data-stu-id="f9308-120">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Office Communications Server 2007 R2, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="f9308-121">As políticas de conferência que permitem que os participantes anônimos **permitam que os participantes convidem usuários anônimos** selecionados no painel de controle do lync Server 2013 e tenham o **AllowAnonymousParticipantsInMeetings** definido como **true** na saída do cmdlet **Get-CsConferencingPolicy** no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f9308-121">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="f9308-122">Para obter detalhes sobre como configurar a política de conferência usando o Shell de gerenciamento do Lync Server, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f9308-122">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

