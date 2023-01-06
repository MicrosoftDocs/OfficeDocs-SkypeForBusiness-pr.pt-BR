---
title: Planos e roteamento do Microsoft Teams Dial
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
- highpri
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
description: Discar planos e roteamento no Microsoft Teams
ms.openlocfilehash: 1d8c4ed750369c6b5bf393ebceae850703f89395
ms.sourcegitcommit: 0a2476471713e1eba791060db2c8c888484033a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2023
ms.locfileid: "69722111"
---
# <a name="microsoft-teams-dial-plans-and-routing"></a>Planos e roteamento do Microsoft Teams Dial

Os artigos nesta seção descrevem planos de discagem e roteamento de chamadas no Microsoft Teams. 

- [O que são planos de discagem](what-are-dial-plans.md)
- [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md)
- [Rotear chamadas para números não atribuídos](routing-calls-to-unassigned-numbers.md)

Os artigos nesta seção se aplicam a todas as opções para se conectar à PSTN (Rede Telefônica Comutada Pública): Plano de Chamada, Conexão do Operador, Teams Phone Mobile e Roteamento Direto. Para obter mais informações sobre todas as opções de conectividade PSTN, confira [Opções de conectividade PSTN](pstn-connectivity.md).

Se você escolher Plano de Chamada, Conexão de Operador ou Teams Phone Mobile, a maioria do roteamento de chamadas será tratada pela Microsoft ou pelo provedor. O Roteamento Direto, no entanto, requer etapas adicionais para configurar o roteamento de chamadas. 

Para Roteamento Direto, você deve configurar o roteamento de chamadas especificando as rotas de voz e atribuindo políticas de roteamento de voz aos usuários. Você pode configurar planos de discagem para tradução numérica no nível do tronco para garantir a interoperabilidade com os SBCs (Controladores de Borda de Sessão). Para obter mais informações, consulte [Configurar roteamento de voz para Roteamento Direto](direct-routing-voice-routing.md), [Gerenciar políticas de roteamento de voz](manage-voice-routing-policies.md) e [Traduzir números de telefone](direct-routing-translate-numbers.md).

Esteja ciente de que você pode atribuir uma política de roteamento de voz online de Roteamento Direto aos usuários do Plano de Chamada e do Operator Connect. Talvez você queira fazer isso, por exemplo, para permitir que os usuários discem diretamente para um call center. Você pode configurar um tronco de Roteamento Direto para o call center.

Se um usuário tiver uma licença de Plano de Chamada, por exemplo, as chamadas de saída desse usuário serão roteadas automaticamente pela infraestrutura PSTN do Plano de Chamada da Microsoft. Se você configurar e atribuir uma política de roteamento de voz online de Roteamento Direto ao usuário, as chamadas de saída do usuário serão verificadas para determinar se o número discado corresponde a um padrão de número definido na política de roteamento de voz online. Se houver uma correspondência, a chamada será roteada pelo tronco de Roteamento Direto. Se não houver correspondência, a chamada será roteada por meio da infraestrutura PSTN do Plano de Chamada.

Para obter mais informações, confira [Considerações sobre a política de roteamento de voz do Roteamento Direto](direct-routing-voice-routing.md#voice-routing-policy-considerations).



