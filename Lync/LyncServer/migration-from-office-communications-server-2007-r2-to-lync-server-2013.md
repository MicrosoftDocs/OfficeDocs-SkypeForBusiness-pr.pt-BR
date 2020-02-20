---
title: Migração do Office Communications Server 2007 R2 para o Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39aef26271594ed57d113bed4c3bb3702df41fac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a><span data-ttu-id="e6896-102">Migração do Office Communications Server 2007 R2 para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6896-102">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6896-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e6896-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e6896-104">Os tópicos desta seção orientam você durante o processo de migração do Office Communications Server 2007 R2 para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6896-104">The topics in this section guide you through the process of migrating from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e6896-p101">Este documento descreve as etapas geralmente necessárias para realizar cada fase de migração. Não resolve todos os cenários de migração possíveis ou de topologia de implantação herdada. Portanto, você pode não precisar realizar cada etapa descrita ou pode precisar realizar etapas adicionais, dependendo da sua implantação. Este documento também oferece exemplos de etapas de verificação. Estas etapas de verificação são oferecidas para ajudar na compreensão do que é necessário procurar para garantir que cada fase seja concluída com êxito conforme você progride na sua implantação. Personalize estas etapas de verificação para seu processo de migração específico.</span><span class="sxs-lookup"><span data-stu-id="e6896-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="e6896-p102">Este guia oferece informações específicas para atualizar sua implantação existente. Explica como alterar sua topologia existente. Este guia não aborda a implementação de novos recursos. Quando um procedimento detalhado é documentado em outro local, este guia orienta você para o documento ou seção adequado.</span><span class="sxs-lookup"><span data-stu-id="e6896-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="e6896-115">Este documento define os termos conforme especificados na lista a seguir.</span><span class="sxs-lookup"><span data-stu-id="e6896-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="e6896-116">*migração*</span><span class="sxs-lookup"><span data-stu-id="e6896-116">*migration*</span></span>  
    <span data-ttu-id="e6896-117">Mover sua implantação de produção de uma versão anterior do Office Communications Server 2007 R2 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6896-117">Moving your production deployment from a previous version of Office Communications Server 2007 R2 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="e6896-118">*atualização*</span><span class="sxs-lookup"><span data-stu-id="e6896-118">*upgrade*</span></span>  
    <span data-ttu-id="e6896-119">Instalação de uma versão mais recente de software em um servidor ou computador cliente.</span><span class="sxs-lookup"><span data-stu-id="e6896-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="e6896-120">*coexistência*</span><span class="sxs-lookup"><span data-stu-id="e6896-120">*coexistence*</span></span>  
    <span data-ttu-id="e6896-121">O ambiente temporário que existe durante a migração quando algumas funcionalidades foram migradas para o Lync Server 2013 e outras funcionalidades ainda permanecem em uma versão anterior do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e6896-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Office Communications Server 2007 R2.</span></span>

<!-- end list -->

  - <span data-ttu-id="e6896-122">*interoperabilidade*</span><span class="sxs-lookup"><span data-stu-id="e6896-122">*interoperability*</span></span>  
    <span data-ttu-id="e6896-123">A capacidade da sua implantação operar com êxito durante o período de coexistência.</span><span class="sxs-lookup"><span data-stu-id="e6896-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e6896-124">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="e6896-124">In This Section</span></span>

  - [<span data-ttu-id="e6896-125">Antes de começar a migração</span><span class="sxs-lookup"><span data-stu-id="e6896-125">Before you begin the migration</span></span>](before-you-begin-the-migration_1.md)

  - [<span data-ttu-id="e6896-126">Fases de migração</span><span class="sxs-lookup"><span data-stu-id="e6896-126">Migration phases</span></span>](migration-phases_1.md)

  - [<span data-ttu-id="e6896-127">Fase 1: planejar a migração do Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="e6896-127">Phase 1: Plan your migration from Office Communications Server 2007 R2</span></span>](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [<span data-ttu-id="e6896-128">Fase 2: preparar-se para a migração</span><span class="sxs-lookup"><span data-stu-id="e6896-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration_1.md)

  - [<span data-ttu-id="e6896-129">Fase 3: implantar o pool piloto do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6896-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [<span data-ttu-id="e6896-130">Fase 4: mesclar topologias</span><span class="sxs-lookup"><span data-stu-id="e6896-130">Phase 4: Merge topologies</span></span>](phase-4-merge-topologies.md)

  - [<span data-ttu-id="e6896-131">Fase 5: configurar o pool piloto</span><span class="sxs-lookup"><span data-stu-id="e6896-131">Phase 5: Configure the pilot pool</span></span>](phase-5-configure-the-pilot-pool.md)

  - [<span data-ttu-id="e6896-132">Fase 6: mover usuários para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="e6896-132">Phase 6: Move users to the pilot pool</span></span>](phase-6-move-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="e6896-133">Fase 7: Adicionar o servidor de borda do Lync Server 2013 ao pool piloto</span><span class="sxs-lookup"><span data-stu-id="e6896-133">Phase 7: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="e6896-134">Fase 8: mover da implantação piloto para a produção</span><span class="sxs-lookup"><span data-stu-id="e6896-134">Phase 8: Move from pilot deployment into production</span></span>](phase-8-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="e6896-135">Fase 9: concluir tarefas de migração</span><span class="sxs-lookup"><span data-stu-id="e6896-135">Phase 9: Complete post-migration tasks</span></span>](phase-9-complete-post-migration-tasks.md)

  - [<span data-ttu-id="e6896-136">Fase 10: encerrar o site herdado</span><span class="sxs-lookup"><span data-stu-id="e6896-136">Phase 10: Decommission legacy site</span></span>](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

