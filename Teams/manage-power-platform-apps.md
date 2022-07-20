---
title: Gerenciar aplicativos do Microsoft Power Platform no centro de administração do Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como gerenciar o acesso a aplicativos personalizados criados usando o Microsoft Power Platform no centro de administração do Teams.
ms.openlocfilehash: 85aa9904b22dd03e1056b353bf91904909c11f59
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880255"
---
# <a name="manage-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Gerenciar aplicativos do Microsoft Power Platform no centro de administração do Teams

## <a name="microsoft-power-platform-apps-in-teams"></a>Aplicativos do Microsoft Power Platform no Teams

Este artigo fornece uma visão geral de como gerenciar aplicativos [do Microsoft Power Platform](https://powerplatform.microsoft.com/) no centro de administração do Microsoft Teams.

> [!NOTE]
> Este artigo se aplica a aplicativos personalizados criados por desenvolvedores em sua organização usando o Power Apps ou o Power Virtual Agents. Este artigo não se aplica ao aplicativo Power Apps ou ao aplicativo Power Virtual Agents instalado na página Aplicativos ou fixado no Teams por meio de uma política de configuração de aplicativo. Você pode gerenciar os aplicativos da Loja usando políticas [de permissão de aplicativo](teams-app-permission-policies.md) e [políticas de configuração de aplicativo](teams-app-setup-policies.md).

[O Power Apps](https://powerapps.microsoft.com) é um ambiente de desenvolvimento de aplicativos de baixo código ou sem código que os criadores de aplicativos em sua organização podem usar para criar aplicativos personalizados que se conectam aos seus dados corporativos. [O Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) é um ambiente de criação de bot sem código para que os criadores de aplicativos criem bots avançados. Com a integração de aplicativos do Microsoft Power Platform ao Teams, as organizações podem simplificar os processos de negócios, responder às necessidades de negócios em constante mudança mais rapidamente para impulsionar maior colaboração e criar e compartilhar soluções personalizadas para serem mais produtivas.  

Os aplicativos do Microsoft Power Platform criados por desenvolvedores em sua organização são adicionados automaticamente ao Teams. Os desenvolvedores podem controlar quem pode acessar seu aplicativo usando o recurso de compartilhamento no [Power Apps](/powerapps/maker/canvas-apps/share-app) e o recurso [de compartilhamento no Power Virtual Agents](/power-virtual-agents/admin-share-bots).

Quando um aplicativo do Microsoft Power Platform é criado ou compartilhado, os usuários podem exibi-lo e instalá-lo na página Aplicativos acessando **Built with Power Platform**. (Pode levar alguns minutos depois que um aplicativo é criado ou compartilhado para que o aplicativo apareça aqui.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Capturas de tela da página Aplicativos, mostrando os aplicativos do Microsoft Power Platform listados em Compilado com o Power Platform.":::

Os usuários finais verão um aplicativo no **Built with Power Platform** se o aplicativo atender a uma das condições a seguir.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>O usuário criou o aplicativo.</li><li>O aplicativo foi compartilhado diretamente com o usuário.</li><li>O usuário usou recentemente o aplicativo. </li></ul>| <ul><li>O usuário criou o bot.</li><li>O bot pertence a uma equipe da que o usuário é membro. </li></ul>        |

Os usuários instalam aplicativos do Microsoft Power Platform da mesma maneira que instalam qualquer outro aplicativo do Teams. Tenha em mente que os usuários só podem instalar aplicativos no contexto ao qual têm permissões. Por exemplo, uma equipe que um usuário possui, um chat do qual o usuário faz parte ou seu escopo pessoal.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Gerenciar o acesso aos aplicativos do Microsoft Power Platform no centro de administração do Teams

Como administrador, você pode controlar se os aplicativos do Microsoft Power Platform estão listados em **Compilado com o Power Platform** na página Aplicativos no Teams. Você pode bloquear ou permitir coletivamente todos os aplicativos criados no Power Apps ou todos os aplicativos criados no Power Virtual Agents no nível [](manage-apps.md) da organização na página Gerenciar aplicativos ou para usuários específicos usando políticas de permissão de [aplicativo](teams-app-permission-policies.md).

Os **aplicativos Power Apps Compartilhados** e **Aplicativos do Power Virtual Agent compartilhados** na loja de aplicativos da sua organização representam todos os aplicativos criados nessa plataforma específica. Se você bloquear um ou ambos os aplicativos para toda a organização ou para usuários específicos, os usuários poderão exibir aplicativos como aplicativos bloqueados, mas não poderão instalá-los no Teams. Os usuários podem solicitar [aprovação do administrador para desbloquear aplicativos](manage-apps.md#manage-user-requests-to-unblock-apps).

Tenha em mente que você pode controlar o acesso a todos os aplicativos criados no Power Apps e no Power Virtual Agents, mas não pode permitir nem bloquear aplicativos individuais. O criador do aplicativo decide quem pode acessar os aplicativos criados por meio do recurso de compartilhamento de dentro do Power Apps e do Power Virtual Agents. Se um criador compartilhou um aplicativo criado no Power Virtual Agents com um usuário e você bloqueou os Aplicativos do **Power Virtual Agents** Compartilhados para esse usuário, o usuário não poderá ver nem instalar nenhum aplicativo dessa plataforma no Teams.

Se um usuário tiver permissão para acessar aplicativos do Power Apps ou do Power Virtual Agents e, em seguida, você impedir que o usuário acesse aplicativos de uma ou ambas as plataformas, o usuário ainda poderá acessar e usar aplicativos do Microsoft Power Platforms instalados antes de você bloquear o aplicativo ou os aplicativos. No entanto, o usuário não pode mais instalar aplicativos dessas plataformas no **Built with Power Platform**.

> [!NOTE]
> A **configuração** Permitir interação com aplicativos personalizados em toda a [](manage-apps.md) organização na página Gerenciar aplicativos se aplica a todos em sua organização e determina se eles podem interagir com aplicativos personalizados. As configurações de aplicativo em toda a organização controlam o comportamento de todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários. Se essa configuração estiver desativada, os usuários em sua organização não poderão instalar aplicativos personalizados, incluindo aplicativos do Microsoft Power Platform. Para saber mais, confira [Gerenciar configurações de aplicativo em toda a organização](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Permitir ou bloquear aplicativos do Microsoft Power Platform para sua organização

Por padrão, o **Power Apps Compartilhado** e os Aplicativos **do Power Virtual Agent** Compartilhado são permitidos para todos os usuários do Teams em sua organização. Você pode bloqueiá-los ou permiti-los no [](manage-apps.md) nível da organização na página Gerenciar aplicativos do Centro de administração do Microsoft Teams.  

1. No painel esquerdo do centro de administração do Microsoft Teams, acesse Aplicativos **do Teams Gerenciar** > **aplicativos**. Você deve ser um administrador global ou administrador de serviço do Teams para acessar a página.
2. Na lista de aplicativos, siga um dos procedimentos a seguir.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Captura de tela da página Gerenciar aplicativos, mostrando aplicativos compartilhados do Microsoft Power Platform.":::

    * Para bloquear aplicativos criados no Power Apps ou no Power Virtual Agents para todos os usuários em sua organização, pesquise Por Aplicativos Do **Power Apps** Compartilhados ou Aplicativos do **Agente Virtual** Compartilhado, selecione-os e, em seguida, **selecione Bloquear**.
    * Para permitir aplicativos criados no Power Apps ou no Power Virtual Agents para todos os usuários em sua organização, pesquise por Aplicativos Compartilhados do **Power Apps** ou Aplicativos do **Power Virtual Agent** Compartilhados, selecione-os e selecione **Permitir**.

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Permitir ou bloquear aplicativos do Microsoft Power Platform para usuários específicos

Para permitir ou impedir que usuários específicos em sua organização acessem aplicativos criados no Power Apps ou no Power Virtual Agents, crie e atribua uma ou mais políticas de permissão [de aplicativo personalizadas](teams-app-permission-policies.md).

Por exemplo, para impedir que usuários específicos acessem aplicativos criados no Power Apps, crie uma política de permissão de aplicativo personalizada para bloquear o **Power Apps** Compartilhado e atribua a política a esses usuários.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Captura de tela do exemplo de política de permissão de aplicativo personalizado com o Power Apps compartilhado bloqueado.":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Usar logs de auditoria para investigar a atividade de instalação do Microsoft Power Platform

Você pode usar os logs de auditoria do Teams para investigar eventos em que os usuários instalaram aplicativos do Microsoft Power Platform na seção **Compilado com o Power Platform** da página Aplicativos no Teams. Para fazer isso, [pesquise no log de auditoria](./audit-log-events.md) o evento Instalado **do** Teams do aplicativo (na operação **AppInstalled** ) para um usuário ou conjunto de usuários. Para localizar aplicativos instalados do **Built with Power Platform**, procure o valor **TemplatedInstance** na propriedade **AppDistributionMode** nos detalhes de um determinado registro.

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Captura de tela do valor TemplatedInstance na propriedade AppDistributionMode." lightbox="media/manage-power-platform-apps-audit.png":::

> [!NOTE]
> Você pode exportar registros de auditoria no formato CSV para facilitar a filtragem.

## <a name="related-articles"></a>Artigos relacionados

* [Compartilhar um aplicativo de tela no Power Apps](/powerapps/maker/canvas-apps/share-app)
* [Compartilhar seu bot com outros usuários](/power-virtual-agents/admin-share-bots)
* [Gerenciar aplicativos no centro de administração do Microsoft Teams](manage-apps.md)
* [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
* [Publicar um aplicativo personalizado enviado por meio da API de Envio de Aplicativo do Teams](submit-approve-custom-apps.md)
