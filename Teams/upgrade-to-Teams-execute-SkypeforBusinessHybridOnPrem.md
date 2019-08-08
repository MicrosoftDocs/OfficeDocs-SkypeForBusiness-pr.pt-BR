---
title: Atualizar para o Microsoft Teams de uma implantação híbrida ou local do Skype for Business ‒ Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Considerações para a atualização do teams a partir de uma implantação híbrida ou local do Skype for Business.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 873e15e5b1f64e82889bfda6fa30c5b9394dcf3a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235867"
---
![Atualize o diagrama de viagem, enfatizando implantação e implementação] (media/upgrade-banner-deployment.png "Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação")

Este artigo faz parte do estágio de implantação e implementação da sua jornada de atualização. Antes de prosseguir, confirme que você concluiu as seguintes atividades:

-   [Listamos os participantes do projeto](upgrade-enlist-stakeholders.md)
-   [Definiu o escopo do projeto](https://aka.ms/SkypetoTeams-Scope)
-   [Compreendemos a coexistência e interoperabilidade do Skype for Business e do teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Escolhido a jornada da atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Seu ambiente foi preparado](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Preparou sua organização](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Conduziu um piloto](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a>Atualize para o Teams a partir de uma implantação híbrida ou local do Skype for Business

Siga as orientações neste artigo se você tiver implantado o Skype for Business ou o Microsoft Lync local e sua organização quiser atualizar para o Microsoft Teams de forma seletiva, usando vários modos de coexistência, ou todos. A primeira etapa é configurar a conectividade híbrida com o seu locatário do Office 365 e, em seguida, mover os usuários para o Skype for Business Online e atribuir a eles o modo de atualização e a coexistência apropriada. 

> [!IMPORTANT]
> O Skype for Business online será desativado em 31 de julho de 2021, após o qual ele não estará mais acessível ou compatível. Para maximizar a concretização de benefícios e garantir que sua organização tenha tempo adequado para implementar a sua atualização, recomendamos que você comece sua jornada ao Microsoft Teams hoje mesmo. Lembre-se de que uma atualização bem-sucedida alinha a prontidão técnica e do usuário, portanto, não deixe de aproveitar as diretrizes contidas ao navegar na jornada para o Microsoft Teams.

## <a name="step-1-deploy-hybrid-connectivity"></a>Etapa 1: implantar a conectividade híbrida 

O principal pré-requisito para atualizar os usuários para o Microsoft Teams é implantar a conectividade híbrida. Isso pode envolver a implantação de uma nova conectividade externa para a implantação existente do Skype for Business ou do Lync, ou simplesmente configurar uma relação híbrida com o seu locatário do Office 365. 

Para obter mais informações, consulte [implantar conectividade híbrida entre o Skype for Business Server e o Skype for Business online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-move-users-to-skype-for-business-online"></a>Etapa 2: mover usuários para o Skype for Business Online 

Depois de concluir a configuração híbrida, mova os usuários para o Skype for Business online. 

Para obter mais informações, consulte [mover usuários do local para o Skype for Business online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online). 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>Etapa 3: atribuir um modo de coexistência e atualização

Depois de mover os usuários para o Skype for Business Online, você pode atribuir a eles o modo de coexistência apropriado com base na jornada de atualização que a sua organização escolheu. Para obter mais informações, consulte [definindo suas configurações de coexistência e atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)a coexistência.

> [!NOTE]
> Com o Skype for Business Server 2019 e uma atualização cumulativa futura do Skype for Business Server 2015, você poderá executar a etapa 2 (movendo usuários para o Skype for Business online) e a etapa 3 (atualizar usuários para o Microsoft Teams) em uma única etapa. Mais informações serão fornecidas após o lançamento do Skype for Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Atualização do sistema de telefonia e do teams

Se você estiver fazendo a transição da sua implantação híbrida do Skype for Business para o sistema telefônico com planos de chamadas e a Microsoft for o seu provedor de rede telefônica pública comutada (PSTN) e presumir que você concluiu a portabilidade do número de telefone, a atualização dos usuários para O Microsoft Teams fará a transição de chamadas PSTN de entrada automaticamente para o Microsoft Teams.

Se os planos de chamada não estiverem disponíveis, você precisará fazer a transição de sua implantação do Enterprise Voice para o roteamento direto do Microsoft Phone System. Para atualizar os usuários para o Microsoft Teams, consulte [considerações adicionais sobre o roteamento direto do sistema telefônico](2-envision-make-my-service-decisions-direct-routing.md).
