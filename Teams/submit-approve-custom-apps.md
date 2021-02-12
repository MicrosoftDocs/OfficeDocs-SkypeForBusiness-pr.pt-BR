---
title: Usar a API de Envio de Aplicativos do Teams para enviar e aprovar seus aplicativos personalizados
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: joglocke, vaibhava
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
localization_priority: Normal
search.appverid: MET150
description: Saiba como aprovar os aplicativos personalizados que são enviados usando a API de Envio de Aplicativos do Teams no Microsoft Teams.
ms.openlocfilehash: 0003bc218b425383ba117296ba847a637d76ac43
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145798"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Publicar um aplicativo personalizado enviado por meio da API de Envio de Aplicativos do Teams

## <a name="overview"></a>Visão Geral

> [!NOTE]
> Quando você publica um aplicativo personalizado do Teams, ele fica disponível para os usuários na loja de aplicativos da sua organização. Há duas maneiras de publicar um aplicativo personalizado e a maneira como você usa depende de como você obter o aplicativo. Este artigo se concentra em como aprovar e publicar um aplicativo personalizado que um desenvolvedor envia por meio da API de Envio de **Aplicativos do Teams.** O outro método, carregar um aplicativo personalizado, é usado quando um desenvolvedor envia um pacote de aplicativos no formato .zip. Para saber mais sobre esse método, consulte <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">Publicar um aplicativo personalizado carregando um pacote de aplicativos.</a> O widget aprovar aplicativo não está disponível em locatários GCC. 

> [!IMPORTANT]
> Este método não está disponível no momento para ambientes GCC. Você deve usar o *carregamento de um método de aplicativo* personalizado.

Este artigo fornece orientações de ponta a ponta sobre como levar seu aplicativo teams do desenvolvimento à implantação até a descoberta. Você terá uma visão geral das experiências conectadas que o Teams fornece em todo o ciclo de vida do aplicativo para simplificar como desenvolver, implantar e gerenciar aplicativos personalizados na loja de aplicativos da sua organização.

Vamos abranger cada etapa do ciclo de vida, incluindo como os desenvolvedores podem usar a API de Envio de Aplicativos do Teams para enviar aplicativos personalizados diretamente para o centro de administração do Microsoft Teams para você revisar e aprovar, como definir políticas para gerenciar aplicativos para usuários em sua organização e como seus usuários os descobrirão no Teams.

![Visão geral do seu aplicativo, desde o desenvolvimento até a implantação](media/custom-app-lifecycle.png)

Essa orientação se concentra nos aspectos do Teams do aplicativo e destina-se a administradores e profissionais de IT. Para obter informações sobre o desenvolvimento de aplicativos do Teams, consulte a documentação <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">de desenvolvedor do Teams.</a>

## <a name="develop"></a>Desenvolver

### <a name="create-the-app"></a>Criar o aplicativo

A plataforma de desenvolvedor do Microsoft Teams torna mais fácil para os desenvolvedores integrar seus próprios aplicativos e serviços para melhorar a produtividade, tomar decisões mais rapidamente e criar colaboração em torno de conteúdo e fluxos de trabalho existentes. Os aplicativos integrados à plataforma Teams são pontes entre o cliente do Teams e seus serviços e fluxos de trabalho, trazendo-os diretamente para o contexto da sua plataforma de colaboração. Para obter mais informações, acesse a documentação <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">de desenvolvedor do Teams.</a>

### <a name="submit-the-app"></a>Enviar o aplicativo

Quando o aplicativo estiver pronto para ser usado em produção, o desenvolvedor poderá enviar o aplicativo usando a API de Envio de Aplicativos do Teams, que pode ser chamada a partir da <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank" target="_blank">API do Graph,</a>de um ambiente de desenvolvimento integrado (IDE), como o Código do Visual Studio, ou de uma plataforma como Power Apps e Power Virtual Agents. Isso disponibiliza o aplicativo na <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank"></a> página Gerenciar aplicativos do Centro de administração do Microsoft Teams, onde você, o administrador, pode revisá-lo e aprove-o.

A API de Envio de Aplicativos do Teams, criada no <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">Microsoft Graph,</a>permite que sua organização se desenvolva na plataforma de sua escolha e automatiza o processo de envio para aprovação para aplicativos personalizados no Teams.

