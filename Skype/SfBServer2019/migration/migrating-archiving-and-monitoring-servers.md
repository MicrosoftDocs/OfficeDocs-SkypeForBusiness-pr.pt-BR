---
title: Migrando servidores de arquivamento e monitoramento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se você implantou o servidor de arquivamento e monitorando o servidor em seu ambiente herdado, poderá implantar esses servidores no ambiente do Skype for Business Server 2019 depois de migrar seus pools front-ends. No entanto, se a funcionalidade de arquivamento e monitoramento for essencial para sua organização, você deverá adicionar arquivamento e monitoramento ao pool piloto do Skype for Business Server 2019 antes de migrar para que a funcionalidade esteja disponível durante o processo de migração.
ms.openlocfilehash: 5088f4b4f72ddc083cf2868df893946561eb2469
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813449"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="ad619-104">Migrando servidores de arquivamento e monitoramento</span><span class="sxs-lookup"><span data-stu-id="ad619-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="ad619-105">Se você implantou o servidor de arquivamento e monitorando o servidor em seu ambiente herdado, poderá implantar esses servidores no ambiente do Skype for Business Server 2019 depois de migrar seus pools front-ends.</span><span class="sxs-lookup"><span data-stu-id="ad619-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="ad619-106">No entanto, se a funcionalidade de arquivamento e monitoramento for essencial para sua organização, você deverá adicionar arquivamento e monitoramento ao pool piloto do Skype for Business Server 2019 antes de migrar para que a funcionalidade esteja disponível durante o processo de migração.</span><span class="sxs-lookup"><span data-stu-id="ad619-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="ad619-107">Se você quiser a funcionalidade de arquivamento e monitoramento durante o processo de migração, tenha em mente as seguintes considerações:</span><span class="sxs-lookup"><span data-stu-id="ad619-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="ad619-108">O arquivamento de dados e monitoramento de dados não são movidos para a implantação do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ad619-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="ad619-109">Os dados que você reproduz antes de descomissionar o ambiente herdado serão o seu histórico de atividades no ambiente herdado.</span><span class="sxs-lookup"><span data-stu-id="ad619-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="ad619-110">A versão herdada do servidor de arquivamento e do Monitoring Server somente pode ser associada a um pool de front-end herdado.</span><span class="sxs-lookup"><span data-stu-id="ad619-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="ad619-111">No Skype for Business Server 2019, o arquivamento e o monitoramento não são mais funções do servidor, mas serviços integrados ao pool de front-end do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ad619-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="ad619-112">Durante o tempo em que suas implantações do 2019 e do Skype for Business Server existentes coexistem, a versão herdada do servidor de arquivamento e monitoração coleta dados para os usuários hospedados em pools herdados.</span><span class="sxs-lookup"><span data-stu-id="ad619-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="ad619-113">O arquivamento e o monitoramento no Skype for Business Server 2019 coletam dados para usuários hospedados no Skype for Business Server 2019 pools.</span><span class="sxs-lookup"><span data-stu-id="ad619-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ad619-114">Durante a fase de migração, quando você ainda estiver usando o seu servidor de borda herdado com o novo pool piloto do Skype for Business Server 2019, a versão herdada do servidor de arquivamento continua a coletar dados para os usuários hospedados em pools herdados e arquivamento no Skype for Business O servidor 2019 coleta dados para usuários hospedados no Skype for Business Server 2019 pools.</span><span class="sxs-lookup"><span data-stu-id="ad619-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="ad619-115">Se você usar uma solução de arquivamento e monitoramento de terceiros em conjunto com o arquivamento e o monitoramento no Skype for Business Server 2019, consulte o fornecedor sobre quando e como você precisa integrar a solução de terceiros com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ad619-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

