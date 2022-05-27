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
description: Saiba como carregar seus aplicativos personalizados na loja de aplicativos da sua organização no Microsoft Teams de administração.
ms.openlocfilehash: 586ece26155daa5a1627dc6288cbc5c88ee52f18
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681932"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Publicar um aplicativo personalizado carregando um pacote de aplicativos

> [!NOTE]
> Quando você publica um Teams personalizado, ele está disponível para os usuários na loja de aplicativos da sua organização. Há duas maneiras de publicar um aplicativo personalizado e a maneira como você usa depende de como você obtém o aplicativo. **Este artigo se concentra em como publicar** um aplicativo personalizado carregando um pacote do aplicativo (no formato .zip) que um desenvolvedor envia para você. O outro método, aprovando um aplicativo personalizado, é usado quando um desenvolvedor envia um aplicativo diretamente para a página [](manage-apps.md) Gerenciar aplicativos por meio da API de Envio Teams Aplicativo. Para saber mais sobre esse método, consulte [Publicar um aplicativo personalizado enviado por meio da API Teams Envio de Aplicativo](submit-approve-custom-apps.md).

Este artigo fornece diretrizes de ponta a ponta sobre como levar seu aplicativo Teams do desenvolvimento à implantação até a descoberta. Essa orientação se concentra nos Teams do aplicativo e destina-se a administradores e profissionais de TI. Para obter mais informações sobre como Teams aplicativos, consulte a [documentação Teams desenvolvedor.](/microsoftteams/platform/)

![Visão geral do seu aplicativo, desde o desenvolvimento até a implantação.](media/upload-custom-apps.png)

## <a name="develop"></a>Desenvolver

### <a name="create-your-app"></a>Criar seu aplicativo

A Microsoft Teams de desenvolvedores torna mais fácil para os desenvolvedores integrarem seus próprios aplicativos e serviços para melhorar a produtividade, tomar decisões mais rapidamente e criar colaboração em torno de conteúdo e fluxos de trabalho existentes. Os aplicativos criados na plataforma Teams são pontes entre o cliente Teams e seus serviços e fluxos de trabalho, colocando-os diretamente no contexto da plataforma de colaboração. Para obter mais informações, acesse a documentação [Teams desenvolvedor.](/microsoftteams/platform/)

## <a name="validate"></a>Validar

### <a name="get-the-app-package"></a>Obter o pacote do aplicativo

Quando o aplicativo estiver pronto para uso em produção, o desenvolvedor deverá produzir um pacote do aplicativo. Eles podem usar [o App Studio](/microsoftteams/platform/concepts/build-and-test/app-studio-overview) para isso. Eles enviarão o arquivo no formato .zip arquivo.

A Microsoft [usa essas diretrizes para](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines) garantir que os aplicativos cumpram os padrões de qualidade e segurança da loja de Teams aplicativos globais.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Permitir que usuários confiáveis carreguem aplicativos personalizados

Para validar se o aplicativo está funcionando corretamente em seu locatário de produção, você precisa permitir que a si mesmo e/ou usuários confiáveis carreguem aplicativos personalizados no locatário de produção. Você usa [políticas de configuração de](teams-app-setup-policies.md) aplicativo para fazer isso.

