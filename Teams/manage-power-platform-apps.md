---
title: Gerencie os aplicativos do Microsoft Power Platform no centro de administração do Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/27/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como gerenciar o acesso a aplicativos personalizados e compilados usando o Microsoft Power Platform no centro de administração do Teams.
ms.openlocfilehash: 93801bb30d0445d13de25976ab23668fde251466
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377199"
---
# <a name="manage-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Gerenciar os aplicativos do Microsoft Power Platform no centro de administração do Teams

## <a name="manage-custom-apps-created-using-microsoft-power-platform-apps"></a>Gerenciar aplicativos personalizados criados usando aplicativos do Microsoft Power Platform

Este artigo fornece uma visão geral de como gerenciar aplicativos personalizados criados usando os aplicativos [do Microsoft Power Platform](https://powerplatform.microsoft.com/) no centro de administração do Microsoft Teams. Aplicativos personalizados são criados por desenvolvedores em sua organização para usuários internos.

> [!NOTE]
> Este artigo não se aplica ao aplicativo Power Apps ou ao aplicativo Power Virtual Agents instalados a partir da página Aplicativos ou afixados ao Teams através de uma política de configuração de aplicativo. Você pode gerenciar os aplicativos do Store usando [políticas de permissão de aplicativo](teams-app-permission-policies.md) e [políticas de configuração de aplicativo](teams-app-setup-policies.md).

[Power Apps](https://powerapps.microsoft.com) é um ambiente de desenvolvimento de aplicativos de código baixo ou sem código que os criadores de aplicativos em sua organização podem usar para compilar aplicativos personalizados que se conectam aos dados de seus negócios. [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) é um ambiente de compilação de bot sem código para que os desenvolvedores de aplicativos criem bots poderosos. Com a integração dos aplicativos do Microsoft Power Platform no Teams, as organizações podem simplificar os processos de negócios, responder mais rapidamente às necessidades de mudanças nos negócios para impulsionar uma maior colaboração e criar e compartilhar soluções personalizadas para serem mais produtivas.  

Os aplicativos do Microsoft Power Platform criados por desenvolvedores em sua organização são automaticamente adicionados ao Teams. Os desenvolvedores podem controlar quem pode acessar seu aplicativo usando o [recurso de compartilhamento no Power Apps](/powerapps/maker/canvas-apps/share-app) e o [recurso de compartilhamento em Power Virtual Agents](/power-virtual-agents/admin-share-bots).

Quando um aplicativo do Microsoft Power Platform é criado ou compartilhado, os usuários podem exibi-lo e instalá-lo na página Aplicativos, acessando **Compilado com Power Platform**. (Pode levar alguns minutos depois que um aplicativo é criado ou compartilhado para que o aplicativo apareça aqui.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Capturas de tela da página Aplicativos, mostrando os aplicativos do Microsoft Power Platform listados em Compilado com Power Platform.":::

Os usuários finais veem um aplicativo em **Compilado com Power Platform** se o aplicativo atender a uma das seguintes condições.

|Power Apps |Agentes virtuais do Power  |
|---------|---------|
|<ul><li>O usuário criou o aplicativo.</li><li>O aplicativo foi compartilhado diretamente com o usuário.</li><li>O usuário usou o aplicativo recentemente. </li></ul>| <ul><li>O usuário criou o bot.</li><li>O bot pertence a uma equipe da que o usuário é membro. </li></ul>        |

Os usuários instalam aplicativos do Microsoft Power Platform da mesma forma que instalam qualquer outro aplicativo do Teams. Tenha em mente que os usuários só podem instalar aplicativos no contexto para o qual eles têm permissões. Por exemplo, uma equipe que um usuário possui, um chat do qual o usuário faz parte, ou seu escopo pessoal.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Gerenciar o acesso aos aplicativos do Microsoft Power Platform no centro de administração do Teams

Como administrador, você pode controlar se os aplicativos do Microsoft Power Platform estão listados em **Compilado com Power Platform** na página Aplicativos no Teams. Você pode coletivamente bloquear ou permitir todos os aplicativos criados no Power Apps ou todos os aplicativos criados no Power Virtual Agents no nível da organização na página [Gerenciar aplicativos](manage-apps.md) ou para usuários específicos usando [políticas de permissão de aplicativo](teams-app-permission-policies.md).

Os aplicativos **Power Apps Compartilhados** e **Power Virtual Agente Apps Compartilhados** na App Store de sua organização representam todos os aplicativos criados nessa plataforma específica. Se você bloquear um ou ambos os aplicativos para toda a organização ou para usuários específicos, os usuários não poderão instalá-los no Teams. Os usuários não podem solicitar aprovação do administrador para permitir aplicativos.

Tenha em mente que você pode controlar o acesso a todos os aplicativos criados no Power Apps e Power Virtual Agents, mas você não pode permitir ou bloquear aplicativos individuais. O criador do aplicativo decide quem pode acessar os aplicativos que eles criam através do recurso de compartilhamento de dentro do Power Apps e Power Virtual Agents. Se um criador compartilhou um aplicativo que criou no Power Virtual Agents com um usuário e você bloqueou **Aplicativos Compartilhados do Power Virtual Agents** para esse usuário, o usuário não será capaz de ver ou instalar qualquer aplicativo dessa plataforma no Teams.

Se um usuário tiver permissão para acessar aplicativos do Power Apps ou Power Virtual Agents, e você bloquear o usuário de acessar aplicativos de uma ou ambas as plataformas, o usuário ainda poderá acessar e usar aplicativos do Microsoft Power Platforms que eles instalaram antes de você bloquear o aplicativo ou aplicativos. No entanto, o usuário não pode mais instalar qualquer aplicativo dessas plataformas no **Compilado com Power Platform**.

> [!NOTE]
> A configuração **Permitir interação com aplicativos personalizados** de toda a organização na página [Gerenciar aplicativos](manage-apps.md) se aplica a todos em sua organização e determina se eles podem interagir com aplicativos personalizados. As configurações de aplicativo em toda a organização controlam o comportamento de todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários. Se esta configuração for desativada, os usuários de sua organização não poderão instalar nenhum aplicativo personalizado, incluindo aplicativos do Microsoft Power Platform. Para saber mais, confira [Gerenciar configurações de aplicativo em toda a organização](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Permitir ou bloquear aplicativos do Microsoft Power Platform para sua organização

Por padrão, são permitidos **Power Apps Compartilhado** e **Power Virtual Agent Apps Compartilhados** para todos os usuários do Teams de sua organização. Você pode bloqueá-los ou permiti-los no nível da organização na página [Gerenciar aplicativos](manage-apps.md) no centro de administração do Microsoft Teams.  

1. Entre no centro de administração do Teams e acesse os aplicativos do **Teams** >  Gerenciar aplicativos. Você deve ser um administrador global ou administrador de serviços do Teams para acessar a página.**[](https://admin.teams.microsoft.com/policies/manage-apps)**
1. Na lista de aplicativos, faça uma das seguintes opções.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Captura de tela da página Gerenciar aplicativos, mostrando aplicativos compartilhados do Microsoft Power Platform.":::

    * Para bloquear aplicativos criados no Power Apps ou Power Virtual Agents para todos os usuários de sua organização, pesquise por **Power Apps Compartilhados** ou **Power Virtual Agent Apps Compartilhados**, selecione-o(s), e então selecione **Bloquear**.
    * Para permitir aplicativos criados no Power Apps ou Power Virtual Agents para todos os usuários de sua organização, pesquise por **Power Apps Compartilhados** ou **Power Virtual Agent Apps Compartilhados**, selecione-o(s), e então selecione **Permitir**.

### <a name="allow-microsoft-power-platform-apps-for-specific-users"></a>Permitir aplicativos do Microsoft Power Platform para usuários específicos

Para permitir ou bloquear o acesso de usuários específicos em sua organização a aplicativos criados no Power Apps ou Power Virtual Agents, crie e atribua uma ou mais [políticas de permissão de aplicativo](teams-app-permission-policies.md) personalizado.

Por exemplo, para bloquear usuários específicos de acessar aplicativos criados no Power Apps, criar uma política personalizada de permissão de aplicativo para bloquear **Power Apps Compartilhados**, e então atribuir a política a esses usuários.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Captura de tela de exemplo de política de permissão de aplicativo personalizado com o Power Apps Compartilhados bloqueado.":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Use logs de auditoria para investigar a atividade de instalação do Microsoft Power Platform

Você pode usar logs de auditoria do Teams para investigar eventos onde os usuários instalaram aplicativos do Microsoft Power Platform na seção **Compilado com Power Platform** da página Aplicativos no Teams. Para fazer isso, [pesquise em log de auditoria](./audit-log-events.md) pelo evento do Teams **Aplicativo instalado** (sob a operação **AppInstalled**) por um usuário ou conjunto de usuários. Para encontrar aplicativos instalados a partir do **Compilado com Power Platform**, procure o valor **TemplatedInstance** na propriedade **AppDistributionMode** nos detalhes de um determinado registro.

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Captura de tela do valor TemplatedInstance na propriedade AppDistributionMode." lightbox="media/manage-power-platform-apps-audit.png":::

> [!NOTE]
> Você pode exportar registros de auditoria em formato CSV para facilitar a filtragem.

## <a name="related-articles"></a>Artigos relacionados

* [Compartilhar um aplicativo de tela no Power Apps](/powerapps/maker/canvas-apps/share-app)
* [Compartilhar seu bot com outros usuários](/power-virtual-agents/admin-share-bots)
* [Gerenciar aplicativos no centro de administração do Microsoft Teams](manage-apps.md)
* [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
* [Publicar um aplicativo personalizado enviado por meio da API de envio de aplicativos do Teams](submit-approve-custom-apps.md)
