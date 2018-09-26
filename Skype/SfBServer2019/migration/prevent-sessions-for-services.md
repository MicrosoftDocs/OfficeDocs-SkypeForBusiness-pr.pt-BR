---
title: Evitar sessões de serviços
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode usar o painel de controle é instalado herdado para impedir novas sessões para todos os serviços de legado executando em um computador específico ou para impedir novas sessões para um serviço específico de legado.
ms.openlocfilehash: af4605f65d7cabe187696eda20bd9082ab73ad02
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027211"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="088e2-103">Evitar sessões de serviços</span><span class="sxs-lookup"><span data-stu-id="088e2-103">Prevent sessions for services</span></span>

<span data-ttu-id="088e2-104">Você pode usar o painel de controle é instalado herdado para impedir novas sessões para todos os serviços de legado executando em um computador específico ou para impedir novas sessões para um serviço específico de legado.</span><span class="sxs-lookup"><span data-stu-id="088e2-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="088e2-105">Para impedir novas sessões para serviços em um computador</span><span class="sxs-lookup"><span data-stu-id="088e2-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="088e2-106">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="088e2-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="088e2-107">Abra o Skype para painel de controle de negócios.</span><span class="sxs-lookup"><span data-stu-id="088e2-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="088e2-108">Na barra de navegação esquerda, clique em **Topologia** e em **Status**. </span><span class="sxs-lookup"><span data-stu-id="088e2-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="088e2-109">Na página **Status** , classificação ou pesquisa através da lista como necessário para localizar o computador que está executando os serviços para o qual você deseja impedir novas sessões e, em seguida, clique nele.</span><span class="sxs-lookup"><span data-stu-id="088e2-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="088e2-110">Clique em **ação**.</span><span class="sxs-lookup"><span data-stu-id="088e2-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="088e2-111">Clique em **impedir novas sessões para todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="088e2-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="088e2-112">Para impedir novas sessões para um serviço específico</span><span class="sxs-lookup"><span data-stu-id="088e2-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="088e2-113">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="088e2-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="088e2-114">Abra o Skype para painel de controle de negócios.</span><span class="sxs-lookup"><span data-stu-id="088e2-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="088e2-115">Na barra de navegação esquerda, clique em **Topologia** e em **Status**. </span><span class="sxs-lookup"><span data-stu-id="088e2-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="088e2-116">Na página **Status** , classificação ou pesquisa até a lista conforme necessário para localizar o computador que está executando o serviço que você deseja iniciar ou parar e, em seguida, clique nele.</span><span class="sxs-lookup"><span data-stu-id="088e2-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="088e2-117">Clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="088e2-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="088e2-118">Classifique a lista de serviços, se necessário e clique no serviço para o qual você deseja impedir novas sessões.</span><span class="sxs-lookup"><span data-stu-id="088e2-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="088e2-119">Clique em **ação**.</span><span class="sxs-lookup"><span data-stu-id="088e2-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="088e2-120">Clique em **impedir novas sessões para o serviço**.</span><span class="sxs-lookup"><span data-stu-id="088e2-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="088e2-121">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="088e2-121">Click **Close**.</span></span>
    

