---
title: Considerações de modo somente de equipes
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Preparar a atualização para o modo somente equipes da Microsoft
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39212613b7ecf86e7138c90adfbf5dc3a021ac46
ms.sourcegitcommit: 42083a67ad92d81643131c8514d82c529a1ac491
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2019
ms.locfileid: "27988236"
---
# <a name="teams-only-mode-considerations"></a>Considerações de modo somente de equipes

Se você é um administrador no seu locatário do Office 365, você verá agora a opção para atualizar para o modo equipes somente no Microsoft Teams & Skype para Business Admin Center.  Com essa funcionalidade, você pode atualizar usuários individuais, ou como alternativa, o locatário inteiro.  

Atualizando para o modo somente equipes oferece aos usuários todos os benefícios do Teams da Microsoft, o hub para o trabalho em equipe no Office 365, por meio de uma experiência de cliente único. Além disso, os usuários no modo exclusivo para equipes receberá todas as chamadas e bate-papos em equipes, independentemente se o remetente está usando o Skype para negócios ou equipes e se beneficiam de suporte de interoperabilidade e federação.

Enquanto milhares de clientes tiverem atualizados com êxito a Microsoft Teams, há algumas considerações que podem influenciar da sua organização atualização cronograma e experiência do usuário ao longo do percurso. Em particular, tendo a opção de atualização não necessariamente significa que sua organização está pronta para que essa alteração. Para a melhor experiência de usuário, confirme que as equipes atende aos seus requisitos de colaboração e comunicação, certifique-se de que sua rede está pronta para equipes de suporte e implementar seu plano de preparação do usuário antes de atualizar os usuários para equipes. 

> [!IMPORTANT]
> Se você apenas começando seu planejamento de atualização, certifique-se de examinar nossa orientação de atualização completa e recursos de planejamento. [Iniciar aqui](upgrade-introduction.md). 

**Considerações sobre coexistência**: as organizações que usam já Skype para Business Online e/ou Skype para Business Server pode introduzir equipes em seu ambiente a um ritmo que atenda às suas necessidades. As organizações podem incrementalmente distribuir equipes para um conjunto desejado de usuários conforme necessário, e os usuários que utilizam as equipes podem se comunicar com usuários que usam Skype para negócios e vice-versa. Para gerenciar essa experiência, modos de coexistência de uso administradores, que definem a experiência do cliente usuário final, o comportamento de roteamento de entrada bate-papos e chama, bem como se novas reuniões agendadas no equipes ou Skype para negócios. Os usuários podem se federar com usuários de outras organizações se o usuário for atualizado para **Equipes apenas**; No entanto, a melhor experiência é fornecida quando as equipes de usar ambos os usuários. Os usuários que são atualizados para equipes apenas ainda poderão ingressar Skype para reuniões de negócios. 

> [!NOTE]
> Os usuários que são atualizados para equipes só não podem se comunicar com usuários que estejam usando Skype para consumidor.

> [!IMPORTANT]
> Para obter mais informações sobre coexistência Consulte para [entender as equipes da Microsoft e Skype para interoperabilidade e coexistência de negócios](teams-and-skypeforbusiness-coexistence-and-interoperability.md). 

**Considerações de todo o locatário**: estamos trabalhando em permitindo que as equipes nos seguintes ambientes; No entanto, no momento, os administradores não devem atualizar todos os usuários em sua organização se seus Skype para locatário de negócios está hospedado em um dos seguintes ambientes:

 - Nuvem de comunidade governamental alta
 - DoD de nuvem de comunidade governamental
 - Office 365 operado pela 21Vianet
 - Alemanha do Office 365
 - Skype para locatário de negócios é hospedado em Coreia do Sul **e** que a organização requer dados de equipes seja armazenado na Coreia do Sul. Atualmente, as organizações com Skype para dados corporativos armazenados em Coreia do Sul que atualizar para equipes terão seus dados de equipes armazenados na região da Ásia datacenter, não na região datacenter Coreia do Sul.

**Considerações de específica do usuário**: ainda estão em evolução alguns cenários de usuário e os administradores podem decidir temporariamente adiar a atualização de determinados usuários durante a atualização de outros usuários na organização. Estamos trabalhando em:/ / Tools.ietf.org esses cenários; Por favor, monitore o site do [Mapa do Office 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) para comunicados.

| Cenário | Notas |
|----------|-------|
|Dispositivo de trabalho principal do usuário é um Mac e o usuário precisa para ver a disponibilidade dos colegas no Outlook. | Presença do Outlook em equipes ainda não é totalmente suportada para dispositivos de Mac. |
| Usuário regularmente é conduzir reuniões com clientes ou parceiros externos em diferentes regiões internacionais. | Os participantes externos cujo locatário reside em um local diferente de geo não vejo IM chat em uma reunião **federados** . Os participantes ainda poderão ingressar na reunião como usuários anônimos. |
| Usuário está realizando Skype para reuniões de transmissão de negócios. |  Enquanto as equipes live (substituindo transmissão do Skype) de eventos já está no modo de visualização público, esse usuário pode precisar permaneçam em Skype para negócios até disponibilidade geral de eventos ao vivo de equipes.
| Dispositivo primário do usuário é baseada em VDI. | |
|||

> [!IMPORTANT]
> **Lembrar**: A mudança para equipes é mais do que uma migração técnica. Uma atualização bem-sucedida avalia a prontidão técnica e a preparação do usuário final. Revise o nosso Skype para negócios equipes a [orientação de atualização](upgrade-framework.md) para obter mais informações sobre como planejar uma implementação da sua atualização às equipes.  
