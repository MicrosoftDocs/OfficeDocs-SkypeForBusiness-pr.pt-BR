---
title: Adicionar Associações de Front End
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
description: 'Agora você pode habilitar o suporte para recursos específicos que exigem a implantação de outros servidores, associando as funções de servidor ao pool de Front-Ends. Também pode associar funções de servidor ao pool de Front-Ends posteriormente. As funções de servidor que podem ser associadas ao pool de Front-Ends incluem:'
ms.openlocfilehash: 499144870cfe4b4158993d9e758c5cd71cdb90e0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390283"
---
# <a name="add-front-end-associations"></a>Adicionar Associações de Front-end

Agora você pode habilitar o suporte para recursos específicos que exigem a implantação de outros servidores, associando as funções de servidor ao pool de Front-Ends. Também pode associar funções de servidor ao pool de Front-Ends posteriormente. As funções de servidor que podem ser associadas ao pool de Front-Ends incluem:

- Servidor de Borda A/V. Para obter detalhes sobre a implantação de um Servidor de Borda A/V, consulte [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) na documentação Planejamento.

> [!IMPORTANT]
> Caso você habilite suporte para qualquer um destes recursos agora, o projeto de topologia publicado por você incluirá os componentes de servidor necessários para implementar cada recurso escolhido. Para que a publicação da topologia seja bem sucedida, os computadores físicos devem estar ingressados ao domínio. Por exemplo, se você habilitar o suporte para arquivamento agora, deverá implantar um Servidor de Arquivamento e configurar as opções de arquivamento apropriadas antes de iniciar as comunicações de arquivamento para sua organização.