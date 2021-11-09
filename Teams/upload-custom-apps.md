---
title: Upload seus aplicativos personalizados no Microsoft Teams de administração
author: HowlinWolf-92
ms.author: v-mahoffman
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como carregar seus aplicativos personalizados no armazenamento de aplicativos da sua organização no Microsoft Teams de administração.
ms.openlocfilehash: 3869019d9becaf85da9c54ebc0ccca801980ec8a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846004"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Publicar um aplicativo personalizado carregando um pacote de aplicativos

> [!NOTE]
> Quando você publica um aplicativo Teams personalizado, ele está disponível para usuários na loja de aplicativos da sua organização. Há duas maneiras de publicar um aplicativo personalizado e a maneira como você usa depende de como você obter o aplicativo. Este artigo se concentra em como publicar um aplicativo personalizado carregando um pacote de **aplicativos (no** formato .zip) que um desenvolvedor envia. O outro método, aprovando um aplicativo personalizado, é usado quando <a href="/microsoftteams/manage-apps" target="_blank"></a> um desenvolvedor envia um aplicativo diretamente para a página Gerenciar aplicativos por meio da API Teams Envio de Aplicativos. Para saber mais sobre esse método, consulte <a href="/microsoftteams/submit-approve-custom-apps" target="_blank">Publish a custom app submitted through the Teams App Submission API</a>.

Este artigo fornece orientações de ponta a ponta sobre como levar seu aplicativo Teams do desenvolvimento para a implantação até a descoberta. Essa orientação se concentra nos aspectos Teams do aplicativo e destina-se a administradores e profissionais de IT. Para obter mais informações sobre o desenvolvimento Teams aplicativos, consulte a <a href="/microsoftteams/platform" target="_blank">documentação Teams desenvolvedor.</a>

![Visão geral do seu aplicativo do desenvolvimento para a implantação.](media/upload-custom-apps.png)

## <a name="develop"></a>Desenvolver

### <a name="create-your-app"></a>Criar seu aplicativo

A Microsoft Teams de desenvolvedores facilita que os desenvolvedores integrem seus próprios aplicativos e serviços para melhorar a produtividade, tomar decisões mais rapidamente e criar colaboração em torno de conteúdo e fluxos de trabalho existentes. Os aplicativos construídos na plataforma Teams são pontes entre o cliente Teams e seus serviços e fluxos de trabalho, trazendo-os diretamente para o contexto da sua plataforma de colaboração. Para obter mais informações, acesse a documentação <a href="/microsoftteams/platform" target="_blank">Teams desenvolvedor.</a>

## <a name="validate"></a>Validar

### <a name="get-the-app-package"></a>Obter o pacote do aplicativo

Quando o aplicativo estiver pronto para uso em produção, o desenvolvedor deverá produzir um pacote de aplicativos. Eles podem usar <a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">o App Studio</a> para isso. Eles enviarão o arquivo no formato .zip.

A Microsoft <a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">usa essas diretrizes para</a> garantir que os aplicativos cumpram os padrões de qualidade e segurança do armazenamento de Teams aplicativos globais.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Permitir que usuários confiáveis carreguem aplicativos personalizados

Para validar se o aplicativo está funcionando corretamente no locatário de produção, você precisa permitir que a si mesmo e/ou usuários confiáveis carreguem aplicativos personalizados no locatário de produção. Você usa <a href="/microsoftteams/teams-app-setup-policies" target="_blank">políticas de configuração de aplicativos</a> para fazer isso.

