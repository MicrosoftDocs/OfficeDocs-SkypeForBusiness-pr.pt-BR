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
description: Saiba mais sobre como definir as configurações de coexistência e atualização para todos os usuários em sua organização ao mesmo tempo ou para um único ou conjunto de usuários em sua organização.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 474c5fc55476e664ba03b9dd82608d8c244b7982
ms.sourcegitcommit: 9bee7cb9433bfc687387647a102f814dc52c8591
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2022
ms.locfileid: "64839182"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a>Definir suas configurações de coexistência e atualização


Quando você atualiza seus Skype for Business para usar Teams, você tem várias opções para ajudá-lo a torná-lo um processo contínuo para seus usuários. Você tem a opção de fazer configurações de coexistência e atualização para todos os usuários em sua organização ao mesmo tempo ou pode fazer alterações de configurações para um único ou conjunto de usuários em sua organização. Observe que as versões mais antigas Skype for Business clientes podem não respeitar essas configurações. Para obter mais informações sobre Skype for Business versões do cliente, acesse a [página Skype for Business downloads e atualizações](/skypeforbusiness/software-updates). 

Você pode obter uma melhor compreensão dos modos que estão disponíveis para você lendo Entender [Microsoft Teams e Skype for Business coexistência e interoperabilidade](teams-and-skypeforbusiness-coexistence-and-interoperability.md) ou [coexistência](coexistence-chat-calls-presence.md) com Skype for Business.  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a>Definir opções de atualização para todos os usuários em sua organização

 **Usando o centro de administração do Microsoft Teams**

1. No centro [Microsoft Teams de administração](https://admin.teams.microsoft.com/), no painel de navegação à esquerda, acesse **Teams** >  **Teams de atualização**. 

2. Na parte superior da página **Teams atualização**, modifique as opções a seguir conforme desejado.

    - Defina o **modo coexistência** .
        - **Ilhas** – Use essa configuração se quiser que os usuários possam usar as Skype for Business e Teams simultaneamente.
        - **Skype for Business somente** - Use essa configuração se quiser que os usuários usem apenas Skype for Business.
        - **Skype for Business com Teams colaboração** - Use essa configuração se quiser que os usuários usem Skype for Business além de usar Teams para colaboração em grupo (canais).
        - **Skype for Business** com colaboração e reuniões do Teams - Use essa configuração se quiser que os usuários usem o Skype for Business, além de usar o Teams para colaboração em grupo (canais) e reuniões Teams reuniões.
        - **Teams somente** - Use essa configuração se quiser que os usuários usem apenas Teams. Observe que, mesmo com essa configuração, os usuários ainda podem ingressar em reuniões hospedadas no Skype for Business.

          > [!IMPORTANT]
          > Você só pode atribuir o modo TeamsOnly a todo o locatário depois que ambas as etapas a seguir forem concluídas:
          >  - Todos os usuários locais foram movidos para Teams somente usando Move-CsUser no conjunto de ferramentas Skype for Business Server local.
          >  - Você atualizou todos os Skype for Business DNS para apontar para Microsoft 365. 
          >
          > Para obter mais detalhes, consulte [Desabilitar sua configuração híbrida para concluir a migração para Teams somente](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).
        
    - **Defina Notificar Skype for Business usuários que Teams está disponível para atualização**. Se você ativar isso, ele informará aos Skype for Business que eles serão atualizados em breve para o Teams aplicativo.

    - Defina o **aplicativo preferencial para que os usuários ingressem Skype for Business reuniões**. Essa configuração determina qual aplicativo é usado para ingressar Skype for Business reuniões e é respeitada independentemente do valor do modo de coexistência.
      - **Skype reuniões**
      - **Skype for Business com recursos limitados**

    - Defina se deseja **baixar o Teams em segundo plano para Skype for Business usuários**. Essa configuração baixa silenciosamente o Teams para usuários que executam Skype for Business no Windows. Ele só será respeitado se o modo de coexistência do usuário for Teams ou se as notificações de atualização pendentes forem habilitadas Skype for Business.

3. Clique **em Salvar** depois de fazer suas alterações.

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a>Definir opções de atualização para um único usuário em sua organização

 **Usando o centro de administração do Microsoft Teams**

1. No painel de navegação esquerdo, vá para **usuários** **usersManage** >  e selecione o usuário na lista. 
2. Na guia **Conta** do usuário, em Teams **,** clique em **Editar**.
3. Você pode definir o **modo coexistência**. Modos diferentes do Teams só podem ser aplicados a usuários hospedados no Skype for Business Server local e, por outro lado, somente os usuários hospedados na nuvem podem ter o modo TeamsOnly.  Escolha uma das seguintes opções:
     - **Usar configurações de toda** a organização – use essa configuração se quiser que o usuário use as configurações nas **configurações** de toda a organização. 
     - **Ilhas** – Use essa configuração se quiser que o usuário possa usar as Skype for Business e Teams. 
     - **Skype for Business somente** - Use essa configuração se quiser que o usuário use Skype for Business.
     - **Skype for Business com Teams colaboração** - Use essa configuração se quiser que o usuário use Skype for Business além de usar Teams para colaboração em grupo (canais).
      - **Skype for Business** com colaboração e reuniões do Teams - Use essa configuração se quiser que o usuário use o Skype for Business além de usar o Teams para colaboração em grupo (canais) e reuniões Teams reuniões.
     - **Teams somente** - Use essa configuração se quiser que o usuário use apenas Teams. O usuário ainda poderá ingressar em Skype for Business reuniões.
4. Se você selecionar qualquer  modo de coexistência diferente de Usar configurações em toda a **organização, terá** a opção de habilitar notificações no aplicativo Skype for Business do usuário que atualizar para o Teams em breve. Você pode habilitar essa notificação para o usuário ativando a opção **Notificar o Skype for Business usuário**.
5. Clique **em Salvar** depois de fazer suas alterações.

### <a name="related-topics"></a>Tópicos relacionados
[Planejar a jornada](upgrade-plan-journey.md)

[Entender a coexistência e o percurso de atualização para Skype for Business e Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md)

[Desativar seu ambiente de Skype for Business local](/skypeforbusiness/hybrid/decommission-on-prem-overview)
