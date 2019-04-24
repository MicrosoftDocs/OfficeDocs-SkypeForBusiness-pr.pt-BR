---
title: Adicionar Pool A/V MCU
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: Todos os servidores Enterprise Edition Front End de um site central que não têm um colocado uma / serviço V Conferencing pode usar a mesma stand-alone A / pool de conferência V. Para cada pool de conferência V, você deve especificar um nome de domínio totalmente qualificado (FQDN) para o pool e se ele terá somente um único a / V Conferencing Server ou múltiplo, com balanceamento de carga A / V Conferencing Servers.
ms.openlocfilehash: f88476165ce6affe23e9e5cbb33e03a997c04971
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202300"
---
# <a name="add-av-mcu-pool"></a>Adicionar Pool A/V MCU
 
Todos os servidores Enterprise Edition Front End de um site central que não têm um colocado uma / serviço V Conferencing pode usar a mesma stand-alone A / pool de conferência V. Para cada pool de conferência V, você deve especificar um nome de domínio totalmente qualificado (FQDN) para o pool e se ele terá somente um único a / V Conferencing Server ou múltiplo, com balanceamento de carga A / V Conferencing Servers.
  
> [!IMPORTANT]
> Você não pode converter um pool de servidor único em um pool de vários servidores. Se posteriormente você decidir que sua organização precisa de um pool de vários servidores, você deve excluir o pool de servidor único e, em seguida, adicione o pool de vários servidores. 
  
> [!TIP]
> Se você pretende implementar um A / pool de conferência V no futuro, selecione **pool de vários computadores**. Embora um pool seja definido como dois ou mais computadores com carga balanceada, é possível criar um único pool de computadores e criar um FQDN de pool para o computador único. Quando você estiver pronto para adicionar mais computadores ao pool posteriormente, você deve construtor de topologia novamente para definir o novo membro do pool, publicar a nova topologia e em seguida, configure a novo A / V Conferencing pool membro por meio do Skype para o Assistente de implantação de servidor de negócios. Uma / pools V Conferencing Server são os únicos que eles não precisam balanceadores de carga para criar um pool. Uma / pools de conferência V internamente o balanceamento de carga e não é necessário hardware adicional. 
  

