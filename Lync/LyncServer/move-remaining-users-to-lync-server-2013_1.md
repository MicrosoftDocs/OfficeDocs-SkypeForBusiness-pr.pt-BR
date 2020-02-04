---
title: Mover usuários restantes para Lync Server 2013
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
ms.openlocfilehash: bcb5a709e896b66a1c8cd33a930bfeed5e05644f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="aee19-102">Mover usuários restantes para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aee19-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aee19-103">_**Tópico da última modificação:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="aee19-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="aee19-104">Você pode mover usuários para a nova implantação do Lync Server 2013 usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aee19-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="aee19-105">Você deve atender a alguns requisitos para garantir uma transição tranqüila para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aee19-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="aee19-106">Para obter detalhes sobre pré-requisitos para completar os procedimentos deste tópico, consulte [configurar clientes para migração](configure-clients-for-migration_1.md).</span><span class="sxs-lookup"><span data-stu-id="aee19-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration_1.md).</span></span> <span data-ttu-id="aee19-107">Para ver as etapas detalhadas sobre como mover usuários, consulte [fase 6: mover usuários para o pool piloto](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="aee19-107">For detailed steps about moving users, see [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aee19-108">Você não pode usar o snap-in usuários e computadores do Active Directory ou as ferramentas administrativas do Microsoft Office Communications Server 2007 R2 para mover os usuários do seu ambiente herdado para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aee19-108">You cannot use the Active Directory Users and Computers snap-in or the Microsoft Office Communications Server 2007 R2 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aee19-109">O cmdlet <STRONG>move-CsLegacyUser</STRONG> requer que os nomes de usuário sejam formados corretamente e não tenham espaços à esquerda ou à direita.</span><span class="sxs-lookup"><span data-stu-id="aee19-109">The <STRONG>Move-CsLegacyUser</STRONG> cmdlet requires that user names are properly formed and do not have leading or trailing spaces.</span></span> <span data-ttu-id="aee19-110">Você não pode mover uma conta de usuário usando o cmdlet <STRONG>move-CsLegacyUser</STRONG> se ele contiver espaços à esquerda ou à direita.</span><span class="sxs-lookup"><span data-stu-id="aee19-110">You cannot move a user account using the <STRONG>Move-CsLegacyUser</STRONG> cmdlet if it contains leading or trailing spaces.</span></span>



</div>

<span data-ttu-id="aee19-111">Quando você move um usuário para um pool do Lync Server 2013, os dados do usuário são movidos para o banco de dados back-end que está associado ao novo pool.</span><span class="sxs-lookup"><span data-stu-id="aee19-111">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aee19-112">Isso inclui as reuniões ativas criadas pelo usuário herdado.</span><span class="sxs-lookup"><span data-stu-id="aee19-112">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="aee19-113">Por exemplo, se um usuário herdado configurou uma conferência de <STRONG>reunião</STRONG> , essa conferência ainda estará disponível no novo pool do Lync Server 2013, após o usuário ter sido movido.</span><span class="sxs-lookup"><span data-stu-id="aee19-113">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool, after the user has been moved.</span></span> <span data-ttu-id="aee19-114">Os detalhes para acessar a reunião ainda serão a mesma <STRONG>URL de conferência e ID de conferência</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="aee19-114">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="aee19-115">A única diferença é que a conferência agora está hospedada no pool do Lync Server 2013 e não no pool do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="aee19-115">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in Office Communications Server 2007 R2 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="aee19-116">A hospedagem de usuários no Lync Server 2013 não requer que você implante clientes atualizados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="aee19-116">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="aee19-117">A nova funcionalidade estará disponível para os usuários somente quando tiverem atualizado para o novo software cliente.</span><span class="sxs-lookup"><span data-stu-id="aee19-117">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="aee19-118">Tarefa pós-migração</span><span class="sxs-lookup"><span data-stu-id="aee19-118">Post Migration Task</span></span>

1.  <span data-ttu-id="aee19-119">Depois de mover os usuários, verifique a política de conferência atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="aee19-119">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="aee19-120">Para garantir que as reuniões organizadas por usuários hospedados no Lync Server 2013 funcionem perfeitamente com usuários federados que são hospedados no Office Communications Server 2007 R2, a política de conferência atribuída aos usuários migrados deve permitir participantes anônimos.</span><span class="sxs-lookup"><span data-stu-id="aee19-120">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Office Communications Server 2007 R2, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="aee19-121">As políticas de conferência que permitem aos participantes anônimos **permitem que os participantes convidem usuários anônimos** selecionados no painel de controle do lync Server 2013 e têm o **AllowAnonymousParticipantsInMeetings** definido como **true** na saída do cmdlet **Get-CsConferencingPolicy** no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aee19-121">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="aee19-122">Para obter detalhes sobre como configurar a política de conferência usando o Shell de gerenciamento do Lync Server, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) na documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aee19-122">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

