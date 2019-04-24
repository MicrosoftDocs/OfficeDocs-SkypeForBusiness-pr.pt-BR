---
title: Adicionar FQDN do Pool de Front-Ends
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Especifique o nome de domínio totalmente qualificado (FQDN) do pool de Front-End que você está criando. Depois de publicar a topologia que contém o pool de Front-End, você não pode alterar o FQDN de um pool. Se você precisar renomear um pool, você deve excluir o pool e, em seguida, adicionar um novo pool com o novo FQDN.
ms.openlocfilehash: 28e831df0cdf86620eefc1a22ced199507026c46
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202058"
---
# <a name="add-front-end-pool-fqdn"></a>Adicionar FQDN do Pool de Front-Ends
 
Especifique o nome de domínio totalmente qualificado (FQDN) do pool de Front-End que você está criando. Depois de publicar a topologia que contém o pool de Front-End, você não pode alterar o FQDN de um pool. Se você precisar renomear um pool, você deve excluir o pool e, em seguida, adicionar um novo pool com o novo FQDN.
  
> [!TIP]
> Se você pretende implementar um pool de Front-End no futuro, selecione **pool de vários computadores**. Embora um pool seja definido como dois ou mais computadores com carga balanceada, é possível criar um único pool de computadores e criar um FQDN de pool para o computador único. Quando você estiver pronto para adicionar mais computadores ao pool posteriormente, você deve executar o construtor de topologias novamente para definir o novo membro do pool, publicar a nova topologia e configurar o novo membro de pool de Front-End por meio do Skype para o Assistente de implantação de servidor de negócios. Você também deve adicionar o novo membro de pool para os balanceadores de carga apropriado para o pool, balanceamento de carga de sistema de nome de domínio (DNS) ou balanceadores de carga de hardware. Em muitos casos, você teria ambos os sistemas in-loco de balanceamento de carga. Certifique-se de que você está adicionando o novo servidor membro para ambos. 
  

