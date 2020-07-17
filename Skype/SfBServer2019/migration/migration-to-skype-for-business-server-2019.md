---
title: Migração para o Skype for Business Server 2019
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
description: Os tópicos desta seção orientam você durante o processo de migração para o Skype for Business Server 2019.
ms.openlocfilehash: 860fce550de33ed726bbbe723c8c7677ff09fc1c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752613"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="82638-103">Migração para o Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="82638-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="82638-104">Os tópicos desta seção orientam você durante o processo de migração para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="82638-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="82638-105">Este artigo aborda a migração do Lync Server 2013 ou do Skype for Business Server 2015 para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="82638-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82638-106">Ao longo do conteúdo, usamos o termo *herdado* para consultar o Lync Server 2013 ou o Skype for Business Server herdado 2015 que você está migrando para o Skype for business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="82638-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="82638-107">Este guia descreve as etapas geralmente necessárias para realizar cada fase da migração.</span><span class="sxs-lookup"><span data-stu-id="82638-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="82638-108">Ele não atende todas as topologias de implantação herdada possíveis ou todos os cenários de migração possíveis.</span><span class="sxs-lookup"><span data-stu-id="82638-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="82638-109">Portanto, talvez não seja necessário executar cada etapa descrita, ou talvez seja necessário executar etapas adicionais, dependendo de sua implantação.</span><span class="sxs-lookup"><span data-stu-id="82638-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="82638-110">Este guia também fornece exemplos de etapas de verificação.</span><span class="sxs-lookup"><span data-stu-id="82638-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="82638-111">Essas etapas de verificação são fornecidas para ajudá-lo a entender o que você precisa procurar para garantir que cada fase seja concluída com êxito à medida que você progride em sua migração.</span><span class="sxs-lookup"><span data-stu-id="82638-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="82638-112">Personalize estas etapas de verificação para seu processo de migração específico.</span><span class="sxs-lookup"><span data-stu-id="82638-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="82638-113">Este guia oferece informações específicas para atualizar sua implantação existente.</span><span class="sxs-lookup"><span data-stu-id="82638-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="82638-114">Ele não explica como alterar sua topologia existente.</span><span class="sxs-lookup"><span data-stu-id="82638-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="82638-115">O documento também não aborda a implementação de novos recursos.</span><span class="sxs-lookup"><span data-stu-id="82638-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="82638-116">Quando um procedimento detalhado é documentado em outro lugar, este guia direciona você para a seção artigo ou artigo.</span><span class="sxs-lookup"><span data-stu-id="82638-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="82638-117">Este artigo define termos conforme especificado na lista a seguir.</span><span class="sxs-lookup"><span data-stu-id="82638-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="82638-118">**migração:** Mover sua implantação de produção do Lync Server 2013 ou do Skype for Business Server 2015 para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="82638-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="82638-119">**coexistência:** O ambiente temporário que existe durante a migração quando algumas funcionalidades foram migradas para o Skype for Business Server 2019 e outras funcionalidades ainda permanecem em uma versão anterior.</span><span class="sxs-lookup"><span data-stu-id="82638-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="82638-120">**interoperabilidade:** A capacidade de sua implantação operar com êxito durante o período de coexistência.</span><span class="sxs-lookup"><span data-stu-id="82638-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="82638-121">**herdado:** O sistema para o qual você está migrando, que é o Lync Server 2013 ou o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="82638-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="82638-122">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="82638-122">In this section</span></span>

- [<span data-ttu-id="82638-123">Antes de começar a migração</span><span class="sxs-lookup"><span data-stu-id="82638-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="82638-124">Fase 1: Planejar sua migração</span><span class="sxs-lookup"><span data-stu-id="82638-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="82638-125">Fase 2: Preparar para migração</span><span class="sxs-lookup"><span data-stu-id="82638-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="82638-126">Fase 3: Implantar pool piloto</span><span class="sxs-lookup"><span data-stu-id="82638-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="82638-127">Fase 4: mover usuários de teste para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="82638-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="82638-128">Etapa 5: Adicionar Servidor de Borda ao pool piloto</span><span class="sxs-lookup"><span data-stu-id="82638-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="82638-129">Fase 6: Mover da implantação piloto para produção</span><span class="sxs-lookup"><span data-stu-id="82638-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="82638-130">Fase 7: Concluir tarefas pós-migração</span><span class="sxs-lookup"><span data-stu-id="82638-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="82638-131">Fase 8: Encerrar os pools herdados</span><span class="sxs-lookup"><span data-stu-id="82638-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