> [!NOTE]
> Se você não estiver à vontade para carregar o aplicativo em seu locatário de produção para validação, mesmo para usuários confiáveis ou para si mesmo, ignore esta etapa e siga as etapas no [Upload](#upload) e [](#set-up-and-manage) configure e gerencie seções para publicar o aplicativo não validado na loja de aplicativos da sua organização. Em seguida, restrinja o acesso a esse aplicativo somente a si mesmo e aos usuários em que você confia. Esses usuários podem, então, obter o aplicativo da loja de aplicativos da sua organização para executar a validação. Depois que o aplicativo for validado, use as mesmas políticas de permissão para abrir o acesso e distribuir o aplicativo para uso em produção.

Para permitir que usuários confiáveis carreguem aplicativos personalizados, siga estas etapas:

1. Ative **a configuração Permitir interação com aplicativos personalizados** em toda a organização. Para fazer isso:
    1. No painel de navegação esquerdo do centro de administração Microsoft Teams, acesse Teams **aplicativos** >  Gerenciar aplicativos **e clique em** Configurações de aplicativos **em toda a organização**.
    2. Em **Aplicativos personalizados**, **ative Permitir interação com aplicativos personalizados** e clique em **Salvar**.
2. Desative a **configuração Upload aplicativos personalizados** na política de configuração de aplicativo global. Para fazer isso:
    1. No painel de navegação à esquerda do centro de administração do Microsoft Teams,  >  acesse Teams configuração de aplicativos e clique na política **Global (** padrão em toda a organização).
    2. Desative **Upload aplicativos personalizados** e clique em **Salvar**.
3. Crie uma nova política de configuração de aplicativo que permita carregar aplicativos personalizados e atribuí-lo ao seu conjunto de usuários confiáveis. Para fazer isso:
    1. No painel de navegação esquerdo do centro de administração Microsoft Teams,  >  vá para Teams políticas de instalação de aplicativos **e clique em** **Adicionar**. Dê um nome e uma descrição à nova política, **ative Upload aplicativos personalizados** e clique em **Salvar**.
    2. Selecione a nova política que você criou e clique em **Gerenciar usuários**. Pesquise um usuário, clique **em Adicionar** e, em seguida, clique em **Aplicar**. Repita esta etapa para atribuir a política a todos os usuários confiáveis.

        ![Captura de tela da página "Adicionar política de configuração de aplicativo"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Esses usuários agora podem carregar o manifesto do aplicativo para validar se o aplicativo está funcionando corretamente no locatário de produção.

## <a name="upload"></a>Upload

Para disponibilizar o aplicativo aos usuários na loja de aplicativos da sua organização, carregue o aplicativo. Você pode fazer isso na [página Gerenciar aplicativos](manage-apps.md) do Microsoft Teams de administração.

1. Na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Aplicativos do Teams** > **Gerenciar aplicativos**.
2. Selecione **Upload**, clique **Upload**, selecione o pacote do aplicativo que você recebeu do desenvolvedor e selecione **Abrir**.

   ![Captura de tela do carregamento de um aplicativo no centro de administração.](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>Configurar e gerenciar

### <a name="control-access-to-the-app"></a>Controlar o acesso ao aplicativo

Por padrão, todos os usuários em sua organização podem acessar o aplicativo na loja de aplicativos da sua organização. Para restringir e controlar quem tem permissão para usar o aplicativo, você pode criar e atribuir uma política de permissão de aplicativo. Para saber mais, confira [Gerenciar políticas de permissão de aplicativos no Teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Fixar e instalar o aplicativo para que os usuários descubram

Por padrão, para que os usuários localizem o aplicativo, eles precisam acessar a loja de aplicativos da sua organização e procurar ou pesquisar por ele. Para facilitar o acesso dos usuários ao aplicativo, você pode fixar o aplicativo na barra de aplicativos Teams. Para fazer isso, crie uma política de configuração de aplicativo e atribua-a aos usuários. Para saber mais, confira [Gerenciar políticas de configuração de aplicativos no Teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Pesquisar o log de auditoria para Teams de aplicativo

Você pode pesquisar o log de auditoria para exibir Teams de aplicativos em sua organização. Para saber mais sobre como pesquisar o log de auditoria e ver uma lista de atividades do Teams que estão registradas no log de auditoria, consulte Pesquisar no log de auditoria eventos no [Teams](audit-log-events.md).

Para examinar o log de auditoria, você precisa ativar a auditoria no [Centro de Conformidade e Segurança](https://sip.protection.office.com/homepage). Para obter instruções, confira [Ativar ou desativar a pesquisa de log de auditoria](/microsoft-365/compliance/turn-audit-log-search-on-or-off). Tenha em mente que os dados de auditoria só estão disponíveis a partir do ponto em que você ativou a auditoria.

## <a name="discover-and-adopt"></a>Descobrir e adotar

Os usuários que têm permissões para o aplicativo podem encontrá-lo na loja de aplicativos da sua organização. Acesse Built **for *Your Organization Name*** na página Aplicativos para encontrar os aplicativos personalizados da sua organização.

![Captura de tela da página Aplicativos mostrando o aplicativo publicado.](media/custom-app-lifecycle-discovery.png)

Se você criou e atribuiu uma política de configuração de aplicativo, o aplicativo será fixado na barra de aplicativos no Teams para facilitar o acesso para os usuários que foram atribuídos à política.

## <a name="update"></a>Atualizar

Para atualizar um aplicativo, os desenvolvedores devem continuar seguindo as etapas [nas seções](#develop) Desenvolver e [Validar](#validate) .

Você pode atualizar o aplicativo na página Gerenciar aplicativos no Microsoft Teams de administração. Para fazer isso, no painel de navegação esquerdo do centro de administração Microsoft Teams, acesse **Teams aplicativos** > **Gerenciar aplicativos**. Clique no nome do aplicativo e clique em **Atualizar**. Isso substitui o aplicativo existente e todas as políticas de permissão de aplicativo e políticas de configuração de aplicativo permanecem impostas para o aplicativo atualizado.

### <a name="end-user-update-experience"></a>Experiência de atualização do usuário final

Na maioria dos casos, depois de concluir uma atualização de aplicativo, a nova versão será exibida automaticamente para os usuários finais. No entanto, há algumas atualizações no manifesto Microsoft Teams [que](/microsoftteams/platform/resources/schema/manifest-schema) exigem que a aceitação do usuário seja concluída:

- Um bot foi adicionado ou removido
- A propriedade "botId" de um bot existente foi alterada
- A propriedade "isNotificationOnly" de um bot existente foi alterada
- A funcionalidade SupportsCalling, SupportsVideo e SupportsFiles de um bot foi adicionada
- Uma extensão de mensagens foi adicionada
- Um novo conector foi adicionado
- Permissões dentro de "Autorização" foram adicionadas ou alteradas

![Captura de tela da lista de aplicativos mostrando aplicativos que têm uma nova versão disponível.](media/manage-your-custom-apps-update1.png)

![Captura de tela da opção de atualização para um aplicativo.](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Tópicos relacionados

- [Publicar um aplicativo personalizado enviado por meio da API de Envio Teams Aplicativo](submit-approve-custom-apps.md)

- [Gerenciar seus aplicativos no Microsoft Teams de administração](manage-apps.md)
- [Gerenciar políticas de aplicativo personalizado e as configurações no Teams](teams-custom-app-policies-and-settings.md)

- [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
- [Gerenciar políticas de configuração de aplicativo no Teams](teams-app-setup-policies.md)
