---
title: Adicionar FQDN do Pool de Front-Ends
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Especifique o FQDN (nome de domínio totalmente qualificado) do pool de Front-Ends que você está criando. Você não pode alterar o FQDN de um pool após publicar a topologia que contém o pool de Front-Ends. Se precisar renomear um pool, você deverá excluí-lo e adicionar um novo pool com o novo FQDN.
ms.openlocfilehash: 7f58f0fb410cff185900138a7ea5c112c359c38f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862588"
---
# <a name="add-front-end-pool-fqdn"></a>Adicionar FQDN do Pool de Front-ends
 
Especifique o FQDN (nome de domínio totalmente qualificado) do pool de Front-Ends que você está criando. Você não pode alterar o FQDN de um pool após publicar a topologia que contém o pool de Front-Ends. Se precisar renomear um pool, você deverá excluí-lo e adicionar um novo pool com o novo FQDN.
  
> [!TIP]
> Se você planeja implementar um pool de Front-Ends no futuro, selecione **Pool de múltiplos computadores**. Embora um pool seja definido como dois ou mais computadores que estão com cargas balanceadas, você pode criar um pool de único computador e criar um pool FQDN para o computador único. Quando estiver pronto para adicionar mais computadores ao pool posteriormente, você deve executar o Construtor de Topologias novamente para definir o novo membro do pool, publicar a nova topologia e configurar o novo membro do pool de Front-End por meio do Assistente de Implantação Skype for Business Server. Também é necessário adicionar o novo membro do pool aos balanceadores de carga apropriados para o pool, balanceamento de carga DNS (Domain Name System) ou balanceadores de carga de hardware. Em muitos casos, existem os dois sistemas de balanceamento de carga. Certifique-se de que você está adicionando o novo servidor membro a ambos. 
  

