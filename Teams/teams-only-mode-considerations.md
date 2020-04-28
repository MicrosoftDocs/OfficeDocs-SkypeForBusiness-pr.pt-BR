---
title: Considerações sobre o modo Teams Only (Apenas Teams)
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dearbeen
description: O administrador pode saber mais sobre como se preparar para uma atualização para o modo Microsoft Teams only no centro de administração do Microsoft Teams.
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
ms.openlocfilehash: c45a21a1aae9facd10dafe675d10955b3fa90c62
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903056"
---
# <a name="teams-only-mode-considerations"></a>Considerações sobre o modo Teams Only (Apenas Teams)

Se você for um administrador em sua organização do Office 365, verá agora a opção atualizar para o modo somente Teams no centro de administração do Microsoft Teams. Com essa funcionalidade, você pode atualizar usuários individuais ou, como alternativa, o locatário inteiro.  

A atualização para o modo somente Teams oferece aos usuários todas as vantagens do Microsoft Teams, o Hub de trabalho em equipe no Office 365, por meio de uma única experiência de cliente. Além disso, os usuários no modo apenas Teams receberão todas as chamadas e chats no Teams, independentemente de o remetente estar usando o Skype for Business ou Teams e se beneficiar do suporte a interoperabilidade e Federação.

Embora milhares de clientes tenham sido atualizados com êxito para o Microsoft Teams, há considerações que podem influenciar a linha do tempo de atualização da sua organização e a experiência do usuário ao longo do caminho. Em particular, ter a opção de atualizar não significa necessariamente que sua organização está pronta para esta mudança. Para obter a melhor experiência do usuário, confirme se o Microsoft Teams atende a seus requisitos de colaboração e comunicação, verifique se a rede está pronta para dar suporte ao Microsoft Teams e implemente seu plano de preparação do usuário antes de atualizar os usuários para o Microsoft Teams. 

> [!IMPORTANT]
> Se você estiver iniciando o planejamento da atualização, lembre-se de rever nossa [introdução ao guia de atualização do Microsoft Teams](upgrade-start-here.md) . 

**Considerações de coexistência**: as organizações que já usam o Skype for Business Online e/ou o Skype for Business Server podem introduzir equipes em seu ambiente em um ritmo que atenda às suas necessidades. As organizações podem implantar de forma incremental as equipes para um conjunto desejado de usuários, conforme necessário, e os usuários que usam equipes podem se comunicar com os usuários que usam o Skype for Business e vice-versa. Para gerenciar essa experiência, os administradores usam modos de coexistência, que definem a experiência do cliente final do usuário, o comportamento de roteamento de chats e chamadas de entrada, bem como se novas reuniões estão agendadas no Teams ou no Skype for Business. Os usuários podem federar-se com usuários em outras organizações se o usuário for atualizado somente para o Microsoft **Teams**; no entanto, a melhor experiência é fornecida quando os dois usuários usam o Microsoft Teams. Os usuários que são atualizados para o Microsoft Teams ainda podem ingressar em reuniões do Skype for Business. 

> [!NOTE]
> Os usuários que são atualizados para o Microsoft Teams não podem se comunicar com os usuários que estão usando o Skype para consumidor.

> [!IMPORTANT]
> Para obter informações mais detalhadas sobre a coexistência, consulte [entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md). 

**Considerações de todos os locatários**: estamos nos empenhando para habilitar o Microsoft Teams nos seguintes ambientes; no entanto, por enquanto, os administradores não devem atualizar os usuários em sua organização se o locatário do Skype for Business estiver hospedado em um dos seguintes ambientes:

 - Office 365 operado pela 21Vianet
 - Office 365 Alemanha
 - O locatário do Skype for Business é hospedado na Coréia do Sul **e** a organização requer que os dados do Team sejam armazenados na Coreia do Sul. Atualmente, as organizações com dados do Skype for Business armazenados na Coréia do Sul que atualizam para o Microsoft Teams terão seus dados de equipe armazenados na região do datacenter da Ásia, e não na região do centro de dados da Coreia do Sul.

**Considerações específicas do usuário**: alguns cenários do usuário ainda estão em evolução, e os administradores podem decidir adiar temporariamente a atualização de certos usuários durante a atualização de outros usuários da organização. Em particular, ainda estamos trabalhando em cenários de endereçamento para usuários cujo dispositivo principal seja baseado em VDI. Monitore o site de [mapa do Office 365](https://www.microsoft.com/microsoft-365/roadmap) para anúncios.

> [!NOTE]
> Antes de mudar para o modo Microsoft Teams, você precisa substituir ou atualizar dispositivos que não dão suporte a equipes. 

> [!IMPORTANT]
> **Lembre-se**: a mudança para o Microsoft Teams é mais do que uma migração técnica. Uma atualização bem-sucedida avalia A prontidão técnica e a prontidão do usuário final. Revise as [diretrizes de atualização](upgrade-framework.md) do Skype for Business para o Teams para obter mais informações sobre como planejar uma implementação da atualização para o Microsoft Teams.  
