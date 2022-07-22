---
title: Usar a API de Envio de Aplicativo do Teams para enviar e aprovar seus aplicativos personalizados
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como aprovar seus aplicativos personalizados enviados usando a API de Envio de Aplicativos do Teams no Microsoft Teams.
ms.openlocfilehash: 2fb0ab6778a0704b0cb60faef0d0fd739351ee10
ms.sourcegitcommit: 70185cd963c5a9d539e65e302d4230018209ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2022
ms.locfileid: "66958066"
---
# <a name="publish-a-custom-app-submitted-using-the-teams-app-submission-api"></a>Publicar um aplicativo personalizado enviado usando a API de Envio de Aplicativo do Teams

Este artigo fornece diretrizes de ponta a ponta sobre como levar seu aplicativo teams do desenvolvimento à implantação até a descoberta. Você obterá uma visão geral das experiências conectadas que o Teams fornece em todo o ciclo de vida do aplicativo para simplificar como desenvolver, implantar e gerenciar aplicativos personalizados na loja de aplicativos da sua organização.

Abordaremos cada etapa do ciclo de vida, incluindo como os desenvolvedores podem usar a API de Envio de Aplicativos do Teams para enviar aplicativos personalizados diretamente para o centro de administração do Microsoft Teams para que você examine e aprove, como definir políticas para gerenciar aplicativos para usuários em sua organização e como os usuários os descobrirão no Teams.

:::image type="content" source="media/custom-app-lifecycle.png" alt-text="Visão geral do seu aplicativo, desde o desenvolvimento até a implantação.":::

Essas diretrizes se concentram nos aspectos do aplicativo do Teams e são destinadas a administradores e profissionais de TI. Para obter informações sobre como desenvolver aplicativos do Teams, consulte a [documentação do desenvolvedor do Teams](/microsoftteams/platform).

> [!NOTE]
> Quando você publica um aplicativo personalizado do Teams, ele está disponível para os usuários na loja de aplicativos da sua organização. Há duas maneiras de publicar um aplicativo personalizado e a maneira como você usa depende de como você obtém o aplicativo. Este artigo se concentra em como aprovar e publicar um aplicativo personalizado que um desenvolvedor envia por meio da API de Envio de Aplicativo do Teams. O outro método, carregando um aplicativo personalizado, é usado quando um desenvolvedor envia um pacote de aplicativos .zip formato. Para saber mais sobre esse método, consulte [Publicar um aplicativo personalizado carregando um pacote de aplicativos](/microsoftteams/upload-custom-apps). O widget aprovar aplicativo não está disponível em locatários GCC.

> [!IMPORTANT]
> Esse método não está disponível atualmente para ambientes GCC. No GCC, use o *método de carregamento de um aplicativo* personalizado.

## <a name="develop"></a>Desenvolver

### <a name="create-the-app"></a>Criar o aplicativo

A plataforma de desenvolvedor do Microsoft Teams facilita para os desenvolvedores integrarem seus próprios aplicativos e serviços para melhorar a produtividade, tomar decisões mais rapidamente e criar colaboração em torno de conteúdo e fluxos de trabalho existentes. Os aplicativos criados na plataforma Teams são pontes entre o cliente do Teams e seus serviços e fluxos de trabalho, colocando-os diretamente no contexto de sua plataforma de colaboração. Para obter mais informações, acesse a documentação [do desenvolvedor do Teams](/microsoftteams/platform).

### <a name="submit-the-app"></a>Enviar o aplicativo

Quando o aplicativo estiver pronto para uso em produção, o desenvolvedor poderá enviar o aplicativo usando a API de Envio de Aplicativo do Teams, que pode ser chamada do [API do Graph](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), um IDE (ambiente de desenvolvimento integrado), como o Visual Studio Code, ou uma plataforma como o Power Apps e o Power Virtual Agents. Isso disponibiliza o aplicativo na página Gerenciar aplicativos [](/microsoftteams/manage-apps) do Centro de administração do Teams, onde você pode revisá-lo e aprová-lo.

A API de Envio de Aplicativos do Teams, criada no [Microsoft Graph](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), permite que sua organização desenvolva na plataforma de sua escolha e automatiza o processo de envio para aprovação para aplicativos personalizados no Teams.

Aqui está um exemplo de como essa etapa de envio de aplicativo é semelhante Visual Studio Code:

:::image type="content" source="media/custom-app-lifecycle-submit-app.png" alt-text="enviando um aplicativo no Visual Studio Code.":::

Tenha em mente que isso ainda não publica o aplicativo na loja de aplicativos da sua organização. Esta etapa envia o aplicativo para o centro de administração do Teams, no qual você pode aprová-lo para publicação na loja de aplicativos da sua organização.

Para obter mais informações sobre como usar o API do Graph para enviar aplicativos, consulte [aqui](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true).

## <a name="notify"></a>Notificar

