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
localization_priority: Normal
search.appverid: MET150
description: Saiba como levar seus aplicativos personalizados do teams do desenvolvimento para a implantação.
ms.openlocfilehash: cd64ff0a3307ada0f1fbfaf29b94cfcd1da3c0df
ms.sourcegitcommit: d6a0ff7f00defda2b58726f5f0f0fac871f46ab7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2019
ms.locfileid: "37682671"
---
# <a name="manage-your-line-of-business-apps-in-microsoft-teams"></a>Gerenciar seus aplicativos de linha de negócios no Microsoft Teams

Este artigo fornece uma orientação de ponta a ponta para como levar o aplicativo Teams do desenvolvimento para a implantação. Esta orientação se concentra nos aspectos da equipe do aplicativo e destina-se aos profissionais de ti. Para obter mais informações sobre o desenvolvimento de aplicativos do Teams, consulte [aqui](https://docs.microsoft.com/microsoftteams/platform).

![Visão geral do seu aplicativo do desenvolvimento para a implantação](media/manage-your-lob-apps.png)

## <a name="getting-started"></a>Introdução

Para criar e gerenciar aplicativos de linha de negócios (LOB) no Teams, você precisará de dois locatários: um locatário de teste para desenvolvimento e um locatário de produção.

> [!NOTE]
> Se ainda não tiver um locatário de teste, você pode criar rapidamente um e preenchê-lo com dados de teste usando o programa para desenvolvedores do Office 365. [Saiba mais aqui](https://developer.microsoft.com/office/dev-program).

## <a name="step-1-develop-and-test"></a>Etapa 1: desenvolver e testar

### <a name="create-test-users"></a>Criar usuários de teste

Certifique-se de que os desenvolvedores, internos ou externos, tenham contas em seu locatário de teste. [Saiba mais sobre como adicionar usuários](https://docs.microsoft.com/office365/admin/add-users/add-users).

### <a name="allow-custom-apps-in-the-test-tenant"></a>Permitir aplicativos personalizados no locatário de teste

Para dar aos desenvolvedores o acesso necessário para o teste, permita que todos os usuários no locatário de teste carreguem aplicativos personalizados (também conhecidos como Sideload). Isso permite que os desenvolvedores carreguem um aplicativo personalizado para serem usados pessoalmente ou em todo o locatário de teste sem precisar enviar o aplicativo para a loja de aplicativos do teams. Carregar um aplicativo personalizado permite aos desenvolvedores testar um aplicativo antes de distribuí-lo mais amplamente.

Para permitir que os usuários carreguem aplicativos personalizados, siga estas etapas:

1. Ative a configuração **permitir interação com aplicativos personalizados** de toda a organização. Para fazer isso:
    1. Na navegação à esquerda do [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/), vá para**políticas de permissão**de **aplicativos** > do Teams e clique em **configurações de toda a organização**.
    2. Em **aplicativos personalizados**, ative **permitir interação com aplicativos personalizados**e, em seguida, clique em **salvar**.

    ![Captura de tela da configuração de "permitir interação com aplicativos personalizados" para toda a organização](media/manage-your-lob-apps-org-wide-custom-apps.png)

2. Ative a configuração **carregar aplicativos personalizados** na política de configuração do aplicativo global. Para fazer isso:
    1. Na navegação à esquerda do [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/), vá para**políticas de configuração**de aplicativos > do **Teams**e clique na política **global (padrão para toda a organização)** .
    2. Ative **carregar aplicativos personalizados**e, em seguida, clique em **salvar**.

    ![Captura de tela da configuração de política "carregar aplicativos personalizados" do aplicativo de configuração de aplicativos](media/manage-your-lob-apps-app-setup-custom-apps.png)

> [!NOTE]
> Também há uma configuração de aplicativo de carregamento personalizado no nível da equipe. Por padrão, essa configuração está ativada. No entanto, se os desenvolvedores não conseguirem carregar um aplicativo personalizado para uma equipe, verifique a configuração seguindo as etapas descritas [aqui](teams-custom-app-policies-and-settings.md#configure-the-team-custom-app-setting).

### <a name="create-your-app"></a>Criar seu aplicativo

Os desenvolvedores agora devem ter o que precisam para criar seu aplicativo. Veja [aqui](https://docs.microsoft.commicrosoftteams/platform) as diretrizes sobre isso.

## <a name="step-2-validate-in-production"></a>Etapa 2: validar na produção

### <a name="get-the-app-package"></a>Obter o pacote do aplicativo

Quando o aplicativo está pronto para ser usado na produção, o desenvolvedor deve produzir um pacote de aplicativo. Eles podem usar o [app Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio) para isso. Eles enviarão o arquivo no formato. zip.

A Microsoft usa [essas diretrizes](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval) para garantir que os aplicativos estejam em conformidade com os padrões de qualidade e segurança da loja de aplicativos global do teams.

### <a name="allow-trusted-users-to-upload-custom-apps-in-the-production-tenant"></a>Permitir que usuários confiáveis carreguem aplicativos personalizados no locatário de produção

Para validar que o aplicativo está funcionando corretamente no seu locatário de produção, você precisa permitir que os usuários de si mesmo e/ou confiáveis em sua organização carreguem aplicativos personalizados.  Assim como na etapa anterior [permitir aplicativos personalizados na etapa testar locatário](#allow-custom-apps-in-the-test-tenant) , você usa políticas de configuração do aplicativo para fazer isso.

> [!NOTE]
> Se você não se sentir à vontade para fazer o upload do aplicativo em seu locatário de produção para validação, mesmo para usuários confiáveis ou para usuários confiáveis, pode ignorar esta etapa e seguir as etapas 3 e 4 para carregar o aplicativo não validado para a loja de aplicativos do locatário. Em seguida, restrinja o acesso a esse aplicativo apenas para você e os usuários confiáveis. Esses usuários podem, então, obter o aplicativo a partir da loja de aplicativos do locatário para executar a validação. Depois que o aplicativo for validado, use as mesmas políticas de permissão para abrir o Access e faça o lançamento do aplicativo para uso em produção.

Para permitir que usuários confiáveis carreguem aplicativos personalizados, siga estas etapas:

1. Ative a configuração **permitir interação com aplicativos personalizados** de toda a organização. Para fazer isso:
    1. Na navegação à esquerda do [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/), vá para**políticas de permissão**de **aplicativos** > do Teams e clique em **configurações de toda a organização**.
    2. Em **aplicativos personalizados**, ative **permitir interação com aplicativos personalizados**e, em seguida, clique em **salvar**.
2. Desative a configuração **carregar aplicativos personalizados** na política de configuração do aplicativo global. Para fazer isso:
    1. Na navegação à esquerda do [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/), vá para**políticas de configuração**de aplicativos > do **Teams**e clique na política **global (padrão para toda a organização)** .
    2. Desative **carregar aplicativos personalizados**e, em seguida, clique em **salvar**.
3. Crie uma nova política de configuração de aplicativo que permita carregar aplicativos personalizados e atribuí-lo ao conjunto de usuários confiáveis. Para fazer isso:
    1. Na navegação à esquerda do [centro de administração do Microsoft Teams](https://admin.teams.microsoft.com/), vá para**políticas de configuração**de aplicativos > do **Teams**e, em seguida, clique em **Adicionar**. Dê um nome e uma descrição para a nova política, ative **carregar aplicativos personalizados**e, em seguida, clique em **salvar**.
    2. Selecione a nova política que você criou e clique em **gerenciar usuários**. Procure um usuário, clique em **Adicionar**e, em seguida, clique em **aplicar**. Repita esta etapa para atribuir a política a todos os usuários confiáveis.

        ![Captura de tela da página "Adicionar política de configuração de aplicativo"](media/manage-your-lob-apps-new-app-setup-policy.png)

    Esses usuários agora podem carregar o manifesto do aplicativo para validar que o aplicativo está funcionando corretamente no locatário de produção.

## <a name="step-3-upload-to-the-tenant-apps-catalog"></a>Etapa 3: carregar para o catálogo de aplicativos do locatário

Para disponibilizar o aplicativo para os usuários no repositório de aplicativos do locatário, carregue o aplicativo. Você pode fazer isso usando o cliente da área de trabalho do teams. Siga as etapas [aqui](tenant-apps-catalog-teams.md#go-to-the-tenant-apps-catalog).

![Captura de tela da página aplicativos](media/manage-your-lob-apps-store.png)

## <a name="step-4-configure-and-assign-permissions"></a>Etapa 4: configurar e atribuir permissões

### <a name="control-access-to-the-app"></a>Controlar o acesso ao aplicativo

Por padrão, todos os usuários têm acesso a este aplicativo na loja de aplicativos do teams. Para restringir e controlar quem tem permissão para usar o aplicativo, você pode criar e atribuir uma nova política de permissão de aplicativo. Siga as etapas [aqui](teams-app-permission-policies.md#create-a-custom-app-permission-policy).

![Captura de tela da página "Adicionar política de permissão de aplicativo"](media/manage-your-lob-apps-new-app-permission-policy.png)

### <a name="pin-the-app-for-users-to-discover"></a>Fixar o aplicativo para que os usuários descubram

Por padrão, para os usuários encontrarem esse aplicativo, eles precisarão ir para a loja de aplicativos do Teams e procurá-lo ou procurá-lo. Para facilitar para os usuários acessar o aplicativo, você pode fixar o aplicativo à barra de aplicativos no Microsoft Teams. Para fazer isso, crie uma nova política de configuração de aplicativo e atribua-a a usuários. Siga as etapas [aqui](teams-app-setup-policies.md#create-a-custom-app-setup-policy).

![Captura de tela do painel "adicionar aplicativos fixos"](media/manage-your-lob-apps-pinned-apps.png)

## <a name="step-5-update-the-app"></a>Etapa 5: atualizar o aplicativo

![Visão geral do seu aplicativo do desenvolvimento para a implantação](media/manage-your-lob-apps-update.png)

Para atualizar um aplicativo, os desenvolvedores devem continuar a seguir a [etapa 1](#step-1-develop-and-test) e a [etapa 2](#step-2-validate-in-production).

Você pode atualizar o aplicativo por meio do catálogo de aplicativos do locatário. Para fazer isso, no cliente da área de trabalho do Teams, vá para **aplicativos** > ** &lt;criados&gt;para o nome do locatário**, clique em **...** no canto superior direito do aplicativo e, em seguida, clique em **Atualizar**. Isso substitui o aplicativo existente no catálogo de aplicativos do locatário, e todas as políticas de permissão e políticas de configuração permanecem impostas para o aplicativo atualizado. 

![Captura de tela da atualização de um aplicativo na página aplicativos](media/manage-your-lob-apps-update-app.png)