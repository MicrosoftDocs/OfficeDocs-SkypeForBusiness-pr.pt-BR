---
title: Adicionar Pool A/V MCU
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: Todos os servidores front-end Enterprise Edition de um site central que não tenham um serviço de conferência A/V posicionado podem usar o mesmo pool autônomo de conferência A/V. Para cada pool de conferência A/V, você deve especificar um FQDN (nome de domínio totalmente qualificado) para o pool e se ele terá apenas um único servidor de conferência A/V ou servidores de conferência A/V com carga balanceada.
ms.openlocfilehash: dfd1fd056e015ed4d6ed1344384efa485e65f318
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304053"
---
# <a name="add-av-mcu-pool"></a>Adicionar Pool A/V MCU
 
Todos os servidores front-end Enterprise Edition de um site central que não tenham um serviço de conferência A/V posicionado podem usar o mesmo pool autônomo de conferência A/V. Para cada pool de conferência A/V, você deve especificar um FQDN (nome de domínio totalmente qualificado) para o pool e se ele terá apenas um único servidor de conferência A/V ou servidores de conferência A/V com carga balanceada.
  
> [!IMPORTANT]
> Não é possível converter um pool de servidor único em um pool de vários servidores. Se, posteriormente, você decidir que a sua organização precisa de um pool de vários servidores, você deve excluir o pool de servidor único e, em seguida, adicionar o pool de vários servidores. 
  
> [!TIP]
> Se você pretende implementar um pool de conferência A/V no futuro, selecione **vários pools de computadores**. Embora um pool seja definido como dois ou mais computadores com carga balanceada, é possível criar um único pool de computadores e criar um FQDN de pool para o computador único. Quando estiver pronto para adicionar mais computadores ao pool mais tarde, você deve ter o construtor de topologia novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro do pool de conferência a/V por meio do assistente de implantação do Skype for Business Server. Os pools do servidor de conferência A/V são exclusivos porque não precisam de balanceadores de carga para criar um pool. O balanceamento de carga de pools de conferência A/V internamente e não precisa de hardware adicional. 
  

