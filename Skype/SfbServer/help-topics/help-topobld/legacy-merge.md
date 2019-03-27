---
title: Mesclagem Herdada
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: O FQDN externo de webconferência permite que usuários externos para participar de reuniões no local. Insira o nome de domínio totalmente qualificado (FQDN) da interface externa de conferência da web do servidor de borda herdado.
ms.openlocfilehash: a6bb1ee83496e98f6097905fdf24c62d20d657ae
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897175"
---
# <a name="legacy-merge"></a><span data-ttu-id="1798b-104">Mesclagem Herdada</span><span class="sxs-lookup"><span data-stu-id="1798b-104">Legacy Merge</span></span>

<span data-ttu-id="1798b-105">O **FQDN externo de webconferência** permite que usuários externos para participar de reuniões no local.</span><span class="sxs-lookup"><span data-stu-id="1798b-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="1798b-106">Insira o nome de domínio totalmente qualificado (FQDN) da interface externa de conferência da web do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="1798b-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="1798b-107">O valor de **porta externa de conferência da Web externa** **443** é a porta de protocolo de controle de transmissão (TCP) Session Initiation Protocol (SIP) do padrão configurada para clientes de conferência.</span><span class="sxs-lookup"><span data-stu-id="1798b-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="1798b-108">Se o valor padrão não foi usado, atualize o valor de **porta externa de conferência da Web externos** .</span><span class="sxs-lookup"><span data-stu-id="1798b-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="1798b-109">Se você planeja usar este servidor de borda para federação, marque a caixa de seleção **borda deste pool é usado para federação e conectividade de IM pública** .</span><span class="sxs-lookup"><span data-stu-id="1798b-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="1798b-110">Se você tiver vários servidores de borda implantado, somente um deles será habilitado para federação.</span><span class="sxs-lookup"><span data-stu-id="1798b-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="1798b-111">Se você não marcar essa caixa e você decidir, posteriormente, que você deseja habilitar a federação, você deve executar novamente o Assistente de mesclagem do construtor de topologia, bem como publicar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="1798b-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="1798b-112">Para obter detalhes, consulte [fase 4: mesclar topologias](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="1798b-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


