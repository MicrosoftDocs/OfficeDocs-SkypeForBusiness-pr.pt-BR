---
title: Adicionar Pool A/V MCU
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Todos os Servidores Front-End Enterprise Edition de um local central que não têm um serviço de Conferência A/V colocado podem usar o mesmo pool de Conferência A/V autônomo. Para cada pool de Conferência A/V, você deve especificar um FQDN (nome de domínio totalmente qualificado) para o pool e indicar se ele terá apenas um Servidor de Conferência A/V ou vários Servidores de Conferência A/V com balanceamento de carga.
ms.openlocfilehash: e38bcf5efa065ef2f9b53a5df47f6a56eafbe29a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217472"
---
# <a name="add-av-mcu-pool"></a>Adicionar Pool A/V MCU
 
Todos os Servidores Front-End Enterprise Edition de um local central que não têm um serviço de Conferência A/V colocado podem usar o mesmo pool de Conferência A/V autônomo. Para cada pool de Conferência A/V, você deve especificar um FQDN (nome de domínio totalmente qualificado) para o pool e indicar se ele terá apenas um Servidor de Conferência A/V ou vários Servidores de Conferência A/V com balanceamento de carga.
  
> [!IMPORTANT]
> Você não pode converter um pool de servidor único em um pool de múltiplos servidores. Caso decida, mais tarde, de que sua organização necessita de um pool de múltiplos servidores, você deve deletar o pool de servidor único e então adicionar o pool de múltiplos servidores. 
  
> [!TIP]
> Caso você planeje implementar um pool de Conferência A/V no futuro, selecione **Pool de múltiplos computadores**. Embora um pool seja definido como dois ou mais computadores que estão com cargas balanceadas, você pode criar um pool de único computador e criar um pool FQDN para o computador único. Quando estiver pronto para adicionar mais computadores ao pool mais tarde, você precisará do construtor de topologias novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro do pool de conferência A/V através do assistente de implantação do Skype for Business Server. Pools de Servidor de Conferência A/V são únicos por não precisarem de balanceadores de carga para criar um pool. Pools de Conferência A/V balanceiam a carga internamente e não exigem hardware adicional. 
  

