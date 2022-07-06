---
title: Carregar seus aplicativos personalizados no centro de administração do Microsoft Teams
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
description: Saiba como carregar seus aplicativos personalizados na loja de aplicativos da sua organização no centro de administração do Microsoft Teams.
ms.openlocfilehash: 5ef5992e01b5de4e2f4feaed51b50e2d0f16c0d8
ms.sourcegitcommit: 4be2a5db44972b35bdde5752eea0d74cf831607a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2022
ms.locfileid: "66642756"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Publicar um aplicativo personalizado carregando um pacote de aplicativos

> [!NOTE]
> Quando você publica um aplicativo personalizado do Teams, ele está disponível para os usuários na loja de aplicativos da sua organização. Há duas maneiras de publicar um aplicativo personalizado e a maneira como você usa depende de como você obtém o aplicativo. **Este artigo se concentra em como publicar** um aplicativo personalizado carregando um pacote do aplicativo (no formato .zip) que um desenvolvedor envia para você. O outro método, aprovando um aplicativo personalizado, é usado quando um desenvolvedor envia um aplicativo diretamente para a página [](manage-apps.md) Gerenciar aplicativos por meio da API de Envio de Aplicativo do Teams. Para saber mais sobre esse método, consulte [Publicar um aplicativo personalizado enviado por meio da API de Envio de Aplicativo do Teams](submit-approve-custom-apps.md).

Este artigo fornece diretrizes de ponta a ponta sobre como levar seu aplicativo teams do desenvolvimento à implantação até a descoberta. Essas diretrizes se concentram nos aspectos do aplicativo do Teams e são destinadas a administradores e profissionais de TI. Para obter mais informações sobre como desenvolver aplicativos do Teams, consulte a [documentação do desenvolvedor do Teams](/microsoftteams/platform/).

![Visão geral do seu aplicativo, desde o desenvolvimento até a implantação.](media/upload-custom-apps.png)

## <a name="create-your-app"></a>Criar seu aplicativo

A plataforma de desenvolvedor do Microsoft Teams facilita para os desenvolvedores integrarem seus próprios aplicativos e serviços para melhorar a produtividade, tomar decisões mais rapidamente e criar colaboração em torno de conteúdo e fluxos de trabalho existentes. Os aplicativos criados na plataforma Teams são pontes entre o cliente do Teams e seus serviços e fluxos de trabalho, colocando-os diretamente no contexto de sua plataforma de colaboração. Para obter mais informações, acesse a documentação [do desenvolvedor do Teams](/microsoftteams/platform/).

## <a name="validate"></a>Validar

### <a name="get-the-app-package"></a>Obter o pacote do aplicativo

Quando o aplicativo estiver pronto para uso em produção, o desenvolvedor deverá produzir um pacote do aplicativo. Eles podem usar [o App Studio](/microsoftteams/platform/concepts/build-and-test/app-studio-overview). Eles enviarão o arquivo no formato .zip arquivo.

Todos os aplicativos na loja do Teams [](overview-of-app-validation.md) passam por uma validação de aplicativo obrigatória para estar em conformidade com os padrões de qualidade e segurança da loja global de aplicativos do Teams. Além disso, a Microsoft incentiva fortemente os desenvolvedores de aplicativos a [](overview-of-app-certification.md) participar de um programa de conformidade de aplicativo opcional que indica controles de conformidade, segurança e privacidade aprimorados. Para obter mais informações, consulte as [diretrizes de validação de aplicativo do Teams](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines).

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Permitir que usuários confiáveis carreguem aplicativos personalizados

Para validar se o aplicativo está funcionando corretamente em seu locatário de produção, você precisa permitir que a si mesmo e/ou usuários confiáveis carreguem aplicativos personalizados no locatário de produção. Você usa [políticas de configuração de](teams-app-setup-policies.md) aplicativo para fazer isso.

