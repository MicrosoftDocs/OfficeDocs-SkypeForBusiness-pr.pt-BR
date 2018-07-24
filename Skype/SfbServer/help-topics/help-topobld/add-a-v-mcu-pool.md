---
title: Adicionar A / V MCU Pool
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Todos os servidores Enterprise Edition Front End de um site central que não têm um colocado uma / serviço V Conferencing pode usar a mesma stand-alone A / pool de conferência V. Para cada pool de conferência V, você deve especificar um nome de domínio totalmente qualificado (FQDN) para o pool e se ele terá somente um único a / V Conferencing Server ou múltiplo, com balanceamento de carga A / V Conferencing Servers.
ms.openlocfilehash: 435b750715246be6e1f461dd49ce53965c85d2a6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21016548"
---
# <a name="add-av-mcu-pool"></a>Adicionar A / V MCU Pool
 
Todos os servidores Enterprise Edition Front End de um site central que não têm um colocado uma / serviço V Conferencing pode usar a mesma stand-alone A / pool de conferência V. Para cada pool de conferência V, você deve especificar um nome de domínio totalmente qualificado (FQDN) para o pool e se ele terá somente um único a / V Conferencing Server ou múltiplo, com balanceamento de carga A / V Conferencing Servers.
  
> [!IMPORTANT]
> Você não pode converter um pool de servidor único em um pool de vários servidores. Se posteriormente você decidir que sua organização precisa de um pool de vários servidores, você deve excluir o pool de servidor único e, em seguida, adicione o pool de vários servidores. 
  
> [!TIP]
> Se você pretende implementar um A / pool de conferência V no futuro, selecione **pool de vários computadores**. Embora um pool seja definido como dois ou mais computadores com carga balanceada, é possível criar um único pool de computadores e criar um FQDN de pool para o computador único. Quando você estiver pronto para adicionar mais computadores ao pool posteriormente, você deve construtor de topologia novamente para definir o novo membro do pool, publicar a nova topologia e em seguida, configure a novo A / V Conferencing pool membro por meio do Skype para o Assistente de implantação de servidor de negócios. Uma / pools V Conferencing Server são os únicos que eles não precisam balanceadores de carga para criar um pool. Uma / pools de conferência V internamente o balanceamento de carga e não é necessário hardware adicional. 
  

