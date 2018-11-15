---
title: Definindo as configurações de atualização e coexistência
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: bjwhalen
search.appverid: MET150
description: Este artigo ajudará você a escolher o modo de coexistência e definir outras configurações de coexistência.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 28d5cd4a967245f1df18530d58ed1c2679e910e3
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531858"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>Definindo as configurações de atualização e coexistência

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Quando você atualiza seu Skype para os usuários corporativos usem equipes, você tem várias opções para ajudá-lo a torná-lo um processo direto para seus usuários. Você tem a opção para tornar a coexistência e atualizar as configurações para todos os usuários em sua organização ao mesmo tempo, ou você pode fazer alterações de configurações para um único ou um conjunto de usuários em sua organização. Observe que as versões mais antigas do Skype para clientes corporativos não podem atendê-essas configurações. Para obter mais informações sobre Skype para as versões de cliente de negócios, vá para o [Skype para negócios baixa e atualiza a página](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates). 

Você pode obter uma compreensão melhor dos tipos de modos que estão disponíveis para você lendo [entender as equipes da Microsoft e Skype para interoperabilidade e coexistência de negócios](teams-and-skypeforbusiness-coexistence-and-interoperability.md).  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Definir opções de atualização para todos os usuários em sua organização

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft & Skype para Business Admin Center**

1. No painel de navegação esquerdo, vá para **configurações de toda a organização** > **equipes de atualização**. 

2. Na parte superior da página **atualização de equipes** , faça as seguintes alterações se eles funcionará para você.
    - Defina o modo de **coexistência** .
        - **Ilhas** - Use esta configuração se você quiser que os usuários possam usar ambos os Skype para negócios e equipes simultaneamente.
        - **Skype para negócios apenas** - Use essa configuração se quiser que os usuários só use Skype para negócios.
        - **Somente as equipes** (no modo de visualização para algumas organizações) - Use esta configuração se quiser que os usuários usem somente equipes. Observe que mesmo com essa configuração, os usuários ainda poderão ingressar reuniões hospedadas no Skype para negócios.
    - Defina **Notificar Skype para usuários corporativos que equipes está disponível para atualização**. Se você ativar isso, ele informará o Skype para usuários comerciais que eles breve serão atualizados para o aplicativo de equipes.
    - Defina o **aplicativo preferencial para os usuários ingressem Skype para reuniões de negócios**. Essa configuração determina qual app é usada para ingressar em Skype para reuniões de negócios e é respeitada independente do valor do modo de coexistência.
      - **Aplicativo de reuniões do Skype**
      - **Skype for Business com os recursos limitados**
    - Defina como **baixar o aplicativo de equipes em segundo plano para Skype para usuários comerciais**.  Essa configuração silenciosamente baixa o aplicativo de equipes para usuários que executam o Skype for Business no Windows. Ela é respeitada somente se o modo de coexistência para o usuário está equipes somente ou se as notificações de atualização pendente estão habilitadas no Skype for Business.
3. Clique em **Salvar** depois de fazer as alterações.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Definir opções de atualização de um único usuário em sua organização

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft & Skype para Business Admin Center**

1. No painel de navegação esquerdo, vá para **usuários**e, em seguida, selecione o usuário na lista. 
2. Na guia **conta** para o usuário, em **atualização de equipes**, clique em **Editar**.
3. Você pode definir o **modo de coexistência**. Escolha entre as seguintes opções:
     - **Configurações de toda a organização usar** - Use esta configuração se você quiser que o usuário a usar as definições nas configurações de **toda a organização** . 
     - **Ilhas** - Use esta configuração se quiser que o usuário seja capaz de usar ambos os Skype para equipes e de negócios. 
     - **Skype para negócios apenas** - Use esta configuração se quiser que o usuário utilize Skype para negócios. 
     - **Equipes apenas** - Use esta configuração se quiser que o usuário use apenas as equipes. O usuário ainda poderá ingressar Skype para reuniões de negócios.
4. Se você selecionar qualquer **modo de coexistência** que não seja de **toda a organização usar configurações**, você tem a opção para habilitar notificações no Skype do usuário para o aplicativo de negócios que atualizar para equipes estarão disponíveis em breve. É possível habilitar essa notificação para o usuário, ativando a opção **notificar o Skype para o usuário de negócios** .
5. Clique em **Salvar** depois de fazer as alterações.

### <a name="related-topics"></a>Tópicos relacionados
[Planejar a jornada](upgrade-plan-journey.md)

[Entender a coexistência e atualizar jornada Skype for Business e equipes](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Diretrizes de migração e interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](migration-interop-guidance-for-teams-with-skype.md)
