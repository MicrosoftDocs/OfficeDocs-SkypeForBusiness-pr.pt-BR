---
title: Migrando servidores de arquivamento e monitoramento
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
description: Se você implantou o Servidor de Arquivamento e o Monitoring Server em seu ambiente herdado, poderá implantar esses servidores em seu ambiente do Skype for Business Server 2019 depois de migrar seus pools de Front-End. No entanto, se a funcionalidade de arquivamento e monitoramento for crítica para sua organização, você deverá adicionar arquivamento e monitoramento ao seu pool piloto do Skype for Business Server 2019 antes de migrar para que a funcionalidade seja disponibilizada durante o processo de migração.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752663"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="c83ed-104">Migrando servidores de arquivamento e monitoramento</span><span class="sxs-lookup"><span data-stu-id="c83ed-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="c83ed-105">Se você implantou o Servidor de Arquivamento e o Monitoring Server em seu ambiente herdado, poderá implantar esses servidores em seu ambiente do Skype for Business Server 2019 depois de migrar seus pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="c83ed-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="c83ed-106">No entanto, se a funcionalidade de arquivamento e monitoramento for crítica para sua organização, você deverá adicionar arquivamento e monitoramento ao seu pool piloto do Skype for Business Server 2019 antes de migrar para que a funcionalidade seja disponibilizada durante o processo de migração.</span><span class="sxs-lookup"><span data-stu-id="c83ed-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="c83ed-107">Se você deseja as funcionalidades de arquivamento e monitoração durante o processo de migração, lembre das considerações a seguir:</span><span class="sxs-lookup"><span data-stu-id="c83ed-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="c83ed-108">Os dados de arquivamento e monitoramento não são movidos para a implantação do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c83ed-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="c83ed-109">Os dados que você faz o back-up antes de descommissionar o ambiente herddo serão seu histórico de atividades no ambiente herddo.</span><span class="sxs-lookup"><span data-stu-id="c83ed-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="c83ed-110">A versão herdada do Servidor de Arquivamento e do Monitoring Server só pode ser associada a um pool de Front-End herdado.</span><span class="sxs-lookup"><span data-stu-id="c83ed-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="c83ed-111">No Skype for Business Server 2019, Arquivamento e Monitoramento não são mais funções de servidor, mas serviços integrados ao pool de front-end do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c83ed-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="c83ed-112">Durante o tempo em que suas implantações herdadas e do Skype for Business Server 2019 coexistiram, a versão herdada do Servidor de Arquivamento e do Monitoring Server coleta dados para usuários que estão em pools herdados.</span><span class="sxs-lookup"><span data-stu-id="c83ed-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="c83ed-113">O Arquivamento e Monitoramento no Skype for Business Server 2019 coletam dados para usuários que estão em pools do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c83ed-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c83ed-114">Durante a fase de migração quando você ainda estiver usando seu servidor de Borda herdado com o novo pool piloto do Skype for Business Server 2019, a versão herdada do Servidor de Arquivamento continua a coletar dados para usuários que estão em pools herdados e arquivamento no Skype for Business Server 2019 coleta dados para usuários que estão no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c83ed-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="c83ed-115">Se você usar uma solução de arquivamento e monitoramento de terceiros em conjunto com o Arquivamento e Monitoramento no Skype for Business Server 2019, consulte seu fornecedor sobre quando e como você precisa integrar a solução de terceiros com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c83ed-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

