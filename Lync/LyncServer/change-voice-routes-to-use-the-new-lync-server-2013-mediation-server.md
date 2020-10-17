---
title: Alterar as rotas de voz para usar o novo servidor de mediação do Lync Server 2013
description: Altere as rotas de voz para usar o novo servidor de mediação do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef58ba61512b5de31a74b79e554dbb3f94b67d99
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545737"
---
# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="636e8-103">Alterar as rotas de voz para usar o novo servidor de mediação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="636e8-103">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="636e8-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="636e8-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="636e8-105">Este procedimento altera as rotas de voz para usar o servidor de mediação do Lync Server 2013, em vez do servidor de mediação do Office Communications Server 2007 R2 herdado.</span><span class="sxs-lookup"><span data-stu-id="636e8-105">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="636e8-106">Para alterar as rotas de voz para usar o novo Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="636e8-106">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="636e8-107">Painel de Controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="636e8-107">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="636e8-108">No painel à esquerda, selecione **Roteamento de Voz** e, em seguida, **Rota**.</span><span class="sxs-lookup"><span data-stu-id="636e8-108">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="636e8-109">Clique em **Novo**para criar uma Nova Rota de Voz.</span><span class="sxs-lookup"><span data-stu-id="636e8-109">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="636e8-110">Preencha os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="636e8-110">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="636e8-111">**Nome**: Digite um nome descritivo para a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="636e8-111">**Name**: Type a descriptive name of the voice route.</span></span> <span data-ttu-id="636e8-112">Para este documento, usaremos o **W15PSTNRoute**.</span><span class="sxs-lookup"><span data-stu-id="636e8-112">For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="636e8-113">**Descrição**: Digite uma descrição curta para a rota de voz.</span><span class="sxs-lookup"><span data-stu-id="636e8-113">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="636e8-p102">Ignore toda as seções remanescente até alcançar **Gateways Associados**. Clique em **Adicionar**. Selecione o novo gateway padrão e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="636e8-p102">Skip all remaining sections until you reach **Associated gateways**. Click **Add**. Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="636e8-117">Sob **Usos do PSTN Associados**, clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="636e8-117">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="636e8-118">Na página **Selecionar Registro de Uso do PSTN**, selecione um nome de registro e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="636e8-118">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="636e8-119">Na página **Nova Rota de Voz**, clique em **OK** para criar a **Rota de Voz**.</span><span class="sxs-lookup"><span data-stu-id="636e8-119">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="636e8-120">Na página **Roteamento de Voz**, selecione **Rota**.</span><span class="sxs-lookup"><span data-stu-id="636e8-120">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="636e8-121">Mova a rota recém criada para o topo da lista e selecione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="636e8-121">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

