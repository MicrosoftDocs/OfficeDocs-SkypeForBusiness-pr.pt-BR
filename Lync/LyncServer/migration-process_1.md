---
title: Processo de migração
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2da65ead79d33ff03a66f4ec5ef54fa4e2167890
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="c9e7c-102">Processo de migração</span><span class="sxs-lookup"><span data-stu-id="c9e7c-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9e7c-103">_**Última modificação do tópico:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="c9e7c-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="c9e7c-104">O procedimento de migração recomendado e com suporte para o Lync Server 2013 é o procedimento de migração lado a lado.</span><span class="sxs-lookup"><span data-stu-id="c9e7c-104">The recommended and supported migration procedure for Lync Server 2013 is the side-by-side migration procedure.</span></span> <span data-ttu-id="c9e7c-105">Este tópico descreve porque você deve usar a migração lado a lado e também inclui informações sobre coexistência.</span><span class="sxs-lookup"><span data-stu-id="c9e7c-105">This topic describes why you should use side-by-side migration and also includes information about coexistence.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="c9e7c-106">Migração lado a lado</span><span class="sxs-lookup"><span data-stu-id="c9e7c-106">Side-by-Side Migration</span></span>

<span data-ttu-id="c9e7c-107">Em praticamente cada migração, você deve usar o caminho de migração lado a lado.</span><span class="sxs-lookup"><span data-stu-id="c9e7c-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="c9e7c-108">Em uma migração lado a lado, você implanta um novo servidor com o Lync Server 2013 juntamente com um servidor correspondente executando o Office Communications Server 2007 R2 e transfere operações para o novo servidor.</span><span class="sxs-lookup"><span data-stu-id="c9e7c-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Office Communications Server 2007 R2, and then you transfer operations to the new server.</span></span> <span data-ttu-id="c9e7c-109">Se for necessário reverter para o Office Communications Server 2007 R2, você terá que alterar as operações de volta para os servidores originais.</span><span class="sxs-lookup"><span data-stu-id="c9e7c-109">If it becomes necessary to roll back to Office Communications Server 2007 R2, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="c9e7c-110">Lembre-se de que nessa situação, quaisquer novas reuniões agendadas com os clientes atualizados não funcionarão e também seria necessário fazer o downgrade dos clientes.</span><span class="sxs-lookup"><span data-stu-id="c9e7c-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="c9e7c-111">Teste de coexistência</span><span class="sxs-lookup"><span data-stu-id="c9e7c-111">Coexistence Testing</span></span>

<span data-ttu-id="c9e7c-112">Depois de implantar o Lync Server 2013 em paralelo com o Office Communications Server 2007 R2, a topologia representa um estado de teste de coexistência do Lync Server 2013 e do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c9e7c-112">After you have deployed Lync Server 2013 in parallel with Office Communications Server 2007 R2, the topology represents a coexistence testing state of Lync Server 2013 and Office Communications Server 2007 R2.</span></span> <span data-ttu-id="c9e7c-113">Neste estado, é importante testar e verificar se os serviços foram inicializados, se cada site pode ser administrador e se os clientes pode se comunicar com usuários atuais e herdados.</span><span class="sxs-lookup"><span data-stu-id="c9e7c-113">While in this state, it is important to test and ensure services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="c9e7c-114">Antes da migração de todos os usuários, é importante entender o estado de cada implantação e verificar se cada implantação está pronta e funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="c9e7c-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="c9e7c-115">Normalmente, a fase de teste de coexistência existe durante o teste piloto do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9e7c-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="c9e7c-116">Os usuários herdados são movidos para o Lync Server 2013 por um período de tempo para garantir que a compatibilidade e os recursos e funções do aplicativo estejam funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="c9e7c-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="c9e7c-117">Após o teste piloto, os usuários e os aplicativos são movidos para a versão de produção do Lync Server 2013, e os pools herdados e os aplicativos do Office Communications Server 2007 R2 são removidos.</span><span class="sxs-lookup"><span data-stu-id="c9e7c-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Office Communications Server 2007 R2 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

