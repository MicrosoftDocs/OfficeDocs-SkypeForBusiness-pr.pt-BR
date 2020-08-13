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
ms.openlocfilehash: 1981640ab06d00e7895e11c0e15adf7555577908
ms.sourcegitcommit: b23d3d583910aa21a62ea69b554ab614c1ae8079
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648602"
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

Se você implantou o Skype for Business Server ou o Microsoft Lync local e sua organização quer atualizar para o Microsoft Teams, siga as orientações deste artigo. Você precisa configurar a conectividade híbrida com sua organização do Microsoft 365 ou do Office 365 e determinar os requisitos de coexistência se estiver movendo os usuários para o Teams em fases. 

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

Em última análise, você desejará mover seus usuários para o modo TeamsOnly. Isso pode envolver uma ou duas etapas, dependendo do seu ambiente local.  

Para obter mais informações, consulte [mover usuários entre locais e a nuvem](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) e [mover usuários do local para o Microsoft Teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Etapa 4: desativar híbrido para concluir a migração para a nuvem

Depois de mover todos os usuários no local para a nuvem, você pode encerrar a implantação do Skype for Business local. Para obter mais informações, consulte [desabilitar a migração híbrida para concluir a nuvem](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).


## <a name="phone-system-and-pstn-connectivity-options"></a>Opções de conectividade PSTN e do sistema telefônico

O sistema telefônico com Teams tem suporte depois que o usuário está no modo TeamsOnly. (Se o usuário estiver no modo de ilhas, o sistema telefônico só tem suporte no Skype for Business.) 

### <a name="pstn-connectivity-options"></a>Opções de conectividade PSTN

Ao considerar as opções de conectividade PSTN (rede telefônica pública comutada), há dois cenários possíveis ao migrar do Skype for Business no local para o modo TeamsOnly:

- Um usuário do Skype for Business no local com o Enterprise Voice, que se moverá para online e usando um plano de chamadas da Microsoft. Migrar este usuário para o Microsoft Teams requer mover a conta do Skype for Business no local para a nuvem e coordenar essa movimentação com uma a porta do número de telefone do usuário para um plano de chamadas da Microsoft ou B) atribuir um novo número de assinante de regiões disponíveis.  Para obter mais informações, consulte [o Skype for Business Server no local, com o Enterprise Voice, para o plano de chamadas da Microsoft](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Um usuário do Skype for Business no local com o Enterprise Voice, que será movido para online e mantendo a conectividade PSTN local. Migrar este usuário para o Teams requer mover a conta do Skype for Business no local para a nuvem e coordenar essa movimentação com a migração do usuário para o roteamento direto. Para obter mais informações, consulte o [Skype for Business Server no local, com o Enterprise Voice, para o roteamento direto](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).
