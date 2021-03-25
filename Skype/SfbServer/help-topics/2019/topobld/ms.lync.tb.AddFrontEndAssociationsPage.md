---
title: Adicionar Associações de Front End
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
ROBOTS: NOINDEX, NOFOLLOW
description: 'Agora você pode habilitar o suporte para recursos específicos que exigem a implantação de outros servidores, associando as funções de servidor ao pool de Front-Ends. Também pode associar funções de servidor ao pool de Front-Ends posteriormente. As funções de servidor que podem ser associadas ao pool de Front-Ends incluem:'
ms.openlocfilehash: 1a528fbeeabc4ca9a4c676a9f064b651c37298c6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122652"
---
# <a name="add-front-end-associations"></a><span data-ttu-id="89aac-105">Adicionar Associações de Front-end</span><span class="sxs-lookup"><span data-stu-id="89aac-105">Add Front End Associations</span></span>

<span data-ttu-id="89aac-p102">Agora você pode habilitar o suporte para recursos específicos que exigem a implantação de outros servidores, associando as funções de servidor ao pool de Front-Ends. Também pode associar funções de servidor ao pool de Front-Ends posteriormente. As funções de servidor que podem ser associadas ao pool de Front-Ends incluem:</span><span class="sxs-lookup"><span data-stu-id="89aac-p102">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool now. You can also associate server roles with the Front End pool at a later time. The server roles that can be associated with a Front End pool include the following:</span></span>

- <span data-ttu-id="89aac-109">Servidor de Borda A/V.</span><span class="sxs-lookup"><span data-stu-id="89aac-109">A/V Edge Server.</span></span> <span data-ttu-id="89aac-110">Para obter detalhes sobre a implantação de um Servidor de Borda A/V, consulte [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) na documentação Planejamento.</span><span class="sxs-lookup"><span data-stu-id="89aac-110">For details about the implementation of an A/V Edge Server, see [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) in the Planning documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89aac-111">Caso você habilite suporte para qualquer um destes recursos agora, o projeto de topologia publicado por você incluirá os componentes de servidor necessários para implementar cada recurso escolhido.</span><span class="sxs-lookup"><span data-stu-id="89aac-111">If you enable support for any of these features now, the topology design that you publish will include the server components that are required to implement each selected feature.</span></span> <span data-ttu-id="89aac-112">Para que a publicação da topologia seja bem sucedida, os computadores físicos devem estar ingressados ao domínio.</span><span class="sxs-lookup"><span data-stu-id="89aac-112">For the publishing of a topology to succeed without error, you must have the physical computers joined to the domain.</span></span> <span data-ttu-id="89aac-113">Por exemplo, se você habilitar o suporte para arquivamento agora, deverá implantar um Servidor de Arquivamento e configurar as opções de arquivamento apropriadas antes de iniciar as comunicações de arquivamento para sua organização.</span><span class="sxs-lookup"><span data-stu-id="89aac-113">For example, if you enable support for archiving now, you must then deploy an Archiving Server and configure the appropriate archiving options before you start archiving communications for your organization.</span></span>