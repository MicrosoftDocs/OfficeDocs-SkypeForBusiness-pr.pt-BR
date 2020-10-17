---
title: Processo de migração
description: Processo de migração.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f363bd79a3d3be709d731d2ca4bffb4f83fe89ea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569557"
---
# <a name="migration-process"></a><span data-ttu-id="79720-103">Processo de migração</span><span class="sxs-lookup"><span data-stu-id="79720-103">Migration process</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79720-104">_**Última modificação do tópico:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="79720-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="79720-105">O procedimento de migração recomendado e com suporte para o Lync Server 2013 é migração lado a lado.</span><span class="sxs-lookup"><span data-stu-id="79720-105">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="79720-106">Este tópico descreve porquê você deve usar a migração lado a lado e também inclui informações sobre testes de coexistência.</span><span class="sxs-lookup"><span data-stu-id="79720-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="79720-107">Migração lado a lado</span><span class="sxs-lookup"><span data-stu-id="79720-107">Side-By-Side Migration</span></span>

<span data-ttu-id="79720-108">Em praticamente cada migração, você deve usar o caminho de migração lado a lado.</span><span class="sxs-lookup"><span data-stu-id="79720-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="79720-109">Em uma migração lado a lado, você implanta um novo servidor com o Lync Server 2013 juntamente com um servidor correspondente que está executando o Lync Server 2010 e transfere operações para o novo servidor.</span><span class="sxs-lookup"><span data-stu-id="79720-109">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="79720-110">Se for necessário reverter para o Lync Server 2010, você terá que alterar as operações de volta para os servidores originais.</span><span class="sxs-lookup"><span data-stu-id="79720-110">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="79720-111">Lembre-se de que nessa situação, quaisquer novas reuniões agendadas com os clientes atualizados não funcionarão e também seria necessário fazer o downgrade dos clientes.</span><span class="sxs-lookup"><span data-stu-id="79720-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="79720-112">Teste de coexistência</span><span class="sxs-lookup"><span data-stu-id="79720-112">Coexistence Testing</span></span>

<span data-ttu-id="79720-113">Após a implantação do Lync Server 2013 em paralelo com o Lync Server 2010, a implantação representa um estado de teste de coexistência do Lync Server 2013 e do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="79720-113">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="79720-114">Durante este estado, é importante testar e garantir que os serviços estejam iniciados, que cada site possa ser administrado e que os clientes possam se comunicar com usuários atuais e herdados.</span><span class="sxs-lookup"><span data-stu-id="79720-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="79720-115">Antes da migração de todos os usuários, é muito importante entender o estado de cada implantação e garantir que cada uma delas esteja funcional e funcionando adequadamente.</span><span class="sxs-lookup"><span data-stu-id="79720-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="79720-116">Normalmente, a fase de teste de coexistência existe durante o teste piloto do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79720-116">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="79720-117">Os usuários herdados são movidos para o Lync Server 2013 por um período de tempo para garantir que a compatibilidade e os recursos e funções do aplicativo estejam funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="79720-117">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="79720-118">Após o teste piloto, os usuários e os aplicativos são movidos para a versão de produção do Lync Server 2013, e os pools e aplicativos herdados do Lync Server 2010 são removidos.</span><span class="sxs-lookup"><span data-stu-id="79720-118">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

