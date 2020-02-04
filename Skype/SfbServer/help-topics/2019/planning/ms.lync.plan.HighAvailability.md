---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: O principal esquema de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server baseia-se na redundância do servidor via pool. Se um servidor que estiver executando uma determinada função do servidor falhar, os outros servidores no pool que executam a mesma função assumirão a carga desse servidor.
ms.openlocfilehash: dc438d5b46f54f7526b0d1327a3263d9e334b68d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689816"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="4399e-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="4399e-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="4399e-105">O principal esquema de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server baseia-se na redundância do servidor via pool.</span><span class="sxs-lookup"><span data-stu-id="4399e-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="4399e-106">Se um servidor que estiver executando uma determinada função do servidor falhar, os outros servidores no pool que executam a mesma função assumirão a carga desse servidor.</span><span class="sxs-lookup"><span data-stu-id="4399e-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="4399e-107">O Skype for Business Server exige pelo menos dois servidores front end para permitir alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="4399e-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="4399e-108">A ferramenta de planejamento usará os seguintes critérios para determinar se ele adicionará servidores extras para dar suporte à alta disponibilidade:</span><span class="sxs-lookup"><span data-stu-id="4399e-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="4399e-109">Se a implantação contiver dois ou mais servidores front-end, a ferramenta de planejamento não adicionará um servidor extra.</span><span class="sxs-lookup"><span data-stu-id="4399e-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="4399e-110">Se a implantação contiver o servidor de borda, um servidor adicional será adicionado.</span><span class="sxs-lookup"><span data-stu-id="4399e-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="4399e-111">Se a implantação contiver chats persistentes, a ferramenta de planejamento adicionará um servidor extra, mas não aumentará o número do pool.</span><span class="sxs-lookup"><span data-stu-id="4399e-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="4399e-112">Por exemplo, se a implantação já contiver quatro servidores, a ferramenta de planejamento irá sugerir a adição de um servidor adicional (para um total de cinco servidores), mas manterá um único pool.</span><span class="sxs-lookup"><span data-stu-id="4399e-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="4399e-113">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4399e-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4399e-114">A mesma funcionalidade está disponível no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4399e-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="4399e-115">Para obter mais informações, consulte [atualização do Skype for Business para o Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="4399e-115">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="4399e-116">Se você precisar usar chats persistentes, suas opções serão migrar usuários que exigem essa funcionalidade para o Microsoft Teams ou continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4399e-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="4399e-117">A ferramenta de planejamento também adiciona um banco de dados espelho do SQL a todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="4399e-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="4399e-118">Por exemplo, se houver um banco de dados de front-end do SQL Server, a ferramenta de planejamento adicionará o outro banco de dados como o banco de dados espelho para este e o nomeará como o banco de dados do SQL espelho do front-end.</span><span class="sxs-lookup"><span data-stu-id="4399e-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="4399e-119">Para obter mais detalhes sobre como preparar seu ambiente para alta disponibilidade, consulte [planejar a alta disponibilidade e a recuperação de desastres no Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="4399e-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

