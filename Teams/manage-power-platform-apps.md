---
title: Gerenciar aplicativos do Microsoft Power Platform no Centro de administração do Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Saiba como gerenciar o acesso a aplicativos personalizados integrados ao Microsoft Power Platform no Centro de administração do Microsoft Teams.
ms.openlocfilehash: b44bd77a6415be9c9c9454fd96028fdbb8c608c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831291"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gerenciar aplicativos do Microsoft Power Platform no Centro de administração do Microsoft Teams

## <a name="microsoft-power-platform-apps-in-teams"></a>Aplicativos do Microsoft Power Platform no Teams

Este artigo apresenta uma visão geral de como gerenciar aplicativos do [Microsoft Power Platform](https://powerplatform.microsoft.com/) no Centro de administração do Microsoft Teams.

> [!NOTE]
> Este artigo se aplica aos aplicativos personalizados criados por criadores em sua organização usando Power Apps ou Power Virtual Agents. Esses aplicativos personalizados são adicionados automaticamente ao Teams. Este artigo não se aplica ao aplicativo Power Apps ou ao aplicativo Power Virtual Agents instalado na página Aplicativos ou fixado no Teams por meio de uma política de configuração de aplicativo. Você gerencia esses aplicativos como faria [](manage-apps.md) com qualquer outro aplicativo na página Gerenciar aplicativos, usando políticas de permissão de aplicativo [e](teams-app-permission-policies.md)políticas [de configuração de aplicativos.](teams-app-setup-policies.md)

[O Power Apps](https://powerapps.microsoft.com) é um ambiente de desenvolvimento de aplicativos de baixo código/sem código que os criadores de sua organização podem usar para criar aplicativos personalizados que se conectam aos seus dados corporativos. [O Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) é um ambiente de criação de bots sem código para criadores criarem bots poderosos. Com a integração dos aplicativos do Microsoft Power Platform com o Teams, as organizações podem simplificar os processos de negócios, responder às necessidades de negócios em mudança de forma mais rápida para impulsionar uma maior colaboração e criar e compartilhar soluções personalizadas para serem mais produtivas.  

Os aplicativos do Microsoft Power Platform criados por criadores em sua organização são adicionados automaticamente ao Teams. Os criadores podem controlar quem pode acessar seu aplicativo usando o recurso de compartilhamento no [Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) e o recurso de compartilhamento no Power [Virtual Agents.](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)

Quando um aplicativo microsoft power platform é criado ou compartilhado, os usuários podem exibi-lo e instalá-lo na página Aplicativos indo para Built for Your ***Organization Name*** Built by your  >  **colleagues.** (Pode levar alguns minutos depois que um aplicativo é criado ou compartilhado para que o aplicativo apareça aqui.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Capturas de tela da página Aplicativos, mostrando os aplicativos do Microsoft Power Platform listados em Criado por seus colegas":::

Um usuário verá um aplicativo em **Built por seus colegas** se o aplicativo atender a uma das seguintes condições.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>O usuário criou o aplicativo.</li><li>O aplicativo foi compartilhado diretamente com o usuário.</li><li>O usuário usou o aplicativo recentemente. </li></ul>| <ul><li>O usuário criou o bot.</li><li>O bot pertence a uma equipe da que o usuário é membro. </li></ul>        |

Os usuários instalam aplicativos do Microsoft Power Platform da mesma forma que instalam qualquer outro aplicativo do Teams. Lembre-se de que os usuários só podem instalar aplicativos no contexto ao qual têm permissões, por exemplo, uma equipe da qual possuem, um chat da qual fazem parte ou seu escopo pessoal.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gerenciar o acesso aos aplicativos do Microsoft Power Platform no Centro de administração do Microsoft Teams

Como administrador, você pode controlar se os aplicativos do Microsoft Power Platform estão listados em **Built por** seus colegas na página Aplicativos no Teams. Você pode bloquear ou permitir coletivamente todos os aplicativos criados no Power Apps [](manage-apps.md) ou em todos os aplicativos criados no nível da organização no nível da organização na página Gerenciar aplicativos ou para usuários específicos que usam políticas de permissão de [aplicativos.](teams-app-permission-policies.md)

Os **aplicativos Power Apps Compartilhados** e **Aplicativos** do Agente Virtual Compartilhado na loja de aplicativos da sua organização representam todos os aplicativos criados nessa plataforma específica. Se você bloquear um ou ambos os aplicativos no nível da organização ou para usuários específicos, esses usuários não poderão ver aplicativos dessas plataformas em Built **por** seus colegas e não poderão instalá-los no Teams.  

Lembre-se de que você pode controlar o acesso a todos os aplicativos criados no Power Apps e no Power Virtual Agents, mas não pode permitir ou bloquear aplicativos individuais. Os criadores decidem quem pode acessar os aplicativos que criam por meio do recurso de compartilhamento no Power Apps e no Power Virtual Agents. Se um criador compartilhou um aplicativo que ele criou no Power Virtual Agents com um usuário e você bloqueou os Aplicativos de Agentes **Virtuais** Compartilhados para esse usuário, o usuário não poderá ver ou instalar aplicativos dessa plataforma no Teams.

Se um usuário tiver permissão para acessar aplicativos do Power Apps ou do Power Virtual Agents e, em seguida, impedir que o usuário acesse aplicativos de uma ou ambas essas plataformas, o usuário ainda poderá acessar e usar os aplicativos do Microsoft Power Platforms instalados antes de você bloquear o aplicativo ou aplicativos. No entanto, o usuário não pode mais ver ou instalar aplicativos dessas plataformas em **Built por seus colegas.**

> [!NOTE]
> A **configuração** Permitir interação com aplicativos [](manage-apps.md) personalizados em toda a organização na página Gerenciar aplicativos se aplica a todos em sua organização e rege se eles podem interagir com aplicativos personalizados. As configurações de aplicativo em toda a organização controlam o comportamento de todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários. Por padrão, essa configuração é ativada. Se essa configuração estiver desligada, os usuários da sua organização não poderão ver ou instalar aplicativos personalizados, incluindo aplicativos do Microsoft Power Platform. Para saber mais, confira [Gerenciar configurações de aplicativos](manage-apps.md#manage-org-wide-app-settings)em toda a organização.

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Permitir ou bloquear aplicativos do Microsoft Power Platform para sua organização

Por padrão, **os Power Apps Compartilhados** e **os Aplicativos** do Agente Virtual Compartilhado são permitidos para todos os usuários do Teams em sua organização. Você pode bloquear ou permitir no nível da organização na página Gerenciar [aplicativos](manage-apps.md) do Centro de administração do Microsoft Teams.  

1. Na navegação à esquerda do Centro de administração do Microsoft Teams, vá para Os **aplicativos do Teams**  >  **Gerenciar aplicativos.** Você deve ser um administrador global ou administrador de serviços do Teams para acessar a página.
2. Na lista de aplicativos, faça um dos seguintes.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Captura de tela da página Gerenciar aplicativos, mostrando aplicativos compartilhados do Microsoft Power Platform":::

    - Para bloquear aplicativos criados no Power Apps ou Power Virtual Agents para todos os usuários em sua organização, procure por Power **Apps** compartilhados ou Aplicativos do **Agente Virtual** Compartilhado, selecione-os e clique em **Bloquear.**
    - Para permitir que os aplicativos criados no Power Apps ou no Power Virtual Agents para todos os usuários em sua organização, pesquisem power **apps** compartilhados ou aplicativos do **Agente Virtual Compartilhado,** selecione-os e clique em **Permitir.**

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Permitir ou bloquear aplicativos do Microsoft Power Platform para usuários específicos

Para permitir ou bloquear usuários específicos em sua organização de acessar aplicativos criados no Power Apps ou Power Virtual Agents, crie e atribua uma ou mais políticas de permissão [personalizadas de aplicativos.](teams-app-permission-policies.md) 

Por exemplo, para bloquear usuários específicos de acessar aplicativos criados no Power Apps, crie uma política de permissão de aplicativo personalizada para bloquear Os **Power Apps** Compartilhados e atribua a política a esses usuários.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Captura de tela da política de permissão de aplicativo personalizado de exemplo com Os Power Apps Compartilhados bloqueados":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Usar logs de auditoria para investigar a atividade de instalação do Microsoft Power Platform

Você pode usar logs de auditoria para o Teams para  investigar eventos em que os usuários instalaram aplicativos do Microsoft Power Platform a partir da seção Criado por seus colegas da página Aplicativos no Teams. Para fazer isso, [pesquise](https://docs.microsoft.com/microsoftteams/audit-log-events) o log de auditoria do evento Teams do aplicativo instalado (na operação **AppInstalled)** para um usuário ou conjunto de usuários.  Para encontrar aplicativos instalados a partir de **Built** por seus colegas, procure o valor **TemplatedInstance** na propriedade **AppDistributionMode** nos detalhes de um determinado registro. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Captura de tela do valor TemplatedInstance na propriedade AppDistributionMode":::

> [!NOTE]
> Você pode exportar registros de auditoria no formato CSV para facilitar a filtragem.

## <a name="related-topics"></a>Tópicos relacionados

- [Compartilhar um aplicativo de tela no Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [Compartilhar seu bot com outros usuários](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Gerenciar aplicativos no Centro de administração do Microsoft Teams](manage-apps.md)
- [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
- [Publicar um aplicativo personalizado enviado por meio da API de Envio de Aplicativos do Teams](submit-approve-custom-apps.md)
