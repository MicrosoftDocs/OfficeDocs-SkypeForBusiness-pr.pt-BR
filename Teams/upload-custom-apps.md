---
title: Upload seus aplicativos personalizados no Microsoft Teams de administração
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como carregar seus aplicativos personalizados no armazenamento de aplicativos da sua organização no Microsoft Teams de administração.
ms.openlocfilehash: e27bd96477846ae3a74b1b405519e2a2c833ec39
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442257"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Publicar um aplicativo personalizado carregando um pacote de aplicativos

> [!NOTE]
> Quando você publica um aplicativo Teams personalizado, ele está disponível para os usuários na loja de aplicativos da sua organização. Há duas maneiras de publicar um aplicativo personalizado e a maneira como você usa depende de como você obter o aplicativo. Este artigo se concentra em como publicar um aplicativo personalizado carregando um pacote de **aplicativos (no formato .zip) que um desenvolvedor envia.** O outro método, aprovando um aplicativo personalizado, é usado quando um desenvolvedor envia um aplicativo diretamente para a página [](manage-apps.md) Gerenciar aplicativos por meio da API Teams Envio de Aplicativos. Para saber mais sobre esse método, consulte [Publish a custom app submitted through the Teams App Submission API](submit-approve-custom-apps.md).

Este artigo fornece orientações de ponta a ponta sobre como levar seu aplicativo Teams desenvolvimento para a implantação até a descoberta. Essa orientação se concentra nos aspectos Teams do aplicativo e destina-se a administradores e profissionais de IT. Para obter mais informações sobre o desenvolvimento Teams aplicativos, consulte a [documentação Teams desenvolvedor.](/microsoftteams/platform/)

![Visão geral do seu aplicativo do desenvolvimento para a implantação.](media/upload-custom-apps.png)

## <a name="develop"></a>Desenvolver

### <a name="create-your-app"></a>Criar seu aplicativo

A Microsoft Teams de desenvolvedores facilita que os desenvolvedores integrem seus próprios aplicativos e serviços para melhorar a produtividade, tomar decisões mais rapidamente e criar colaboração em torno de conteúdo e fluxos de trabalho existentes. Os aplicativos construídos na plataforma Teams são pontes entre o cliente Teams e seus serviços e fluxos de trabalho, trazendo-os diretamente para o contexto da sua plataforma de colaboração. Para obter mais informações, acesse a documentação [Teams desenvolvedor.](/microsoftteams/platform/)

## <a name="validate"></a>Validar

### <a name="get-the-app-package"></a>Obter o pacote do aplicativo

Quando o aplicativo estiver pronto para uso em produção, o desenvolvedor deverá produzir um pacote de aplicativos. Eles podem usar [o App Studio](/microsoftteams/platform/concepts/build-and-test/app-studio-overview) para isso. Eles enviarão o arquivo no formato .zip.

A Microsoft [usa essas diretrizes](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines) para garantir que os aplicativos cumpram os padrões de qualidade e segurança do armazenamento de Teams de aplicativos globais.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Permitir que usuários confiáveis carreguem aplicativos personalizados

Para validar se o aplicativo está funcionando corretamente no locatário de produção, você precisa permitir que a si mesmo e/ou usuários confiáveis carreguem aplicativos personalizados no locatário de produção. Você usa [políticas de configuração de aplicativos](teams-app-setup-policies.md) para fazer isso.

