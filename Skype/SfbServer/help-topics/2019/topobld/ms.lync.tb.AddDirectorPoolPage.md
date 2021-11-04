---
title: Adicionar Pool de Diretor
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: Para  Definir o FQDN do Pool de Diretores, selecione um  Pool de vários computadores , formado por dois ou mais Diretores em um pool com carga balanceada, ou um  Pool com um único computador . Você também deve digitar o FQDN (nome de domínio totalmente qualificado) que será usado para se conectar ao pool de Diretores ou ao FQDN do diretor único. Para um pool de computadores Diretores, essa seria a entrada de DNS (Sistema de Nomes de Domínio) do IP virtual de um balanceador de carga de hardware ou a entrada de DNS compartilhada para balanceamento de carga de DNS.
ms.openlocfilehash: 2e95c7b83d3feee398da93dac2a9bd9e1500e174
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741087"
---
# <a name="add-director-pool"></a>Adicionar Pool de Diretor
 
Para  **Definir o FQDN do Pool de Diretores**, selecione um  **Pool de vários computadores**, formado por dois ou mais Diretores em um pool com carga balanceada, ou um  **Pool com um único computador**. Você também deve digitar o FQDN (nome de domínio totalmente qualificado) que será usado para se conectar ao pool de Diretores ou ao FQDN do diretor único. Para um pool de computadores Diretores, essa seria a entrada de DNS (Sistema de Nomes de Domínio) do IP virtual de um balanceador de carga de hardware ou a entrada de DNS compartilhada para balanceamento de carga de DNS.
  
> [!TIP]
> Caso planeje implementar um pool de Diretor no futuro, selecione  **Pool de múltiplos computadores**. Embora um pool seja definido como dois ou mais computadores que estão com cargas balanceadas, você pode criar um pool de único computador e criar um pool FQDN para o computador único. Quando estiver pronto para adicionar mais computadores ao pool posteriormente, você deverá executar o Construtor de Topologias novamente para definir o novo membro do pool, publicar a nova topologia e configurar o novo membro do pool de Diretores por meio do Assistente de Implantação Skype for Business Server. Você também deve adicionar o novo membro do pool aos balanceadores de carga do pool, balanceamento de carga DNS (Domain Name System) ou para balanceadores de carga de hardware apropriados. Em muitos caso, você terá ambos sistemas de balanceamento de carga instalados. Certifique-se de que você está adicionando o novo servidor membro a ambos. 
  

