---
title: Implantar o servidor de borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 'Resumo: saiba como implantar um servidor de borda ou um pool de bordas no ambiente do Skype for Business Server.'
ms.openlocfilehash: bcb6f7fdd7b322411e793fe3466418db1dd00894
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306948"
---
# <a name="deploy-edge-server-in-skype-for-business-server"></a><span data-ttu-id="e8352-103">Implantar o servidor de borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e8352-103">Deploy Edge Server in Skype for Business Server</span></span>
 
<span data-ttu-id="e8352-104">**Resumo:** Saiba como implantar um servidor de borda ou um pool de bordas no ambiente do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e8352-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="e8352-105">Por que implantar um servidor de borda ou um pool de bordas no ambiente do Skype for Business Server?</span><span class="sxs-lookup"><span data-stu-id="e8352-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server environment?</span></span> <span data-ttu-id="e8352-106">Isto é necessário se você precisa que os usuários externos que não estão conectados à rede interna de suas organizações sejam capazes de interagir com usuários internos.</span><span class="sxs-lookup"><span data-stu-id="e8352-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="e8352-107">Esses usuários externos podem ser usuários remotos anônimos e autenticados, parceiros federados ou outros clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="e8352-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server"></a><span data-ttu-id="e8352-108">Lista de verificação de implantação do Edge para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e8352-108">Deployment checklist for the Edge, for Skype for Business Server</span></span>

<span data-ttu-id="e8352-109">Conforme observado acima, muitas coisas entram em uma implantação do servidor de borda para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e8352-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server.</span></span> <span data-ttu-id="e8352-110">Esta lista de verificação fornece uma visão geral das tarefas que você precisará fazer e links para etapas mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="e8352-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="e8352-111">Esperamos que você tenha começado na seção [planejar implantações de servidor de borda no Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) .</span><span class="sxs-lookup"><span data-stu-id="e8352-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="e8352-112">Caso contrário, muitos itens que mencionamos estão detalhados lá.</span><span class="sxs-lookup"><span data-stu-id="e8352-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="e8352-113">A seção de implantação contém apenas procedimentos, portanto, se você quiser saber o raciocínio para chegar até estas etapas, o planejamento é o ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="e8352-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="e8352-114">Esta documentação também pressupõe que você também realizou a implantação básica do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e8352-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server.</span></span> <span data-ttu-id="e8352-115">Você pode estar fazendo essa implantação lado a lado com a borda, mas é necessário seguir essas etapas primeiro e, em seguida, fazer as alterações de topologia para a borda que são documentadas aqui.</span><span class="sxs-lookup"><span data-stu-id="e8352-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="e8352-116">Estas são etapas de alto nível que deverão ser seguidas e os locais onde você as encontrará:</span><span class="sxs-lookup"><span data-stu-id="e8352-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="e8352-117">Requisitos do sistema do servidor de borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e8352-117">Edge Server system requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="e8352-118">Requisitos ambientais do servidor de borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e8352-118">Edge Server environmental requirements in Skype for Business Server</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="e8352-119">Criar sua topologia de borda para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e8352-119">Create your Edge topology for Skype for Business Server</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="e8352-120">Implantar servidores de borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e8352-120">Deploy Edge Servers in Skype for Business Server</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="e8352-121">Validar a implantação do seu Edge no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e8352-121">Validate your Edge deployment in Skype for Business Server</span></span>](validate-edge-deployment.md)
    

