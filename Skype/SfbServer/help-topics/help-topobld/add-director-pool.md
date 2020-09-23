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
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Para  Definir o FQDN do Pool de Diretores, selecione um  Pool de vários computadores , formado por dois ou mais Diretores em um pool com carga balanceada, ou um  Pool com um único computador . Você também deve digitar o FQDN (nome de domínio totalmente qualificado) que será usado para se conectar ao pool de diretores ou ao FQDN do diretor único. Para um pool de computadores Diretores, essa seria a entrada de DNS (Sistema de Nomes de Domínio) do IP virtual de um balanceador de carga de hardware ou a entrada de DNS compartilhada para balanceamento de carga de DNS.
ms.openlocfilehash: 9209fa9e4417644b20b95668b05e660114414efc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219482"
---
# <a name="add-director-pool"></a>Adicionar Pool de Diretor
 
Para  **Definir o FQDN do Pool de Diretores**, selecione um  **Pool de vários computadores **, formado por dois ou mais Diretores em um pool com carga balanceada, ou um  **Pool com um único computador **. Você também deve digitar o FQDN (nome de domínio totalmente qualificado) que será usado para se conectar ao pool de diretores ou ao FQDN do diretor único. Para um pool de computadores Diretores, essa seria a entrada de DNS (Sistema de Nomes de Domínio) do IP virtual de um balanceador de carga de hardware ou a entrada de DNS compartilhada para balanceamento de carga de DNS.
  
> [!TIP]
> Caso planeje implementar um pool de Diretor no futuro, selecione  **Pool de múltiplos computadores **. Embora um pool seja definido como dois ou mais computadores que estão com cargas balanceadas, você pode criar um pool de único computador e criar um pool FQDN para o computador único. Quando estiver pronto para adicionar mais computadores ao pool mais tarde, você deverá executar o construtor de topologias novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro do pool de diretores através do assistente de implantação do Skype for Business Server. Você também deve adicionar o novo membro do pool aos balanceadores de carga do pool, balanceamento de carga DNS (Domain Name System) ou para balanceadores de carga de hardware apropriados. Em muitos caso, você terá ambos sistemas de balanceamento de carga instalados. Certifique-se de que você está adicionando o novo servidor membro a ambos. 
  

