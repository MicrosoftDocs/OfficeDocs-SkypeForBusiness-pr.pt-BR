---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: O esquema principal de alta disponibilidade para a maioria das funções de servidor em Skype para Business Server 2015 se baseia em redundância de servidor por meio do pool. Se um servidor que estiver executando uma determinada função do servidor falhar, os outros servidores no pool que executam a mesma função assumirão a carga desse servidor.
ms.openlocfilehash: 50cc5f371e4964555aae2a7f50ce3d1431f4f10c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874022"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="600e3-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="600e3-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="600e3-105">O esquema principal de alta disponibilidade para a maioria das funções de servidor em Skype para Business Server 2015 se baseia em redundância de servidor por meio do pool.</span><span class="sxs-lookup"><span data-stu-id="600e3-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="600e3-106">Se um servidor que estiver executando uma determinada função do servidor falhar, os outros servidores no pool que executam a mesma função assumirão a carga desse servidor.</span><span class="sxs-lookup"><span data-stu-id="600e3-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="600e3-107">Skype para Business Server 2015 requer pelo menos dois servidores Front-End para habilitar a alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="600e3-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="600e3-108">A ferramenta de planejamento usa os seguintes critérios para determinar se ele adicionará servidores adicionais para dar suporte à alta disponibilidade:</span><span class="sxs-lookup"><span data-stu-id="600e3-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="600e3-109">Se a implantação contiver dois ou mais servidores Front-End, a ferramenta de planejamento não adiciona um servidor adicional.</span><span class="sxs-lookup"><span data-stu-id="600e3-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="600e3-110">Se a implantação contiver um servidor de borda, um servidor adicional é adicionado.</span><span class="sxs-lookup"><span data-stu-id="600e3-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="600e3-111">Se a implantação contiver Chat persistente, a ferramenta de planejamento irá adicionar um servidor extra, mas não aumentar o número de pool.</span><span class="sxs-lookup"><span data-stu-id="600e3-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="600e3-112">Por exemplo, se a implantação já contiver quatro servidores, a ferramenta de planejamento irá sugerir adicionando um servidor adicional (para um total de cinco servidores) mas manterá um único pool.</span><span class="sxs-lookup"><span data-stu-id="600e3-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="600e3-113">A ferramenta de planejamento também adiciona um banco de dados do SQL de espelho para todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="600e3-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="600e3-114">Por exemplo, se houver um banco de dados do servidor SQL Front-End, a ferramenta de planejamento irá adicionar outro banco de dados como o banco de dados de espelho para que este e nomeie-o como o "banco de dados SQL de espelho de Front-End.</span><span class="sxs-lookup"><span data-stu-id="600e3-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="600e3-115">Para obter mais detalhes sobre como preparar seu ambiente para alta disponibilidade, consulte [Planejar a alta disponibilidade e recuperação de desastres em Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="600e3-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

