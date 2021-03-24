---
title: Gerenciar aplicativos da Plataforma Microsoft Power no centro de administração do Microsoft Teams
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
description: Saiba como gerenciar o acesso a aplicativos personalizados construídos na Plataforma Microsoft Power no centro de administração do Microsoft Teams.
ms.openlocfilehash: 03940d402bd2259287e1e69f844e6560424f15e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096155"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gerenciar aplicativos da Plataforma Microsoft Power no centro de administração do Microsoft Teams

## <a name="microsoft-power-platform-apps-in-teams"></a>Aplicativos da Plataforma Do Microsoft Power no Teams

Este artigo fornece uma visão geral de como gerenciar aplicativos [da Plataforma Microsoft Power](https://powerplatform.microsoft.com/) no centro de administração do Microsoft Teams.

> [!NOTE]
> Este artigo se aplica a aplicativos personalizados criados por fabricantes em sua organização usando Power Apps ou Agentes Virtuais do Power. Esses aplicativos personalizados são adicionados automaticamente ao Teams. Este artigo não se aplica ao aplicativo Power Apps ou ao aplicativo Power Virtual Agents instalado na página Aplicativos ou fixado no Teams por meio de uma política de configuração de aplicativo. Gerencie esses aplicativos como faria com qualquer outro aplicativo na página [Gerenciar](manage-apps.md) aplicativos, usando políticas de permissão de aplicativo [e](teams-app-permission-policies.md)políticas de [configuração de aplicativos.](teams-app-setup-policies.md)

[O Power Apps](https://powerapps.microsoft.com) é um ambiente de desenvolvimento de aplicativos de baixo código/sem código que os criadores em sua organização podem usar para criar aplicativos personalizados que se conectam aos dados corporativos. [O Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) é um ambiente de criação de bots sem código para os criadores criarem bots poderosos. Com a integração dos aplicativos da Plataforma Do Microsoft Power no Teams, as organizações podem simplificar os processos de negócios, responder às necessidades de negócios em mudança mais rapidamente para gerar maior colaboração e criar e compartilhar soluções personalizadas para serem mais produtivas.  

Os aplicativos da Plataforma Microsoft Power criados por criadores em sua organização são adicionados automaticamente ao Teams. Os criadores podem controlar quem pode acessar seu aplicativo usando o recurso de compartilhamento no [Power Apps](/powerapps/maker/canvas-apps/share-app) e o recurso [de compartilhamento em Agentes Virtuais do Power.](/power-virtual-agents/admin-share-bots)

Quando um aplicativo da Plataforma Microsoft Power é criado ou compartilhado, os usuários podem exibi-lo e instalá-lo na página Aplicativos, indo para **Built for Your Organization *Name***  >  **Built by your colleagues**. (Pode levar alguns minutos depois que um aplicativo é criado ou compartilhado para que o aplicativo apareça aqui.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Screenshots of Apps page, showing Microsoft Power Platform apps listed in Built by your colleagues":::

Um usuário verá um aplicativo em **Built by your colleagues** se o aplicativo atender a uma das seguintes condições.

|Power Apps |Agentes Virtuais do Power  |
|---------|---------|
|<ul><li>O usuário criou o aplicativo.</li><li>O aplicativo foi compartilhado diretamente com o usuário.</li><li>O usuário usou recentemente o aplicativo. </li></ul>| <ul><li>O usuário criou o bot.</li><li>O bot pertence a uma equipe de que o usuário é membro. </li></ul>        |

Os usuários instalam aplicativos da Plataforma Microsoft Power da mesma forma que instalam qualquer outro aplicativo do Teams. Lembre-se de que os usuários só podem instalar aplicativos no contexto ao qual eles têm permissões, por exemplo, uma equipe que possuem, um chat do qual fazem parte ou seu escopo pessoal.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gerenciar o acesso aos aplicativos da Plataforma Microsoft Power no centro de administração do Microsoft Teams

Como administrador, você pode controlar se os aplicativos do Microsoft Power Platform estão listados em **Built by your colleagues** na página Aplicativos no Teams. Você pode bloquear ou permitir coletivamente todos os aplicativos criados no Power Apps [](manage-apps.md) ou em todos os aplicativos criados no Power Virtual Agents no nível da organização na página Gerenciar aplicativos ou para usuários específicos usando políticas de permissão de [aplicativo.](teams-app-permission-policies.md)

Os **aplicativos do Power Apps compartilhados** e aplicativos de Agente Virtual do **Power** Compartilhado na loja de aplicativos da sua organização representam todos os aplicativos criados nessa plataforma específica. Se você bloquear um ou ambos os aplicativos no nível da organização ou para usuários específicos, esses usuários não poderão ver nenhum aplicativo dessas plataformas em Built by your **colleagues** e não poderão instalá-los no Teams.  

Lembre-se de que você pode controlar o acesso a todos os aplicativos criados no Power Apps e no Power Virtual Agents, mas não pode permitir ou bloquear aplicativos individuais. Os criadores decidem quem pode acessar os aplicativos que eles criam por meio do recurso de compartilhamento de dentro do Power Apps e dos Agentes Virtuais do Power. Se um criador compartilhou um aplicativo criado no Power Virtual Agents com um usuário e você bloqueou os Aplicativos de Agentes Virtuais do **Power** Compartilhado para esse usuário, o usuário não poderá ver ou instalar aplicativos dessa plataforma no Teams.

Se um usuário tiver permissão para acessar aplicativos de Power Apps ou Agentes Virtuais do Power e, em seguida, impedir que o usuário acesse aplicativos de uma ou ambas as plataformas, o usuário ainda poderá acessar e usar aplicativos do Microsoft Power Platforms instalados antes de bloquear o aplicativo ou aplicativos. No entanto, o usuário não pode mais ver ou instalar aplicativos dessas plataformas em **Built by your colleagues**.

> [!NOTE]
> A **configuração Permitir** interação com aplicativos [](manage-apps.md) personalizados em toda a organização na página Gerenciar aplicativos se aplica a todos em sua organização e rege se eles podem interagir com aplicativos personalizados. As configurações de aplicativo em toda a organização controlam o comportamento de todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários. Por padrão, essa configuração é ativada. Se essa configuração estiver desligada, os usuários da sua organização não poderão ver ou instalar aplicativos personalizados, incluindo aplicativos da Plataforma Do Microsoft Power. Para saber mais, confira [Gerenciar configurações de aplicativo](manage-apps.md#manage-org-wide-app-settings)em toda a organização.

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Permitir ou bloquear aplicativos da Plataforma Microsoft Power para sua organização

Por padrão, **aplicativos do Power Compartilhado** e **Aplicativos** de Agente Virtual Do Power Compartilhado são permitidos para todos os usuários do Teams em sua organização. Você pode bloquear ou permitir que eles no nível da organização na página [Gerenciar aplicativos](manage-apps.md) do centro de administração do Microsoft Teams.  

1. Na navegação à esquerda do Centro de Administração do Microsoft Teams, vá para **Aplicativos do Teams** > **Gerenciar aplicativos**. Você deve ser um administrador global ou administrador de serviço do Teams para acessar a página.
2. Na lista de aplicativos, faça um dos seguintes.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Captura de tela da página Gerenciar aplicativos, mostrando aplicativos compartilhados do Microsoft Power Platform":::

    - Para bloquear aplicativos criados no Power Apps ou no Power Virtual Agents para todos os usuários em sua organização, pesquise por Aplicativos do **Power Compartilhado** ou Aplicativos de Agente Virtual Do **Power** Compartilhado, selecione-o e clique em **Bloquear**.
    - Para permitir aplicativos criados no Power Apps ou no Power Virtual Agents para todos os usuários em sua organização, pesquise por Aplicativos de **Energia** Compartilhada ou Aplicativos de Agente Virtual Do **Power** Compartilhado, selecione-o e clique em **Permitir**.

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Permitir ou bloquear aplicativos da Plataforma Microsoft Power para usuários específicos

Para permitir ou bloquear usuários específicos em sua organização de acessar aplicativos criados no Power Apps ou agentes virtuais do Power, crie e atribua uma ou mais políticas de permissão de [aplicativo personalizadas.](teams-app-permission-policies.md) 

Por exemplo, para impedir que usuários específicos acessem aplicativos criados no Power Apps, crie uma política de permissão de aplicativo personalizada para bloquear aplicativos **power compartilhados** e atribua a política a esses usuários.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Captura de tela da política de permissão de aplicativo personalizada de exemplo com Aplicativos do Power Compartilhado bloqueados":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Usar logs de auditoria para investigar a atividade de instalação da Plataforma Microsoft Power

Você pode usar logs de auditoria para o Teams para investigar eventos em que os usuários instalaram aplicativos da Plataforma Microsoft Power a partir da seção **Criado** por seus colegas da página Aplicativos no Teams. Para fazer isso, [pesquise](./audit-log-events.md) o log de auditoria do evento Do **Teams** do aplicativo instalado (na operação **AppInstalled)** para um usuário ou conjunto de usuários. Para encontrar aplicativos instalados de **Built por** seus colegas, procure o valor **TemplatedInstance** na propriedade **AppDistributionMode** em detalhes de um determinado registro. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Captura de tela do valor TemplatedInstance na propriedade AppDistributionMode":::

> [!NOTE]
> Você pode exportar registros de auditoria no formato CSV para facilitar a filtragem.

## <a name="related-topics"></a>Tópicos relacionados

- [Compartilhar um aplicativo de tela no Power Apps](/powerapps/maker/canvas-apps/share-app)
- [Compartilhar seu bot com outros usuários](/power-virtual-agents/admin-share-bots)
- [Gerenciar aplicativos no centro de administração do Microsoft Teams](manage-apps.md)
- [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
- [Publicar um aplicativo personalizado enviado por meio da API de Envio de Aplicativos do Teams](submit-approve-custom-apps.md)