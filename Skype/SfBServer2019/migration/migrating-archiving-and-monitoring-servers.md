---
title: Migrando servidores de arquivamento e monitoramento
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se você implantou o servidor de arquivamento e Monitoring Server no seu ambiente herdado, você pode implantar esses servidores no seu Skype para ambiente de negócios Server 2019 após migrar seus pools de Front-End. Se a funcionalidade de monitoramento e arquivamento são essenciais para sua organização, no entanto, você deve adicionar arquivamento e monitoramento para seu Skype para o pool piloto Business Server 2019 antes de migrar para que a funcionalidade está disponível durante o processo de migração.
ms.openlocfilehash: cd6e3bf7ef04ca7906b707a30211d0c22d22d837
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028751"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="a8142-104">Migrando servidores de arquivamento e monitoramento</span><span class="sxs-lookup"><span data-stu-id="a8142-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="a8142-105">Se você implantou o servidor de arquivamento e Monitoring Server no seu ambiente herdado, você pode implantar esses servidores no seu Skype para ambiente de negócios Server 2019 após migrar seus pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="a8142-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="a8142-106">Se a funcionalidade de monitoramento e arquivamento são essenciais para sua organização, no entanto, você deve adicionar arquivamento e monitoramento para seu Skype para o pool piloto Business Server 2019 antes de migrar para que a funcionalidade está disponível durante o processo de migração.</span><span class="sxs-lookup"><span data-stu-id="a8142-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="a8142-107">Se você deseja as funcionalidades de arquivamento e monitoração durante o processo de migração, lembre-se das considerações a seguir:</span><span class="sxs-lookup"><span data-stu-id="a8142-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="a8142-108">Dados de arquivamento e monitoramento de dados não são movidas para o Skype para implantação Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8142-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="a8142-109">Os dados de que backup antes de encerrar o ambiente Herdado será seu histórico de atividade no ambiente herdado.</span><span class="sxs-lookup"><span data-stu-id="a8142-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="a8142-110">A versão herdada do servidor de arquivamento e Monitoring Server pode ser associada somente um pool de Front-End herdado.</span><span class="sxs-lookup"><span data-stu-id="a8142-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="a8142-111">No Skype para Business Server 2019, arquivamento e monitoramento não são mais funções de servidor, mas serviços integrados do Skype para pool de negócios 2019 Front-End Server.</span><span class="sxs-lookup"><span data-stu-id="a8142-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="a8142-112">Durante o tempo que seu herdado e Skype para implantações de negócios Server 2019 coexistir, a versão herdada do servidor de arquivamento e Monitoring Server colete dados para usuários hospedados em pools herdados.</span><span class="sxs-lookup"><span data-stu-id="a8142-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="a8142-113">Arquivamento e monitoramento no Skype para Business Server 2019 coletam dados para usuários hospedagem no Skype para Business Server 2019 pools.</span><span class="sxs-lookup"><span data-stu-id="a8142-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a8142-114">Durante a fase de migração quando você estiver ainda usando seu servidor de borda herdado com o novo Skype para o servidor de negócios 2019 continua do pool piloto, a versão herdada do servidor de arquivamento para coletar dados para usuários hospedado em pools herdados e arquivamento no Skype para negócios Servidor 2019 reúne dados para usuários hospedagem no Skype para Business Server 2019 pools.</span><span class="sxs-lookup"><span data-stu-id="a8142-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="a8142-115">Se você usar um terceiro de arquivamento e monitoramento de solução em conjunto com o arquivamento e monitoramento no Skype para Business Server 2019, consulte o fornecedor sobre quando e como você precisa integrar a solução de terceiros com Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8142-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

