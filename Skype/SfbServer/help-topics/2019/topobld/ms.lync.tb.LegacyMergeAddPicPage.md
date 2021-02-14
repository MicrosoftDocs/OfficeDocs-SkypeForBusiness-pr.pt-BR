---
title: Mesclagem Herdada
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: O FQDN externo de Webconferência permite que usuários externos ingressem em reuniões locais. Digite o FQDN (nome de domínio totalmente qualificado) da interface externa de Webconferência do Servidor de Borda herdado.
ms.openlocfilehash: bd259179ea61e20efec2fca81bddd40b0c53f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805701"
---
# <a name="legacy-merge"></a><span data-ttu-id="8ef7f-104">Mesclagem Herdada</span><span class="sxs-lookup"><span data-stu-id="8ef7f-104">Legacy Merge</span></span>

<span data-ttu-id="8ef7f-p102">O **FQDN externo de Webconferência** permite que usuários externos ingressem em reuniões locais. Digite o FQDN (nome de domínio totalmente qualificado) da interface externa de Webconferência do Servidor de Borda herdado.</span><span class="sxs-lookup"><span data-stu-id="8ef7f-p102">The **Web Conferencing external FQDN** permits external users to join on-premises meetings. Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="8ef7f-p103">O valor de **Porta externa de Webconferência Externa** de **443** é a porta SIP (Session Initiation Protocol) TCP (Transmission Control Protocol) configurada para clientes de conferência. Caso o valor padrão não tenha sido usado, atualize o valor **Porta externa de Webconferência Externa**.</span><span class="sxs-lookup"><span data-stu-id="8ef7f-p103">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients. If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="8ef7f-109">Marque a caixa de seleção **Este pool de Borda é usado para conectividade de IM pública e de federação** se você planeja usar este Servidor de Borda para federação.</span><span class="sxs-lookup"><span data-stu-id="8ef7f-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="8ef7f-110">Caso você tenha múltiplos Servidores de Borda implantados, apenas um deles será habilitado para federação.</span><span class="sxs-lookup"><span data-stu-id="8ef7f-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="8ef7f-111">Caso você não marque essa caixa e decida mais tarde que você deseja habilitar federação, você deve executar o assistente para Mescla de Construtor de Topologia e também publicar sua topologia novamente.</span><span class="sxs-lookup"><span data-stu-id="8ef7f-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="8ef7f-112">Para maiores detalhes, consulte [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="8ef7f-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