Veja um exemplo da aparência desta etapa de envio de aplicativos no Código do Visual Studio:

![enviar um aplicativo no Código do Visual Studio](media/custom-app-lifecycle-submit-app.png)

Lembre-se de que isso ainda não publica o aplicativo na loja de aplicativos da sua organização. Esta etapa envia o aplicativo para o centro de administração do Microsoft Teams, onde você pode aprove-lo para publicação na loja de aplicativos da sua organização.

Para obter mais informações sobre como usar a API do Graph para enviar aplicativos, consulte <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">aqui.</a>

## <a name="validate"></a>Validar

A <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">página Gerenciar aplicativos</a> no Centro de administração do Microsoft Teams (na navegação à esquerda, vá para Os aplicativos do **Teams** Gerenciar aplicativos), oferece uma exibição em todos os aplicativos do Teams para  >  sua organização. O **widget de aprovação** pendente na parte superior da página permite que você saiba quando um aplicativo personalizado é enviado para aprovação.

Na tabela, um aplicativo recém-enviado mostra automaticamente o **status** de Publicação de **Enviado e** **Status** de **Bloqueado.** Você pode classificar **a coluna de status de** Publicação em ordem decrescente para encontrar rapidamente o aplicativo.

![status de publicação ](media/custom-app-lifecycle-validate-app.png)

Clique no nome do aplicativo para ir para a página de detalhes do aplicativo. Na guia **Sobre,** você pode exibir detalhes sobre o aplicativo, incluindo descrição, status, enviador e ID do aplicativo.

![página de detalhes do aplicativo para um aplicativo enviado](media/custom-app-lifecycle-app-details.png)

Para obter mais informações sobre como usar a API do Graph para verificar o **status de Publicação,** consulte <a href="https://docs.microsoft.com/graph/api/appcatalogs-list-teamsapps?view=graph-rest-beta&tabs=http#example-3-find-application-based-on-the-teams-app-manifest-id" target="_blank">aqui.</a>

## <a name="publish"></a>Publicar

Quando estiver pronto para disponibilizar o aplicativo aos usuários, publique o aplicativo.

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Os **aplicativos do Teams**  >  **Gerenciar aplicativos.**
2. Clique no nome do aplicativo para ir para a página de detalhes do aplicativo e, na caixa **de status** publicação, selecione **Publicar.**

    Depois de publicar o aplicativo, o **status de** Publicação muda para Publicado **e** o **Status** muda automaticamente para **Permitido.**

## <a name="set-up-and-manage"></a>Configurar e gerenciar

### <a name="control-access-to-the-app"></a>Controlar o acesso ao aplicativo

Por padrão, todos os usuários em sua organização podem acessar o aplicativo na loja de aplicativos da sua organização. Para restringir e controlar quem tem permissão para usar o aplicativo, você pode criar e atribuir uma política de permissão de aplicativo. Para saber mais, consulte <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Gerenciar políticas de permissão do aplicativo no Teams.</a>

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Fixar e instalar o aplicativo para que os usuários descubram

Por padrão, para os usuários encontrarem o aplicativo, eles precisam ir para a loja de aplicativos da sua organização e procurar ou pesquisar por ele. Para facilitar o acesso dos usuários ao aplicativo, você pode fixar o aplicativo na barra de aplicativos no Teams. Para fazer isso, crie uma política de configuração de aplicativo e atribua-a aos usuários. Para saber mais, consulte <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Gerenciar políticas de configuração de aplicativos no Teams.</a>

### <a name="search-the-audit-log-for-teams-app-events"></a>Pesquisar o log de auditoria para eventos do aplicativo Teams

Você pode pesquisar no log de auditoria para exibir a atividade de aplicativos do Teams em sua organização. Para saber mais sobre como pesquisar no log de auditoria e ver uma lista de atividades do Teams que estão registradas no log de auditoria, consulte Pesquisar no log de auditoria para ver eventos <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">no Teams.</a>

Antes de poder pesquisar o log de auditoria, primeiro você precisa ativar a auditoria no Centro de <a href="https://protection.office.com" target="_blank">Conformidade & Segurança.</a> Para saber mais, confira Ativar ou desativar a pesquisa <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">de log de auditoria.</a> Lembre-se de que os dados de auditoria só estão disponíveis a partir do ponto em que você a adotou a auditoria.

