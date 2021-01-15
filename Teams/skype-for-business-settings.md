---
title: Gerenciar configurações do Skype for Business no centro de administração do Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como gerenciar as configurações dos recursos do Skype for Business no centro de administração do Microsoft Teams.
ms.openlocfilehash: 944a5f8101b8355f4a2cc3e18966e5eb01b94be9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834211"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Gerenciar configurações do Skype for Business no centro de administração do Microsoft Teams

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Como administrador, o centro de administração do Microsoft Teams é onde você gerencia os recursos do Skype for Business para usuários do Skype for Business em sua organização. Você pode gerenciar configurações [para](#manage-skype-for-business-settings-for-your-organization) sua organização na página **Skype for Business** e configurações para usuários individuais na guia Skype for **Business** de páginas de detalhes do usuário. [](#manage-skype-for-business-settings-for-individual-users)

Você só verá a página **do Skype for Business** se o modo de coexistência da sua organização não estiver definido apenas para o **Teams.** Da mesma forma, você só verá a guia **Skype for Business** para um usuário se o modo de coexistência do usuário não for apenas o **Teams.** Para saber mais sobre modos de coexistência, consulte Entender a coexistência e [a interoperabilidade](teams-and-skypeforbusiness-coexistence-and-interoperability.md) do Teams e do Skype for Business e definir suas configurações de [coexistência e atualização.](setting-your-coexistence-and-upgrade-settings.md)

> [!NOTE]
> As configurações do Skype for Business anteriormente estavam **no portal herdado** no centro de administração do Microsoft Teams. Com a desabilitação do portal herdada, migramos as configurações para esses novos locais no centro de administração do Teams para gerenciamento do Skype for Business.

Você deve ter a função de administrador do [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) de administrador global ou administrador do Skype for Business para gerenciar os recursos do Skype for Business no centro de administração do Microsoft Teams.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Gerenciar configurações do Skype for Business para sua organização

Na navegação à esquerda do centro de administração do Microsoft Teams, vá para configurações do Skype for Business em toda a  >  **organização.** A partir daqui, você pode configurar e gerenciar a Transmissão de Reunião do Skype, a privacidade de presença e as notificações de dispositivo móvel para todos os usuários do Skype for Business em sua organização.

### <a name="skype-meeting-broadcast"></a>Transmissão de Reunião do Skype

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Use as configurações a seguir para gerenciar a [Transmissão de Reunião do Skype](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) em sua organização.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Captura de tela das configurações de Transmissão de Reunião do Skype no centro de administração":::

- **Transmissões de Reunião do Skype:** ative isso para habilitar a Transmissão de Reunião do Skype para sua organização. Depois de habilitar esse recurso, você precisará configurar sua [rede para a Transmissão de Reunião do Skype.](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)
- **Confira os recursos de** visualização: a ligue para obter acesso antecipado aos novos recursos.
- **Os organizadores podem agendar** reuniões anônimas: a ligue se você quiser permitir que os organizadores criem eventos de transmissão que permitam que qualquer pessoa de fora da sua organização participe sem precisar entrar. 
- **Gravar reuniões de Transmissão de Reunião do Skype:** ative isso para permitir que organizadores e apresentadores gravem reuniões.  
- **URL de suporte do Helpdesk** para participantes: insira a URL de suporte da sua organização que os participantes da reunião podem usar se eles precisam de ajuda durante uma reunião.

### <a name="presence-and-mobile-notifications"></a>Notificações de presença e dispositivos móveis

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Use as configurações a seguir para gerenciar a privacidade de presença do Skype for Business e as notificações móveis em sua organização.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Captura de tela das configurações de presença no centro de administração":::

#### <a name="presence"></a>Presença

Por padrão, os usuários do Skype for Business em sua organização podem ver o status de presença (como Disponível, Ocupado ou Fora) de outros usuários do Skype for Business. Escolha um dos seguintes para definir quem pode ver a presença de seus usuários do Skype for Business.

- **Exibir automaticamente informações** de presença: qualquer usuário do Skype for Business  em  sua organização que não tenha sido adicionado à lista externa ou bloqueada do usuário pode ver a presença desse usuário.
- **Exibir** informações de presença somente para os contatos de um usuário: qualquer usuário do Skype for Business na lista de Contatos do usuário que não foi adicionado à sua lista externa ou bloqueada pode ver a presença desse usuário.   Os usuários podem substituir essa configuração no Skype for Business indo para **Opções de** Ferramentas  >  **de**  >  **Configurações.**

#### <a name="mobile-notifications"></a>Notificações móveis

Você pode definir se seus usuários móveis do Skype for Business receberão alertas sobre mensagens instantâneas recebidas e perdidas, mensagens de caixa postal e chamadas perdidas por meio de um serviço de notificação por push. Dependendo dos dispositivos móveis usados em sua organização, você pode usar o Serviço de Notificação por Push da **Microsoft,** o Serviço de Notificação por Push da **Apple** ou ambos.

Considere o seguinte:

- Se você desativar as notificações por push, os usuários receberão todos os alertas na próxima vez que iniciarem o Skype for Business em seus dispositivos móveis.
- Por padrão, as notificações por push são ativas. Usuários individuais podem desativar o Skype for Business em seus dispositivos móveis.
- Quando você desativa as notificações push, os usuários não podem ativá-las. 

> [!IMPORTANT]
> [!IMPORTANTE] A Microsoft usa outras empresas para fornecer notificações por celular para o Skype for Business em tempo real para os usuários do Windows Phone, iPhone e iPad. Consulte esta [Política de Privacidade.](https://go.microsoft.com/fwlink/p/?linkid=247732)

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Gerenciar configurações do Skype for Business para usuários individuais

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Para gerenciar as configurações do Skype for Business para usuários individuais, na navegação à esquerda do Centro de administração do Teams, vá para **Usuários,** clique no nome de exibição do usuário para abrir a página de detalhes do usuário e selecione a guia **configurações do Skype for Business.** A partir daqui, você pode definir o acesso externo e as configurações de reunião para o usuário.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Captura de tela da guia Skype for Business na página de detalhes do usuário":::

### <a name="external-access-settings"></a>Configurações de acesso externo

Você pode permitir ou bloquear seletivamente se um usuário pode se comunicar com pessoas de fora da sua organização.

- **Usuários externos do Skype for Business:** a ligue se você quiser permitir que o usuário se comunique com usuários do Skype for Business em domínios federados.
- **Usuários externos do Skype:** a ligue se você quiser permitir que o usuário se comunique com usuários do Skype. 

### <a name="meeting-settings"></a>Configurações de reunião

Você pode definir as seguintes configurações de reunião para o usuário.

- **Vídeo & áudio:** escolha uma das seguintes configurações de áudio e vídeo:

    - **Nenhuma**: o usuário não pode usar áudio ou vídeo.
    - **Somente áudio:** o usuário pode usar áudio, mas não vídeo.
    - **Áudio e vídeo:** o usuário pode usar áudio e vídeo.
    - **Áudio e vídeo (HD)**: o usuário pode usar áudio e vídeo de alta definição.
    
- **Gravar conversas & reuniões:** ativar para permitir que o usuário grave conversas e reuniões.
- **Conformidade:** a ligue se você for legalmente obrigado a reter informações armazenadas eletronicamente. 
