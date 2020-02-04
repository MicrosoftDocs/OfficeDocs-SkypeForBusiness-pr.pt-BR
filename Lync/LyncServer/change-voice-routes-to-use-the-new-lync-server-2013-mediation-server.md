---
title: Alterar as rotas de voz para usar o novo servidor de mediação do Lync Server 2013
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
ms.openlocfilehash: 40f9bed4262adcabdb23e5b5b85e7de43292d18b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="0872a-102">Alterar as rotas de voz para usar o novo servidor de mediação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0872a-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0872a-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="0872a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0872a-104">Esse procedimento altera as rotas de voz para usar o servidor de mediação do Lync Server 2013, em vez do servidor de mediação do Office Communications Server 2007 R2 herdado.</span><span class="sxs-lookup"><span data-stu-id="0872a-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="0872a-105">Para alterar as rotas de voz para usar o novo servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="0872a-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="0872a-106">Painel de Controle do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0872a-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="0872a-107">No painel esquerdo, selecione **Roteamento de voz** e **encaminhar**.</span><span class="sxs-lookup"><span data-stu-id="0872a-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="0872a-108">Clique em **novo** para criar uma nova rota de voz.</span><span class="sxs-lookup"><span data-stu-id="0872a-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="0872a-109">Preencha os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="0872a-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="0872a-110">**Nome**: digite um nome descritivo da rota de voz.</span><span class="sxs-lookup"><span data-stu-id="0872a-110">**Name**: Type a descriptive name of the voice route.</span></span> <span data-ttu-id="0872a-111">Para este documento, vamos usar o **W15PSTNRoute**.</span><span class="sxs-lookup"><span data-stu-id="0872a-111">For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="0872a-112">**Descrição**: digite uma breve descrição da rota de voz.</span><span class="sxs-lookup"><span data-stu-id="0872a-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="0872a-113">Ignore todas as seções restantes até alcançar os **gateways associados**.</span><span class="sxs-lookup"><span data-stu-id="0872a-113">Skip all remaining sections until you reach **Associated gateways**.</span></span> <span data-ttu-id="0872a-114">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0872a-114">Click **Add**.</span></span> <span data-ttu-id="0872a-115">Selecione o novo gateway padrão e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0872a-115">Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="0872a-116">Em **usos de PSTN associados**, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="0872a-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="0872a-117">Na página **selecionar registro de uso de PSTN** , selecione um nome de registro e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0872a-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="0872a-118">Na página **nova rota de voz** , clique em **OK** para criar a **rota de voz**.</span><span class="sxs-lookup"><span data-stu-id="0872a-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="0872a-119">Na página **Roteamento de voz** , selecione **roteiro**.</span><span class="sxs-lookup"><span data-stu-id="0872a-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="0872a-120">Mova a rota recém-criada para a parte superior da lista e selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0872a-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

