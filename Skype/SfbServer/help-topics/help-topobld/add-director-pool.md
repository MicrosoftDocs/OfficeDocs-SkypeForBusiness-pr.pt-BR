---
title: Adicionar Pool de Diretor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Para definir o FQDN do pool de directors, selecione um pool de vários computadores que consistirá em dois ou mais directors em um pool de balanceamento de carga ou em um único pool de computador. Você também deve digitar o FQDN (nome de domínio totalmente qualificado) que será usado para se conectar ao pool do diretor ou ao FQDN do diretor único. Para um pool de computadores do diretor, essa seria a entrada do sistema de nome de domínio (DNS) para o IP virtual de um balanceador de carga de hardware ou a entrada DNS compartilhada para o balanceamento de carga de DNS.
ms.openlocfilehash: 163de8a6091e74238c4a4127ae39f7cd500cdb84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304783"
---
# <a name="add-director-pool"></a>Adicionar Pool de Diretor
 
Para **definir o FQDN do pool de directors**, selecione um **pool de vários computadores** que consistirá em dois ou mais directors em um pool de balanceamento de carga ou em um **único pool de computador**. Você também deve digitar o FQDN (nome de domínio totalmente qualificado) que será usado para se conectar ao pool do diretor ou ao FQDN do diretor único. Para um pool de computadores do diretor, essa seria a entrada do sistema de nome de domínio (DNS) para o IP virtual de um balanceador de carga de hardware ou a entrada DNS compartilhada para o balanceamento de carga de DNS.
  
> [!TIP]
> Se você pretende implementar um pool de diretor no futuro, selecione **vários pools de computadores**. Embora um pool seja definido como dois ou mais computadores com balanceamento de carga, você pode criar um único pool de computador e criar um FQDN do pool para o único computador. Quando estiver pronto para adicionar mais computadores ao pool mais tarde, você deve executar o construtor de topologia novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro do pool de directors por meio do assistente de implantação do Skype for Business Server. Você também deve adicionar o novo membro do pool aos balanceadores de carga apropriados para o pool, para o balanceamento de carga do sistema de nome de domínio (DNS) ou para balanceadores de carga de hardware. Em muitos casos, você terá os dois sistemas de balanceamento de carga in-loco. Certifique-se de que você está adicionando o novo servidor membro a ambos. 
  

