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
description: Saiba mais sobre como definir as configurações de coexistência e atualização para todos os usuários em sua organização ao mesmo tempo ou para um único ou conjunto de usuários em sua organização.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a20e8c355df4103980dc9da460d003382c721800
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940601"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Definir suas configurações de coexistência e atualização


Quando você atualiza seus usuários do Skype for Business para usar o Teams, há várias opções para ajudá-lo a torná-lo um processo perfeito para seus usuários. Você tem a opção de fazer configurações de coexistência e atualização para todos os usuários em sua organização ao mesmo tempo ou pode fazer alterações nas configurações de um único ou conjunto de usuários em sua organização. Observe que versões mais antigas de clientes do Skype for Business podem não honrar essas configurações. Para saber mais sobre as versões do cliente Skype for Business, acesse a página de downloads e atualizações [do Skype for Business.](https://docs.microsoft.com/skypeforbusiness/software-updates) 

Para entender melhor os modos disponíveis, leia Entender a [coexistência](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e a interoperabilidade do Skype for Business do Microsoft Teams e do Skype for Business ou a coexistência com o [Skype for Business.](coexistence-chat-calls-presence.md)  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Definir opções de atualização para todos os usuários em sua organização

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. No Centro [de administração do Microsoft Teams,](https://admin.teams.microsoft.com/)na navegação à esquerda, vá para Atualização do Teams de configurações em toda **a**  >  **organização.** 

2. Na parte superior da página **de atualização do Teams,** modifique as seguintes opções conforme desejado.
    - Definir o **modo coexistência.**
        - **Ilhas** – Use essa configuração se quiser que os usuários sejam capazes de usar o Skype for Business e o Teams simultaneamente.
        - **Skype for Business somente** – Use essa configuração se quiser que os usuários usem apenas o Skype for Business.
        - **Colaboração do Skype for Business** com o Teams - Use essa configuração se quiser que os usuários usem o Skype for Business, além de usar o Teams para colaboração em grupo (canais).
        - **Skype for Business com** colaboração e reuniões do Teams - Use essa configuração se quiser que os usuários usem o Skype for Business, além de usar o Teams para colaboração em grupo (canais) e reuniões do Teams.
        - **Somente equipes** – Use essa configuração se quiser que seus usuários usem apenas o Teams. Observe que, mesmo com essa configuração, os usuários ainda podem ingressar em reuniões hospedadas no Skype for Business.
        
    - De **configurar Notificar os usuários do Skype for Business de que o Teams está disponível para atualização.** Se você ativar isso, ele dirá aos usuários do Skype for Business que eles serão atualizados em breve para o aplicativo Teams.
    - De definir o **aplicativo Preferencial para os usuários ingressarem em reuniões do Skype for Business.** Essa configuração determina qual aplicativo é usado para ingressar em reuniões do Skype for Business e é atendida independentemente do valor do modo de coexistência.
      - **Aplicativo Reuniões do Skype**
      - **Skype for Business com recursos limitados**
    - De definir se você **deve baixar o aplicativo Teams em segundo plano para usuários do Skype for Business.**  Essa configuração baixa silenciosamente o aplicativo Teams para usuários que executam o Skype for Business no Windows. Ela só será atendida se o modo de coexistência do usuário for somente do Teams ou se as notificações de atualização pendente estão habilitadas no Skype for Business.
3. Clique **em Salvar** depois de fazer suas alterações.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Definir opções de atualização para um único usuário em sua organização

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. No painel de navegação esquerdo, vá **para Usuários** e selecione o usuário na lista. 
2. Na guia **Conta** do usuário, em Atualização do **Teams,** clique em **Editar.**
3. Você pode definir o **modo coexistência.** Escolha uma das seguintes opções:
     - **Use as configurações** de toda a organização - Use essa configuração se quiser que o usuário use as configurações nas **configurações** de toda a organização. 
     - **Ilhas** – Use essa configuração se quiser que o usuário possa usar o Skype for Business e o Teams. 
     - **Skype for Business somente** - Use essa configuração se quiser que o usuário use o Skype for Business.
     - **Colaboração do Skype for Business** com o Teams - Use essa configuração se quiser que o usuário use o Skype for Business, além de usar o Teams para colaboração em grupo (canais).
      - **Skype for Business com** colaboração e reuniões do Teams - Use essa configuração se quiser que o usuário use o Skype for Business, além de usar o Teams para colaboração em grupo (canais) e reuniões do Teams.
     - **Somente teams** - Use essa configuração se quiser que o usuário use apenas o Teams. O usuário ainda poderá ingressar em reuniões do Skype for Business.
4. Se você selecionar qualquer modo de **coexistência** diferente de Usar configurações de toda a **organização,** você terá a opção de habilitar notificações no aplicativo Skype for Business do usuário que atualizar para o Teams estará em breve. Você pode habilitar essa notificação para o usuário ativando a opção Notificar o **usuário do Skype for Business.**
5. Clique **em Salvar** depois de fazer suas alterações.

### <a name="related-topics"></a>Tópicos relacionados
[Atualizar do Skype for Business para o Teams — para administradores de IT](upgrade-to-teams-on-prem-overview.md)

[Planejar a jornada](upgrade-plan-journey.md)

[Compreender a coexistência e a jornada de atualização do Skype for Business e do Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md)
