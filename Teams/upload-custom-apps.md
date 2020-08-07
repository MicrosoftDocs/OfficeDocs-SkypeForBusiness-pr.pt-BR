---
title: Carregar seus aplicativos personalizados no centro de administração do Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Saiba como carregar seus aplicativos personalizados para a loja de aplicativos da sua organização no centro de administração do Microsoft Teams.
ms.openlocfilehash: d43b19f4ada3ce6f0424a324cdea6f194575325b
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583640"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Publicar um aplicativo personalizado carregando um pacote de aplicativo

> [!NOTE]
> Quando você publica um aplicativo personalizado do Teams, ele está disponível para os usuários na loja de aplicativos da sua organização. Há duas maneiras de publicar um aplicativo personalizado e a maneira como você pode usar depende de como você obtém o aplicativo. **Este artigo se concentra em como publicar um aplicativo personalizado carregando um pacote de aplicativo (em formato. zip) que um desenvolvedor envia para você**. O outro método, a aprovação de um aplicativo personalizado, é usado quando um desenvolvedor envia um aplicativo diretamente para a página <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">gerenciar aplicativos</a> por meio da API de envio do aplicativo Teams. Para saber mais sobre esse método, consulte <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">publicar um aplicativo personalizado enviado por meio da API de envio do aplicativo Teams</a>.

Este artigo fornece uma orientação de ponta a ponta para como levar o aplicativo Teams do desenvolvimento à implantação para descoberta. Esta orientação concentra-se nos aspectos da equipe do aplicativo e destina-se a administradores e profissionais de ti. Para obter mais informações sobre o desenvolvimento de aplicativos do Teams, consulte a <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentação do desenvolvedor do teams</a>.

![Visão geral do seu aplicativo do desenvolvimento para a implantação](media/upload-custom-apps.png)

## <a name="develop"></a>Desenvolver

### <a name="create-your-app"></a>Criar seu aplicativo

A plataforma de desenvolvedor do Microsoft Teams facilita para os desenvolvedores integrarem seus próprios aplicativos e serviços para melhorar a produtividade, tomar decisões mais rápidas e criar colaboração em torno de conteúdo e fluxos de trabalho existentes. Os aplicativos criados na plataforma de equipe são pontes entre o cliente do Teams e seus serviços e fluxos de trabalho, trazendo-os diretamente para o contexto de sua plataforma de colaboração. Para obter mais informações, acesse a <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentação do desenvolvedor do teams</a>.

## <a name="validate"></a>Válida

### <a name="get-the-app-package"></a>Obter o pacote do aplicativo

Quando o aplicativo está pronto para ser usado na produção, o desenvolvedor deve produzir um pacote de aplicativo. Eles podem usar o <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">app Studio</a> para isso. Eles enviarão o arquivo no formato. zip.

A Microsoft usa <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">essas diretrizes</a> para garantir que os aplicativos estejam em conformidade com os padrões de qualidade e segurança da loja de aplicativos global do teams.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Permitir que usuários confiáveis carreguem aplicativos personalizados

Para validar que o aplicativo está funcionando corretamente em seu locatário de produção, você precisa permitir que os usuários de si mesmo e/ou confiáveis carreguem aplicativos personalizados no locatário de produção. Você usa <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">políticas de configuração do aplicativo</a> para fazer isso.

