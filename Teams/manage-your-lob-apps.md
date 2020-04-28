---
title: Gerenciar seus aplicativos de linha de negócios no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
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
description: Saiba como levar seus aplicativos personalizados do teams do desenvolvimento para a implantação.
ms.openlocfilehash: dd34b96a40affc2ffd7e5ddeb6a118a122831296
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904943"
---
# <a name="manage-your-line-of-business-apps-in-microsoft-teams"></a>Gerenciar seus aplicativos de linha de negócios no Microsoft Teams

Este artigo fornece uma orientação de ponta a ponta para como levar o aplicativo Teams do desenvolvimento para a implantação. Esta orientação se concentra nos aspectos da equipe do aplicativo e destina-se aos profissionais de ti. Para obter mais informações sobre o desenvolvimento de aplicativos do Teams, consulte <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">aqui</a>.

![Visão geral do seu aplicativo do desenvolvimento para a implantação](media/manage-your-lob-apps.png)

## <a name="getting-started"></a>Introdução

Para criar e gerenciar aplicativos de linha de negócios (LOB) no Teams, você precisará de dois locatários: um locatário de teste para desenvolvimento e um locatário de produção.

> [!NOTE]
> Se ainda não tiver um locatário de teste, você pode criar rapidamente um e preenchê-lo com dados de teste usando o programa para desenvolvedores do Office 365. <a href="https://developer.microsoft.com/office/dev-program" target="_blank">Saiba mais aqui</a>.

## <a name="step-1-develop-and-test"></a>Etapa 1: desenvolver e testar

### <a name="create-test-users"></a>Criar usuários de teste

Certifique-se de que os desenvolvedores, internos ou externos, tenham contas em seu locatário de teste. <a href="https://docs.microsoft.com/office365/admin/add-users/add-users" target="_blank">Saiba mais sobre como adicionar usuários</a>.

### <a name="allow-custom-apps-in-the-test-tenant"></a>Permitir aplicativos personalizados no locatário de teste

Para dar aos desenvolvedores o acesso necessário para o teste, permita que todos os usuários no locatário de teste carreguem aplicativos personalizados (também conhecidos como Sideload). Isso permite que os desenvolvedores carreguem um aplicativo personalizado para serem usados pessoalmente ou em todo o locatário de teste sem precisar enviar o aplicativo para a loja de aplicativos do teams. Carregar um aplicativo personalizado permite aos desenvolvedores testar um aplicativo antes de distribuí-lo mais amplamente.

Para permitir que os usuários carreguem aplicativos personalizados, siga estas etapas:

