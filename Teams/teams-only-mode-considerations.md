---
title: Considerações sobre o modo Teams Only (Apenas Teams)
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Administração saber mais sobre como se preparar para uma atualização para o modo somente do Microsoft Teams no centro de administração do Microsoft Teams.
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
ms.openlocfilehash: b80a563d6d3938a597e57aab4ac93e41df976d32
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605860"
---
# <a name="teams-only-mode-considerations"></a>Considerações sobre o modo Teams Only (Apenas Teams)

Os administradores do Microsoft 365 ou Office 365 podem atualizar usuários individuais ou todo o locatário para o modo Somente Teams.  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

Atualizar para o modo Somente teams oferece aos usuários os benefícios completos do Microsoft Teams, o hub para trabalho em equipe no Microsoft 365 ou Office 365, por meio de uma única experiência de cliente. Os usuários no modo Somente Teams receberão todas as chamadas e chats no Teams, independentemente de o remetente usar o Skype for Business ou o Teams, e se beneficiarão do suporte de interoperabilidade e federação.

Embora milhares de clientes tenham atualizado com êxito para o Microsoft Teams, há considerações que podem influenciar a linha do tempo de atualização e a experiência do usuário da sua organização ao longo do caminho. Para obter a melhor experiência do usuário, confirme se o Microsoft Teams atende a seus requisitos de colaboração e comunicação, verifique se a rede está pronta para dar suporte ao Microsoft Teams e implemente seu plano de preparação do usuário antes de atualizar os usuários para o Microsoft Teams. 

> [!IMPORTANT]
> Se você estiver apenas iniciando seu planejamento de atualização, não deixe de examinar nossa Introdução [ao guia de atualização do Microsoft Teams](upgrade-start-here.md) . 

**Considerações de coexistência**: as organizações que já usam o Skype for Business Online e/ou Skype for Business Server podem introduzir o Teams em seu ambiente em um ritmo que atenda às suas necessidades. As organizações podem distribuir incrementalmente o Teams para um conjunto desejado de usuários, conforme necessário, e os usuários que usam o Teams podem se comunicar com usuários que usam Skype for Business e vice-versa. Para gerenciar essa experiência, os administradores usam modos de coexistência, que definem a experiência do cliente do usuário final, o comportamento de roteamento de chats e chamadas de entrada e se novas reuniões são agendadas no Teams ou Skype for Business. Os usuários podem federar com usuários em outras organizações se o usuário for atualizado somente para **o Teams**; no entanto, a melhor experiência é fornecida quando ambos os usuários usam o Teams. Os usuários que são atualizados apenas para o Teams ainda podem ingressar Skype for Business reuniões. 

> [!IMPORTANT]
> Para obter informações mais detalhadas sobre coexistência, consulte [Entender o Microsoft Teams e Skype for Business coexistência e interoperabilidade](teams-and-skypeforbusiness-coexistence-and-interoperability.md). Para obter mais informações sobre o Teams e o Skype (Consumidor), consulte [a interoperabilidade do Teams e do Skype](teams-skype-interop.md).


**Considerações específicas do** usuário: alguns cenários de usuário ainda estão evoluindo e os administradores podem decidir adiar temporariamente a atualização de determinados usuários ao atualizar outros usuários na organização. Em particular, ainda estamos trabalhando em cenários de endereçamento para usuários cujo dispositivo primário é baseado em VDI. Para comunicados do site, monitore o [Roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap).

> [!NOTE]
> Antes de passar para o modo Somente teams, você precisa substituir ou atualizar dispositivos que não dão suporte ao Teams. 

> [!IMPORTANT]
> **Lembre-se**: a mudança para o Teams é mais do que uma migração técnica. Uma atualização bem-sucedida avalia a preparação técnica e a preparação do usuário final. Examine nossas diretrizes Skype for Business [atualização](upgrade-framework.md) do Teams para obter mais informações sobre como planejar uma implementação da atualização para o Teams.  
