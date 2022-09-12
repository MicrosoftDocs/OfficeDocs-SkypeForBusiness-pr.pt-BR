---
title: Solicitações do usuário para que os administradores permitam aplicativos
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.collection:
- M365-collaboration
- m365-frontline
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Saiba como gerenciar e configurar a solicitação do usuário final para permitir os aplicativos bloqueados em uma organização.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 122d41de6f1cb5ea67a5ce85ba9f8f7d02e26339
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647535"
---
# <a name="manage-user-requests"></a>Gerenciar solicitações de usuário

Os aplicativos bloqueados em sua organização podem afetar a produtividade e a colaboração do usuário final. Os aplicativos que estão disponíveis na loja do Teams, mas estão bloqueados em sua organização, não podem ser usados pelos usuários finais. No entanto, para se manter informado, os usuários finais podem exibir aplicativos bloqueados, exibir as informações do aplicativo e os casos de uso que ele servidores. Os usuários solicitam aprovação do administrador para que eles usem esses aplicativos no Teams, depois que você avaliar a solicitação.

Essa funcionalidade fornece um sinal sobre a demanda por um aplicativo em sua organização. Você pode exibir facilmente o número agregado de solicitações para aplicativos. Ele ajuda você a tomar uma decisão informada sobre quais aplicativos devem ser avaliados para permitir em sua organização.

Você mantém o controle total dos aplicativos que são permitidos ou bloqueados para os usuários. Se você optar por permitir um aplicativo, os controles e a interface do usuário para gerenciar aplicativos permanecerão os mesmos.

* A opção padrão envia as solicitações de usuário no Centro de administração do Teams, onde você pode exibir solicitações de [usuário e permitir os aplicativos solicitados](#view-user-requests).

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="Captura de tela mostrando a opção de solicitar que um administrador aprove um aplicativo bloqueado.":::

* Uma personalização permite configurar [a experiência do usuário final](#modify-the-default-setting-to-receive-end-user-requests) mais adequada para sua organização. Você pode fornecer uma instrução personalizada que é exibida aos usuários finais em aplicativos bloqueados na loja de aplicativos do Teams e direcionar os usuários para um site interno para coletar suas solicitações.

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="Captura de tela mostrando a experiência do usuário final para aplicativos na loja quando um administrador redireciona a URL de solicitação de aplicativo permitido para um site interno.":::

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>Modificar a configuração padrão para receber solicitações do usuário final

Para configurar uma mensagem personalizada e redirecionar os usuários para uma URL específica da organização para solicitar aprovação do aplicativo, siga estas etapas:

1. Entre no centro de administração do Teams e acesse a página Gerenciar aplicativos **dos aplicativos** > **[do](https://admin.teams.microsoft.com/policies/manage-apps)** Teams.

1. Selecione configurações de aplicativo em toda a organização.

1. Para exibir uma mensagem ou instrução personalizada no repositório de clientes do Teams, forneça uma mensagem de texto na configuração de solicitações do usuário.

1. Para fornecer uma URL específica da organização para coletar solicitações de usuário, faça o seguinte:

   1. Altere as solicitações de redirecionamento para a opção de ferramenta externa para Ativado.
   1. Forneça sua URL personalizada específica da organização.

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="Captura de tela para alternar a personalização da URL para a solicitação do usuário para desbloquear o aplicativo na interface do usuário de configurações de toda a organização.":::

1. Selecione **Salvar**.

## <a name="view-user-requests"></a>Exibir solicitações de usuário

As solicitações do usuário final recebidas pelo método padrão são exibidas no Centro de administração do Teams. Você pode facilmente exibir e gerenciar as solicitações. É recomendável ter uma triagem regular para verificar se há solicitações do usuário final. Para exibir e permitir os aplicativos, siga estas etapas:

1. Entre no centro de administração do Teams e acesse a página Gerenciar aplicativos **dos aplicativos** > **[do](https://admin.teams.microsoft.com/policies/manage-apps)** Teams.

1. Escolha exibir a coluna **Solicitações por** usuários. Você também pode classificar a coluna.

   :::image type="content" source="media/user-requests-tac.png" alt-text="Captura de tela mostrando a coluna para solicitações de usuário no Centro de administração do Teams e que ela pode ser classificada." lightbox="media/user-requests-tac-expanded.png":::

1. Para abrir a página de detalhes do aplicativo que você deseja permitir, selecione o nome do aplicativo.

1. Selecione **Gerenciar solicitações**.

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="Captura de tela mostrando a opção gerenciar solicitações na página de detalhes do aplicativo." lightbox="media/apps-manage-user-requests-expanded.png":::

1. Siga uma ou mais das etapas a seguir, conforme exibido na caixa de diálogo pop-up. As etapas para aprovar um aplicativo variam com base no método usado para bloqueá-lo.

   * Se o aplicativo for bloqueado usando políticas de permissão, [modifique as políticas de permissão](teams-app-permission-policies.md).
   * Se o aplicativo estiver bloqueado para todos os usuários, [permita o aplicativo](manage-apps.md#allow-and-block-apps).
   * Se todos os aplicativos forem bloqueados para todos os usuários, [modifique as configurações de toda a organização](manage-apps.md#manage-org-wide-app-settings).

1. Opcionalmente, para alternar para uma configuração personalizada para a URL específica da organização, selecione Configurar link de solicitações de usuário na caixa de diálogo Gerenciar solicitações de usuário. Ele abre o painel de configurações de aplicativo em toda a organização no qual você pode [configurar a experiência de solicitação do usuário final](#modify-the-default-setting-to-receive-end-user-requests).

Se você permitir um aplicativo depois de receber solicitações no Centro de administração do Teams, o Teams não informará ao usuário final que a solicitação foi acionda. O usuário pode verificar o aplicativo na Loja do Teams para verificar se o aplicativo é permitido. A opção para Adicionar o aplicativo estará disponível para o usuário depois que você permitir. Se você permitir um aplicativo depois de receber solicitações por meio de seu método específico da organização, seus mecanismos internos para fornecer atualização de status ao usuário final serão aplicados.

Para redefinir o número de solicitações de aplicativo como zero, ignore as solicitações. Apenas permitir que um aplicativo não redefina seu contador de solicitações para zero.

## <a name="dismiss-user-requests"></a>Ignorar solicitações de usuário

Para ignorar as solicitações para permitir o aplicativo, siga estas etapas:

1. Selecione o nome do aplicativo para o qual você deseja ignorar as solicitações do usuário.
1. Selecione **Gerenciar solicitações** e selecione **Ignorar todas as solicitações** na caixa de diálogo.

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="Os administradores podem aprovar uma solicitação do usuário permitindo um aplicativo ou ignorando a solicitação e não realizando nenhuma ação.":::

Se você ignorar uma solicitação, ela não informará ao usuário final que a solicitação foi acionda. Quando você ignora uma solicitação para permitir um aplicativo, a contagem de solicitações no centro de administração é redefinida como zero. Além disso, após algumas horas de você ignorar uma solicitação, os usuários finais poderão solicitar novamente que o mesmo aplicativo seja permitido.

## <a name="related-article"></a>Artigo relacionado

* [Visão geral de como gerenciar aplicativos de terceiros](manage-apps.md).
