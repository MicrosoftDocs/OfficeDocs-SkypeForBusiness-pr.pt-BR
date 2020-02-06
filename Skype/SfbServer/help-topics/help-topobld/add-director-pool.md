---
title: Adicionar Pool de Diretor
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
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Para definir o FQDN do pool de directors, selecione um pool de vários computadores que consistirá em dois ou mais directors em um pool de balanceamento de carga ou em um único pool de computador. Você também deve digitar o FQDN (nome de domínio totalmente qualificado) que será usado para se conectar ao pool do diretor ou ao FQDN do diretor único. Para um pool de computadores do diretor, essa seria a entrada do sistema de nome de domínio (DNS) para o IP virtual de um balanceador de carga de hardware ou a entrada DNS compartilhada para o balanceamento de carga de DNS.
ms.openlocfilehash: 1a419c6a27118cbdf7ffe841a39b9b60e6e84577
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821183"
---
# <a name="add-director-pool"></a>Adicionar Pool de Diretor
 
Para **definir o FQDN do pool de directors**, selecione um **pool de vários computadores** que consistirá em dois ou mais directors em um pool de balanceamento de carga ou em um **único pool de computador**. Você também deve digitar o FQDN (nome de domínio totalmente qualificado) que será usado para se conectar ao pool do diretor ou ao FQDN do diretor único. Para um pool de computadores do diretor, essa seria a entrada do sistema de nome de domínio (DNS) para o IP virtual de um balanceador de carga de hardware ou a entrada DNS compartilhada para o balanceamento de carga de DNS.
  
> [!TIP]
> Se você pretende implementar um pool de diretor no futuro, selecione **vários pools de computadores**. Embora um pool seja definido como dois ou mais computadores com balanceamento de carga, você pode criar um único pool de computador e criar um FQDN do pool para o único computador. Quando estiver pronto para adicionar mais computadores ao pool mais tarde, você deve executar o construtor de topologia novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro do pool de directors por meio do assistente de implantação do Skype for Business Server. Você também deve adicionar o novo membro do pool aos balanceadores de carga apropriados para o pool, para o balanceamento de carga do sistema de nome de domínio (DNS) ou para balanceadores de carga de hardware. Em muitos casos, você terá os dois sistemas de balanceamento de carga in-loco. Certifique-se de que você está adicionando o novo servidor membro a ambos. 
  

