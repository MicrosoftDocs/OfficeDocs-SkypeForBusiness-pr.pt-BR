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
- NOCSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Todos os servidores front-end Enterprise Edition de um site central que não tenham um serviço de conferência A/V posicionado podem usar o mesmo pool autônomo de conferência A/V. Para cada pool de conferência A/V, você deve especificar um FQDN (nome de domínio totalmente qualificado) para o pool e se ele terá apenas um único servidor de conferência A/V ou servidores de conferência A/V com carga balanceada.
ms.openlocfilehash: 1d78a9d24659ec2ad571c01528323796e7ae5d18
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821313"
---
# <a name="add-av-mcu-pool"></a>Adicionar Pool A/V MCU
 
Todos os servidores front-end Enterprise Edition de um site central que não tenham um serviço de conferência A/V posicionado podem usar o mesmo pool autônomo de conferência A/V. Para cada pool de conferência A/V, você deve especificar um FQDN (nome de domínio totalmente qualificado) para o pool e se ele terá apenas um único servidor de conferência A/V ou servidores de conferência A/V com carga balanceada.
  
> [!IMPORTANT]
> Não é possível converter um pool de servidor único em um pool de vários servidores. Se, posteriormente, você decidir que a sua organização precisa de um pool de vários servidores, você deve excluir o pool de servidor único e, em seguida, adicionar o pool de vários servidores. 
  
> [!TIP]
> Se você pretende implementar um pool de conferência A/V no futuro, selecione **vários pools de computadores**. Embora um pool seja definido como dois ou mais computadores com carga balanceada, é possível criar um único pool de computadores e criar um FQDN de pool para o computador único. Quando estiver pronto para adicionar mais computadores ao pool mais tarde, você deve ter o construtor de topologia novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro do pool de conferência a/V por meio do assistente de implantação do Skype for Business Server. Os pools do servidor de conferência A/V são exclusivos porque não precisam de balanceadores de carga para criar um pool. O balanceamento de carga de pools de conferência A/V internamente e não precisa de hardware adicional. 
  

