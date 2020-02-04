---
title: Evitar sessões de serviços
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf8fb96fef5a01f9b25ca954dd27d1bdfd1f7055
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a><span data-ttu-id="44f6c-102">Evitar sessões de serviços</span><span class="sxs-lookup"><span data-stu-id="44f6c-102">Prevent sessions for services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44f6c-103">_**Tópico da última modificação:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="44f6c-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="44f6c-104">Você pode usar o painel de controle do Microsoft Lync Server 2010 para impedir novas sessões para todos os serviços do Lync Server 2010 em execução em um computador específico ou para impedir novas sessões para um serviço específico do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="44f6c-104">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="44f6c-105">Para impedir novas sessões para todos os serviços do Lync Server em um computador</span><span class="sxs-lookup"><span data-stu-id="44f6c-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="44f6c-106">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="44f6c-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="44f6c-107">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44f6c-107">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="44f6c-108">Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **status**.</span><span class="sxs-lookup"><span data-stu-id="44f6c-108">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="44f6c-109">Na página **status** , classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando os serviços para os quais você deseja impedir novas sessões e, em seguida, clique nela.</span><span class="sxs-lookup"><span data-stu-id="44f6c-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="44f6c-110">Clique em **ação**.</span><span class="sxs-lookup"><span data-stu-id="44f6c-110">Click **Action**.</span></span>

6.  <span data-ttu-id="44f6c-111">Clique em **impedir novas sessões para todos os serviços**.</span><span class="sxs-lookup"><span data-stu-id="44f6c-111">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="44f6c-112">Para impedir novas sessões para um serviço específico</span><span class="sxs-lookup"><span data-stu-id="44f6c-112">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="44f6c-113">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="44f6c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="44f6c-114">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44f6c-114">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="44f6c-115">Na barra de navegação à esquerda, clique em **topologia** e, em seguida, clique em **status**.</span><span class="sxs-lookup"><span data-stu-id="44f6c-115">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="44f6c-116">Na página **status** , classifique ou pesquise a lista, conforme necessário, para localizar o computador que está executando o serviço que você deseja iniciar ou parar e, em seguida, clique nele.</span><span class="sxs-lookup"><span data-stu-id="44f6c-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="44f6c-117">Clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="44f6c-117">Click **Properties**.</span></span>

6.  <span data-ttu-id="44f6c-118">Classifique a lista de serviços, se necessário, e clique no serviço para o qual você deseja impedir novas sessões.</span><span class="sxs-lookup"><span data-stu-id="44f6c-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="44f6c-119">Clique em **ação**.</span><span class="sxs-lookup"><span data-stu-id="44f6c-119">Click **Action**.</span></span>

8.  <span data-ttu-id="44f6c-120">Clique em **impedir novas sessões para o serviço**.</span><span class="sxs-lookup"><span data-stu-id="44f6c-120">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="44f6c-121">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="44f6c-121">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