> [!NOTE]
> Se você não estiver confortável ao carregar o aplicativo para seu locatário de produção para validação, mesmo para [](#set-up-and-manage) você ou usuários confiáveis, você pode ignorar essa etapa e seguir as etapas no [Upload](#upload) e Configurar e gerenciar seções para publicar o aplicativo não validado no armazenamento de aplicativos da sua organização. Em seguida, restrinja o acesso a esse aplicativo somente a si mesmo e aos usuários em que você confia. Esses usuários podem, em seguida, obter o aplicativo da loja de aplicativos da sua organização para executar a validação. Depois que o aplicativo for validado, use as mesmas políticas de permissão para abrir o acesso e rolar o aplicativo para uso de produção.

Para permitir que usuários confiáveis carreguem aplicativos personalizados, siga estas etapas:

1. A opção Permitir **interação com aplicativos** personalizados em toda a organização. Para fazer isso:
    1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Teams **aplicativos** Gerenciar aplicativos e clique em  >   **Configurações de aplicativos em** toda a organização.
    2. Em **Aplicativos personalizados,** a ativar **Permitir interação com aplicativos personalizados** e clique em **Salvar**.
2. Desativar a **configuração Upload aplicativos personalizados** na política de configuração de aplicativo global. Para fazer isso:
    1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Teams políticas de Instalação de aplicativos e clique na política  >   **Global (padrão em** toda a organização).
    2. Desativar Upload **aplicativos personalizados** e clique em **Salvar**.
3. Crie uma nova política de configuração de aplicativo que permita carregar aplicativos personalizados e atribuí-la ao seu conjunto de usuários confiáveis. Para fazer isso:
    1. Na navegação à esquerda do centro de administração Microsoft Teams, vá para Teams políticas de Instalação de  >  **aplicativos** e clique em **Adicionar**. Dê à nova política um nome e uma descrição, a Upload **aplicativos personalizados** e clique em **Salvar**.
    2. Selecione a nova política criada e clique em **Gerenciar usuários**. Procure um usuário, clique em **Adicionar** e clique em **Aplicar**. Repita esta etapa para atribuir a política a todos os usuários confiáveis.

        ![Captura de tela da página "Adicionar política de configuração de aplicativo"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Esses usuários agora podem carregar o manifesto do aplicativo para validar se o aplicativo está funcionando corretamente no locatário de produção.

## <a name="upload"></a>Upload

Para disponibilizar o aplicativo aos usuários na loja de aplicativos da sua organização, carregue o aplicativo. Você pode fazer isso na página <a href="/microsoftteams/manage-apps" target="_blank">Gerenciar aplicativos</a> do Microsoft Teams de administração.

1. Na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Aplicativos do Teams** > **Gerenciar aplicativos**.
2. Clique **Upload,** clique em **Selecionar um** arquivo e selecione o pacote de aplicativos que você recebeu do desenvolvedor.

   ![Captura de tela do carregamento de um aplicativo no centro de administração.](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>Configurar e gerenciar

### <a name="control-access-to-the-app"></a>Controlar o acesso ao aplicativo

Por padrão, todos os usuários em sua organização podem acessar o aplicativo na loja de aplicativos da sua organização. Para restringir e controlar quem tem permissão para usar o aplicativo, você pode criar e atribuir uma política de permissão de aplicativo. Para saber mais, confira <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Gerenciar políticas de permissão de aplicativos no Teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Fixar e instalar o aplicativo para que os usuários descubram

Por padrão, para os usuários encontrarem o aplicativo, eles precisam ir até a loja de aplicativos da sua organização e procurar ou pesquisar por ele. Para facilitar o acesso dos usuários ao aplicativo, você pode fixar o aplicativo na barra de aplicativos Teams. Para fazer isso, crie uma política de configuração de aplicativo e atribua-a aos usuários. Para saber mais, confira <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Gerenciar políticas de configuração de aplicativos no Teams</a>.

### <a name="search-the-audit-log-for-teams-app-events"></a>Pesquisar o log de auditoria para Teams eventos do aplicativo

Você pode pesquisar o log de auditoria para exibir Teams de aplicativos em sua organização. Para saber mais sobre como pesquisar o log de auditoria e ver uma lista de atividades Teams que estão registradas no log de auditoria, consulte Pesquisar o log de auditoria em busca de eventos em <a href="/microsoftteams/audit-log-events" target="_blank">Teams</a>.

Para examinar o log de auditoria, você precisa ativar a auditoria no <a href="https://protection.office.com" target="_blank">Centro de Conformidade e Segurança</a>. Para obter instruções, confira <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Ativar ou desativar a pesquisa de log de auditoria</a>. Tenha em mente que os dados de auditoria só estão disponíveis a partir do ponto em que você ativou a auditoria.

## <a name="discover-and-adopt"></a>Descobrir e adotar

Os usuários que têm permissões para o aplicativo podem encontrá-lo na loja de aplicativos da sua organização. Vá para **Built for Your Organization *Name*** na página Aplicativos para encontrar os aplicativos personalizados da sua organização.

![Captura de tela da página Aplicativos mostrando o aplicativo publicado.](media/custom-app-lifecycle-discovery.png)

Se você criou e atribuiu uma política de configuração de aplicativo, o aplicativo será fixado na barra de aplicativos Teams acesso fácil para os usuários que foram atribuídos à política.

## <a name="update"></a>Atualizar

Para atualizar um aplicativo, os desenvolvedores devem continuar a seguir as etapas nas seções [Desenvolver](#develop) [e Validar.](#validate)

Você pode atualizar o aplicativo na página Gerenciar aplicativos no Microsoft Teams de administração. Para fazer isso, na navegação à esquerda do centro de administração Microsoft Teams, acesse **Teams**  >  **Aplicativos Gerenciar aplicativos**. Clique no nome do aplicativo e clique em **Atualizar**. Isso substitui o aplicativo existente, e todas as políticas de permissão de aplicativo e políticas de configuração de aplicativo permanecem impostas para o aplicativo atualizado.

### <a name="end-user-update-experience"></a>Experiência de atualização do usuário final

Na maioria dos casos, depois de concluir uma atualização de aplicativo, a nova versão será exibida automaticamente para usuários finais. No entanto, há algumas atualizações para o manifesto <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams que</a> exigem que a aceitação do usuário seja concluída:

* Um bot foi adicionado ou removido
* A propriedade "botId" de um bot existente foi alterada
* A propriedade "isNotificationOnly" de um bot existente foi alterada
* A propriedade "supportsFiles" do bot foi alterada
* Uma extensão de Mensagens foi adicionada ou removida
* Um novo conector foi adicionado
* Uma nova guia estática foi adicionada
* Uma nova guia configurável foi adicionada
* Propriedades dentro de "webApplicationInfo" alteradas

![Captura de tela da lista de aplicativos, mostrando aplicativos que têm uma nova versão disponível.](media/manage-your-custom-apps-update1.png)

![Captura de tela da opção de atualização para um aplicativo.](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Tópicos relacionados

- [Publicar um aplicativo personalizado enviado por meio da API Teams envio de aplicativos](submit-approve-custom-apps.md)
- [Gerenciar seus aplicativos no Microsoft Teams de administração](manage-apps.md)
- [Gerenciar políticas de aplicativo personalizado e as configurações no Teams](teams-custom-app-policies-and-settings.md)
- [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
- [Gerenciar políticas de configuração de aplicativo no Teams](teams-app-setup-policies.md)