> [!NOTE]
> Se você não estiver à vontade para carregar o aplicativo em seu locatário de produção para validação, mesmo para usuários confiáveis ou para si mesmo, ignore esta etapa e siga [](#upload) as etapas [](#set-up-and-manage) nas seções Carregar e Configurar e gerenciar para publicar o aplicativo não validado na loja de aplicativos da sua organização. Em seguida, restrinja o acesso a esse aplicativo somente a si mesmo e aos usuários em que você confia. Esses usuários podem, então, obter o aplicativo da loja de aplicativos da sua organização para executar a validação. Depois que o aplicativo for validado, use as mesmas políticas de permissão para abrir o acesso e distribuir o aplicativo para uso em produção.

Para permitir que usuários confiáveis carreguem aplicativos personalizados, siga estas etapas:

1. Ative **a configuração Permitir interação com aplicativos personalizados** em toda a organização. Para fazer isso:

    1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, acesse Aplicativos do **Teams** >  Gerenciar aplicativos **e clique em** **Configurações de aplicativos em toda a organização**.
    
    2. Em **Aplicativos personalizados**, **ative Permitir interação com aplicativos personalizados** e clique em **Salvar**.
    
1. Desative a **configuração Carregar aplicativos personalizados** na política de configuração de aplicativo global. Para fazer isso:

    1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá para políticas de Instalação de aplicativos do **Teams** > **e clique na** política **Global (padrão** em toda a organização).
    
    2. Desative **Carregar aplicativos personalizados** e clique em **Salvar**.
    
1. Crie uma nova política de configuração de aplicativo que permita carregar aplicativos personalizados e atribuí-lo ao seu conjunto de usuários confiáveis. Para fazer isso:

    1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá para políticas de Instalação de **aplicativos** >  do Teams **e clique em** **Adicionar**. Dê um nome e uma descrição à nova política, ative Carregar aplicativos **personalizados** e clique em **Salvar**.
    
    2. Selecione a nova política que você criou e clique em **Gerenciar usuários**. Pesquise um usuário, clique **em Adicionar** e, em seguida, clique em **Aplicar**. Repita esta etapa para atribuir a política a todos os usuários confiáveis.

       ![Captura de tela da página "Adicionar política de configuração de aplicativo"](media/manage-your-lob-apps-new-app-setup-policy.png)

Esses usuários agora podem carregar o manifesto do aplicativo para validar se o aplicativo está funcionando corretamente no locatário de produção.

## <a name="upload"></a>Carregar

Para disponibilizar o aplicativo aos usuários na loja de aplicativos da sua organização, carregue o aplicativo.

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, acesse **Aplicativos do Teams Gerenciar** > **[aplicativos](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Selecione **Carregar**, clique **em Carregar**, selecione o pacote do aplicativo que você recebeu do desenvolvedor e selecione **Abrir**.

   ![Captura de tela do carregamento de um aplicativo no centro de administração.](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>Configurar e gerenciar

### <a name="control-access-to-the-app"></a>Controlar o acesso ao aplicativo

Por padrão, todos os usuários em sua organização podem acessar o aplicativo na loja de aplicativos da sua organização. Para restringir e controlar quem tem permissão para usar o aplicativo, você pode criar e atribuir uma política de permissão de aplicativo. Para saber mais, confira [Gerenciar políticas de permissão de aplicativos no Teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Fixar e instalar o aplicativo para que os usuários descubram

Por padrão, para que os usuários localizem o aplicativo, eles precisam acessar a loja de aplicativos da sua organização e procurar ou pesquisar por ele. Para facilitar o acesso dos usuários ao aplicativo, você pode fixar o aplicativo na barra de aplicativos no Teams. Para fazer isso, crie uma política de configuração de aplicativo e atribua-a aos usuários. Para saber mais, confira [Gerenciar políticas de configuração de aplicativos no Teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Pesquisar no log de auditoria eventos de aplicativo do Teams

Você pode pesquisar o log de auditoria para exibir a atividade de aplicativos do Teams em sua organização. Para saber mais sobre como auditar as atividades do Teams, consulte [pesquisar no log de auditoria eventos no Teams](audit-app-management-activities.md).

Para examinar o log de auditoria, você precisa ativar a auditoria no [Centro de Conformidade e Segurança](https://sip.protection.office.com/homepage). Para obter instruções, confira [Ativar ou desativar a pesquisa de log de auditoria](/microsoft-365/compliance/turn-audit-log-search-on-or-off). Tenha em mente que os dados de auditoria só estão disponíveis a partir do ponto em que você ativou a auditoria.

## <a name="discover-and-adopt"></a>Descobrir e adotar

Os usuários finais que têm permissões para o aplicativo podem encontrá-lo na loja de aplicativos da sua organização. Acesse Built **for *Your Organization Name*** na página Aplicativos para encontrar os aplicativos personalizados da sua organização.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Captura de tela da loja do Teams mostrando o aplicativo personalizado publicado para a organização" lightbox="media/custom-app-lifecycle-discovery.png":::

Se você criou e atribuiu uma política de configuração de aplicativo, o aplicativo será fixado na barra de aplicativos no Teams para facilitar o acesso para os usuários que foram atribuídos à política.

## <a name="update"></a>Atualizar

Para atualizar um aplicativo, os desenvolvedores seguem as etapas nas seções [Criar seu aplicativo](#create-your-app) e [Validar](#validate) .

Você pode atualizar o aplicativo na página Gerenciar aplicativos no Centro de administração do Microsoft Teams. Para fazer isso, no painel de navegação esquerdo do centro de administração do Microsoft Teams, acesse **Aplicativos do Teams Gerenciar** > **aplicativos**. Clique no nome do aplicativo e clique em **Atualizar**. Isso substitui o aplicativo existente e todas as políticas de permissão de aplicativo e políticas de configuração de aplicativo permanecem impostas para o aplicativo atualizado.

### <a name="end-user-update-experience"></a>Experiência de atualização do usuário final

Na maioria dos casos, depois de concluir uma atualização de aplicativo, a nova versão será exibida automaticamente para os usuários finais. Para obter mais informações, consulte [a experiência de atualização do usuário final](apps-update-experience.md).

## <a name="related-topics"></a>Tópicos relacionados

* [Publicar um aplicativo personalizado enviado por meio da API de Envio de Aplicativo do Teams](submit-approve-custom-apps.md)
* [Gerenciar seus aplicativos no centro de administração do Microsoft Teams](manage-apps.md)
* [Gerenciar políticas de aplicativo personalizado e as configurações no Teams](teams-custom-app-policies-and-settings.md)
* [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
* [Gerenciar políticas de configuração de aplicativo no Teams](teams-app-setup-policies.md)
