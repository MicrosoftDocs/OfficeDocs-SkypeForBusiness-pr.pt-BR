---
title: Migração para o Skype for Business Server 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Os tópicos desta seção guiam você pelo processo de migração para o Skype for Business Server 2019.
ms.openlocfilehash: 8e58eaa3870e8149e874a1ec196a728976f429f3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237769"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="cb0ff-103">Migração para o Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="cb0ff-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="cb0ff-104">Os tópicos desta seção guiam você pelo processo de migração para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="cb0ff-105">Este artigo aborda a migração do Lync Server 2013 ou do Skype for Business Server 2015 para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb0ff-106">Ao longo do conteúdo, usamos o termo *herdado* para consultar o Lync Server 2013 ou o Skype for Business Server herdado 2015 que você está migrando para o Skype for business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cb0ff-107">Este guia descreve as etapas geralmente necessárias para realizar cada fase da migração.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="cb0ff-108">Ele não trata cada possível topologia de implantação herdada ou todos os possíveis cenários de migração.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="cb0ff-109">Portanto, talvez você não precise executar todas as etapas descritas ou talvez seja necessário executar etapas adicionais, dependendo da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="cb0ff-110">Este guia também fornece exemplos de etapas de verificação.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="cb0ff-111">Estas etapas de verificação são fornecidas para ajudá-lo a entender o que você precisa procurar para garantir que cada fase seja concluída com êxito enquanto avança pela migração.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="cb0ff-112">Personalize essas etapas de verificação para seu processo de migração específico.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="cb0ff-113">Este guia fornece informações específicas para atualizar sua implantação existente.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="cb0ff-114">Ele não explica como alterar a topologia existente.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="cb0ff-115">Este guia não aborda a implementação de novos recursos.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="cb0ff-116">Quando um procedimento detalhado é documentado em outro lugar, este guia direciona você para o artigo ou para a seção do artigo.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="cb0ff-117">Este artigo define termos conforme especificado na lista a seguir.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="cb0ff-118">**migração:** Mover a implantação de produção do Lync Server 2013 ou do Skype for Business Server 2015 para o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="cb0ff-119">**coexistência:** O ambiente temporário que existe durante a migração quando algumas funcionalidades foram migradas para o Skype for Business Server 2019 e outras funcionalidades ainda permanecem em uma versão anterior.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="cb0ff-120">**interoperabilidade:** A capacidade de sua implantação operar com sucesso durante o período de coexistência.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="cb0ff-121">**herdado:** O sistema do qual você está migrando para longe, que é o Lync Server 2013 ou o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="cb0ff-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="cb0ff-122">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="cb0ff-122">In this section</span></span>

- [<span data-ttu-id="cb0ff-123">Antes de começar a migração</span><span class="sxs-lookup"><span data-stu-id="cb0ff-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="cb0ff-124">Fase 1: Planejar sua migração</span><span class="sxs-lookup"><span data-stu-id="cb0ff-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="cb0ff-125">Fase 2: Preparar para migração</span><span class="sxs-lookup"><span data-stu-id="cb0ff-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="cb0ff-126">Fase 3: Implantar pool piloto</span><span class="sxs-lookup"><span data-stu-id="cb0ff-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="cb0ff-127">Fase 4: mover os usuários de teste para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="cb0ff-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="cb0ff-128">Etapa 5: Adicionar Servidor de Borda ao pool piloto</span><span class="sxs-lookup"><span data-stu-id="cb0ff-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="cb0ff-129">Fase 6: Mover da implantação piloto para produção</span><span class="sxs-lookup"><span data-stu-id="cb0ff-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="cb0ff-130">Fase 7: Concluir tarefas pós-migração</span><span class="sxs-lookup"><span data-stu-id="cb0ff-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="cb0ff-131">Fase 8: Encerrar os pools herdados</span><span class="sxs-lookup"><span data-stu-id="cb0ff-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

