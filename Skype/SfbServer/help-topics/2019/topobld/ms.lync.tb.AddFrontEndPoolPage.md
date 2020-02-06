---
title: Adicionar FQDN do Pool de Front-Ends
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Especifique o nome de domínio totalmente qualificado (FQDN) do pool de front-ends que você está criando. Não é possível alterar o FQDN de um pool após a publicação da topologia que contém o pool de front-ends. Se precisar renomear um pool, você deve excluir o pool e adicionar um novo pool com o novo FQDN.
ms.openlocfilehash: 0c6fdf24ec19fe56ff86d4a5b43af2e48aedb3e2
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798518"
---
# <a name="add-front-end-pool-fqdn"></a>Adicionar FQDN do Pool de Front-Ends
 
Especifique o nome de domínio totalmente qualificado (FQDN) do pool de front-ends que você está criando. Não é possível alterar o FQDN de um pool após a publicação da topologia que contém o pool de front-ends. Se precisar renomear um pool, você deve excluir o pool e adicionar um novo pool com o novo FQDN.
  
> [!TIP]
> Se você pretende implementar um pool de front-end no futuro, selecione **vários pools de computadores**. Embora um pool seja definido como dois ou mais computadores com carga balanceada, é possível criar um único pool de computadores e criar um FQDN de pool para o computador único. Quando estiver pronto para adicionar mais computadores ao pool mais tarde, você deve executar o construtor de topologia novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro do pool de front-end por meio do assistente de implantação do Skype for Business Server. Você também deve adicionar o novo membro do pool aos balanceadores de carga apropriados para o pool, o balanceamento de carga DNS (sistema de nomes de domínio) ou balanceadores de carga de hardware. Em muitos casos, você teria dois sistemas de balanceamento de carga in-loco. Certifique-se de que você está adicionando o novo servidor membro a ambos. 
  

