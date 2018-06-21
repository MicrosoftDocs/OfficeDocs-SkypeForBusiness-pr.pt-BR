---
title: Adicionar Pool de diretor
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Para definir o FQDN do pool de diretor, selecione um pool de vários computadores que consiste em dois ou mais diretores em um pool com balanceamento de carga, ou um pool de computador único. Você também deverá digitar o nome de domínio totalmente qualificado (FQDN) que será usado para conectar ao pool de diretores ou FQDN do Diretor único. Para um pool de computadores de diretor, isso seria a entrada de sistema de nome de domínio (DNS) para o IP virtual de um balanceador de carga de hardware ou a entrada DNS compartilhada para balanceamento de carga DNS.
ms.openlocfilehash: 84f74962465645890e976a6f1ff77b6ef55ca930
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19967177"
---
# <a name="add-director-pool"></a>Adicionar Pool de diretor
 
Para **definir o FQDN do pool de diretor**, selecione um **pool de vários computadores** que consiste em dois ou mais diretores em um pool com balanceamento de carga ou um **pool de computador único**. Você também deverá digitar o nome de domínio totalmente qualificado (FQDN) que será usado para conectar ao pool de diretores ou FQDN do Diretor único. Para um pool de computadores de diretor, isso seria a entrada de sistema de nome de domínio (DNS) para o IP virtual de um balanceador de carga de hardware ou a entrada DNS compartilhada para balanceamento de carga DNS.
  
> [!TIP]
> Se você pretende implementar um pool de diretores no futuro, selecione **pool de vários computadores**. Embora um pool estiver definido como dois ou mais computadores que estão com balanceamento de carga, você pode criar um pool de computador único e criar um pool FQDN para o único computador. Quando você estiver pronto para adicionar mais computadores ao pool posteriormente, você deve executar o construtor de topologias novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro de pool de diretor através do Skype para o Assistente de implantação de servidor de negócios. Você também deve adicionar o novo membro de pool para os balanceadores de carga apropriado para o pool, para o sistema de nome de domínio (DNS) balanceamento de carga, ou balanceadores de carga de hardware. Em muitos casos, você terá de ambos os sistemas in-loco de balanceamento de carga. Certifique-se de que você está adicionando o novo servidor membro para ambos. 
  

