---
title: Evitar sessões de serviços
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f85595acd38e69af9fb8108cab44f4839904799a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a><span data-ttu-id="235ba-102">Evitar sessões de serviços</span><span class="sxs-lookup"><span data-stu-id="235ba-102">Prevent sessions for services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="235ba-103">_**Última modificação do tópico:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="235ba-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="235ba-104">Você pode usar o painel de controle do Microsoft Lync Server 2010 para impedir novas sessões para todos os serviços do Lync Server 2010 em execução em um computador específico ou para impedir novas sessões para um serviço do Lync Server 2010 específico.</span><span class="sxs-lookup"><span data-stu-id="235ba-104">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="235ba-105">Para impedir novas sessões para todos os serviços do Lync Server em um computador</span><span class="sxs-lookup"><span data-stu-id="235ba-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="235ba-106">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="235ba-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="235ba-107">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="235ba-107">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="235ba-108">Na barra de navegação esquerda, clique em **Topologia** e em **Status**.</span><span class="sxs-lookup"><span data-stu-id="235ba-108">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="235ba-109">Na página **Status**, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando os serviços para os quais você deseja impedir novas sessões e clique nele.</span><span class="sxs-lookup"><span data-stu-id="235ba-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="235ba-110">Clique em **Ação**.</span><span class="sxs-lookup"><span data-stu-id="235ba-110">Click **Action**.</span></span>

6.  <span data-ttu-id="235ba-111">Clique em **Impedir novas sessões para todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="235ba-111">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="235ba-112">Para Impedir novas sessões para um serviço específico</span><span class="sxs-lookup"><span data-stu-id="235ba-112">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="235ba-113">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="235ba-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="235ba-114">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="235ba-114">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="235ba-115">Na barra de navegação esquerda, clique em **Topologia** e em **Status**.</span><span class="sxs-lookup"><span data-stu-id="235ba-115">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="235ba-116">Na página **Status**, classifique ou pesquise na lista conforme o necessário para encontrar o computador que está executando o serviço que você deseja iniciar ou interromper e clique nele.</span><span class="sxs-lookup"><span data-stu-id="235ba-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="235ba-117">Clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="235ba-117">Click **Properties**.</span></span>

6.  <span data-ttu-id="235ba-118">Classifique a lista de serviços, se necessário e clique no serviço para o qual você deseja impedir novas sessões.</span><span class="sxs-lookup"><span data-stu-id="235ba-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="235ba-119">Clique em **Ações**.</span><span class="sxs-lookup"><span data-stu-id="235ba-119">Click **Action**.</span></span>

8.  <span data-ttu-id="235ba-120">Clique em **Impedir novas sessões para o serviço**.</span><span class="sxs-lookup"><span data-stu-id="235ba-120">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="235ba-121">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="235ba-121">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

