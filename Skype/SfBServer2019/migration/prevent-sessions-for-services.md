---
title: Evitar sessões de serviços
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode usar o painel de controle de instalações herdadas para impedir novas sessões para todos os serviços herdados em execução em um computador específico ou para impedir novas sessões para um serviço herdado específico.
ms.openlocfilehash: 978c97bd7f610e6b40d467b80f5df8483b6d370f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244362"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="c363d-103">Evitar sessões de serviços</span><span class="sxs-lookup"><span data-stu-id="c363d-103">Prevent sessions for services</span></span>

<span data-ttu-id="c363d-104">Você pode usar o painel de controle de instalações herdadas para impedir novas sessões para todos os serviços herdados em execução em um computador específico ou para impedir novas sessões para um serviço herdado específico.</span><span class="sxs-lookup"><span data-stu-id="c363d-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="c363d-105">Para impedir novas sessões para serviços em um computador</span><span class="sxs-lookup"><span data-stu-id="c363d-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="c363d-106">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c363d-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="c363d-107">Abra o painel de controle do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c363d-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="c363d-108">Na barra de navegação esquerda, clique em **Topologia** e em **Status**. </span><span class="sxs-lookup"><span data-stu-id="c363d-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="c363d-109">Na página **status** , classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando os serviços para os quais você deseja impedir novas sessões e, em seguida, clique nela.</span><span class="sxs-lookup"><span data-stu-id="c363d-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="c363d-110">Clique em **ação**.</span><span class="sxs-lookup"><span data-stu-id="c363d-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="c363d-111">Clique em **impedir novas sessões para todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="c363d-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="c363d-112">Para impedir novas sessões para um serviço específico</span><span class="sxs-lookup"><span data-stu-id="c363d-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="c363d-113">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c363d-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="c363d-114">Abra o painel de controle do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="c363d-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="c363d-115">Na barra de navegação esquerda, clique em **Topologia** e em **Status**. </span><span class="sxs-lookup"><span data-stu-id="c363d-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="c363d-116">Na página **status** , classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando o serviço que você deseja iniciar ou parar e, em seguida, clique nele.</span><span class="sxs-lookup"><span data-stu-id="c363d-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="c363d-117">Clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c363d-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="c363d-118">Classifique a lista de serviços, se necessário, e clique no serviço para o qual você deseja impedir novas sessões.</span><span class="sxs-lookup"><span data-stu-id="c363d-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="c363d-119">Clique em **ação**.</span><span class="sxs-lookup"><span data-stu-id="c363d-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="c363d-120">Clique em **impedir novas sessões para o serviço**.</span><span class="sxs-lookup"><span data-stu-id="c363d-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="c363d-121">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c363d-121">Click **Close**.</span></span>
    

