---
title: Gerenciar Skype for Business configurações no centro de administração do Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como gerenciar configurações para Skype for Business recursos no Centro de administração do Microsoft Teams.
ms.openlocfilehash: 26b2ba51d42a7be227b513d72add3e34f07d0fcd
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269756"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Gerenciar Skype for Business configurações no centro de administração do Microsoft Teams

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Como administrador, o Centro de administração do Microsoft Teams é onde você gerencia Skype for Business recursos para Skype for Business usuários em sua organização. Você pode gerenciar configurações [para](#manage-skype-for-business-settings-for-your-organization) sua organização na página **Skype for Business** e configurações para usuários [individuais na](#manage-skype-for-business-settings-for-individual-users) guia **Skype for Business de páginas** de detalhes do usuário.

Você só verá a página **Skype for Business** se o modo de coexistência da sua organização não estiver definido apenas como **Teams**. Da mesma forma, você só verá a guia **Skype for Business** para um usuário se o modo de coexistência do usuário não for apenas **o Teams**. Para saber mais sobre os modos de coexistência, consulte Entender o Teams e Skype for Business [coexistência e interoperabilidade](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e definir suas [configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md).

> [!NOTE]
> Skype for Business configurações anteriormente estavam **no portal herdado** no centro de administração do Microsoft Teams. Com a desativação do portal herdado, migramos as configurações para esses novos locais no Centro de administração do Teams para Skype for Business gerenciamento.

Você deve receber a função [Azure AD](/azure/active-directory/roles/permissions-reference) administrador global ou administrador do Skype for Business para gerenciar Skype for Business recursos no centro de administração do Microsoft Teams.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Gerenciar Skype for Business configurações para sua organização

No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá para **configurações de** toda a organização  > **Skype for Business**. A partir daqui, você pode configurar e gerenciar Reunião do Skype difusão, privacidade de presença e notificações de dispositivo móvel para todos os Skype for Business em sua organização.

### <a name="skype-meeting-broadcast"></a>Transmissão de Reunião do Skype

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Use as configurações a seguir para gerenciar [Reunião do Skype Difusão](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) em sua organização.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Captura de tela Reunião do Skype configurações de difusão no centro de administração.":::

- **Reunião do Skype difusões**: ative isso para habilitar Reunião do Skype Difusão para sua organização. Depois de habilitar esse recurso, você precisará [configurar sua rede para Reunião do Skype Difusão](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).
- **Confira a versão prévia** dos recursos: ative isso para obter acesso antecipado a novos recursos.
- **Os organizadores podem agendar** reuniões anônimas: ative isso se você quiser permitir que os organizadores criem eventos de difusão que permitam que qualquer pessoa de fora da sua organização ingresse sem precisar entrar. 
- **Gravar Reunião do Skype de transmissão**: ative isso para permitir que organizadores e apresentadores gravem reuniões.  
- **URL de suporte da Assistência** Técnica para participantes: insira a URL de suporte da sua organização que os participantes da reunião podem usar se eles precisam de ajuda durante uma reunião.

### <a name="presence-and-mobile-notifications"></a>Notificações de presença e dispositivos móveis

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Use as configurações a seguir para gerenciar Skype for Business privacidade de presença e notificações móveis em sua organização.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Captura de tela das configurações de presença no centro de administração.":::

#### <a name="presence"></a>Presença

Por padrão, Skype for Business usuários em sua organização podem ver o status de presença (como Disponível, Ocupado ou Ausente) de outros Skype for Business usuários. Escolha uma das opções a seguir para definir quem pode ver a presença de seus Skype for Business usuários.

- **Exibir automaticamente** as informações de presença: qualquer Skype for Business usuário em sua organização que não tenha sido adicionado à lista Externa ou Bloqueada  do usuário  pode ver a presença desse usuário.
- **Exibir** informações de presença somente para os contatos de um usuário: qualquer usuário Skype for Business na lista de Contatos do usuário que não é adicionado à sua lista Externa ou Bloqueada pode ver  a presença  desse usuário. Os usuários podem substituir essa configuração no Skype for Business acessando **Opções de Ferramentas de** > **Configurações** > .

#### <a name="mobile-notifications"></a>Notificações móveis

Você pode definir se seus usuários Skype for Business móveis receberão alertas sobre mensagens instantâneas recebidas e perdidas, mensagens de caixa postal e chamadas perdidas por meio de um serviço de notificação por push. Dependendo dos dispositivos móveis usados em sua organização, você pode usar o Serviço de Notificação por **Push da Microsoft**, o Serviço de Notificação por **Push da Apple** ou ambos.

Considere o seguinte:

- Se você desativar as notificações por push, os usuários receberão todos os alertas na próxima vez que Skype for Business em seu dispositivo móvel.
- Por padrão, as notificações por push são ativadas. Usuários individuais podem desativá-los Skype for Business dispositivo móvel.
- Quando você desativa as notificações push, os usuários não podem ativá-las. 

> [!IMPORTANT]
> [!IMPORTANTE] A Microsoft usa outras empresas para fornecer notificações por celular para o Skype for Business em tempo real para os usuários do Windows Phone, iPhone e iPad. Consulte esta [Política de Privacidade](https://go.microsoft.com/fwlink/p/?linkid=247732).

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Gerenciar Skype for Business configurações para usuários individuais

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Para gerenciar Skype for Business configurações para usuários individuais, no painel de navegação esquerdo do Centro de administração do Teams, acesse **Usuários, clique** no nome de exibição do usuário para abrir a página de detalhes do usuário e selecione **a** guia Skype for Business configurações. A partir daqui, você pode definir o acesso externo e as configurações de reunião para o usuário.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Captura de tela Skype for Business guia na página de detalhes do usuário.":::

### <a name="external-access-settings"></a>Configurações de acesso externo

Você pode permitir ou bloquear seletivamente se um usuário pode se comunicar com pessoas de fora da sua organização.

- **Usuários Skype for Business externos**: ative isso se você quiser permitir que o usuário se comunique com Skype for Business usuários em domínios federados.
- **Usuários externos do Skype**: ative isso se você quiser permitir que o usuário se comunique com usuários do Skype. 

### <a name="meeting-settings"></a>Configurações de reunião

Você pode definir as seguintes configurações de reunião para o usuário.

- **Áudio & Vídeo**: escolha uma das seguintes configurações de áudio e vídeo:

    - **Nenhum**: o usuário não pode usar áudio ou vídeo.
    - **Somente áudio**: o usuário pode usar áudio, mas não vídeo.
    - **Áudio e vídeo**: o usuário pode usar áudio e vídeo.
    - **Áudio e vídeo (HD):** o usuário pode usar áudio e vídeo de alta definição.
    
- **Gravar conversas & reuniões**: ative isso para permitir que o usuário grave conversas e reuniões.
- **Conformidade**: ative isso se você for legalmente obrigado a reter informações armazenadas eletronicamente.