---
title: Migração do Lync Server 2010 para o Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c32d2679d4f31863e389735efb6660ea670b959
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="51efb-102">Migração do Lync Server 2010 para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51efb-102">Migration from Lync Server 2010 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51efb-103">_**Tópico da última modificação:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="51efb-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="51efb-104">Os tópicos desta seção guiam você pelo processo de migração do Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51efb-104">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="51efb-105">Este documento descreve as etapas geralmente necessárias para realizar cada fase da migração.</span><span class="sxs-lookup"><span data-stu-id="51efb-105">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="51efb-106">Ele não trata cada possível topologia de implantação herdada ou todos os possíveis cenários de migração.</span><span class="sxs-lookup"><span data-stu-id="51efb-106">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="51efb-107">Portanto, talvez você não precise executar todas as etapas descritas ou talvez seja necessário executar etapas adicionais, dependendo da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="51efb-107">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="51efb-108">Este documento também fornece exemplos de etapas de verificação.</span><span class="sxs-lookup"><span data-stu-id="51efb-108">This document also provides examples of verification steps.</span></span> <span data-ttu-id="51efb-109">Estas etapas de verificação são fornecidas para ajudá-lo a entender o que você precisa procurar para garantir que cada fase seja concluída com êxito enquanto avança pela migração.</span><span class="sxs-lookup"><span data-stu-id="51efb-109">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="51efb-110">Personalize essas etapas de verificação para seu processo de migração específico.</span><span class="sxs-lookup"><span data-stu-id="51efb-110">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="51efb-111">Este guia fornece informações específicas para atualizar sua implantação existente.</span><span class="sxs-lookup"><span data-stu-id="51efb-111">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="51efb-112">Ele não explica como alterar a topologia existente.</span><span class="sxs-lookup"><span data-stu-id="51efb-112">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="51efb-113">Este guia não aborda a implementação de novos recursos.</span><span class="sxs-lookup"><span data-stu-id="51efb-113">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="51efb-114">Quando um procedimento detalhado for documentado em outro lugar, este guia direcionará você para a seção do documento ou documento apropriado.</span><span class="sxs-lookup"><span data-stu-id="51efb-114">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="51efb-115">Este documento define termos conforme especificado na lista a seguir.</span><span class="sxs-lookup"><span data-stu-id="51efb-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="51efb-116">*migração*</span><span class="sxs-lookup"><span data-stu-id="51efb-116">*migration*</span></span>  
    <span data-ttu-id="51efb-117">Mover a implantação de produção de uma versão anterior do Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51efb-117">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="51efb-118">*atualização*</span><span class="sxs-lookup"><span data-stu-id="51efb-118">*upgrade*</span></span>  
    <span data-ttu-id="51efb-119">Instalar uma versão mais recente do software em um computador cliente ou servidor.</span><span class="sxs-lookup"><span data-stu-id="51efb-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="51efb-120">*coexistência*</span><span class="sxs-lookup"><span data-stu-id="51efb-120">*coexistence*</span></span>  
    <span data-ttu-id="51efb-121">O ambiente temporário que existe durante a migração quando algumas funcionalidades foram migradas para o Lync Server 2013 e outras funcionalidades ainda permanecem em uma versão anterior do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="51efb-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="51efb-122">*interoperabilidade*</span><span class="sxs-lookup"><span data-stu-id="51efb-122">*interoperability*</span></span>  
    <span data-ttu-id="51efb-123">A capacidade de sua implantação operar com sucesso durante o período de coexistência.</span><span class="sxs-lookup"><span data-stu-id="51efb-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="51efb-124">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="51efb-124">In This Section</span></span>

  - [<span data-ttu-id="51efb-125">Antes de começar a migração</span><span class="sxs-lookup"><span data-stu-id="51efb-125">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="51efb-126">Fase 1: planejar a migração do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="51efb-126">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="51efb-127">Fase 2: Preparar para migração</span><span class="sxs-lookup"><span data-stu-id="51efb-127">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="51efb-128">Fase 3: implantar o pool piloto do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51efb-128">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="51efb-129">Fase 4: mover os usuários de teste para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="51efb-129">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="51efb-130">Fase 5: Adicionar o servidor de borda do Lync Server 2013 ao pool piloto</span><span class="sxs-lookup"><span data-stu-id="51efb-130">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="51efb-131">Fase 6: Mover da implantação piloto para produção</span><span class="sxs-lookup"><span data-stu-id="51efb-131">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="51efb-132">Fase 7: Concluir tarefas pós-migração</span><span class="sxs-lookup"><span data-stu-id="51efb-132">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="51efb-133">Fase 8: Encerrar os pools herdados</span><span class="sxs-lookup"><span data-stu-id="51efb-133">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

