---
title: Migração do Lync Server 2010 para o Lync Server 2013
description: Migração do Lync Server 2010 para o Lync Server 2013.
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
ms.openlocfilehash: fbe1bc1b7745c5ddc89a7f8fb64295a82f52c9bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543197"
---
# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="bd487-103">Migração do Lync Server 2010 para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd487-103">Migration from Lync Server 2010 to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd487-104">_**Última modificação do tópico:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="bd487-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="bd487-105">Os tópicos desta seção orientam você durante o processo de migração do Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd487-105">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bd487-p101">Este documento descreve as etapas geralmente necessárias para realizar cada fase de migração. Não resolve todos os cenários de migração possíveis ou de topologia de implantação herdada. Portanto, você pode não precisar realizar cada etapa descrita ou pode precisar realizar etapas adicionais, dependendo da sua implantação. Este documento também oferece exemplos de etapas de verificação. Estas etapas de verificação são oferecidas para ajudar na compreensão do que é necessário procurar para garantir que cada fase seja concluída com êxito conforme você progride na sua implantação. Personalize estas etapas de verificação para seu processo de migração específico.</span><span class="sxs-lookup"><span data-stu-id="bd487-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="bd487-p102">Este guia oferece informações específicas para atualizar sua implantação existente. Explica como alterar sua topologia existente. Este guia não aborda a implementação de novos recursos. Quando um procedimento detalhado é documentado em outro local, este guia orienta você para o documento ou seção adequado.</span><span class="sxs-lookup"><span data-stu-id="bd487-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="bd487-116">Este documento define os termos conforme especificados na lista a seguir.</span><span class="sxs-lookup"><span data-stu-id="bd487-116">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="bd487-117">*migração*</span><span class="sxs-lookup"><span data-stu-id="bd487-117">*migration*</span></span>  
    <span data-ttu-id="bd487-118">Mover sua implantação de produção de uma versão anterior do Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd487-118">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="bd487-119">*atualização*</span><span class="sxs-lookup"><span data-stu-id="bd487-119">*upgrade*</span></span>  
    <span data-ttu-id="bd487-120">Instalação de uma versão mais recente de software em um servidor ou computador cliente.</span><span class="sxs-lookup"><span data-stu-id="bd487-120">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="bd487-121">*coexistência*</span><span class="sxs-lookup"><span data-stu-id="bd487-121">*coexistence*</span></span>  
    <span data-ttu-id="bd487-122">O ambiente temporário que existe durante a migração quando algumas funcionalidades foram migradas para o Lync Server 2013 e outras funcionalidades ainda permanecem em uma versão anterior do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bd487-122">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="bd487-123">*interoperabilidade*</span><span class="sxs-lookup"><span data-stu-id="bd487-123">*interoperability*</span></span>  
    <span data-ttu-id="bd487-124">A capacidade da sua implantação operar com êxito durante o período de coexistência.</span><span class="sxs-lookup"><span data-stu-id="bd487-124">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bd487-125">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="bd487-125">In This Section</span></span>

  - [<span data-ttu-id="bd487-126">Antes de começar a migração</span><span class="sxs-lookup"><span data-stu-id="bd487-126">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="bd487-127">Fase 1: planejar a migração do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bd487-127">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="bd487-128">Fase 2: Preparar para migração</span><span class="sxs-lookup"><span data-stu-id="bd487-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="bd487-129">Fase 3: implantar o pool piloto do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd487-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="bd487-130">Fase 4: mover usuários de teste para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="bd487-130">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="bd487-131">Fase 5: Adicionar o servidor de borda do Lync Server 2013 ao pool piloto</span><span class="sxs-lookup"><span data-stu-id="bd487-131">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="bd487-132">Fase 6: Mover da implantação piloto para produção</span><span class="sxs-lookup"><span data-stu-id="bd487-132">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="bd487-133">Fase 7: Concluir tarefas pós-migração</span><span class="sxs-lookup"><span data-stu-id="bd487-133">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="bd487-134">Fase 8: Encerrar os pools herdados</span><span class="sxs-lookup"><span data-stu-id="bd487-134">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