## <a name="discover-and-adopt"></a>Descobrir e adotar

Os usuários que têm permissões para o aplicativo podem encontrá-lo na loja de aplicativos da sua organização. Vá para **Built for Your Organization *Name*** na página Aplicativos para encontrar os aplicativos personalizados da sua organização.

![Página Aplicativos mostrando o aplicativo publicado ](media/custom-app-lifecycle-discovery.png)

Se você criou e atribuiu uma política de configuração de aplicativo, o aplicativo é fixado na barra de aplicativos no Teams para facilitar o acesso para os usuários que foram atribuídos à política.

## <a name="update"></a>Atualizar

Para atualizar um aplicativo, os desenvolvedores devem continuar a seguir as etapas [na](#develop) seção Desenvolver.

Quando o desenvolvedor enviar uma atualização para um aplicativo personalizado publicado, você será notificado no **widget** de aprovação pendente da página Gerenciar <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">aplicativos.</a> Na tabela, o **status de Publicação** do aplicativo será definido como Atualização **enviada.**

![Página Gerenciar aplicativos mostrando solicitações pendentes e status do aplicativo ](media/custom-app-lifecycle-update-submitted.png)

Para revisar e publicar uma atualização de aplicativo:

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Os **aplicativos do Teams**  >  **Gerenciar aplicativos.**
2. Clique no nome do aplicativo para ir para a página de detalhes do aplicativo e selecione Atualizar **disponível** para revisar os detalhes da atualização.

    ![página de detalhes do aplicativo](media/custom-app-lifecycle-update-app.png)
3. Quando estiver pronto, selecione **Publicar para** publicar a atualização. Isso substitui o aplicativo existente, atualiza o número da versão e altera o **status de** Publicação para **Publicado.** Todas as políticas de permissão de aplicativo e as políticas de configuração de aplicativo permanecem aplicadas para o aplicativo atualizado.

    Se você rejeitar a atualização, a versão anterior do aplicativo permanecerá publicada.

Lembre-se do seguinte:

- Quando um aplicativo é aprovado, qualquer pessoa pode enviar uma atualização para o aplicativo. Isso significa que outros desenvolvedores, incluindo o desenvolvedor que enviou originalmente o aplicativo, podem enviar uma atualização para o aplicativo.
- Quando um desenvolvedor envia um aplicativo e a solicitação está pendente, somente esse mesmo desenvolvedor pode enviar uma atualização para o aplicativo. Outros desenvolvedores só podem enviar uma atualização depois que o aplicativo for aprovado.

Para obter mais informações sobre como usar a API do Graph para atualizar aplicativos, consulte <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-beta#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">aqui.</a>

### <a name="update-experience-for-users"></a>Experiência de atualização para usuários

Na maioria dos casos, depois que você publica uma atualização de aplicativo, a nova versão é exibida automaticamente para os usuários. No entanto, há algumas atualizações do manifesto do <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams</a> que exigem a aceitação do usuário para concluir:

* Um bot foi adicionado ou removido
* A propriedade "botId" de um bot existente foi alterada
* A propriedade "isNotificationOnly" de um bot existente foi alterada
* A propriedade "supportsFiles" do bot foi alterada
* Uma extensão de mensagens foi adicionada ou removida
* Um novo conector foi adicionado
* Uma nova guia estática foi adicionada
* Uma nova guia configurável foi adicionada
* Propriedades dentro de "WebApplicationInfo" alteradas

![nova versão disponível](media/manage-your-custom-apps-update1.png)

![opção de atualização para um aplicativo](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Tópicos relacionados

- [Publicar um aplicativo personalizado carregando um pacote de aplicativos](upload-custom-apps.md)
- [Gerenciar seus aplicativos no Centro de administração do Microsoft Teams](manage-apps.md)
- [Gerenciar políticas de aplicativo personalizado e as configurações no Teams](teams-custom-app-policies-and-settings.md)
- [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
- [Gerenciar políticas de configuração de aplicativo no Teams](teams-app-setup-policies.md)
- <a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-beta" target="_blank">API do Microsoft Graph para aplicativos do Teams</a>
