---
title: Adicionar Máquina de Front End
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: Especifique o FQDN (nome de domínio totalmente qualificado) de cada computador que você deseja adicionar como Servidor Front-End a esse pool. Após adicionar um computador à lista, você poderá atualizar o FQDN do computador ou removê-lo do pool a qualquer momento antes da publicação da topologia. Depois da publicação da topologia, a alteração do FQDN exigirá a exclusão do servidor do Construtor de Topologia e a adição de um novo servidor ao pool com o novo FQDN. Para obter detalhes sobre a adição de um pool de Front-Ends à topologia, consulte Define and Configure a Front End Pool, na documentação de Implantação.
ms.openlocfilehash: f962c41de50bad710edb80422911cb0c3f59943e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118680"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="0cc31-106">Adicionar Máquina de Front-end</span><span class="sxs-lookup"><span data-stu-id="0cc31-106">Add Front End Machine</span></span>

<span data-ttu-id="0cc31-107">Especifique o FQDN (nome de domínio totalmente qualificado) de cada computador que você deseja adicionar como Servidor Front-End a esse pool.</span><span class="sxs-lookup"><span data-stu-id="0cc31-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="0cc31-108">Após adicionar um computador à lista, você poderá atualizar o FQDN do computador ou removê-lo do pool a qualquer momento antes da publicação da topologia.</span><span class="sxs-lookup"><span data-stu-id="0cc31-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="0cc31-109">Depois da publicação da topologia, a alteração do FQDN exigirá a exclusão do servidor do Construtor de Topologia e a adição de um novo servidor ao pool com o novo FQDN.</span><span class="sxs-lookup"><span data-stu-id="0cc31-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="0cc31-110">Para obter detalhes sobre a adição de um pool de Front-Ends à topologia, consulte [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server), na documentação de Implantação.</span><span class="sxs-lookup"><span data-stu-id="0cc31-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0cc31-111">Observe que o Construtor de Topologias indica que você pode ter até 20 Servidores Front-End em um pool.</span><span class="sxs-lookup"><span data-stu-id="0cc31-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="0cc31-112">O número máximo de servidores com suporte é 12.</span><span class="sxs-lookup"><span data-stu-id="0cc31-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="0cc31-113">Você pode ter até 20 servidores statefull definidos no fabric, dos quais 12 podem estar ativos e online a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="0cc31-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>