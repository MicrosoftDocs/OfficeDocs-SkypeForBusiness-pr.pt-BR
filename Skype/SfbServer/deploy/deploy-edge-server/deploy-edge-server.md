---
title: Implantar o Servidor de Borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 'Resumo: saiba como implantar um Servidor de Borda ou um pool de Borda em seu ambiente do Skype for Business Server.'
ms.openlocfilehash: edd2ff501320c4252b8032d1528ede7b83b8fcd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804381"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="c8971-103">Implantar o Servidor de Borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8971-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="c8971-104">**Resumo:** Saiba como implantar um Servidor de Borda ou um pool de Borda em seu ambiente do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c8971-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="c8971-105">Por que implantar um Servidor de Borda ou um pool de Borda em seu ambiente do Skype for Business Server?</span><span class="sxs-lookup"><span data-stu-id="c8971-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="c8971-106">É necessário que usuários externos que não estão conectados à rede interna da sua organização sejam capazes de interagir com usuários internos.</span><span class="sxs-lookup"><span data-stu-id="c8971-106">It's necessary if you need external users who aren't logged into your organization's internal network to be able to interact with internal users.</span></span> <span data-ttu-id="c8971-107">Esses usuários externos podem ser usuários remotos autenticados e anônimos, parceiros federados ou outros clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="c8971-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="c8971-108">Lista de verificação de implantação para o Edge, para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8971-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="c8971-109">Conforme mencionado acima, muito entra em uma implantação do Servidor de Borda para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c8971-109">As noted above, a lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="c8971-110">Esta lista de verificação fornece uma visão geral das tarefas que você precisará executar e links para etapas mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="c8971-110">This checklist gives you an overview of the tasks you'll need to perform, and links to more detailed steps.</span></span>
  
<span data-ttu-id="c8971-111">Esperamos que você tenha começado na seção Planejar implantações do Servidor de Borda [no Skype for Business Server.](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)</span><span class="sxs-lookup"><span data-stu-id="c8971-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="c8971-112">Caso não seja, muitos dos aspectos a que nos referimos estão detalhados lá.</span><span class="sxs-lookup"><span data-stu-id="c8971-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="c8971-113">A seção de implantação contém apenas procedimentos, portanto, se você quiser saber o raciocínio por trás dessas etapas, o planejamento é o local para começar.</span><span class="sxs-lookup"><span data-stu-id="c8971-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="c8971-114">Esta documentação também presume que você já concluiu a Implantação Básica do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c8971-114">This documentation also presumes you've already completed the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="c8971-115">Você pode estar fazendo essa implantação lado a lado com a Borda, mas precisa seguir essas etapas primeiro e, em seguida, poderá fazer as alterações de topologia para a Borda documentadas aqui.</span><span class="sxs-lookup"><span data-stu-id="c8971-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="c8971-116">Estas são as etapas de alto nível que você precisará seguir e os locais onde você encontrará essas etapas:</span><span class="sxs-lookup"><span data-stu-id="c8971-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="c8971-117">Requisitos de sistema do Servidor de Borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8971-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="c8971-118">Requisitos ambientais do Servidor de Borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8971-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="c8971-119">Criar sua topologia de borda para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8971-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="c8971-120">Implantar Servidores de Borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8971-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="c8971-121">Validar sua implantação de Borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c8971-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