> [!NOTE]
> Se você não se sentir à vontade para fazer o upload do aplicativo em seu locatário de produção para validação, mesmo para usuários confiáveis ou confiáveis, pode ignorar esta etapa e seguir as etapas nas seções [carregar](#upload) e [configurar e gerenciar](#set-up-and-manage) para publicar o aplicativo não validado na loja de aplicativos da sua organização. Em seguida, restrinja o acesso a esse aplicativo apenas para você e os usuários confiáveis. Esses usuários podem obter o aplicativo na loja de aplicativos da sua organização para executar a validação. Depois que o aplicativo for validado, use as mesmas políticas de permissão para abrir o Access e faça o lançamento do aplicativo para uso em produção.

Para permitir que usuários confiáveis carreguem aplicativos personalizados, siga estas etapas:

1. Ative a configuração **permitir interação com aplicativos personalizados** do aplicativo de toda a organização. Para fazer isso:
    1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos**e clique em **configurações de aplicativo de toda a organização**.
    2. Em **aplicativos personalizados**, ative **permitir interação com aplicativos personalizados**e, em seguida, clique em **salvar**.
2. Desative a configuração **carregar aplicativos personalizados** na política de configuração do aplicativo global. Para fazer isso:
    1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de configuração de **aplicativos do teams**  >  **Setup policies**e clique na política **global (padrão para toda a organização)** .
    2. Desative **carregar aplicativos personalizados**e, em seguida, clique em **salvar**.
3. Crie uma nova política de configuração de aplicativo que permita carregar aplicativos personalizados e atribuí-lo ao conjunto de usuários confiáveis. Para fazer isso:
    1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de configuração de **aplicativos do teams**  >  **Setup policies**e, em seguida, clique em **Adicionar**. Dê um nome e uma descrição para a nova política, ative **carregar aplicativos personalizados**e, em seguida, clique em **salvar**.
    2. Selecione a nova política que você criou e clique em **gerenciar usuários**. Procure um usuário, clique em **Adicionar**e, em seguida, clique em **aplicar**. Repita esta etapa para atribuir a política a todos os usuários confiáveis.

        ![Captura de tela da página "Adicionar política de configuração de aplicativo"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Esses usuários agora podem carregar o manifesto do aplicativo para validar que o aplicativo está funcionando corretamente no locatário de produção.

## <a name="upload"></a>Upload

Para disponibilizar o aplicativo para os usuários na loja de aplicativos da sua organização, carregue o aplicativo. Você pode fazer isso na página <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">gerenciar aplicativos</a> do centro de administração do Microsoft Teams.

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos**.
2. Clique em **carregar**, clique em **selecionar um arquivo**e selecione o pacote do aplicativo que você recebeu do desenvolvedor.

   ![Captura de tela do carregamento de um aplicativo no centro de administração](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>Configurar e gerenciar

### <a name="control-access-to-the-app"></a>Controlar o acesso ao aplicativo

Por padrão, todos os usuários em sua organização podem acessar o aplicativo na loja de aplicativos da sua organização. Para restringir e controlar quem tem permissão para usar o aplicativo, você pode criar e atribuir uma política de permissão do aplicativo. Para saber mais, consulte <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">gerenciar políticas de permissão do aplicativo no Microsoft Teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Fixar e instalar o aplicativo para que os usuários descubram

Por padrão, para que os usuários localizem o aplicativo, eles precisam ir para a loja de aplicativos da sua organização e procurar ou procurá-lo. Para facilitar para os usuários acessar o aplicativo, você pode fixar o aplicativo à barra de aplicativos no Microsoft Teams. Para fazer isso, crie uma política de configuração de aplicativo e atribua-a a usuários. Para saber mais, consulte <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">gerenciar políticas de configuração de aplicativos no Microsoft Teams</a>.

### <a name="search-the-audit-log-for-teams-app-events"></a>Pesquisar eventos do aplicativo Teams no log de auditoria

Você pode pesquisar o log de auditoria para ver a atividade de aplicativos do teams em sua organização. Para saber mais sobre como Pesquisar no log de auditoria e ver uma lista de atividades do teams que são registradas no log de auditoria, consulte <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Pesquisar o log de auditoria para eventos no Teams</a>.

Para que você possa Pesquisar no log de auditoria, primeiro ative a auditoria no <a href="https://protection.office.com" target="_blank">centro de conformidade do & de segurança</a>. Para saber mais, confira <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Ativar ou desativar a pesquisa de log de auditoria</a>. Lembre-se de que os dados de auditoria estão disponíveis apenas no ponto em que você ativou a auditoria.

## <a name="discover-and-adopt"></a>Descubra e adote

Os usuários que têm permissões para o aplicativo podem encontrá-lo na loja de aplicativos da sua organização. Vá para ** *o nome da sua organização* específico** na página aplicativos para localizar os aplicativos personalizados da sua organização.

![Captura de tela da página de aplicativos mostrando o aplicativo publicado ](media/custom-app-lifecycle-discovery.png)

Se você criou e atribuiu uma política de configuração de aplicativo, o aplicativo é fixado à barra de aplicativos no Teams para facilitar o acesso para os usuários que receberam a política.

## <a name="update"></a>Atualizar

Para atualizar um aplicativo, os desenvolvedores devem continuar a seguir as etapas nas seções [desenvolver](#develop) e [validar](#validate) .

Você pode atualizar o aplicativo na página Gerenciar aplicativos no centro de administração do Microsoft Teams. Para fazer isso, na navegação à esquerda do centro de administração do Microsoft Teams, vá até **Team apps**  >  **gerenciar aplicativos**. Clique no nome do aplicativo e, em seguida, clique em **Atualizar**. Isso substitui o aplicativo existente, e todas as políticas de permissão do aplicativo e políticas de configuração do aplicativo permanecem impostas para o aplicativo atualizado.

### <a name="end-user-update-experience"></a>Experiência de atualização do usuário final

Na maioria dos casos, após concluir uma atualização do aplicativo, a nova versão será exibida automaticamente para os usuários finais. No entanto, há algumas atualizações do <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">manifesto do Microsoft Teams</a> que exigem a aceitação do usuário para serem concluídas:

* Um bot foi adicionado ou removido
* A propriedade "botId" de um bot existente foi alterada
* A propriedade "isNotificationOnly" de um bot existente foi alterada
* A propriedade "supportsFiles" do bot foi alterada
* Uma extensão de mensagens foi adicionada ou removida
* Um novo conector foi adicionado
* Uma nova guia estática foi adicionada
* Uma nova guia configurável foi adicionada
* As propriedades dentro de "webApplicationInfo" foram alteradas

![Captura de tela da lista de aplicativos, mostrando os aplicativos que têm uma nova versão disponível](media/manage-your-custom-apps-update1.png)

![Captura de tela da opção de atualização para um aplicativo](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Tópicos relacionados

- [Publicar um aplicativo personalizado enviado por meio da API de envio do aplicativo Teams](submit-approve-custom-apps.md)
- [Gerenciar seus aplicativos no centro de administração do Microsoft Teams](manage-apps.md)
- [Gerenciar políticas de aplicativo personalizado e as configurações no Teams](teams-custom-app-policies-and-settings.md)
- [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
- [Gerenciar políticas de configuração de aplicativo no Teams](teams-app-setup-policies.md)
