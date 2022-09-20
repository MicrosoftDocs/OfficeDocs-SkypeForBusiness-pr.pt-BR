---
title: Gerenciar aplicativos personalizados e com sideload
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Entenda o que são aplicativos personalizados e aplicativos de sideload no Microsoft Teams e gerencie os aplicativos para controlar seu comportamento, distribuição e permissões.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 4ba559d605f1465fda7caf9b253c18864c8b4c20
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837371"
---
# <a name="understand-and-manage-custom-and-sideloaded-apps"></a>Entender e gerenciar aplicativos personalizados e com sideload

O Microsoft Teams permite que os desenvolvedores em sua organização criem, testem e implantem aplicativos personalizados para os usuários internos da organização. Esses aplicativos são chamados de aplicativos personalizados ou aplicativos de linha de negócios. A sua organização pode encomendar a criação de aplicativos personalizados para requisitos específicos da organização.

Você, como administrador, tem o controle para permitir ou bloquear esses aplicativos para toda a organização ou para usuários específicos. Os desenvolvedores podem criar soluções personalizadas de baixo código usando a integração do Teams com o [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions).

Os desenvolvedores podem enviar seus aplicativos personalizados por meio do Teams para aprovação do administrador. Você pode usar políticas de configuração de aplicativo para controlar a distribuição, a distribuição e as permissões de aplicativos personalizados.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Captura de tela que mostra como permitir aplicativos personalizados em sua organização no painel de configurações de toda a organização." lightbox="media/custom-app-policy.png":::

Depois de permitir o uso de um aplicativo personalizado, os usuários finais poderão encontrá-lo selecionando  Compilar para sua organização na navegação à esquerda da loja do Teams.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Captura de tela de aplicativos personalizados na loja do Teams no aplicativo de desktop do Teams." lightbox="media/built-for-your-org2.png":::

## <a name="understand-sideloading-of-custom-apps"></a>Entender o sideload de aplicativos personalizados

Ao desenvolver aplicativos personalizados e antes de distribuir esses aplicativos para os usuários finais, os desenvolvedores testam os aplicativos adicionando-os à Loja do Teams para testar. Os desenvolvedores podem testar por conta própria ou com um grupo especificado de usuários, mas o aplicativo não está disponível para outros usuários finais na organização por meio da loja. Esse método é chamado de sideload de aplicativos e se aplica somente a aplicativos personalizados.

Os desenvolvedores podem fazer sideload de um aplicativo para disponibilizá-lo aos membros de uma equipe específica, normalmente para testar um aplicativo em desenvolvimento. Usar um aplicativo dessa maneira limita seu uso aos desenvolvedores de aplicativos e não requer aprovação do administrador, desde que o administrador permita o sideload no Teams.

Os desenvolvedores podem compartilhar um aplicativo de sideload com uma equipe específica sem enviá-lo ao catálogo de aplicativos do Teams. Ele disponibiliza o aplicativo personalizado de sideload para um grupo limitado de usuários finais, mas não está disponível na loja de aplicativos da sua organização para todos os usuários finais.

Como administrador, você pode proibir o sideload do aplicativo para todos os desenvolvedores. Se você não permitir o sideload, os desenvolvedores ainda poderão testar seus aplicativos [criando um locatário de teste separado](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Após a conclusão do desenvolvimento de aplicativos personalizados, os desenvolvedores solicitam que os administradores distribuam seus aplicativos personalizados para os usuários finais. Para obter detalhes, confira [como publicar um aplicativo personalizado](/microsoftteams/upload-custom-apps). Como administrador, você pode permitir ou não o uso de um aplicativo personalizado para usuários específicos.

## <a name="allow-developers-to-upload-custom-apps"></a>Permitir que os desenvolvedores carreguem aplicativos personalizados

Você pode criar uma política personalizada ou editar a política global para permitir ou bloquear aplicativos personalizados com base nas necessidades de sua organização. Para criar uma política personalizada que permita que os desenvolvedores da organização carreguem aplicativos personalizados, siga estas etapas:

1. Entre no Centro de administração do Teams e acesse **Aplicativos do Teams** > **[Políticas de configuração](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Selecione **Adicionar**.

1. Forneça um nome e uma descrição para a política.

1. Ativar ou desativar o **carregamento de aplicativos personalizados**.

> [!NOTE]
> Para alterar essa configuração, permita aplicativos de terceiros nas configurações de [aplicativo em toda a organização do locatário](manage-apps.md#manage-org-wide-app-settings).

## <a name="related-articles"></a>Artigos relacionados

* [Gerenciar configurações e políticas de aplicativo personalizadas](teams-custom-app-policies-and-settings.md)
* [Entender as políticas para controlar aplicativos](app-policies.md)
* [Entender aplicativos de terceiros](overview-third-party-apps.md)
