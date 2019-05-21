---
title: Mesclagem Herdada
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: O FQDN externo da webconferência permite que usuários externos ingressem em reuniões locais. Digite o nome de domínio totalmente qualificado (FQDN) da interface externa da webconferência do servidor de borda herdado.
ms.openlocfilehash: b1d0211c51864b55a81b7c648d84402a44300f2a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284127"
---
# <a name="legacy-merge"></a><span data-ttu-id="f872c-104">Mesclagem Herdada</span><span class="sxs-lookup"><span data-stu-id="f872c-104">Legacy Merge</span></span>

<span data-ttu-id="f872c-105">O **FQDN externo da webconferência** permite que usuários externos ingressem em reuniões locais.</span><span class="sxs-lookup"><span data-stu-id="f872c-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="f872c-106">Digite o nome de domínio totalmente qualificado (FQDN) da interface externa da webconferência do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="f872c-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="f872c-107">O valor da **porta externa da conferência da Web externa** do **443** é a porta do protocolo de controle de transmissão (TCP) de protocolo de controle de transmissão (SIP) padrão configurada para clientes de conferência.</span><span class="sxs-lookup"><span data-stu-id="f872c-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="f872c-108">Se o valor padrão não for usado, atualize o valor de **porta externa da webconferência externa** .</span><span class="sxs-lookup"><span data-stu-id="f872c-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="f872c-109">Marque a caixa de seleção **este pool de bordas é usado para a Federação e conectividade de im pública** se você planeja usar esse servidor de borda para Federação.</span><span class="sxs-lookup"><span data-stu-id="f872c-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="f872c-110">Se você tiver vários servidores de Borda implantados, apenas um deles será habilitado para Federação.</span><span class="sxs-lookup"><span data-stu-id="f872c-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="f872c-111">Se você não marcar esta caixa e decidir mais tarde de que deseja habilitar a Federação, você deve executar o assistente de mesclagem do construtor de topologia novamente, bem como publicar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="f872c-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="f872c-112">Para obter detalhes, consulte [fase 4: mesclar topologias](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="f872c-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