Você pode ativar notificações para saber quando os desenvolvedores enviam um novo aplicativo para revisão e aprovação. Você também receberá notificações quando os desenvolvedores enviarem atualizações de aplicativo. Para habilitar notificações de envio de aplicativo no Centro de administração do Teams, vá para Notificações & **envios** > **[](https://admin.teams.microsoft.com/notifications/rules)** >  de aplicativo de regras de **alertas** e ative a regra alterando o status para **Ativo**. Por padrão, essa configuração é desabilitada. Você deve ser um administrador global ou administrador do Teams para ativar essa configuração.

Depois de ativar essa configuração, você receberá notificações na equipe Administração **alertas** e notificações em um novo canal chamado **Envios de aplicativo.** Como alternativa, você pode escolher uma equipe e um canal existentes para receber notificações entregues a uma equipe e canal especificados. Para fazer isso, execute estas etapas:

1. Na regra **de envios de aplicativo** , marque a caixa **de** seleção Alerta do Canal em **Ações**.
1. Escolha o **botão Selecionar canal** .
1. Pesquise uma equipe para adicionar.
1. Pesquise um canal a ser adicionado.
1. Selecione **Aplicar**.

   :::image type="content" source="media/channel-alert.png" alt-text="Caixa de seleção de notificação de alerta de canal personalizado." lightbox="media/channel-alert.png":::

> [!NOTE]
> Marque a **caixa de seleção** De alerta de canal padrão para receber notificações para a equipe Administração **alertas** e notificações no canal **Envios de Aplicativos**.

:::image type="content" source="media/default-channel-alert.png" alt-text="Caixa de seleção de notificação de alerta de canal padrão." lightbox="media/default-channel-alert.png":::

Você também pode configurar notificações para um webhook externo especificando uma URL de webhook público depois de selecionar a caixa de **seleção webhook** . Uma carga de notificação JSON será enviada para a URL do webhook.

:::image type="content" source="media/app-submission-notification.png" alt-text="Notificação de envio de aplicativo." lightbox="media/app-submission-notification.png":::

Depois de configurar a regra de envios de aplicativo, você pode examinar os cartões de notificação no canal especificado para ver os detalhes  do aplicativo e selecionar Exibir detalhes para abrir aplicativos no Centro de administração do Teams.

## <a name="validate"></a>Validar

A [página Gerenciar aplicativos](/microsoftteams/manage-apps) no Centro de administração do Teams (no painel de navegação esquerdo, acesse Aplicativos do [**Teams** > ](https://admin.teams.microsoft.com/manage-apps) Gerenciar aplicativos), fornece uma exibição de todos os aplicativos do Teams para sua organização. O widget **de aprovação** pendente na parte superior da página permite que você saiba quando um aplicativo personalizado é enviado para aprovação.

Na tabela, um aplicativo recém-enviado mostra automaticamente um **status** de Publicação de **Enviado e** **Status** de **Bloqueado**. Você pode classificar **a coluna de status de** Publicação em ordem decrescente para localizar rapidamente o aplicativo.

:::image type="content" source="media/custom-app-lifecycle-validate-app.png" alt-text="Status da publicação." lightbox="media/custom-app-lifecycle-validate-app.png":::

Clique no nome do aplicativo para ir para a página de detalhes do aplicativo. Na guia **Sobre** , você pode exibir detalhes sobre o aplicativo, incluindo descrição, status, enviador e ID do aplicativo.

:::image type="content" source="media/custom-app-lifecycle-app-details.png" alt-text="Página de detalhes do aplicativo para um aplicativo enviado." lightbox="media/custom-app-lifecycle-app-details.png":::

Para obter mais informações sobre como usar o API do Graph para verificar o **status da** publicação, consulte [aqui](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&preserve-view=true).

## <a name="publish"></a>Publicar

Quando estiver pronto para disponibilizar o aplicativo aos usuários, publique o aplicativo.

1. Entre no Centro de administração do Teams e vá para aplicativos **do Teams Gerenciar** > **[aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Selecione o nome do aplicativo para ir para a página de detalhes do aplicativo e, na caixa **de status** Publicação, selecione **Publicar**.

    :::image type="content" source="media/submitted-app-pending-action.png" alt-text="Botão Publicar na página de detalhes do aplicativo.":::

Depois de publicar o aplicativo, o **status de** Publicação será alterado para **Publicado** e **o Status** será alterado para **Permitido**.

## <a name="set-up-and-manage"></a>Configurar e gerenciar

### <a name="control-access-to-the-app"></a>Controlar o acesso ao aplicativo

Por padrão, todos os usuários em sua organização podem acessar o aplicativo na loja de aplicativos da sua organização. Para restringir e controlar quem tem permissão para usar o aplicativo, você pode criar e atribuir uma política de permissão de aplicativo. Para saber mais, confira [Gerenciar políticas de permissão de aplicativos no Teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Fixar e instalar o aplicativo para que os usuários descubram

Por padrão, para que os usuários localizem o aplicativo, eles precisam acessar a loja de aplicativos da sua organização e procurar ou pesquisar por ele. Para facilitar o acesso dos usuários ao aplicativo, você pode fixar o aplicativo na barra de aplicativos no Teams. Para fazer isso, crie uma política de configuração de aplicativo e atribua-a aos usuários. Para saber mais, confira [Gerenciar políticas de configuração de aplicativos no Teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Pesquisar no log de auditoria eventos de aplicativo do Teams

Você pode pesquisar o log de auditoria para exibir a atividade de aplicativos do Teams em sua organização. Para saber mais sobre como pesquisar o log de auditoria e ver uma lista de atividades do Teams registradas no log de auditoria, consulte Pesquisar no [log de auditoria eventos no Teams](audit-log-events.md).

Para examinar o log de auditoria, você precisa ativar a auditoria no [Centro de Conformidade e Segurança](https://sip.protection.office.com/). Para obter instruções, confira [Ativar ou desativar a pesquisa de log de auditoria](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&preserve-view=true). Tenha em mente que os dados de auditoria só estão disponíveis a partir do ponto em que você ativou a auditoria.

## <a name="discover-and-adopt"></a>Descobrir e adotar

Os usuários que têm permissões para o aplicativo podem encontrá-lo na loja de aplicativos da sua organização. Acesse Built **for *Your Organization Name*** na página Aplicativos para encontrar os aplicativos personalizados da sua organização.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Página Aplicativos mostrando o aplicativo publicado." lightbox="media/custom-app-lifecycle-discovery.png":::

Se você criou e atribuiu uma política de configuração de aplicativo, o aplicativo será fixado na barra de aplicativos no Teams para facilitar o acesso para os usuários que foram atribuídos à política.

## <a name="update"></a>Atualizar

Para atualizar um aplicativo, os desenvolvedores devem continuar seguindo as [etapas na seção](#develop) Desenvolver.

Quando o desenvolvedor enviar uma atualização para um aplicativo personalizado publicado, você será notificado **no widget de** aprovação pendente da página Gerenciar [aplicativos](/microsoftteams/manage-apps) . Na tabela, o **status de** Publicação do aplicativo será definido como **Atualização enviada**. Você também será notificado na equipe de **alertas** e notificações do Administração no canal de envio do aplicativo se  você ativou as notificações de envio do aplicativo. O cartão de notificação terá um link para levá-lo diretamente ao aplicativo no centro de administração do Teams. Para obter mais informações sobre como ativar notificações de envio de aplicativo, consulte [Notificar](#notify).

:::image type="content" source="media/custom-app-lifecycle-update-submitted.png" alt-text="Página Gerenciar aplicativos mostrando solicitações pendentes e status do aplicativo." lightbox="media/custom-app-lifecycle-update-submitted.png":::

Para examinar e publicar uma atualização de aplicativo:

1. No painel de navegação esquerdo do Centro de administração do Teams, acesse Aplicativos **do Teams Gerenciar** > **aplicativos**.
1. Clique no nome do aplicativo para ir para a página de detalhes do aplicativo e selecione Atualizar **disponível** para examinar os detalhes da atualização.

   :::image type="content" source="media/custom-app-lifecycle-update-app.png" alt-text="Página de detalhes do aplicativo." lightbox="media/custom-app-lifecycle-update-app.png":::

1. Quando estiver pronto, selecione **Publicar para** publicar a atualização. Isso substitui o aplicativo existente, atualiza o número de versão e altera o **status de Publicação** para **Publicado**. Todas as políticas de permissão de aplicativo e políticas de configuração de aplicativo permanecem impostas para o aplicativo atualizado.

    Se você rejeitar a atualização, a versão anterior do aplicativo permanecerá publicada.

Tenha em mente o seguinte:

* Quando um aplicativo é aprovado, qualquer um pode enviar uma atualização para o aplicativo. Isso significa que outros desenvolvedores, incluindo o desenvolvedor que originalmente enviou o aplicativo, podem enviar uma atualização para o aplicativo.
* Quando um desenvolvedor envia um aplicativo e a solicitação está pendente, somente esse mesmo desenvolvedor pode enviar uma atualização para o aplicativo. Outros desenvolvedores só podem enviar uma atualização depois que o aplicativo for aprovado.

Para obter mais informações sobre como usar o API do Graph para atualizar aplicativos, consulte [aqui](/graph/api/teamsapp-update?view=graph-rest-1.0&tabs=http&preserve-view=true).

## <a name="related-articles"></a>Artigos relacionados

* [Publicar um aplicativo personalizado carregando um pacote de aplicativos](upload-custom-apps.md)
* [Gerenciar seus aplicativos no centro de administração do Microsoft Teams](manage-apps.md)
* [Gerenciar políticas de aplicativo personalizado e as configurações no Teams](teams-custom-app-policies-and-settings.md)
* [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
* [Gerenciar políticas de configuração de aplicativo no Teams](teams-app-setup-policies.md)
* [Monitoramento e alertas do Teams](alerts/teams-admin-alerts.md)
* [Microsoft API do Graph aplicativos do Teams](alerts/teams-admin-alerts.md)
