---
title: Processo de migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f48d486332bf03204d25aaadfc2ea351bcf581a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="60497-102">Processo de migração</span><span class="sxs-lookup"><span data-stu-id="60497-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60497-103">_**Tópico da última modificação:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="60497-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="60497-104">O procedimento de migração recomendado e com suporte para o Lync Server 2013 é migração lado a lado.</span><span class="sxs-lookup"><span data-stu-id="60497-104">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="60497-105">Este tópico descreve porque você deve usar a migração lado a lado e também inclui informações sobre testes de coexistência.</span><span class="sxs-lookup"><span data-stu-id="60497-105">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="60497-106">Migração lado a lado</span><span class="sxs-lookup"><span data-stu-id="60497-106">Side-By-Side Migration</span></span>

<span data-ttu-id="60497-107">Em quase todas as migrações, você deve usar o caminho de migração lado a lado.</span><span class="sxs-lookup"><span data-stu-id="60497-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="60497-108">Em uma migração lado a lado, implante um novo servidor com o Lync Server 2013 juntamente com um servidor correspondente executando o Lync Server 2010 e transfira operações para o novo servidor.</span><span class="sxs-lookup"><span data-stu-id="60497-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="60497-109">Se for necessário reverter para o Lync Server 2010, você só terá que mudar as operações de volta para os servidores originais.</span><span class="sxs-lookup"><span data-stu-id="60497-109">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="60497-110">Lembre-se de que, nesta situação, todas as novas reuniões agendadas com clientes atualizados não funcionarão, e os clientes também precisariam ser rebaixados.</span><span class="sxs-lookup"><span data-stu-id="60497-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="60497-111">Teste de coexistência</span><span class="sxs-lookup"><span data-stu-id="60497-111">Coexistence Testing</span></span>

<span data-ttu-id="60497-112">Depois de implantar o Lync Server 2013 em paralelo com o Lync Server 2010, a implantação representa um estado de teste de coexistência do Lync Server 2013 e do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="60497-112">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="60497-113">Nesse estado, é importante testar e garantir que os serviços sejam iniciados, que cada site pode ser administrado, e os clientes podem se comunicar com os usuários atuais e herdados.</span><span class="sxs-lookup"><span data-stu-id="60497-113">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="60497-114">Antes da migração de todos os usuários, é muito importante que você compreenda o estado de cada implantação e certifique-se de que cada implantação está funcional e funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="60497-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="60497-115">Geralmente, a fase de teste de coexistência existe durante o teste piloto do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="60497-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="60497-116">Os usuários herdados são movidos para o Lync Server 2013 por um período de tempo para garantir que a compatibilidade e os recursos e funções do aplicativo estejam funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="60497-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="60497-117">Após o teste piloto, os usuários e os aplicativos são movidos para a versão de produção do Lync Server 2013, e os pools herdados e os aplicativos do Lync Server 2010 são desativados.</span><span class="sxs-lookup"><span data-stu-id="60497-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

