---
title: Carregar seus aplicativos personalizados no centro de administração do Microsoft Teams
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
description: Saiba como carregar seus aplicativos personalizados na loja de aplicativos da sua organização no centro de administração do Microsoft Teams.
ms.openlocfilehash: f1b5267fe1003d69c0d91349f5b6bc425df2b038
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831161"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Publicar um aplicativo personalizado carregando um pacote de aplicativo

> [!NOTE]
> Quando você publica um aplicativo personalizado do Teams, ele está disponível para os usuários na loja de aplicativos da sua organização. Há duas maneiras de publicar um aplicativo personalizado e a maneira como você usa depende de como você obter o aplicativo. Este artigo se concentra em como publicar um aplicativo personalizado carregando um pacote de aplicativo (no formato **.zip)** que um desenvolvedor envia para você. O outro método, aprovando um aplicativo personalizado, é usado quando <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank"></a> um desenvolvedor envia um aplicativo diretamente para a página Gerenciar aplicativos por meio da API de Envio de Aplicativos do Teams. Para saber mais sobre esse método, consulte <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">Publicar um aplicativo personalizado enviado por meio da API de Envio de Aplicativos do Teams.</a>

Este artigo fornece orientações de ponta a ponta sobre como levar seu aplicativo Teams do desenvolvimento à implantação até a descoberta. Essa orientação se concentra nos aspectos do Teams do aplicativo e destina-se a administradores e profissionais de IT. Para obter mais informações sobre o desenvolvimento de aplicativos do Teams, consulte a <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentação do desenvolvedor do Teams.</a>

![Visão geral do seu aplicativo, desde o desenvolvimento até a implantação](media/upload-custom-apps.png)

## <a name="develop"></a>Desenvolver

### <a name="create-your-app"></a>Criar seu aplicativo

A plataforma de desenvolvedor do Microsoft Teams facilita a integração de seus próprios aplicativos e serviços para melhorar a produtividade, tomar decisões com mais rapidez e criar colaboração em torno de conteúdo e fluxos de trabalho existentes. Os aplicativos integrados à plataforma Teams são pontes entre o cliente do Teams e seus serviços e fluxos de trabalho, trazendo-os diretamente para o contexto da sua plataforma de colaboração. Para obter mais informações, acesse a documentação <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">do desenvolvedor do Teams.</a>

## <a name="validate"></a>Validar

### <a name="get-the-app-package"></a>Obter o pacote do aplicativo

Quando o aplicativo estiver pronto para ser usado na produção, o desenvolvedor deverá produzir um pacote de aplicativo. Eles podem usar <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">o App Studio</a> para isso. Eles enviarão o arquivo no formato .zip.

A Microsoft <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">usa essas diretrizes para</a> garantir que os aplicativos cumpram os padrões de qualidade e segurança do armazenamento global de aplicativos do Teams.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Permitir que usuários confiáveis carreguem aplicativos personalizados

Para validar se o aplicativo está funcionando corretamente em seu locatário de produção, você precisa permitir que a si mesmo e/ou usuários confiáveis carreguem aplicativos personalizados no locatário de produção. Você usa políticas <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">de configuração de aplicativo</a> para fazer isso.

