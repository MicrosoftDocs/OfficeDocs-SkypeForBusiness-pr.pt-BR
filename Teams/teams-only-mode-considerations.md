---
title: Considerações sobre o modo Teams Only (Apenas Teams)
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: O administrador pode aprender sobre como se preparar para uma atualização para o modo Somente microsoft Teams no centro de administração do Microsoft Teams.
localization_priority: Normal
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
ms.openlocfilehash: 86c27d8619a436c6a77ab435cfcb2cc4133befe0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802371"
---
# <a name="teams-only-mode-considerations"></a>Considerações sobre o modo Teams Only (Apenas Teams)

Se você for um administrador em sua organização do Microsoft 365 ou office 365, agora verá a opção de atualizar para o modo Somente do Teams no centro de administração do Microsoft Teams. Com essa funcionalidade, você pode atualizar usuários individuais ou, como alternativa, todo o locatário.  

A atualização para o modo Somente teams oferece aos usuários os benefícios completos do Microsoft Teams, o hub de trabalho em equipe no Microsoft 365 ou no Office 365, por meio de uma única experiência de cliente. Além disso, os usuários no modo Somente Teams receberão todas as chamadas e chats no Teams, independentemente de o remetente usar o Skype for Business ou o Teams, e se beneficiarão do suporte à interopção e federação.

Embora milhares de clientes tenham atualizado com êxito para o Microsoft Teams, há considerações que podem influenciar a linha do tempo de atualização da sua organização e a experiência do usuário ao longo do caminho. Em particular, ter a opção de atualizar não significa necessariamente que sua organização está pronta para essa alteração. Para obter a melhor experiência do usuário, confirme se o Microsoft Teams atende a seus requisitos de colaboração e comunicação, verifique se a rede está pronta para dar suporte ao Microsoft Teams e implemente seu plano de preparação do usuário antes de atualizar os usuários para o Microsoft Teams. 

> [!IMPORTANT]
> Se você estiver apenas iniciando seu planejamento de atualização, confira nosso guia de guia de atualização do [Microsoft Teams.](upgrade-start-here.md) 

**Considerações de coexistência:** as organizações que já usam o Skype for Business Online e/ou o Skype for Business Server podem introduzir o Teams em seu ambiente em um ritmo que atenda às suas necessidades. As organizações podem lançar o Teams incrementalmente para um conjunto desejado de usuários, conforme necessário, e os usuários que usam o Teams podem se comunicar com usuários que usam o Skype for Business e vice-versa. Para gerenciar essa experiência, os administradores usam modos de coexistência, que definem a experiência do cliente do usuário final, o comportamento de roteamento de chats e chamadas de entrada, bem como se novas reuniões são agendadas no Teams ou no Skype for Business. Os usuários podem federar com usuários em outras organizações se o usuário for atualizado somente para **o Teams;** no entanto, a melhor experiência é fornecida quando ambos os usuários usam o Teams. Os usuários atualizados para o Teams Only ainda podem ingressar em reuniões do Skype for Business. 

> [!IMPORTANT]
> Para obter informações mais detalhadas sobre coexistência, consulte Compreender a coexistência e interoperabilidade do Microsoft Teams e [do Skype for Business.](teams-and-skypeforbusiness-coexistence-and-interoperability.md) Para obter mais informações sobre o Teams e o Skype (Consumidor), consulte [a interoperabilidade do Teams e do Skype.](teams-skype-interop.md)

**Considerações para todo o locatário:** estamos trabalhando para habilenciar o Teams nos seguintes ambientes; no entanto, por enquanto, os administradores não devem atualizar nenhum usuário em sua organização se o locatário do Skype for Business estiver hospedado em um dos seguintes ambientes:

 - Office 365 operado pela 21Vianet
 - Office 365 Germany
 - O locatário do Skype for  Business está hospedado na Coreia do Sul e a organização exige que os dados do Teams sejam armazenados na Coreia do Sul. Atualmente, as organizações com dados do Skype for Business armazenados na Coreia do Sul que atualizem para o Teams terão seus dados do Teams armazenados na região de datacenter da Ásia, não na região do datacenter da Coreia do Sul.

**Considerações específicas** do usuário: alguns cenários do usuário ainda estão evoluindo, e os administradores podem optar por adiar temporariamente a atualização de determinados usuários durante a atualização de outros usuários na organização. Em particular, ainda estamos trabalhando em cenários de endereçamento para usuários cujo dispositivo principal é baseado em VDI. Monitore o site de mapa do [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para ver comunicados.

> [!NOTE]
> Antes de mudar para o modo Somente do Teams, você precisa substituir ou atualizar dispositivos que não são compatíveis com o Teams. 

> [!IMPORTANT]
> **Lembre-se:** a migração para o Teams é mais do que uma migração técnica. Uma atualização bem-sucedida avalia a prontidão técnica e a prontidão do usuário final. Revise nossas diretrizes de atualização do Skype for Business para [o](upgrade-framework.md) Teams para obter mais informações sobre como planejar uma implementação da atualização para o Teams.  
