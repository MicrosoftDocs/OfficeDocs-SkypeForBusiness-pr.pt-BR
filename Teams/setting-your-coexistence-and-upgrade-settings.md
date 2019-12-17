---
title: Definir suas configurações de coexistência e atualização
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Este artigo vai ajudá-lo a escolher o modo de coexistência e definir outras configurações de coexistência.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 674c4c43e1fe99639c6e8bfd9665e1bf0755e1ba
ms.sourcegitcommit: dc240b123efb03d5ab0545d650a973bf60d04506
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2019
ms.locfileid: "40069372"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a>Definir suas configurações de coexistência e atualização

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Ao atualizar os usuários do Skype for Business para usar o Microsoft Teams, você tem várias opções para ajudá-lo a fazer dele um processo perfeito para seus usuários. Você tem a opção de fazer as configurações de coexistência e atualização para todos os usuários de sua organização ao mesmo tempo ou pode fazer alterações nas configurações de um único ou conjunto de usuários em sua organização. Observe que as versões mais antigas dos clientes do Skype for Business podem não respeitar essas configurações. Para obter mais informações sobre as versões do cliente Skype for Business, acesse a [página de downloads e atualizações do Skype for Business](https://docs.microsoft.com/skypeforbusiness/software-updates). 

Você pode obter uma compreensão melhor dos tipos de modos disponíveis para você lendo [compreender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business com o](teams-and-skypeforbusiness-coexistence-and-interoperability.md) [Skype for Business](coexistence-chat-calls-presence.md).  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Definir opções de atualização para todos os usuários em sua organização

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para a**atualização de equipes**de **configurações** > em toda a organização. 

2. Na parte superior da página de **atualização do teams** , faça as seguintes alterações se elas funcionarem para você.
    - Defina o modo de **coexistência** .
        - **Ilhas** – Use essa configuração se quiser que os usuários possam usar o Skype for Business e o Teams simultaneamente.
        - **Skype para empresas apenas** – Use esta configuração se quiser que os usuários usem o Skype for Business apenas.
        - **Skype for Business com colaboração do teams** – Use essa configuração se quiser que os usuários usem o Skype for Business, além de usar o Teams para colaboração em grupo (canais).
        - **Skype for Business com colaboração e reuniões do teams** – Use essa configuração se quiser que os usuários usem o Skype for Business, além de usar o Teams para colaboração em grupo (canais) e reuniões de equipe.
        - **Somente equipes** (em visualização para algumas organizações) – Use essa configuração se desejar que os usuários usem apenas as equipes. Observe que, mesmo com essa configuração, os usuários ainda podem ingressar em reuniões hospedadas no Skype for Business.
    - Defina **notificar os usuários do Skype for Business de que o Microsoft Teams está disponível para atualização**. Se você ativar esse recurso, ele informará aos usuários do Skype for Business que eles logo serão atualizados para o aplicativo Teams.
    - Defina o **aplicativo preferencial para que os usuários ingressem em reuniões do Skype for Business**. Essa configuração determina qual aplicativo é usado para ingressar em reuniões do Skype for Business e é respeitado independentemente do valor do modo de coexistência.
      - **Aplicativo reuniões do Skype**
      - **Skype for Business com recursos limitados**
    - Defina se **o aplicativo Teams deve ser baixado em segundo plano para usuários do Skype for Business**.  Essa configuração faz o download silencioso do aplicativo Teams para usuários que executam o Skype for Business no Windows. Ele será aceito apenas se o modo de coexistência do usuário for Teams only ou se as notificações de atualização pendente estiverem habilitadas no Skype for Business.
3. Clique em **salvar** depois de fazer as alterações.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Definir opções de atualização para um único usuário em sua organização

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**

1. No painel de navegação esquerdo, vá para **usuários**e selecione o usuário na lista. 
2. Na guia **conta** do usuário, em atualização do Microsoft **Teams**, clique em **Editar**.
3. Você pode definir o **modo de coexistência**. Escolha uma das seguintes opções:
     - **Use as configurações de toda a organização** – Use essa configuração se quiser que o usuário use as configurações nas configurações de **toda a organização** . 
     - **Ilhas** – Use essa configuração se quiser que o usuário possa usar o Skype for Business e o Teams. 
     - **Skype para empresas somente** – Use esta configuração se quiser que o usuário use o Skype for Business.
     - **Skype for Business com colaboração do teams** – Use essa configuração se quiser que o usuário use o Skype for Business, além de usar o Teams para colaboração em grupo (canais).
      - **Skype for Business com colaboração e reuniões do teams** – Use essa configuração se quiser que o usuário use o Skype for Business, além de usar o Teams para colaboração em grupo (canais) e reuniões de equipe.
     - **Somente para equipes** – Use essa configuração se quiser que o usuário use apenas as equipes. O usuário ainda poderá ingressar em reuniões do Skype for Business.
4. Se você selecionar qualquer **modo de coexistência** diferente de **usar as configurações de toda a organização**, terá a opção de habilitar notificações no aplicativo Skype for Business do usuário que a atualização para o Microsoft Teams estará disponível em breve. Você pode habilitar essa notificação para o usuário ativando a opção **notificar o usuário do Skype for Business** .
5. Clique em **salvar** depois de fazer as alterações.

### <a name="related-topics"></a>Tópicos relacionados
[Planejar a jornada](upgrade-plan-journey.md)

[Compreender a coexistência e atualizar a viagem para o Skype for Business e o Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md)
