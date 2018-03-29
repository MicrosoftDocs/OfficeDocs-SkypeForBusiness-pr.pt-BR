---
title: Implantar o Servidor de Borda no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 2fdf418e-e571-4f2b-bb83-91fdcf738edb
description: 'Resumo: Saiba como implantar um servidor de borda ou um pool de borda em sua Skype para ambiente de negócios Server 2015.'
ms.openlocfilehash: 38eb0344488512a47f4dc21223d881c15f618e22
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-edge-server-in-skype-for-business-server-2015"></a><span data-ttu-id="20a1b-103">Implantar o Servidor de Borda no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="20a1b-103">Deploy Edge Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="20a1b-104">**Resumo:** Saiba como implantar um servidor de borda ou um pool de borda em sua Skype para ambiente de negócios Server 2015.</span><span class="sxs-lookup"><span data-stu-id="20a1b-104">**Summary:** Learn how to deploy an Edge Server or an Edge pool into your Skype for Business Server 2015 environment.</span></span>
  
<span data-ttu-id="20a1b-105">Por que implantar um servidor de borda ou um pool de borda em sua Skype para ambiente de negócios Server 2015?</span><span class="sxs-lookup"><span data-stu-id="20a1b-105">Why deploy an Edge Server or an Edge pool into your Skype for Business Server 2015 environment?</span></span> <span data-ttu-id="20a1b-106">Isto é necessário se você precisa que os usuários externos que não estão conectados à rede interna de suas organizações sejam capazes de interagir com usuários internos.</span><span class="sxs-lookup"><span data-stu-id="20a1b-106">It's necessary if you need external users who aren't logged into your organizations internal network to be able to interact with internal users.</span></span> <span data-ttu-id="20a1b-107">Esses usuários externos podem ser usuários remotos anônimos e autenticados, parceiros federados ou outros clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="20a1b-107">These external users could be authenticated and anonymous remote users, federated partners, or other mobile clients.</span></span>
  
## <a name="deployment-checklist-for-the-edge-for-skype-for-business-server-2015"></a><span data-ttu-id="20a1b-108">Lista de verificação de implantação para a borda, para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="20a1b-108">Deployment checklist for the Edge, for Skype for Business Server 2015</span></span>

<span data-ttu-id="20a1b-109">Conforme observado anteriormente, muito entra em uma implantação de servidor de borda para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="20a1b-109">As noted above,, A lot goes into an Edge Server deployment for Skype for Business Server 2015.</span></span> <span data-ttu-id="20a1b-110">Esta lista de verificação fornece uma visão geral dos links e as tarefas que você precisará fazer às etapas mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="20a1b-110">This checklist gives you an overview of the tasks you'll need to do, and links to more detailed steps.</span></span>
  
<span data-ttu-id="20a1b-111">Esperamos que você tenha começado na seção [plano para implantações de servidor de borda em Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) .</span><span class="sxs-lookup"><span data-stu-id="20a1b-111">We hope you've begun in the [Plan for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) section.</span></span> <span data-ttu-id="20a1b-112">Caso contrário, muitos itens que mencionamos estão detalhados lá.</span><span class="sxs-lookup"><span data-stu-id="20a1b-112">If not, many of the things we refer to are detailed there.</span></span> <span data-ttu-id="20a1b-113">A seção de implantação contém apenas procedimentos, portanto, se você quiser saber o raciocínio para chegar até estas etapas, o planejamento é o ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="20a1b-113">The deployment section contains only procedures, so if you want to know the reasoning behind these steps, planning is the place to begin.</span></span>
  
<span data-ttu-id="20a1b-114">Esta documentação também partem do princípio que também tiver concluído a implantação básica do Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="20a1b-114">This documentation also presumes you've also done the Basic Deployment of Skype for Business Server 2015.</span></span> <span data-ttu-id="20a1b-115">Talvez você esteja fazendo essa implantação lado a lado com a borda, mas é necessário seguir essas etapas primeiro e, em seguida, você poderá fazer as alterações de topologia para a borda que estão documentadas aqui.</span><span class="sxs-lookup"><span data-stu-id="20a1b-115">You may be doing that deployment side-by-side with the Edge, but you do need to follow those steps first, and then you'll be able to make the topology changes for the Edge that are documented here.</span></span>
  
<span data-ttu-id="20a1b-116">Estas são etapas de alto nível que deverão ser seguidas e os locais onde você as encontrará:</span><span class="sxs-lookup"><span data-stu-id="20a1b-116">These are the high-level steps you'll need to follow, and the places you'll find those steps:</span></span>
  
- [<span data-ttu-id="20a1b-117">Requisitos de sistema do servidor de borda no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="20a1b-117">Edge Server system requirements in Skype for Business Server 2015</span></span>](../../plan-your-deployment/edge-server-deployments/system-requirements.md)
    
- [<span data-ttu-id="20a1b-118">Requisitos de ambiente de servidor de borda no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="20a1b-118">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md)
    
- [<span data-ttu-id="20a1b-119">Criar a topologia de borda para Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="20a1b-119">Create your Edge topology for Skype for Business Server 2015</span></span>](create-your-edge-topology.md)
    
- [<span data-ttu-id="20a1b-120">Implante servidores de borda em Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="20a1b-120">Deploy Edge Servers in Skype for Business Server 2015</span></span>](deploy-edge-servers.md)
    
- [<span data-ttu-id="20a1b-121">Validar sua implantação de borda no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="20a1b-121">Validate your Edge deployment in Skype for Business Server 2015</span></span>](validate-edge-deployment.md)
    

