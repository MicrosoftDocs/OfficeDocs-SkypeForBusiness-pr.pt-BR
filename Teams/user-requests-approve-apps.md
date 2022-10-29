---
title: Solicitações de usuário para administradores
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 09/20/2022
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Saiba como gerenciar e configurar a solicitação do usuário final para aprovação dos aplicativos bloqueados em uma organização.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 00c8659d82b4c633790f1b663d11d27e015146f1
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784386"
---
# <a name="manage-user-requests"></a>Gerenciar solicitações de usuário

Os aplicativos bloqueados em sua organização podem afetar a produtividade e a colaboração do usuário final. Os usuários finais não podem usar aplicativos bloqueados, mas exibir esses aplicativos e suas informações na loja do Teams e solicitar aprovação dos administradores. Depois de avaliar a solicitação, você pode optar por permitir um aplicativo ou rejeitar a solicitação.

Essa funcionalidade fornece um sinal sobre a demanda por um aplicativo em sua organização. Você pode exibir facilmente o número agregado de solicitações para cada aplicativo solicitado. Ele ajuda você a tomar uma decisão informada sobre quais aplicativos avaliar para permitir.

Você mantém o controle completo dos aplicativos permitidos ou bloqueados para usuários. Se você optar por permitir um aplicativo, os controles e a interface do usuário para gerenciar aplicativos permanecerão os mesmos.

* A opção padrão envia as solicitações de usuário para o centro de administração do Teams, onde você pode [exibir solicitações de usuário e permitir os aplicativos solicitados](#view-and-act-on-user-requests-in-teams-admin-center).

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="Captura de tela mostrando a opção de solicitar um administrador para aprovar um aplicativo bloqueado.":::

* Uma personalização permite configurar a [experiência do usuário final](#modify-the-default-setting-to-receive-end-user-requests) que é mais adequada para sua organização. Você pode fornecer uma instrução ou uma mensagem personalizada exibida no repositório de aplicativos do Teams e a opção de aprovação de solicitação direciona os usuários para uma URL específica da organização para coletar suas solicitações.

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="Captura de tela mostrando a experiência do usuário final para aplicativos na loja quando um administrador redireciona a URL de solicitação de aplicativo para uma URL específica da organização.":::

## <a name="view-and-act-on-user-requests-in-teams-admin-center"></a>Exibir e agir em solicitações de usuário no centro de administração do Teams

As solicitações de usuário final recebidas pelo método padrão são exibidas no centro de administração do Teams. Você pode exibir e gerenciar facilmente as solicitações. Recomendamos uma triagem regular para verificar se há solicitações de usuário final. Para exibir e permitir os aplicativos, siga as etapas:

1. Entre no centro de administração do Teams e vá para **aplicativos** >  do Teams [**Gerenciar aplicativos**](https://admin.teams.microsoft.com/policies/manage-apps).

1. Escolha exibir a coluna **Solicitações por usuários** . Você também pode classificar a coluna.

   :::image type="content" source="media/user-requests-tac.png" alt-text="Captura de tela mostrando a coluna para solicitações de usuário no centro de administração do Teams e que ela pode ser classificada." lightbox="media/user-requests-tac-expanded.png":::

1. Para abrir a página de detalhes do aplicativo que você deseja permitir, selecione o nome do aplicativo.

1. Selecione **Gerenciar solicitações**.

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="Captura de tela mostrando a opção gerenciar solicitações na página de detalhes do aplicativo." lightbox="media/apps-manage-user-requests-expanded.png":::

1. Siga uma ou mais etapas a seguir, conforme exibido na caixa de diálogo pop-up. As etapas para aprovar um aplicativo variam com base no método usado para bloqueá-lo.

   * Se o aplicativo for bloqueado usando políticas de permissão, [modifique as políticas de permissão](teams-app-permission-policies.md).
   * Se o aplicativo estiver bloqueado para todos os usuários, [permita o aplicativo](manage-apps.md#allow-and-block-apps).
   * Se todos os aplicativos forem bloqueados para todos os [usuários, modifique as configurações em toda a organização](manage-apps.md#manage-org-wide-app-settings).

Os usuários finais podem exibir a opção **Adicionar** para um aplicativo na loja do Teams para verificar se o aplicativo é permitido. Quando você permite um aplicativo após receber solicitações no centro de administração do Teams, o Teams não informa aos usuários finais que sua solicitação é atendida. Quando você permite um aplicativo, o contador de solicitações não é redefinido para zero.

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>Modificar a configuração padrão para receber solicitações do usuário final

O Teams fornece uma mensagem padrão para que os usuários solicitem aprovação a um aplicativo. Você pode modificar a configuração padrão para adicionar uma mensagem personalizada com instruções, URL específica da organização ou ambos. As modificações são exibidas para cada aplicativo na loja do Teams.

Para configurar uma mensagem personalizada e redirecionar os usuários para uma URL específica da organização, siga as etapas:

1. Entre no centro de administração do Teams e vá para **aplicativos** >  do Teams [**Gerenciar aplicativos**](https://admin.teams.microsoft.com/policies/manage-apps).

1. No canto superior direito, selecione **Configurações de aplicativo em toda a organização**.

1. Para exibir uma mensagem ou instrução personalizada no armazenamento do Teams, insira uma mensagem de texto no campo de texto em **Configuração de solicitações de usuário**. O campo tem um limite de 300 caracteres.

1. Para fornecer uma URL específica da organização para coletar solicitações de usuário, siga as etapas:

   1. Ative as **solicitações de redirecionamento para alternância de link externo** .
   1. Forneça sua URL específica da organização.

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="Captura de tela para alternar a personalização da URL para as solicitações de usuário na interface do usuário de configurações em toda a organização.":::

1. Selecione **Salvar**.

Se você optar por fazer isso, os métodos para avaliar aplicativos de terceiros e permitir que os aplicativos solicitados permaneçam os mesmos.

## <a name="dismiss-user-requests"></a>Descartar solicitações de usuário

Para descartar as solicitações, siga as etapas:

1. Selecione o nome do aplicativo para o qual você deseja ignorar as solicitações do usuário.
1. Selecione **Gerenciar solicitações**.
1. Na caixa de diálogo Gerenciar solicitações de usuário, selecione **Descartar todas as solicitações**.

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="Os administradores podem aprovar uma solicitação do usuário permitindo um aplicativo ou ignorando a solicitação e não realizando nenhuma ação.":::

Se você rejeitar uma solicitação, ela não informará ao usuário final que sua solicitação é atendida. Quando você rejeita uma solicitação para permitir um aplicativo, a contagem de solicitações no centro de administração é redefinida para zero. Além disso, depois de algumas horas rejeitando uma solicitação, os usuários finais podem solicitar novamente que o mesmo aplicativo seja permitido.

## <a name="related-article"></a>Artigo relacionado

* [Visão geral de como gerenciar aplicativos de terceiros](manage-apps.md).
