---
title: Usar a API de Envio de Aplicativos do Teams para enviar e aprovar seus aplicativos personalizados
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/19/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como aprovar seus aplicativos personalizados enviados usando a API de Envio de Aplicativos do Teams no Microsoft Teams.
ms.openlocfilehash: 63493041d834c99f5ffa93ba2fb580130afa0e29
ms.sourcegitcommit: d6e180791134426445a35fd485dcca18bde2006b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2022
ms.locfileid: "68494614"
---
# <a name="publish-a-custom-app-submitted-using-the-teams-app-submission-api"></a>Publicar um aplicativo personalizado enviado usando a API de Envio de Aplicativos do Teams

Este artigo fornece diretrizes de ponta a ponta sobre como levar seu aplicativo do Teams do desenvolvimento à implantação até a descoberta. Você terá uma visão geral das experiências conectadas que o Teams oferece ao longo do ciclo de vida do aplicativo para simplificar como desenvolver, implantar e gerenciar aplicativos personalizados na app store da sua organização.

Abordaremos cada etapa do ciclo de vida, incluindo como os desenvolvedores podem usar a API de Envio de Aplicativos do Teams para enviar aplicativos personalizados diretamente ao centro de administração do Microsoft Teams para você examinar e aprovar, como definir políticas para gerenciar aplicativos para usuários na sua organização e como seus usuários os descobrem no Teams.

:::image type="content" source="media/custom-app-lifecycle.png" alt-text="Visão geral do seu aplicativo, desde o desenvolvimento até a implantação.":::

Essas diretrizes focam nos aspectos do aplicativo do Teams e são destinadas a administradores e profissionais de TI. Para obter informações sobre o desenvolvimento de aplicativos do Teams, confira a [Documentação do desenvolvedor do Teams](/microsoftteams/platform).

> [!NOTE]
> Ao publicar um aplicativo personalizado do Teams, ele fica disponível para os usuários na loja de aplicativos da sua organização. Há duas maneiras de publicar um aplicativo personalizado e a maneira como você usa depende de como obtém o aplicativo. Este artigo se concentra em como aprovar e publicar um aplicativo personalizado que um desenvolvedor envia através da API de Envio de Aplicativo do Teams. O outro método, o upload de um aplicativo personalizado, é usado quando um desenvolvedor envia um pacote de aplicativo no formato .zip. Para saber mais sobre esse método, confira [Publicar um aplicativo personalizado fazendo upload de um pacote de aplicativos](/microsoftteams/upload-custom-apps). O widget de aprovação do aplicativo não está disponível nos locatários do GCC.

> [!IMPORTANT]
> Este método não está disponível em ambientes GCC. [Faça o upload de um aplicativo personalizado ](upload-custom-apps.md) para publicá-lo em ambientes GCC.

## <a name="develop"></a>Desenvolver

### <a name="create-the-app"></a>Criar o aplicativo

A plataforma de desenvolvedor do Microsoft Teams facilita para os desenvolvedores integrarem seus próprios aplicativos e serviços para melhorar a produtividade, tomar decisões mais rapidamente e colaborar em torno de conteúdo e fluxos de trabalho existentes. Os aplicativos criados na plataforma Teams são pontes entre o cliente do Teams e seus serviços e fluxos de trabalho, colocando-os diretamente no contexto de sua plataforma de colaboração. Para obter mais informações, acesse a [documentação do desenvolvedor do Teams](/microsoftteams/platform).

### <a name="submit-the-app"></a>Enviar o aplicativo

Quando o aplicativo estiver pronto para uso na produção, o desenvolvedor poderá enviá-lo usando a API de envio de aplicativos do Teams, que pode ser chamada a partir da [API do Graph](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), um ambiente de desenvolvimento integrado (IDE), como o Visual Studio Code, ou uma plataforma, como o Power Apps e os Agentes Virtuais do Power. Isso torna o aplicativo disponível na página [Gerenciar aplicativos](/microsoftteams/manage-apps) do centro de administração do Teams, onde você pode examiná-lo e aprová-lo.

A API de Envio de Aplicativos do Teams, [criada no Microsoft Graph](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), permite que sua organização se desenvolva na plataforma de sua escolha e automatiza o processo de envio para aprovação de aplicativos personalizados no Teams.

Este é um exemplo de como essa etapa de envio de aplicativo se parece no Visual Studio Code:

:::image type="content" source="media/custom-app-lifecycle-submit-app.png" alt-text="Captura de tela do envio do aplicativo no Visual Studio Code.":::

Lembre-se de que isso ainda não publica o aplicativo na app store da sua organização. Esta etapa envia o aplicativo para o centro de administração do Teams, onde você pode aprová-lo para publicação na app store da sua organização.

Para obter mais informações sobre como usar a API do Graph para enviar aplicativos, confira [aqui](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true).

## <a name="notify"></a>Notificar

