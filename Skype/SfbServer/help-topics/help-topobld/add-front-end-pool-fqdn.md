---
title: Adicionar FQDN do Pool de Front-Ends
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
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Especifique o FQDN (nome de domínio totalmente qualificado) do pool de Front-Ends que você está criando. Você não pode alterar o FQDN de um pool após publicar a topologia que contém o pool de Front-Ends. Se precisar renomear um pool, você deverá excluí-lo e adicionar um novo pool com o novo FQDN.
ms.openlocfilehash: 99bf31760ce908952547ccfb3f150c136966e9f0
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218852"
---
# <a name="add-front-end-pool-fqdn"></a>Adicionar FQDN do Pool de Front-Ends
 
Especifique o FQDN (nome de domínio totalmente qualificado) do pool de Front-Ends que você está criando. Você não pode alterar o FQDN de um pool após publicar a topologia que contém o pool de Front-Ends. Se precisar renomear um pool, você deverá excluí-lo e adicionar um novo pool com o novo FQDN.
  
> [!TIP]
> Se você planeja implementar um pool de Front-Ends no futuro, selecione **Pool de múltiplos computadores**. Embora um pool seja definido como dois ou mais computadores que estão com cargas balanceadas, você pode criar um pool de único computador e criar um pool FQDN para o computador único. Quando estiver pronto para adicionar mais computadores ao pool mais tarde, você deverá executar o construtor de topologias novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro do pool de front-ends através do assistente de implantação do Skype for Business Server. Também é necessário adicionar o novo membro do pool aos balanceadores de carga apropriados para o pool, balanceamento de carga DNS (Domain Name System) ou balanceadores de carga de hardware. Em muitos casos, existem os dois sistemas de balanceamento de carga. Certifique-se de que você está adicionando o novo servidor membro a ambos. 
  

