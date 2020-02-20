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
ms.openlocfilehash: 0688fc80bb763a4b5aa3e7ff10970cef96465b84
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="1cc51-102">Migração do Lync Server 2010 para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cc51-102">Migration from Lync Server 2010 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cc51-103">_**Última modificação do tópico:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="1cc51-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="1cc51-104">Os tópicos desta seção orientam você durante o processo de migração do Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1cc51-104">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1cc51-p101">Este documento descreve as etapas geralmente necessárias para realizar cada fase de migração. Não resolve todos os cenários de migração possíveis ou de topologia de implantação herdada. Portanto, você pode não precisar realizar cada etapa descrita ou pode precisar realizar etapas adicionais, dependendo da sua implantação. Este documento também oferece exemplos de etapas de verificação. Estas etapas de verificação são oferecidas para ajudar na compreensão do que é necessário procurar para garantir que cada fase seja concluída com êxito conforme você progride na sua implantação. Personalize estas etapas de verificação para seu processo de migração específico.</span><span class="sxs-lookup"><span data-stu-id="1cc51-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="1cc51-p102">Este guia oferece informações específicas para atualizar sua implantação existente. Explica como alterar sua topologia existente. Este guia não aborda a implementação de novos recursos. Quando um procedimento detalhado é documentado em outro local, este guia orienta você para o documento ou seção adequado.</span><span class="sxs-lookup"><span data-stu-id="1cc51-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="1cc51-115">Este documento define os termos conforme especificados na lista a seguir.</span><span class="sxs-lookup"><span data-stu-id="1cc51-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="1cc51-116">*migração*</span><span class="sxs-lookup"><span data-stu-id="1cc51-116">*migration*</span></span>  
    <span data-ttu-id="1cc51-117">Mover sua implantação de produção de uma versão anterior do Lync Server 2010 para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1cc51-117">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="1cc51-118">*atualização*</span><span class="sxs-lookup"><span data-stu-id="1cc51-118">*upgrade*</span></span>  
    <span data-ttu-id="1cc51-119">Instalação de uma versão mais recente de software em um servidor ou computador cliente.</span><span class="sxs-lookup"><span data-stu-id="1cc51-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="1cc51-120">*coexistência*</span><span class="sxs-lookup"><span data-stu-id="1cc51-120">*coexistence*</span></span>  
    <span data-ttu-id="1cc51-121">O ambiente temporário que existe durante a migração quando algumas funcionalidades foram migradas para o Lync Server 2013 e outras funcionalidades ainda permanecem em uma versão anterior do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1cc51-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="1cc51-122">*interoperabilidade*</span><span class="sxs-lookup"><span data-stu-id="1cc51-122">*interoperability*</span></span>  
    <span data-ttu-id="1cc51-123">A capacidade da sua implantação operar com êxito durante o período de coexistência.</span><span class="sxs-lookup"><span data-stu-id="1cc51-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1cc51-124">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1cc51-124">In This Section</span></span>

  - [<span data-ttu-id="1cc51-125">Antes de começar a migração</span><span class="sxs-lookup"><span data-stu-id="1cc51-125">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="1cc51-126">Fase 1: planejar a migração do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1cc51-126">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="1cc51-127">Fase 2: preparar-se para a migração</span><span class="sxs-lookup"><span data-stu-id="1cc51-127">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="1cc51-128">Fase 3: implantar o pool piloto do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cc51-128">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="1cc51-129">Fase 4: mover usuários de teste para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="1cc51-129">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="1cc51-130">Fase 5: Adicionar o servidor de borda do Lync Server 2013 ao pool piloto</span><span class="sxs-lookup"><span data-stu-id="1cc51-130">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="1cc51-131">Fase 6: mover da implantação piloto para a produção</span><span class="sxs-lookup"><span data-stu-id="1cc51-131">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="1cc51-132">Fase 7: concluir tarefas de migração</span><span class="sxs-lookup"><span data-stu-id="1cc51-132">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="1cc51-133">Fase 8: encerrar pools herdados</span><span class="sxs-lookup"><span data-stu-id="1cc51-133">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

