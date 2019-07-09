---
title: Considerações sobre o modo Teams Only (Apenas Teams)
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Preparar-se para a atualização para o modo somente Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords: ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11378d35e042a69c2eff8f171cdc266108505774
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588115"
---
# <a name="teams-only-mode-considerations"></a>Considerações sobre o modo Teams Only (Apenas Teams)

Se você for um administrador do seu locatário do Office 365, agora verá a opção atualizar para o modo somente Teams no centro de administração do Microsoft Teams. Com essa funcionalidade, você pode atualizar usuários individuais ou, como alternativa, o locatário inteiro.  

A atualização para o modo somente Teams oferece aos usuários todas as vantagens do Microsoft Teams, o Hub de trabalho em equipe no Office 365, por meio de uma única experiência de cliente. Além disso, os usuários no modo apenas Teams receberão todas as chamadas e chats no Teams, independentemente de o remetente estar usando o Skype for Business ou Teams e se beneficiar do suporte a interoperabilidade e Federação.

Embora milhares de clientes tenham sido atualizados com êxito para o Microsoft Teams, há considerações que podem influenciar a linha do tempo de atualização da sua organização e a experiência do usuário ao longo do caminho. Em particular, ter a opção de atualizar não significa necessariamente que sua organização está pronta para esta mudança. Para obter a melhor experiência do usuário, confirme se o Microsoft Teams atende a seus requisitos de colaboração e comunicação, verifique se a rede está pronta para dar suporte ao Microsoft Teams e implemente seu plano de preparação do usuário antes de atualizar os usuários para o Microsoft Teams. 

> [!IMPORTANT]
> Se você está apenas começando a planejar a atualização, lembre-se de rever nossa orientação de atualização e planejamento de recursos. [Comece aqui](upgrade-start-here.md). 

**Considerações**de coexistência: as organizações que já usam o Skype for Business Online e/ou o Skype for Business Server podem introduzir equipes em seu ambiente em um ritmo que atenda às suas necessidades. As organizações podem implantar de forma incremental as equipes para um conjunto desejado de usuários, conforme necessário, e os usuários que usam equipes podem se comunicar com os usuários que usam o Skype for Business e vice-versa. Para gerenciar essa experiência, os administradores usam modos de coexistência, que definem a experiência do cliente final do usuário, o comportamento de roteamento de chats e chamadas de entrada, bem como se novas reuniões estão agendadas no Teams ou no Skype for Business. Os usuários podem federar-se com usuários em outras organizações se o usuário for atualizado **somente**para o Microsoft Teams; no entanto, a melhor experiência é fornecida quando os dois usuários usam o Microsoft Teams. Os usuários que são atualizados para o Microsoft Teams ainda podem ingressar em reuniões do Skype for Business. 

> [!NOTE]
> Os usuários que são atualizados para o Microsoft Teams não podem se comunicar com os usuários que estão usando o Skype para consumidor.

> [!IMPORTANT]
> Para obter informações mais detalhadas sobre a coexistência, consulte [entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md). 

**Considerações de todos**os locatários: estamos nos empenhando para habilitar o Microsoft Teams nos seguintes ambientes; no entanto, por enquanto, os administradores não devem atualizar os usuários em sua organização se o locatário do Skype for Business estiver hospedado em um dos seguintes ambientes:

 - Nuvem da Comunidade governamental alta
 - Nuvem da Comunidade governamental DoD
 - Office 365 operado pela 21Vianet
 - Office 365 Alemanha
 - O locatário do Skype for Business é hospedado na Coréia do Sul **e** a organização requer que os dados do Team sejam armazenados na Coreia do Sul. Atualmente, as organizações com dados do Skype for Business armazenados na Coréia do Sul que atualizam para o Microsoft Teams terão seus dados de equipe armazenados na região do datacenter da Ásia, e não na região do centro de dados da Coreia do Sul.

**Considerações específicas do usuário**: alguns cenários do usuário ainda estão em evolução, e os administradores podem decidir adiar temporariamente a atualização de certos usuários durante a atualização de outros usuários da organização. Estamos nos empenhando para abordar esses cenários; Monitore o site de [mapa do Office 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) para anúncios.

> [!NOTE]
> Antes de mudar para o modo Microsoft Teams, você precisa substituir ou atualizar dispositivos que não dão suporte a equipes. 

| Cenário | Observações |
|----------|-------|
|O dispositivo de trabalho principal do usuário é um Mac e o usuário precisa ver a disponibilidade dos colegas no Outlook. | A presença do Outlook no Microsoft Teams ainda não é totalmente suportada para dispositivos Mac. |
| O usuário está conduzindo regularmente reuniões com clientes ou parceiros externos em diferentes regiões internacionais. | Os participantes externos cujo locatário reside em uma localização geográfica diferente não vêem chats de mensagem instantânea durante uma reunião **federada** . Os participantes ainda podem ingressar na reunião como usuários anônimos. |
| O usuário está conduzindo reuniões de transmissão do Skype for Business. |  Embora os eventos do Team Live (substituindo a transmissão do Skype) já estejam na visualização pública, talvez seja necessário que este usuário permaneça no Skype for Business até a disponibilidade geral de eventos ao vivo do teams.
| O dispositivo primário do usuário é baseado em VDI. | |
|||

> [!IMPORTANT]
> **Lembre-se**: a mudança para o Microsoft Teams é mais do que uma migração técnica. Uma atualização bem-sucedida avalia A prontidão técnica e a prontidão do usuário final. Revise as [diretrizes de atualização](upgrade-framework.md) do Skype for Business para o Teams para obter mais informações sobre como planejar uma implementação da atualização para o Microsoft Teams.  
