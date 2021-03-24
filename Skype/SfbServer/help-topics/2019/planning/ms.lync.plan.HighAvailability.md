---
title: Alta disponibilidade (Ferramenta de Planejamento)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: O principal esquema de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server baseia-se na redundância do servidor por meio do pool. Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor.
ms.openlocfilehash: 36b2d9fad34e16daf11fb7539f73c815264a55a6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093309"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="0245a-104">Alta disponibilidade (Ferramenta de Planejamento)</span><span class="sxs-lookup"><span data-stu-id="0245a-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="0245a-105">O principal esquema de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server baseia-se na redundância do servidor por meio do pool.</span><span class="sxs-lookup"><span data-stu-id="0245a-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="0245a-106">Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor.</span><span class="sxs-lookup"><span data-stu-id="0245a-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="0245a-107">O Skype for Business Server requer pelo menos dois Servidores Front-End para habilitar a alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="0245a-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="0245a-108">A Ferramenta de Planejamento usa os critérios a seguir para determinar se adicionará servidores extras para dar suporte à alta disponibilidade:</span><span class="sxs-lookup"><span data-stu-id="0245a-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="0245a-109">Se a implantação contiver dois ou mais Servidores Front-End, a Ferramenta de Planejamento não adicionará um servidor extra.</span><span class="sxs-lookup"><span data-stu-id="0245a-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="0245a-110">Se a implantação contiver o Servidor de Borda, um servidor adicional será adicionado.</span><span class="sxs-lookup"><span data-stu-id="0245a-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="0245a-111">Se a implantação contiver Chat Persistente, a ferramenta de planejamento adicionará um servidor extra, mas não aumentará o número do pool.</span><span class="sxs-lookup"><span data-stu-id="0245a-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="0245a-112">Por exemplo, se a implantação já contiver quatro servidores, a Ferramenta de Planejamento sugerirá adicionar um servidor adicional (para um total de cinco servidores), mas manterá um único pool.</span><span class="sxs-lookup"><span data-stu-id="0245a-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="0245a-113">O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0245a-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0245a-114">A mesma funcionalidade está disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="0245a-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="0245a-115">Para obter mais informações, consulte [Atualização do Skype for Business para o Microsoft Teams.](/MicrosoftTeams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="0245a-115">For more information, see [Skype for Business to Microsoft Teams upgrade](/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="0245a-116">Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0245a-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="0245a-117">A Ferramenta de Planejamento também adiciona um banco de dados SQL espelho para todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="0245a-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="0245a-118">Por exemplo, se houver um banco de dados de SQL Server front-end, a Ferramenta de Planejamento adicionará o outro banco de dados como o banco de dados espelho para este e o nomeará como o "banco de dados de espelho de front-end SQL.</span><span class="sxs-lookup"><span data-stu-id="0245a-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="0245a-119">Para obter mais detalhes sobre como preparar seu ambiente para alta disponibilidade, consulte [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="0245a-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
