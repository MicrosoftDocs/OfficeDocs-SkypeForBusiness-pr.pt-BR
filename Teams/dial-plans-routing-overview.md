---
title: Planos de discagem e roteamento
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
description: Planos de discagem e roteamento Microsoft Teams
ms.openlocfilehash: 1d99b5edef1cf6c4440a218097933e4ff5843f1d
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686708"
---
# <a name="overview"></a>Visão geral

Os artigos nesta seção descrevem os planos de discagem e o roteamento de chamadas Microsoft Teams. 

- [O que são planos de discagem](what-are-dial-plans.md)
- [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md)
- [Rotear chamadas para dormentes não atribuídos](routing-calls-to-unassigned-numbers.md)

Os artigos desta seção se aplicam a todas as opções de conexão à PSTN (Rede Telefônica Pública Comunada): Plano de Chamadas, Conexão do operador e Roteamento Direto. Para obter mais informações sobre todas as opções de conectividade PSTN, consulte [as opções de conectividade PSTN](pstn-connectivity.md).

Se você escolher Plano de Chamada ou Conexão do operador, a maioria do roteamento de chamadas será tratada pela Microsoft ou pelo seu provedor. O Roteamento Direto, no entanto, requer etapas adicionais para configurar o roteamento de chamadas. 

Para Roteamento Direto, você deve configurar o roteamento de chamadas especificando as rotas de voz e atribuindo políticas de roteamento de voz aos usuários. Você pode configurar planos de discagem para conversão de números no nível do tronco para garantir a interoperabilidade com controladores de borda de sessão (SBCs). Para obter mais informações, consulte [Configurar o roteamento de voz para Roteamento Direto](direct-routing-voice-routing.md), Gerenciar políticas de roteamento [de voz](manage-voice-routing-policies.md) e [Traduzir números de telefone](direct-routing-translate-numbers.md).

Lembre-se de que você pode atribuir uma política de roteamento de voz online de Roteamento Direto para o Plano de Chamadas e Conexão do operador usuários. Talvez você queira fazer isso, por exemplo, para permitir que os usuários discem diretamente para um call center. Você pode configurar um tronco de Roteamento Direto para o call center.

Se um usuário tiver uma licença de Plano de Chamada, por exemplo, as chamadas de saída desse usuário serão roteadas automaticamente por meio da infraestrutura PSTN do Plano de Chamada da Microsoft. Se você configurar e atribuir uma política de roteamento de voz online de Roteamento Direto ao usuário, as chamadas de saída do usuário serão verificadas para determinar se o número discado corresponde a um padrão de número definido na política de roteamento de voz online. Se houver uma correspondência, a chamada será roteada por meio do tronco de Roteamento Direto. Se não houver nenhuma correspondência, a chamada será roteada por meio da infraestrutura PSTN do Plano de Chamada.

Para obter mais informações, consulte [considerações sobre a política de roteamento de voz de Roteamento Direto](direct-routing-voice-routing.md#voice-routing-policy-considerations).