> [!NOTE]
> Se você não estiver confortável ao carregar o aplicativo para seu locatário de produção para validação, mesmo para você ou usuários confiáveis, você pode ignorar essa etapa e seguir as etapas no [Upload](#upload) e Configurar [](#set-up-and-manage) e gerenciar seções para publicar o aplicativo não validado no armazenamento de aplicativos da sua organização. Em seguida, restrinja o acesso a esse aplicativo somente a si mesmo e aos usuários em que você confia. Esses usuários podem, em seguida, obter o aplicativo da loja de aplicativos da sua organização para executar a validação. Depois que o aplicativo for validado, use as mesmas políticas de permissão para abrir o acesso e rolar o aplicativo para uso de produção.

Para permitir que usuários confiáveis carreguem aplicativos personalizados, siga estas etapas:

1. A opção Permitir **interação com aplicativos** personalizados em toda a organização. Para fazer isso:
    1. Na navegação à esquerda do centro de administração Microsoft Teams, acesse Teams **appsManage** >  apps e clique em **Configurações de** aplicativo em toda a organização.
    2. Em **Aplicativos personalizados**, a ligue **Permitir interação com aplicativos personalizados** e clique em **Salvar**.
2. Desativar a **configuração Upload aplicativos personalizados** na política de configuração de aplicativo global. Para fazer isso:
    1. Na navegação à esquerda do centro de administração Microsoft Teams, acesse Teams **appsSetup** >  e clique na política **Global (padrão em** toda a organização).
    2. Desativar Upload **aplicativos personalizados** e clique em **Salvar**.
3. Crie uma nova política de configuração de aplicativo que permita carregar aplicativos personalizados e atribuí-la ao seu conjunto de usuários confiáveis. Para fazer isso:
    1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Teams **appsSetup** >  e clique em **Adicionar**. Dê à nova política um nome e uma descrição, a Upload **aplicativos personalizados** e clique em **Salvar**.
    2. Selecione a nova política criada e clique em **Gerenciar usuários**. Procure um usuário, clique em **Adicionar** e clique em **Aplicar**. Repita esta etapa para atribuir a política a todos os usuários confiáveis.

        ![Captura de tela da página "Adicionar política de configuração de aplicativo"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Esses usuários agora podem carregar o manifesto do aplicativo para validar se o aplicativo está funcionando corretamente no locatário de produção.

## <a name="upload"></a>Upload

Para disponibilizar o aplicativo aos usuários na loja de aplicativos da sua organização, carregue o aplicativo. Você pode fazer isso na página [Gerenciar aplicativos](manage-apps.md) do Microsoft Teams de administração.

1. Na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Aplicativos do Teams** > **Gerenciar aplicativos**.
2. Selecione **Upload**, clique **Upload**, selecione o pacote de aplicativos que você recebeu do desenvolvedor e selecione **Abrir**.

   ![Captura de tela do carregamento de um aplicativo no centro de administração.](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>Configurar e gerenciar

### <a name="control-access-to-the-app"></a>Controlar o acesso ao aplicativo

Por padrão, todos os usuários em sua organização podem acessar o aplicativo na loja de aplicativos da sua organização. Para restringir e controlar quem tem permissão para usar o aplicativo, você pode criar e atribuir uma política de permissão de aplicativo. Para saber mais, confira [Gerenciar políticas de permissão de aplicativos no Teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Fixar e instalar o aplicativo para que os usuários descubram

Por padrão, para os usuários encontrarem o aplicativo, eles precisam ir até a loja de aplicativos da sua organização e procurar ou pesquisar por ele. Para facilitar o acesso dos usuários ao aplicativo, você pode fixar o aplicativo na barra de aplicativos Teams. Para fazer isso, crie uma política de configuração de aplicativo e atribua-a aos usuários. Para saber mais, confira [Gerenciar políticas de configuração de aplicativos no Teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Pesquisar o log de auditoria para Teams eventos do aplicativo

Você pode pesquisar o log de auditoria para exibir Teams de aplicativos em sua organização. Para saber mais sobre como pesquisar o log de auditoria e ver uma lista de atividades Teams que estão registradas no log de auditoria, consulte [Pesquisar o log](audit-log-events.md) de auditoria em busca de eventos no Teams.

Para examinar o log de auditoria, você precisa ativar a auditoria no [Centro de Conformidade e Segurança](https://sip.protection.office.com/homepage). Para obter instruções, confira [Ativar ou desativar a pesquisa de log de auditoria](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide). Tenha em mente que os dados de auditoria só estão disponíveis a partir do ponto em que você ativou a auditoria.

## <a name="discover-and-adopt"></a>Descobrir e adotar

Os usuários que têm permissões para o aplicativo podem encontrá-lo na loja de aplicativos da sua organização. Vá para **Built for *Your Organization Name*** na página Aplicativos para encontrar os aplicativos personalizados da sua organização.

![Captura de tela da página Aplicativos mostrando o aplicativo publicado.](media/custom-app-lifecycle-discovery.png)

Se você criou e atribuiu uma política de configuração de aplicativo, o aplicativo será fixado na barra de aplicativos Teams acesso fácil para os usuários que foram atribuídos à política.

## <a name="update"></a>Atualizar

Para atualizar um aplicativo, os desenvolvedores devem continuar a seguir as etapas nas seções [Desenvolver](#develop) [e Validar](#validate) .

Você pode atualizar o aplicativo na página Gerenciar aplicativos no Microsoft Teams de administração. Para fazer isso, na navegação à esquerda do centro de administração Microsoft Teams, vá para Teams **appsManage** > . Clique no nome do aplicativo e clique em **Atualizar**. Isso substitui o aplicativo existente, e todas as políticas de permissão de aplicativo e políticas de configuração de aplicativo permanecem impostas para o aplicativo atualizado.

### <a name="end-user-update-experience"></a>Experiência de atualização do usuário final

Na maioria dos casos, depois de concluir uma atualização de aplicativo, a nova versão será exibida automaticamente para usuários finais. No entanto, há algumas atualizações no manifesto Microsoft Teams [que](/microsoftteams/platform/resources/schema/manifest-schema) exigem que a aceitação do usuário seja concluída:

* Um bot foi adicionado ou removido
* A propriedade "botId" de um bot existente foi alterada
* A propriedade "isNotificationOnly" de um bot existente foi alterada
* A funcionalidade SupportsCalling, SupportsVideo e SupportsFiles de um bot foi adicionada
* Uma extensão de mensagens foi adicionada
* Um novo conector foi adicionado
* Permissões dentro de "Autorização" foram adicionadas ou alteradas

![Captura de tela da lista de aplicativos, mostrando aplicativos que têm uma nova versão disponível.](media/manage-your-custom-apps-update1.png)

![Captura de tela da opção de atualização para um aplicativo.](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Tópicos relacionados

* [Publicar um aplicativo personalizado enviado por meio da API Teams envio de aplicativos](submit-approve-custom-apps.md)

* [Gerenciar seus aplicativos no Microsoft Teams de administração](manage-apps.md)
* [Gerenciar políticas de aplicativo personalizado e as configurações no Teams](teams-custom-app-policies-and-settings.md)

* [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
* [Gerenciar políticas de configuração de aplicativo no Teams](teams-app-setup-policies.md)