1. Ative a configuração **permitir interação com aplicativos personalizados** do aplicativo de toda a organização. Para fazer isso:
    1. Na navegação à esquerda do <a href="https://admin.teams.microsoft.com/" target="_blank">centro de administração do Microsoft Teams</a>, vá até **Team apps** > **gerenciar aplicativos**e clique em **configurações de aplicativo de toda a organização**.
    2. Em **aplicativos personalizados**, ative **permitir interação com aplicativos personalizados**e, em seguida, clique em **salvar**.

    ![Captura de tela da configuração "permitir interação com aplicativos personalizados" do aplicativo em toda a organização](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. Ative a configuração **carregar aplicativos personalizados** na política de configuração do aplicativo global. Para fazer isso:
    1. Na navegação à esquerda do <a href="https://admin.teams.microsoft.com/" target="_blank">centro de administração do Microsoft Teams</a>, vá para**políticas de configuração**de aplicativos > do **Teams**e clique na política **global (padrão para toda a organização)** .
    2. Ative **carregar aplicativos personalizados**e, em seguida, clique em **salvar**.

    ![Captura de tela da configuração de política "carregar aplicativos personalizados" do aplicativo de configuração de aplicativos](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> Também há uma configuração de aplicativo de carregamento personalizado no nível da equipe. Por padrão, essa configuração está ativada. No entanto, se os desenvolvedores não conseguirem carregar um aplicativo personalizado para uma equipe, verifique a configuração seguindo as etapas descritas <a href="https://docs.microsoft.com/microsoftteams/teams-custom-app-policies-and-settings#configure-the-team-custom-app-setting" target="_blank">aqui</a>.

### <a name="create-your-app"></a>Criar seu aplicativo

Os desenvolvedores agora devem ter o que precisam para criar seu aplicativo. Veja <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">aqui</a> as diretrizes sobre isso.

## <a name="step-2-validate-in-production"></a>Etapa 2: validar na produção

### <a name="get-the-app-package"></a>Obter o pacote do aplicativo

Quando o aplicativo está pronto para ser usado na produção, o desenvolvedor deve produzir um pacote de aplicativo. Eles podem usar o <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">app Studio</a> para isso. Eles enviarão o arquivo no formato. zip.

A Microsoft usa <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">essas diretrizes</a> para garantir que os aplicativos estejam em conformidade com os padrões de qualidade e segurança da loja de aplicativos global do teams.

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a>Permitir que usuários confiáveis carreguem aplicativos personalizados no locatário de produção

Para validar que o aplicativo está funcionando corretamente no seu locatário de produção, você precisa permitir que os usuários de si mesmo e/ou confiáveis em sua organização carreguem aplicativos personalizados.  Assim como na <a href="https://docs.microsoft.com/microsoftteams/manage-your-lob-apps#allow-custom-apps-in-the-test-tenant" target="_blank">etapa</a>anterior, você usa políticas de configuração do aplicativo para fazer isso.

> [!NOTE]
> Se você não se sentir à vontade para fazer o upload do aplicativo em seu locatário de produção para validação, mesmo para usuários confiáveis ou para usuários confiáveis, pode ignorar esta etapa e seguir as etapas 3 e 4 para carregar o aplicativo não validado na sua loja de aplicativos locatário. Em seguida, restrinja o acesso a esse aplicativo apenas para você e os usuários confiáveis. Esses usuários podem obter o aplicativo a partir da App Store do locatário para executar a validação. Depois que o aplicativo for validado, use as mesmas políticas de permissão para abrir o Access e faça o lançamento do aplicativo para uso em produção.

Para permitir que usuários confiáveis carreguem aplicativos personalizados, siga estas etapas:

1. Ative a configuração **permitir interação com aplicativos personalizados** do aplicativo de toda a organização. Para fazer isso:
    1. Na navegação à esquerda do <a href="https://admin.teams.microsoft.com/" target="_blank">centro de administração do Microsoft Teams</a>, vá até **Team apps** > **gerenciar aplicativos**e clique em **configurações de aplicativo de toda a organização**.
    2. Em **aplicativos personalizados**, ative **permitir interação com aplicativos personalizados**e, em seguida, clique em **salvar**.
2. Desative a configuração **carregar aplicativos personalizados** na política de configuração do aplicativo global. Para fazer isso:
    1. Na navegação à esquerda do <a href="https://admin.teams.microsoft.com/" target="_blank">centro de administração do Microsoft Teams</a>, vá para**políticas de configuração**de aplicativos > do **Teams**e clique na política **global (padrão para toda a organização)** .
    2. Desative **carregar aplicativos personalizados**e, em seguida, clique em **salvar**.
3. Crie uma nova política de configuração de aplicativo que permita carregar aplicativos personalizados e atribuí-lo ao conjunto de usuários confiáveis. Para fazer isso:
    1. Na navegação à esquerda do <a href="https://admin.teams.microsoft.com/" target="_blank">centro de administração do Microsoft Teams</a>, vá para**políticas de configuração**de aplicativos > do **Teams**e, em seguida, clique em **Adicionar**. Dê um nome e uma descrição para a nova política, ative **carregar aplicativos personalizados**e, em seguida, clique em **salvar**.
    2. Selecione a nova política que você criou e clique em **gerenciar usuários**. Procure um usuário, clique em **Adicionar**e, em seguida, clique em **aplicar**. Repita esta etapa para atribuir a política a todos os usuários confiáveis.

        ![Captura de tela da página "Adicionar política de configuração de aplicativo"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Esses usuários agora podem carregar o manifesto do aplicativo para validar que o aplicativo está funcionando corretamente no locatário de produção.

## <a name="step-3-upload-to-the-tenant-app-catalog"></a>Etapa 3: carregar para o catálogo de aplicativos do locatário

Para disponibilizar o aplicativo para os usuários na App Store do locatário, carregue o aplicativo. Você pode fazer isso na página [gerenciar aplicativos](manage-apps.md) do centro de administração do Microsoft Teams.

![Captura de tela da página Gerenciar aplicativos no centro de administração](media/manage-your-lob-apps-upload-new-app.png)

## <a name="step-4-configure-and-assign-permissions"></a>Etapa 4: configurar e atribuir permissões

### <a name="control-access-to-the-app"></a>Controlar o acesso ao aplicativo

Por padrão, todos os usuários têm acesso a este aplicativo na loja de aplicativos do teams. Para restringir e controlar quem tem permissão para usar o aplicativo, você pode criar e atribuir uma nova política de permissão de aplicativo. Siga as etapas <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies#create-a-custom-app-permission-policy" target="_blank">aqui</a>.

![Captura de tela da página "Adicionar política de permissão de aplicativo"](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a>Fixar o aplicativo para que os usuários descubram

Por padrão, para os usuários encontrarem esse aplicativo, eles precisarão ir para a loja de aplicativos do Teams e procurá-lo ou procurá-lo. Para facilitar para os usuários acessar o aplicativo, você pode fixar o aplicativo à barra de aplicativos no Microsoft Teams. Para fazer isso, crie uma nova política de configuração de aplicativo e atribua-a a usuários. Siga as etapas <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies#create-a-custom-app-setup-policy" target="_blank">aqui</a>.

![Captura de tela do painel "adicionar aplicativos fixos"](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a>Etapa 5: atualizar o aplicativo

![Visão geral do seu aplicativo do desenvolvimento para a implantação](media/manage-your-lob-apps-update.png)

Para atualizar um aplicativo, os desenvolvedores devem continuar a seguir a [etapa 1](#step-1-develop-and-test) e a [etapa 2](#step-2-validate-in-production).

Você pode atualizar o aplicativo por meio do catálogo de aplicativos do locatário. Para fazer isso, no centro de administração do Microsoft Teams, vá até **Team apps** > **gerenciar aplicativos**. Na lista de aplicativos, clique no nome do aplicativo e, em seguida, clique em **Atualizar**. Isso substitui o aplicativo existente no catálogo do aplicativo locatário, e todas as políticas de permissão do aplicativo e políticas de configuração do aplicativo permanecem impostas para o aplicativo atualizado.

### <a name="end-user-update-experience"></a>Experiência de atualização do usuário final

Na maioria dos casos, após concluir uma atualização do aplicativo, a nova versão será exibida automaticamente para os usuários finais. No entanto, há algumas atualizações do <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">manifesto do Microsoft Teams</a> que exigem a aceitação do usuário para serem concluídas:

* um bot foi adicionado ou removido
* a propriedade "botId" de um bot existente foi alterada
* a propriedade "isNotificationOnly" de um bot existente foi alterada
* a propriedade "supportsFiles" do bot foi alterada
* uma extensão de mensagens foi adicionada ou removida
* um novo conector foi adicionado
* uma nova guia estática foi adicionada
* uma nova guia configurável foi adicionada
* as propriedades dentro de "webApplicationInfo" foram alteradas

## <a name="related-apps"></a>Aplicativos relacionados

- [Gerenciar seus aplicativos no centro de administração do Microsoft Teams](manage-apps.md)