Você pode ativar as notificações para saber quando os desenvolvedores enviarem um novo aplicativo para análise e aprovação. Você também receberá notificações quando os desenvolvedores enviarem as atualizações do aplicativo. Para ativar as notificações de envio de aplicativos no centro de administração do Teams, acesse **Notificações e alertas** > **[ Regras](https://admin.teams.microsoft.com/notifications/rules)** > **Envio de aplicativos** e ative a regra alterando o status para **Ativo**. Por padrão, essa configuração é desabilitada. Você precisa ser um administrador global ou um administrador do Teams para ativar essa configuração.

Depois de ativar essa configuração, você receberá notificações na equipe de **Alertas e Notificações do Administrador** em um novo canal denominado **Envio de aplicativos**. Alternativamente, você pode escolher uma equipe e um canal existentes para receber as notificações entregues a uma equipe e um canal especificados. Para fazer isso, execute estas etapas:

1. Na regra **Envios de aplicativos**, marque a caixa de seleção **Alerta de canal** em **Ações**.
1. Escolha o botão **Selecionar canal**.
1. Pesquisar uma equipe para adicionar.
1. Pesquisar um canal para adicionar.
1. Selecione **Aplicar**.

   :::image type="content" source="media/channel-alert.png" alt-text="Caixa de seleção de notificações de alertas do canal personalizado." lightbox="media/channel-alert.png":::

> [!NOTE]
> Selecione a caixa de seleção **Alerta de canal padrão** para receber notificações para a equipe **Alertas e Notificações do Administrador** no canal **Envio de Aplicativos**.

:::image type="content" source="media/default-channel-alert.png" alt-text="Caixa de seleção de notificações de alertas do canal padrão." lightbox="media/default-channel-alert.png":::

Você também pode configurar notificações para um webhook externo especificando uma URL pública do webhook depois de selecionar a caixa de seleção **Webhook**. Um conteúdo de notificação JSON será enviado para a URL do seu webhook.

:::image type="content" source="media/app-submission-notification.png" alt-text="Notificação de envio do aplicativo." lightbox="media/app-submission-notification.png":::

Após configurar a regra de envio de aplicativos, você pode revisar os cartões de notificação no canal especificado para ver os detalhes do aplicativo e selecionar **Exibir detalhes** para abrir aplicativos no centro de administração do Teams.

## <a name="validate"></a>Validar

A página [Gerenciar aplicativos](/microsoftteams/manage-apps) no centro de administração do Teams (no painel de navegação esquerdo, vá para [**Aplicativos do Teams** > **Gerenciar aplicativos**](https://admin.teams.microsoft.com/manage-apps)), fornece uma visão de todos os aplicativos do Teams para sua organização. O widget **Aprovação pendente** na parte superior da página permite que você saiba quando um aplicativo personalizado é enviado para aprovação.

Na tabela, um aplicativo enviado recentemente mostra automaticamente um **Status de publicação** de **Enviado** e **Status** de **Bloqueado**. Você pode classificar a coluna **Status da publicação** em ordem decrescente para encontrar rapidamente o aplicativo.

:::image type="content" source="media/custom-app-lifecycle-validate-app.png" alt-text="Status da publicação." lightbox="media/custom-app-lifecycle-validate-app.png":::

Clique no nome do aplicativo para acessar a página de detalhes do aplicativo. Na guia **Sobre**, você pode visualizar detalhes sobre o aplicativo, incluindo descrição, status, remetente e ID do aplicativo.

:::image type="content" source="media/custom-app-lifecycle-app-details.png" alt-text="Página de detalhes do aplicativo para um aplicativo enviado." lightbox="media/custom-app-lifecycle-app-details.png":::

Para obter mais informações sobre como usar a API do Graph para verificar o **Status da publicação**, confira [aqui](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&preserve-view=true).

## <a name="publish"></a>Publicar

Quando estiver pronto para disponibilizar o aplicativo para os usuários, publique o aplicativo.

1. Entre no centro de administração do Teams e acesse **Aplicativos do Teams** > **[Gerenciar aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Selecione o nome do aplicativo para acessar a página de detalhes do aplicativo e, em seguida, na caixa **Status da publicação**, selecione **Publicar**.

    :::image type="content" source="media/submitted-app-pending-action.png" alt-text="Botão Publicar na página de detalhes do aplicativo.":::

Depois de publicar o aplicativo, o **Status da publicação** é alterado para **Publicado** e o **Status** é alterado para **Permitido**.

## <a name="set-up-and-manage"></a>Configurar e gerenciar

### <a name="control-access-to-the-app"></a>Controlar o acesso ao aplicativo

Por padrão, todos os usuários em sua organização podem acessar o aplicativo na loja de aplicativos da sua organização. Para restringir e controlar quem tem permissão para usar o aplicativo, você pode criar e atribuir uma política de permissão de aplicativo. Para saber mais, confira [Gerenciar políticas de permissão de aplicativos no Teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Fixar e instalar o aplicativo para que os usuários descubram

Por padrão, para que os usuários localizem o aplicativo, eles precisam acessar a loja de aplicativos da sua organização e procurar ou pesquisar por ele. Para facilitar o acesso dos usuários ao aplicativo, você pode fixar o aplicativo na barra de aplicativos no Teams. Para fazer isso, crie uma política de configuração de aplicativo e atribua-a aos usuários. Para saber mais, confira [Gerenciar políticas de configuração de aplicativos no Teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Pesquisar o log de auditoria para eventos de aplicativos do Teams

Você pode pesquisar o log de auditoria para exibir a atividade de aplicativos do Teams em sua organização. Para saber mais sobre como pesquisar o log de auditoria e ver uma lista de atividades do Teams que estão registradas no log de auditoria, consulte [Pesquisar eventos no log de auditoria no Teams ](audit-log-events.md).

Para examinar o log de auditoria, você precisa ativar a auditoria no [Centro de Conformidade e Segurança](https://sip.protection.office.com/). Para obter instruções, confira [Ativar ou desativar a pesquisa de log de auditoria](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&preserve-view=true). Tenha em mente que os dados de auditoria só estão disponíveis a partir do ponto em que você ativou a auditoria.

## <a name="discover-and-adopt"></a>Descobrir e adotar

Os usuários que têm permissões para o aplicativo podem encontrá-lo na app store da sua organização. Acesse **Criado para *Nome da sua organização*** na página Aplicativos para encontrar os aplicativos personalizados da sua organização.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Página de aplicativos mostrando o aplicativo publicado." lightbox="media/custom-app-lifecycle-discovery.png":::

Se você criou e atribuiu uma política de configuração de aplicativo, o aplicativo será fixado na barra de aplicativos no Teams para facilitar o acesso para os usuários que foram atribuídos à política.

## <a name="update"></a>Atualizar

Para atualizar um aplicativo, os desenvolvedores devem continuar seguindo as etapas na seção [Desenvolver](#develop).

Quando o desenvolvedor enviar uma atualização para um aplicativo personalizado publicado, você será notificado no widget **Aprovação pendente** da página [Gerenciar aplicativos](/microsoftteams/manage-apps). Na tabela, o **Status da publicação** do aplicativo será definido como **Atualização enviada**. Você também será notificado na equipe **Alertas e notificações do Administrador** no canal **Envio de aplicativos** se você ativar as notificações de envio de aplicativos. O cartão de notificações terá um link para levá-lo diretamente ao aplicativo no centro de administração do Teams. Para obter mais informações sobre como ativar as notificações de envio de aplicativos, confira [Notificar](#notify).

:::image type="content" source="media/custom-app-lifecycle-update-submitted.png" alt-text="Página Gerenciar aplicativos mostrando as solicitações pendentes e o status do aplicativo." lightbox="media/custom-app-lifecycle-update-submitted.png":::

Para examinar e publicar uma atualização do aplicativo:

1. Na navegação à esquerda do centro de administração do Teams, acesse **Aplicativos do Teams** > **Gerenciar aplicativos**.
1. Clique no nome do aplicativo para ir para a página de detalhes do aplicativo e, em seguida, selecione **Atualização disponível** para revisar os detalhes da atualização.

   :::image type="content" source="media/custom-app-lifecycle-update-app.png" alt-text="Página de detalhes do aplicativo." lightbox="media/custom-app-lifecycle-update-app.png":::

1. Quando estiver pronto, selecione **Publicar** para publicar a atualização. Isso substitui o aplicativo existente, atualiza o número da versão e altera o **Status da publicação** para **Publicado**. Todas as políticas de permissão de aplicativo e as políticas de configuração de aplicativo permanecem aplicadas ao aplicativo atualizado.

    Se você rejeitar a atualização, a versão anterior do aplicativo permanecerá publicada.

Lembre-se do seguinte:

* Quando um aplicativo é aprovado, qualquer pessoa pode enviar uma atualização para o aplicativo. Isso significa que outros desenvolvedores, incluindo o desenvolvedor que enviou o aplicativo originalmente, podem enviar uma atualização para o aplicativo.
* Quando um desenvolvedor envia um aplicativo e a solicitação está pendente, apenas esse mesmo desenvolvedor pode enviar uma atualização para o aplicativo. Outros desenvolvedores só podem enviar uma atualização depois que o aplicativo for aprovado.

Para obter mais informações sobre como usar a API do Graph para atualizar aplicativos, confira [aqui](/graph/api/teamsapp-update?view=graph-rest-1.0&tabs=http&preserve-view=true).

## <a name="related-articles"></a>Artigos relacionados

* [Publicar um aplicativo personalizado carregando um pacote de aplicativos](upload-custom-apps.md)
* [Gerenciar seus aplicativos no Centro de Administração do Microsoft Teams](manage-apps.md)
* [Gerenciar políticas e configurações para aplicativos personalizados](teams-custom-app-policies-and-settings.md)
* [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
* [Gerenciar políticas de configuração de aplicativo no Teams](teams-app-setup-policies.md)
* [Monitoramento e alerta do Teams](alerts/teams-admin-alerts.md)
* [API do Microsoft Graph para aplicativos do Teams ](alerts/teams-admin-alerts.md)
