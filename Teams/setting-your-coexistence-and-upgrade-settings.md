---
title: Definir suas configurações de coexistência e atualização
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Saiba como definir as configurações de coexistência e atualização para todos os usuários da sua organização de uma só vez ou para um único ou conjunto de usuários em sua organização.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 489f5315df8c818fd674e30fdaef7c057e9a8ff3
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536492"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Definir suas configurações de coexistência e atualização


Quando você atualiza seus Skype for Business usuários para usar Teams, você tem várias opções para ajudá-lo a tornar um processo contínuo para seus usuários. Você tem a opção de fazer configurações de coexistência e atualização para todos os usuários em sua organização de uma só vez ou pode fazer alterações de configurações para um único ou conjunto de usuários em sua organização. Observe que as versões mais antigas Skype for Business clientes podem não honrar essas configurações. Para obter mais informações sobre Skype for Business versões do cliente, acesse a página Skype for Business [downloads e atualizações.](/skypeforbusiness/software-updates) 

Você pode obter uma melhor compreensão dos modos que estão disponíveis para você lendo Entender Microsoft Teams e [Skype for Business coexistência](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e interoperabilidade ou coexistência com Skype for Business [.](coexistence-chat-calls-presence.md)  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Definir opções de atualização para todos os usuários em sua organização

 **Usando o centro de administração do Microsoft Teams**

1. No centro [Microsoft Teams de](https://admin.teams.microsoft.com/)administração , na navegação à esquerda, acesse **Configurações** em toda  >  **a organização Teams atualização**. 

2. Na parte superior da página de **atualização Teams,** modifique as opções a seguir conforme desejado.

    - De definir **o modo coexistência.**
        - **Ilhas** - Use essa configuração se quiser que os usuários sejam capazes de usar o Skype for Business e Teams simultaneamente.
        - **Skype for Business -** Use essa configuração se quiser que seus usuários usem apenas Skype for Business.
        - **Skype for Business com Teams** colaboração - Use essa configuração se quiser que seus usuários usem Skype for Business além de usar o Teams para colaboração em grupo (canais).
        - **Skype for Business** com Teams colaboração e reuniões - Use essa configuração se quiser que seus usuários usem o Skype for Business, além de usar o Teams para colaboração em grupo (canais) e reuniões Teams reuniões.
        - **Teams somente** - Use essa configuração se quiser que seus usuários usem apenas Teams. Observe que, mesmo com essa configuração, os usuários ainda podem participar de reuniões hospedadas em Skype for Business.

          > [!IMPORTANT]
          > Você só pode atribuir o modo TeamsOnly a todo o locatário depois que ambas as etapas a seguir foram concluídas:
          >  - Todos os usuários locais foram movidos para Teams somente usando Move-CsUser no Skype for Business Server de ferramentas local.
          >  - Você atualizou quaisquer registros DNS Skype for Business para apontar para Microsoft 365. 
          >
          > Para obter mais detalhes, consulte [Disable your hybrid configuration to complete migration to Teams Only](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).
        
    - Definir **Notificar Skype for Business usuários que Teams está disponível para atualização**. Se você ativar isso, ele dirá aos usuários Skype for Business que eles serão atualizados em breve para o Teams aplicativo.

    - De definir **o aplicativo Preferencial para que os usuários participem Skype for Business reuniões.** Essa configuração determina qual aplicativo é usado para ingressar Skype for Business reuniões e é atendida independentemente do valor do modo de coexistência.
      - **Skype Aplicativo reuniões**
      - **Skype for Business recursos limitados**

    - Definir se deve **baixar o aplicativo Teams em segundo** plano para Skype for Business usuários .  Essa configuração baixa silenciosamente o aplicativo Teams para usuários que executam Skype for Business no Windows. Ela só será atendida se o modo de coexistência do usuário for Teams somente ou se as notificações da atualização pendente estão habilitadas Skype for Business.

3. Clique **em Salvar** depois de fazer suas alterações.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Definir opções de atualização para um único usuário em sua organização

 **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Usuários** e selecione o usuário na lista. 
2. Na guia **Conta** do usuário, em Teams **atualização,** clique em **Editar**.
3. Você pode definir o **modo coexistência**. Modos diferentes do Teams Somente podem ser aplicados aos usuários que estão no Skype for Business Server local e, por outro lado, somente os usuários que estão na nuvem podem ter o modo TeamsOnly.  Escolha entre as seguintes opções:
     - **Use configurações em toda a** organização - Use essa configuração se quiser que o usuário use as configurações nas **configurações em** toda a organização. 
     - **Ilhas** - Use essa configuração se quiser que o usuário possa usar o Skype for Business e Teams. 
     - **Skype for Business somente** - Use essa configuração se quiser que o usuário use Skype for Business.
     - **Skype for Business com Teams colaboração** - Use essa configuração se quiser que o usuário use Skype for Business além de usar o Teams para colaboração em grupo (canais).
      - **Skype for Business** com Teams colaboração e reuniões - Use essa configuração se quiser que o usuário use o Skype for Business além de usar o Teams para colaboração em grupo (canais) e reuniões Teams.
     - **Teams -** Use essa configuração se quiser que o usuário use somente Teams. O usuário ainda poderá participar de Skype for Business reuniões.
4. Se você selecionar qualquer modo de **coexistência** diferente de Usar configurações em toda a **organização,** você terá a opção de habilitar notificações no aplicativo Skype for Business do usuário que atualize para Teams em breve. Você pode habilitar essa notificação para o usuário ativando a opção **Notificar o Skype for Business** usuário.
5. Clique **em Salvar** depois de fazer suas alterações.

### <a name="related-topics"></a>Tópicos relacionados
[Planejar a jornada](upgrade-plan-journey.md)

[Entenda a coexistência e a jornada de atualização para Skype for Business e Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Desative seu ambiente de Skype for Business local](/skypeforbusiness/hybrid/decommission-on-prem-overview)
