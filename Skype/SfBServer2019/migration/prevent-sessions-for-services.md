---
title: Evitar sessões de serviços
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
description: Você pode usar o Painel de Controle de instalação herdado para impedir novas sessões de todos os serviços herdado em execução em um computador específico ou para impedir novas sessões para um serviço herdado específico.
ms.openlocfilehash: c5cc8846febaf690376e01c36b9fa023b8377970
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752283"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="ebe1c-103">Evitar sessões de serviços</span><span class="sxs-lookup"><span data-stu-id="ebe1c-103">Prevent sessions for services</span></span>

<span data-ttu-id="ebe1c-104">Você pode usar o Painel de Controle de instalação herdado para impedir novas sessões de todos os serviços herdado em execução em um computador específico ou para impedir novas sessões para um serviço herdado específico.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="ebe1c-105">Para impedir novas sessões de serviços em um computador</span><span class="sxs-lookup"><span data-stu-id="ebe1c-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="ebe1c-106">Em uma conta de usuário membro do grupo RTCUniversalServerAdmins (ou com direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="ebe1c-107">Abra o Painel de Controle do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="ebe1c-108">Na barra de navegação à esquerda, clique em **Topologia** e em **Status**.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="ebe1c-109">Na página **Status**, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando os serviços para os quais você deseja impedir novas sessões e clique nele.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="ebe1c-110">Clique em **Ação**.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="ebe1c-111">Clique em **Impedir novas sessões para todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="ebe1c-112">Para Impedir novas sessões para um serviço específico</span><span class="sxs-lookup"><span data-stu-id="ebe1c-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="ebe1c-113">Em uma conta de usuário membro do grupo RTCUniversalServerAdmins (ou com direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="ebe1c-114">Abra o Painel de Controle do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="ebe1c-115">Na barra de navegação à esquerda, clique em **Topologia** e em **Status**.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="ebe1c-116">Na página **Status**, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando o serviço que você deseja iniciar ou interromper e clique nele.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="ebe1c-117">Clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="ebe1c-118">Classifique a lista de serviços, se necessário e clique no serviço para o qual você deseja impedir novas sessões.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="ebe1c-119">Clique em **Ações**.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="ebe1c-120">Clique em **Impedir novas sessões para o serviço**.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="ebe1c-121">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="ebe1c-121">Click **Close**.</span></span>
    

