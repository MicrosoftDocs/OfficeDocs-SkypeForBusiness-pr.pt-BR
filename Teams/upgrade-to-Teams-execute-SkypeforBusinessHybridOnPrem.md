---
title: Atualizar do Skype for Business local para o Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Saiba como atualizar sua organização para o Microsoft Teams a partir de uma implantação local do Skype for Business.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 491f4132d5f5c4c4e5d8215d0d48277a864cf064
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905213"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Atualize o Skype for Business no local para o Microsoft Teams

![Atualize o diagrama de viagem, enfatizando implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação")

Este artigo faz parte do estágio de implantação e implementação da sua jornada de atualização. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

-   [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
-   [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
-   [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Seu ambiente foi preparado](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Preparou sua organização](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Conduziu um piloto](https://aka.ms/SkypeToTeams-Pilot)

Se você implantou o Skype for Business Server ou o Microsoft Lync local e sua organização quer atualizar para o Microsoft Teams, siga as orientações deste artigo. Você precisa configurar a conectividade híbrida com sua organização do Office 365 e determinar os requisitos de coexistência se estiver movendo os usuários para o Teams em fases. 

> [!IMPORTANT]
> O Skype for Business Online será desativado em 31 de julho de 2021, e depois disso não estará mais acessível nem terá suporte. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams. Lembre-se de que uma atualização bem-sucedida alinha a prontidão técnica e do usuário, portanto, não deixe de aproveitar as diretrizes contidas ao navegar na jornada para o Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Etapa 1: configurar a conectividade híbrida 

O principal pré-requisito para atualizar seus usuários locais para o Teams é configurar a conectividade híbrida para a implantação local do Skype for Business Server. 

Comece lendo [planejar conectividade híbrida](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e siga as tarefas descritas em [configurar conectividade híbrida](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).


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