> [!NOTE]
> Se você não estiver confortável ao carregar o aplicativo em seu locatário de produção para validação, mesmo [](#set-up-and-manage) para si mesmo ou para usuários confiáveis, ignore esta etapa e siga as etapas nas seções [Carregar](#upload) e Configurar e gerenciar para publicar o aplicativo nãovalidado na loja de aplicativos da sua organização. Em seguida, restrinja o acesso a esse aplicativo somente a si mesmo e aos usuários em que você confia. Esses usuários podem então obter o aplicativo da loja de aplicativos da sua organização para realizar a validação. Depois que o aplicativo for validado, use as mesmas políticas de permissão para abrir o acesso e roll-out do aplicativo para uso em produção.

Para permitir que usuários confiáveis carreguem aplicativos personalizados, siga estas etapas:

1. Ativar a **configuração Permitir interação com aplicativos** personalizados em toda a organização. Para fazer isso:
    1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para os aplicativos **do Teams** Gerenciar aplicativos e clique em Configurações de aplicativos em toda a  >   **organização.**
    2. Em **Aplicativos Personalizados,** a ligue **Permitir interação com aplicativos personalizados** e clique em **Salvar**.
2. Desativar a **configuração Carregar aplicativos personalizados** na política de configuração de aplicativo global. Para fazer isso:
    1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de Instalação de aplicativos do **Teams** e clique na política Global (padrão em toda  >   **a** organização).
    2. Desativar o **carregamento de aplicativos personalizados** e clique em **Salvar.**
3. Crie uma nova política de configuração de aplicativo que permita carregar aplicativos personalizados e atribuí-la ao seu conjunto de usuários confiáveis. Para fazer isso:
    1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de Instalação de aplicativos do **Teams** e clique  >  em **Adicionar**. Dê um nome e uma descrição à nova política, a ligue Carregar aplicativos **personalizados** e clique em **Salvar.**
    2. Selecione a nova política que você criou e clique em **Gerenciar usuários.** Pesquise um usuário, clique **em Adicionar** e, em seguida, clique em **Aplicar.** Repita esta etapa para atribuir a política a todos os usuários confiáveis.

        ![Captura de tela da página "Adicionar política de configuração de aplicativo"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Esses usuários agora podem carregar o manifesto do aplicativo para validar se o aplicativo está funcionando corretamente no locatário de produção.

## <a name="upload"></a>Carregar

Para disponibilizar o aplicativo para os usuários na loja de aplicativos da sua organização, carregue o aplicativo. Você pode fazer isso na página <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Gerenciar aplicativos</a> do centro de administração do Microsoft Teams.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **aplicativos do Teams**  >  **Gerenciar aplicativos.**
2. Clique **em Carregar,** **clique em Selecionar um** arquivo e selecione o pacote do aplicativo que você recebeu do desenvolvedor.

   ![Captura de tela do carregamento de um aplicativo no centro de administração](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>Configurar e gerenciar

### <a name="control-access-to-the-app"></a>Controlar o acesso ao aplicativo

Por padrão, todos os usuários em sua organização podem acessar o aplicativo na loja de aplicativos da sua organização. Para restringir e controlar quem tem permissão para usar o aplicativo, você pode criar e atribuir uma política de permissão de aplicativo. Para saber mais, confira <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Gerenciar políticas de permissão de aplicativo no Teams.</a>

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Fixar e instalar o aplicativo para que os usuários descubram

Por padrão, para os usuários encontrarem o aplicativo, eles precisam ir para a loja de aplicativos da sua organização e procurar ou procurar por ele. Para facilitar o acesso dos usuários ao aplicativo, você pode fixar o aplicativo na barra de aplicativos no Teams. Para fazer isso, crie uma política de configuração de aplicativo e atribua-a aos usuários. Para saber mais, confira <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Gerenciar políticas de configuração de aplicativo no Teams.</a>

### <a name="search-the-audit-log-for-teams-app-events"></a>Pesquisar o log de auditoria para eventos de aplicativos do Teams

Você pode pesquisar o log de auditoria para exibir a atividade de aplicativos do Teams em sua organização. Para saber mais sobre como pesquisar o log de auditoria e ver uma lista de atividades do Teams que estão registradas no log de auditoria, consulte Pesquisar o log de auditoria para eventos <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">no Teams.</a>

Antes de poder pesquisar o log de auditoria, primeiro você precisa ativar a auditoria no Centro de Conformidade & <a href="https://protection.office.com" target="_blank">Segurança.</a> Para saber mais, confira Ativar ou desativar a pesquisa <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">de log de auditoria.</a> Lembre-se de que os dados de auditoria só estão disponíveis a partir do momento em que você a adotou a auditoria.

## <a name="discover-and-adopt"></a>Descobrir e adotar

Os usuários que têm permissões para o aplicativo podem encontrá-lo na loja de aplicativos da sua organização. Vá para **Built for Your Organization *Name*** na página Aplicativos para encontrar os aplicativos personalizados da sua organização.

![Captura de tela da página Aplicativos mostrando o aplicativo publicado ](media/custom-app-lifecycle-discovery.png)

Se você criou e atribuiu uma política de configuração de aplicativo, o aplicativo é fixado na barra de aplicativos no Teams para facilitar o acesso para os usuários que foram atribuídos à política.

## <a name="update"></a>Atualizar

Para atualizar um aplicativo, os desenvolvedores devem continuar seguindo as etapas nas seções [Desenvolver](#develop) [e Validar.](#validate)

Você pode atualizar o aplicativo na página Gerenciar aplicativos no centro de administração do Microsoft Teams. Para fazer isso, na navegação à esquerda do centro de administração do Microsoft Teams, vá para **aplicativos do Teams**  >  **Gerenciar aplicativos.** Clique no nome do aplicativo e clique em **Atualizar.** Isso substitui o aplicativo existente, e todas as políticas de permissão do aplicativo e as políticas de configuração de aplicativos permanecem impostas para o aplicativo atualizado.

### <a name="end-user-update-experience"></a>Experiência de atualização do usuário final

Na maioria dos casos, depois de concluir uma atualização de aplicativo, a nova versão aparecerá automaticamente para os usuários finais. No entanto, há algumas atualizações no manifesto do <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams</a> que exigem que a aceitação do usuário seja concluída:

* Um bot foi adicionado ou removido
* A propriedade "botId" de um bot existente foi alterada
* A propriedade "isNotificationOnly" de um bot existente foi alterada
* A propriedade "supportsFiles" do bot foi alterada
* Uma extensão de Mensagens foi adicionada ou removida
* Um novo conector foi adicionado
* Uma nova guia estática foi adicionada
* Uma nova guia configurável foi adicionada
* Propriedades dentro de "webApplicationInfo" alteradas

![Captura de tela da lista de aplicativos, mostrando aplicativos que têm uma nova versão disponível](media/manage-your-custom-apps-update1.png)

![Captura de tela da opção de atualização para um aplicativo](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Tópicos relacionados

- [Publicar um aplicativo personalizado enviado por meio da API de Envio de Aplicativos do Teams](submit-approve-custom-apps.md)
- [Gerenciar seus aplicativos no centro de administração do Microsoft Teams](manage-apps.md)
- [Gerenciar políticas de aplicativo personalizado e as configurações no Teams](teams-custom-app-policies-and-settings.md)
- [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
- [Gerenciar políticas de configuração de aplicativo no Teams](teams-app-setup-policies.md)
