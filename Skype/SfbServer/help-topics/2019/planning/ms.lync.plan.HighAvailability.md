---
title: High Availability (Planning Tool)
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
description: O principal esquema de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server é baseado na redundância de servidor via pooling. Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor.
ms.openlocfilehash: 5c9895e325770f5c826b5c55213fcc1b569aa701
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819791"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="c19c0-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="c19c0-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="c19c0-105">O principal esquema de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server é baseado na redundância de servidor via pooling.</span><span class="sxs-lookup"><span data-stu-id="c19c0-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="c19c0-106">Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor.</span><span class="sxs-lookup"><span data-stu-id="c19c0-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="c19c0-107">O Skype for Business Server requer pelo menos dois Servidores front-end para habilitar a alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="c19c0-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="c19c0-108">A Ferramenta de Planejamento usa os seguintes critérios para determinar se adicionará servidores extras para dar suporte à alta disponibilidade:</span><span class="sxs-lookup"><span data-stu-id="c19c0-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="c19c0-109">Se a implantação contiver dois ou mais Servidores Front-End, a Ferramenta de Planejamento não adicionará um servidor adicional.</span><span class="sxs-lookup"><span data-stu-id="c19c0-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="c19c0-110">Se a implantação contiver Servidor de Borda, um servidor adicional será adicionado.</span><span class="sxs-lookup"><span data-stu-id="c19c0-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="c19c0-111">Se a implantação contiver Chat Persistente, a ferramenta de planejamento adicionará um servidor extra, mas não aumentará o número do pool.</span><span class="sxs-lookup"><span data-stu-id="c19c0-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="c19c0-112">Por exemplo, se a implantação já contiver quatro servidores, a Ferramenta de Planejamento sugerirá a adição de um servidor adicional (para um total de cinco servidores), mas manterá um único pool.</span><span class="sxs-lookup"><span data-stu-id="c19c0-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="c19c0-113">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c19c0-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c19c0-114">A mesma funcionalidade está disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="c19c0-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="c19c0-115">Para saber mais, confira [a atualização do Skype for Business para o Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="c19c0-115">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="c19c0-116">Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c19c0-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="c19c0-117">A Ferramenta de Planejamento também adiciona um banco de dados SQL espelho para todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="c19c0-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="c19c0-118">Por exemplo, se houver um banco de dados do SQL Server front-end, a Ferramenta de Planejamento adicionará o outro banco de dados como o banco de dados espelho para este e o chamará de "Banco de dados SQL espelho front-end."</span><span class="sxs-lookup"><span data-stu-id="c19c0-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="c19c0-119">Para obter mais detalhes sobre como preparar seu ambiente para alta disponibilidade, consulte Plano para alta disponibilidade e recuperação de desastres [no Skype for Business Server.](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="c19c0-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

