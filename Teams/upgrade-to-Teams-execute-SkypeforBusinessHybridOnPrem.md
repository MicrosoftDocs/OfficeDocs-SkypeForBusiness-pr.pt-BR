---
title: Atualize para o Teams a partir de uma implantação local do Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Considerações para a atualização para o Teams a partir de uma implantação local do Skype for Business.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b41e716bb115d84b38aa5f2ead25d6347e2e0f1a
ms.sourcegitcommit: 8fb89d6226b02ba8b1f8396eb4d1a37da4608b7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "37396416"
---
![Atualize o diagrama de jornada, enfatizando os estágios de implantação e implementação](media/upgrade-banner-deployment.png "da jornada da atualização, com ênfase no estágio de implantação e implementação")

Este artigo faz parte do estágio de implantação e implementação da sua jornada de atualização. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

-   [Listamos os participantes do projeto](upgrade-enlist-stakeholders.md)
-   [Definiu o escopo do projeto](https://aka.ms/SkypetoTeams-Scope)
-   [Compreendemos a coexistência e interoperabilidade do Skype for Business e do teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Escolhido a jornada da atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Seu ambiente foi preparado](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Preparou sua organização](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Conduziu um piloto](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Atualize o Skype for Business no local para o Microsoft Teams

Se você implantou o Skype for Business Server ou o Microsoft Lync local e sua organização quer atualizar para o Microsoft Teams, siga as orientações deste artigo. Você precisa configurar a conectividade híbrida com o seu locatário do Office 365 e determinar os requisitos de coexistência se estiver movendo os usuários para o Teams em fases. 

> [!IMPORTANT]
> O Skype for Business online será desativado em 31 de julho de 2021, após o qual ele não estará mais acessível ou compatível. Para maximizar a concretização de benefícios e garantir que sua organização tenha tempo adequado para implementar a sua atualização, recomendamos que você comece sua jornada ao Microsoft Teams hoje mesmo. Lembre-se de que uma atualização bem-sucedida alinha a prontidão técnica e do usuário, portanto, não deixe de aproveitar as diretrizes contidas ao navegar na jornada para o Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Etapa 1: configurar a conectividade híbrida 

O principal pré-requisito para atualizar seus usuários locais para o Teams é configurar a conectividade híbrida para a implantação local do Skype for Business Server. 

Comece lendo [planejar conectividade híbrida](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e siga as tarefas descritas em [configurar conectividade híbrida](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Etapa 2: definir o modo de coexistência de transições (opcional)

A coexistência e interoperabilidade entre clientes do Skype for Business e do Teams e usuários são definidas pelos modos de atualização de equipe.  Por padrão, as organizações estão no modo de ilhas, o que permite que os usuários usem o Teams e os clientes do Skype for Business lado a lado.

Para uma organização migrando para o Microsoft Teams, o modo TeamsOnly é o destino final de cada usuário, mas nem todos os usuários precisam ser atribuídos TeamsOnly (ou qualquer outro modo) ao mesmo tempo.

Antes de os usuários alcançarem o modo TeamsOnly, as organizações podem usar opcionalmente qualquer um dos modos de coexistência do Skype for Business para garantir a comunicação previsível entre os usuários que estão no modo TeamsOnly e usuários que ainda não estão.  A finalidade dos modos de coexistência do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) é fornecer uma experiência simples e previsível para os usuários finais como as organizações migrando do Skype for Business para o Teams. 

Quando um usuário está em qualquer um dos modos do Skype for Business, todos os chats e chamadas recebidos são roteados para o cliente Skype for Business do usuário. Para evitar a confusão do usuário final e garantir o roteamento adequado, a chamada e a funcionalidade de chat no cliente do teams são desabilitadas quando um usuário está em qualquer um dos modos do Skype for Business. Da mesma forma, o agendamento da reunião no Teams é explicitamente desabilitado quando os usuários estão nos modos SfBOnly ou SfBWithTeamsCollab, e explicitamente habilitados quando um usuário está no modo de SfBWithTeamsCollabAndMeetings.

Dependendo dos seus requisitos, você pode atribuir o modo de coexistência apropriado com base no caminho de atualização que a sua organização escolheu. Para obter mais informações, consulte [orientação de migração e interoperabilidade para organizações que usam o Microsoft Teams com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md) e [como configurar sua coexistência e configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence).


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Etapa 3: mover os usuários do Skype for Business no local apenas para o Microsoft Teams

Em última análise, você desejará mover seus usuários para o modo TeamsOnly. Isso pode envolver uma ou duas etapas, dependendo do seu ambiente local atual.  

Para obter mais informações, consulte [mover usuários entre locais e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) e [mover usuários do local para o Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 



## <a name="phone-system-and-teams-upgrade"></a>Atualização do sistema de telefonia e do teams

Se você estiver migrando sua implantação do Skype for Business para o sistema telefônico com planos de chamada, a Microsoft será o seu provedor de rede telefônica pública comutada (PSTN). Pressupondo que você concluiu a portabilidade do número de telefone--a atualização dos usuários para o Teams fará automaticamente a chamada PSTN de entrada para o Microsoft Teams.

Se estiver migrando sua implantação do Skype for Business para o sistema telefônico, mas não estiver usando planos de chamada, você precisará fazer a transição de sua implantação do Enterprise Voice para o roteamento direto do sistema de telefone da Microsoft. Para obter mais informações, consulte [Roteamento direto do sistema telefônico](direct-routing-landing-page.md).
