---
title: Atualizar o Skype for Business local para o Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
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
ms.openlocfilehash: 961ac4f9bcce3c24d62ec1c744d2c9cd15e2ee1b
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578164"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Atualizar do Skype for Business local para o Teams

![Diagrama de atualização da jornada, enfatizando Implantação e Implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio de Implantação e Implementação")

Este artigo faz parte da etapa implantação e implementação da sua jornada de atualização. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

-   [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
-   [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
-   [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Preparou seu ambiente](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Preparar sua organização](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Piloto conduzido](https://aka.ms/SkypeToTeams-Pilot)

Se você implantou o Skype for Business Server ou o Microsoft Lync local e sua organização deseja atualizar para o Teams, siga as orientações neste artigo. Você precisa configurar a conectividade híbrida com sua organização do Microsoft 365 ou do Office 365 e determinar os requisitos de coexistência se você estiver movendo os usuários para o Teams em fases. 

> [!IMPORTANT]
> O Skype for Business Online será desativado em 31 de julho de 2021, e depois disso não estará mais acessível nem terá suporte. Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams. Lembre-se de que uma atualização bem-sucedida alinha a preparação técnica e do usuário, portanto, lembre-se de aproveitar as orientações aqui enquanto navega para o Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Etapa 1: configurar a conectividade híbrida 

O principal pré-requisito para atualizar os usuários locais para o Teams é configurar a conectividade híbrida para a implantação local do Skype for Business Server. 

Comece lendo Plano [de conectividade híbrida](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e siga as tarefas descritas em [Configurar conectividade híbrida.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Etapa 2: Definir o modo de coexistência transicional (opcional)

A coexistência e a interoperabilidade entre clientes e usuários do Skype for Business e do Teams são definidas pelos modos de Atualização do Teams.  Por padrão, as organizações estão no modo Ilhas, o que permite que os usuários usem os clientes do Teams e do Skype for Business lado a lado.

Para uma organização que está mudando para o Teams, o modo TeamsOnly é o destino final para cada usuário, embora nem todos os usuários precisem ter o TeamsOnly (ou qualquer outro modo) ao mesmo tempo.

Antes de os usuários chegarem ao modo TeamsOnly, as organizações podem usar opcionalmente qualquer um dos modos de coexistência do Skype for Business para garantir uma comunicação previsível entre usuários que estão no modo TeamsOnly e usuários que ainda não estão.  A finalidade dos modos de coexistência do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) é fornecer uma experiência simples e previsível para os usuários finais à medida que as organizações migram do Skype for Business para o Teams. 

Quando um usuário está em qualquer um dos modos do Skype for Business, todos os chats de entrada e chamadas são roteados para o cliente Skype for Business do usuário. Para evitar confusão do usuário final e garantir o roteamento adequado, as chamadas e a funcionalidade de chat no cliente do Teams são desabilitadas quando um usuário está em qualquer um dos modos do Skype for Business. Da mesma forma, o agendamento de reunião no Teams é explicitamente desabilitado quando os usuários estão nos modos SfBOnly ou SfBWithTeamsCollab e explicitamente habilitados quando um usuário está no modo SfBWithTeamsCollabAndMeetings.

Dependendo dos seus requisitos, você pode atribuir o modo de coexistência apropriado com base no caminho de atualização que sua organização escolheu. Para obter mais informações, consulte as diretrizes de migração e [interoperabilidade](migration-interop-guidance-for-teams-with-skype.md) para as organizações que usam o Teams em conjunto com o Skype for Business e como definir suas configurações de [coexistência e atualização.](https://aka.ms/SkypeToTeams-SetCoexistence)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Etapa 3: mover usuários do Skype for Business local para o Teams Somente

Em última análise, você vai querer mover seus usuários para o modo TeamsOnly. Isso pode envolver uma ou duas etapas, dependendo do ambiente local.  

Para obter mais informações, consulte [Mover usuários](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) entre o local e a nuvem e Mover usuários do local para [o Teams.](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Etapa 4: desabilitar a migração híbrida para concluir a migração para a nuvem

Depois de ter movido todos os usuários do local para a nuvem, você pode desativá-la no local da implantação do Skype for Business. Para obter mais informações, consulte [Desabilitar a migração híbrida para concluir a migração para a nuvem.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>Opções de conectividade PSTN e sistema telefônico

O Sistema telefônico com o Teams tem suporte depois que o usuário está no modo TeamsOnly. (Se o usuário estiver no modo Ilhas, o Sistema telefônico só tem suporte no Skype for Business.) 

### <a name="pstn-connectivity-options"></a>Opções de conectividade PSTN

Ao considerar as opções de conectividade PSTN (Rede Telefônica Pública Comutado), há dois cenários possíveis ao mudar do Skype for Business local para o modo TeamsOnly:

- Um usuário no Skype for Business local com o Enterprise Voice, que vai se mudar para online e usar um plano de Chamada da Microsoft. Migrar esse usuário para o Teams requer mover a conta do Skype for Business local do usuário para a nuvem e coordenar essa movimentação com A) a porta do número de telefone desse usuário para um Plano de Chamada da Microsoft ou B) atribuindo um novo número de assinante de regiões disponíveis.  Para obter mais informações, consulte Do Skype for Business Server local, com [o Enterprise Voice, para o Plano de Chamada da Microsoft.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)

- Um usuário no Skype for Business local com o Enterprise Voice, que se move para a conectividade PSTN local e online. Migrar esse usuário para o Teams requer mover a conta do Skype for Business local do usuário para a nuvem e coordenar essa movimentação com a migração do usuário para o Roteamento Direto. Para obter mais informações, consulte Do Skype for Business Server local, com [o Enterprise Voice, para o Roteamento Direto.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)
