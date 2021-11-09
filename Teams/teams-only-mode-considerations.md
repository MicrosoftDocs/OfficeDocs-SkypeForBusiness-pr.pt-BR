---
title: Considerações sobre o modo Teams Only (Apenas Teams)
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: O administrador pode aprender sobre como se preparar para uma atualização para Microsoft Teams modo Somente no Microsoft Teams de administração.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c0c3f6715c1dc1ebce70f108b4634055b00f56c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855135"
---
# <a name="teams-only-mode-considerations"></a>Considerações sobre o modo Teams Only (Apenas Teams)

Os administradores de Microsoft 365 ou Office 365 podem atualizar usuários individuais ou o locatário inteiro para Teams modo Somente.  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

A atualização para o modo Somente Teams oferece aos usuários os benefícios completos do Microsoft Teams, o hub para trabalho em equipe no Microsoft 365 ou Office 365, por meio de uma única experiência do cliente. Os usuários no modo somente Teams receberão todas as chamadas e chats no Teams, independentemente de o remetente usar Skype for Business ou Teams e se beneficiarão do suporte de interop e federação.

Embora milhares de clientes tenham sido atualizados com êxito para Microsoft Teams, há considerações que podem influenciar a linha do tempo de atualização da sua organização e a experiência do usuário ao longo do caminho. Para obter a melhor experiência do usuário, confirme se o Microsoft Teams atende a seus requisitos de colaboração e comunicação, verifique se a rede está pronta para dar suporte ao Microsoft Teams e implemente seu plano de preparação do usuário antes de atualizar os usuários para o Microsoft Teams. 

> [!IMPORTANT]
> Se você está apenas iniciando seu planejamento de atualização, não deixe de revisar nosso guia De início [Microsoft Teams atualização.](upgrade-start-here.md) 

**Considerações de coexistência:** as organizações que já usam o Skype for Business Online e/ou Skype for Business Server podem introduzir Teams em seu ambiente em um ritmo que atenda às suas necessidades. As organizações podem Teams um conjunto desejado de usuários, conforme necessário, e os usuários que usam o Teams podem se comunicar com usuários que usam Skype for Business e vice-versa. Para gerenciar essa experiência, os administradores usam modos de coexistência, que definem a experiência do cliente do usuário final, o comportamento de roteamento de chats e chamadas de entrada e se novas reuniões são agendadas em Teams ou Skype for Business. Os usuários podem federar com usuários em outras organizações se o usuário for atualizado para Teams **Somente**; no entanto, a melhor experiência é fornecida quando ambos os usuários usam Teams. Os usuários que são atualizados para o Teams Somente ainda podem ingressar Skype for Business reuniões. 

> [!IMPORTANT]
> Para obter informações mais detalhadas sobre coexistência, consulte [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md). Para obter mais informações sobre Teams e Skype (Consumidor), consulte [Teams e Skype interoperabilidade](teams-skype-interop.md).


**Considerações específicas** do usuário : alguns cenários do usuário ainda estão evoluindo, e os administradores podem optar por adiar temporariamente a atualização de determinados usuários enquanto atualiza outros usuários na organização. Em particular, ainda estamos trabalhando em cenários de endereçamento para usuários cujo dispositivo principal é baseado em VDI. Para anúncios de site, monitore [o Microsoft 365 mapa](https://www.microsoft.com/microsoft-365/roadmap).

> [!NOTE]
> Antes de mover para Teams modo Somente, você precisa substituir ou atualizar dispositivos que não suportam Teams. 

> [!IMPORTANT]
> **Lembre-se**: a mudança para Teams é mais do que uma migração técnica. Uma atualização bem-sucedida avalia a preparação técnica e a preparação do usuário final. Revise nossa Skype for Business para Teams [de](upgrade-framework.md) atualização para obter mais informações sobre como planejar uma implementação da atualização para Teams.  
