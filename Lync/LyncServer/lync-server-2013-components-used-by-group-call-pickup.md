---
title: 'Lync Server 2013: componentes usados pelo recebimento de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 062dc114534abb7d2a011c31b9747c2d6a0a45bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502358"
---
# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="a1c5f-102">Componentes usados por recebimento de chamada em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1c5f-102">Components used by Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1c5f-103">_**Última modificação do tópico:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="a1c5f-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="a1c5f-104">O recebimento de chamadas em grupo é implantado automaticamente quando você implanta o Enterprise Voice e o aplicativo de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="a1c5f-104">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="a1c5f-105">Você habilita o recebimento de chamadas em grupo Configurando a tabela de órbita de estacionamento de chamada com intervalos separados de números designados como números de grupo de recebimento de chamadas e, em seguida, atribuindo usuários para chamar grupos de retirada e habilitando os usuários para o recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="a1c5f-105">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span> <span data-ttu-id="a1c5f-106">Os seguintes componentes do Lync Server oferecem suporte ao recebimento de chamadas de Grupo:</span><span class="sxs-lookup"><span data-stu-id="a1c5f-106">The following Lync Server components support Group Call Pickup:</span></span>

  - <span data-ttu-id="a1c5f-107">**Serviço**     de aplicativo O serviço de aplicativo fornece uma plataforma para implantar, hospedar e gerenciar aplicativos de comunicação unificada, como o aplicativo de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="a1c5f-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="a1c5f-108">O serviço de aplicativo é instalado automaticamente em todos os servidores front-end em um pool de front-ends e em cada servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a1c5f-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="a1c5f-109">Aplicativo de estacionamento de **chamada**     O aplicativo de estacionamento de chamada é um dos aplicativos de comunicações unificadas hospedados pelo serviço de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a1c5f-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="a1c5f-110">O recebimento de chamadas em grupo é baseado no aplicativo de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="a1c5f-110">Group Call Pickup is based on the Call Park application.</span></span>

  - <span data-ttu-id="a1c5f-111">Shell de gerenciamento **do Lync Server**     Você usa o Shell de gerenciamento do Lync Server para gerenciar grupos de recebimento de chamadas de grupo.</span><span class="sxs-lookup"><span data-stu-id="a1c5f-111">**Lync Server Management Shell**   You use Lync Server Management Shell to manage Group Call Pickup groups.</span></span>

  - <span data-ttu-id="a1c5f-112">Ferramenta SEFAUtil Resource **Kit**     Use o utilitário de ativação de recurso de extensão secundária (SEFAUtil) para atribuir usuários a um grupo de recebimento de chamadas e habilitar ou desabilitar o recebimento de chamadas para usuários.</span><span class="sxs-lookup"><span data-stu-id="a1c5f-112">**SEFAUtil resource kit tool**   You use the secondary extension feature activation utility (SEFAUtil) to assign users to a call pickup group and to enable or disable call pickup for users.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

