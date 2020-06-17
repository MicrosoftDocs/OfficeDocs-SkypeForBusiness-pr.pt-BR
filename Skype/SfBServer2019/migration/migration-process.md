---
title: Processo de migração
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
description: O procedimento de migração recomendado e com suporte para o Skype for Business Server 2019 é migração lado a lado. Este tópico descreve porquê você deve usar a migração lado a lado e também inclui informações sobre testes de coexistência.
ms.openlocfilehash: 2343e3d6dd7eadbcfbf2b900d51594253e22f933
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752633"
---
# <a name="migration-process"></a><span data-ttu-id="f62b8-104">Processo de migração</span><span class="sxs-lookup"><span data-stu-id="f62b8-104">Migration process</span></span>

<span data-ttu-id="f62b8-105">O procedimento de migração recomendado e com suporte para o Skype for Business Server 2019 é migração lado a lado.</span><span class="sxs-lookup"><span data-stu-id="f62b8-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="f62b8-106">Este tópico descreve porquê você deve usar a migração lado a lado e também inclui informações sobre testes de coexistência.</span><span class="sxs-lookup"><span data-stu-id="f62b8-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="f62b8-107">Migração lado a lado</span><span class="sxs-lookup"><span data-stu-id="f62b8-107">Side-By-Side Migration</span></span>

<span data-ttu-id="f62b8-108">Em praticamente cada migração, você deve usar o caminho de migração lado a lado.</span><span class="sxs-lookup"><span data-stu-id="f62b8-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="f62b8-109">Em uma migração lado a lado, você implanta um novo servidor com o Skype for Business Server 2019 junto com um servidor correspondente que está executando uma versão anterior e transfere operações para o novo servidor.</span><span class="sxs-lookup"><span data-stu-id="f62b8-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="f62b8-110">Se for necessário reverter para a versão anterior, você terá que alterar as operações de volta para os servidores originais.</span><span class="sxs-lookup"><span data-stu-id="f62b8-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="f62b8-111">Lembre-se de que nessa situação, quaisquer novas reuniões agendadas com os clientes atualizados não funcionarão e também seria necessário fazer o downgrade dos clientes.</span><span class="sxs-lookup"><span data-stu-id="f62b8-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="f62b8-112">Teste de coexistência</span><span class="sxs-lookup"><span data-stu-id="f62b8-112">Coexistence Testing</span></span>

<span data-ttu-id="f62b8-113">Depois de ter implantado o Skype for Business Server 2019 em paralelo com a versão anterior, a implantação representa um estado de teste de coexistência do Skype for Business Server 2019 e a versão anterior.</span><span class="sxs-lookup"><span data-stu-id="f62b8-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="f62b8-114">Durante este estado, é importante testar e garantir que os serviços estejam iniciados, que cada site possa ser administrado e que os clientes possam se comunicar com usuários atuais e herdados.</span><span class="sxs-lookup"><span data-stu-id="f62b8-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="f62b8-115">Antes da migração de todos os usuários, é muito importante entender o estado de cada implantação e garantir que cada uma delas esteja funcional e funcionando adequadamente.</span><span class="sxs-lookup"><span data-stu-id="f62b8-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="f62b8-116">Normalmente, a fase de teste de coexistência existe durante o teste piloto do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f62b8-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="f62b8-117">Os usuários herdados são movidos para o Skype for Business Server 2019 por um período de tempo para garantir que a compatibilidade e os recursos e funções do aplicativo estejam funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="f62b8-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="f62b8-118">Após o teste piloto, os usuários e os aplicativos são movidos para a versão de produção do Skype for Business Server 2019, e os pools herdados e os aplicativos da versão anterior são removidos.</span><span class="sxs-lookup"><span data-stu-id="f62b8-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
