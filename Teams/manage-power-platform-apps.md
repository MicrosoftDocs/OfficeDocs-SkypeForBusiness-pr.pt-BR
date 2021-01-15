---
title: Gerenciar aplicativos do Microsoft Power Platform no centro de administração do Microsoft Teams
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
description: Saiba como gerenciar o acesso a aplicativos personalizados integrados ao Microsoft Power Platform no centro de administração do Microsoft Teams.
ms.openlocfilehash: b44bd77a6415be9c9c9454fd96028fdbb8c608c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831291"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gerenciar aplicativos do Microsoft Power Platform no centro de administração do Microsoft Teams

## <a name="microsoft-power-platform-apps-in-teams"></a>Aplicativos do Microsoft Power Platform no Teams

Este artigo fornece uma visão geral de como gerenciar aplicativos do [Microsoft Power Platform](https://powerplatform.microsoft.com/) no centro de administração do Microsoft Teams.

> [!NOTE]
> Este artigo se aplica a aplicativos personalizados criados por criadores em sua organização usando Power Apps ou Power Virtual Agents. Esses aplicativos personalizados são adicionados automaticamente ao Teams. Este artigo não se aplica ao aplicativo Power Apps ou ao aplicativo Power Virtual Agents instalado na página Aplicativos ou fixado no Teams por meio de uma política de configuração de aplicativo. Gerencie esses aplicativos como faria [](manage-apps.md) para qualquer outro aplicativo na página Gerenciar aplicativos, usando políticas de permissão de aplicativo [e](teams-app-permission-policies.md)políticas [de configuração de aplicativos.](teams-app-setup-policies.md)

[O Power Apps](https://powerapps.microsoft.com) é um ambiente de desenvolvimento de aplicativos de código/sem código que os criadores em sua organização podem usar para criar aplicativos personalizados que se conectam aos seus dados corporativos. [O Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) é um ambiente de criação de bot sem código para criadores criarem bots poderosos. Com a integração dos aplicativos do Microsoft Power Platform ao Teams, as organizações podem simplificar os processos de negócios, responder às necessidades de negócios em mudança mais rapidamente para gerar maior colaboração e criar e compartilhar soluções personalizadas para serem mais produtivas.  

Os aplicativos do Microsoft Power Platform criados por criadores em sua organização são adicionados automaticamente ao Teams. Os criadores podem controlar quem pode acessar seus aplicativos usando o recurso de compartilhamento no [Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) e o recurso de [compartilhamento no Power Virtual Agents.](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)

Quando um aplicativo do Microsoft Power Platform é criado ou compartilhado, os usuários podem exibi-lo e instalá-lo na página Aplicativos, indo para **Built for Your Organization *Name***  >  **Built by your colleagues**. (Pode levar alguns minutos depois que um aplicativo é criado ou compartilhado para que o aplicativo apareça aqui.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Screenshots of Apps page, showing Microsoft Power Platform apps listed in Built by your colleagues":::

Um usuário verá um aplicativo criado por **seus colegas se** o aplicativo atender a uma das seguintes condições.

|Power Apps |Agentes Virtuais do Power  |
|---------|---------|
|<ul><li>O usuário criou o aplicativo.</li><li>O aplicativo foi compartilhado diretamente com o usuário.</li><li>O usuário usou recentemente o aplicativo. </li></ul>| <ul><li>O usuário criou o bot.</li><li>O bot pertence a uma equipe da que o usuário é membro. </li></ul>        |

Os usuários instalam aplicativos do Microsoft Power Platform da mesma maneira que instalam qualquer outro aplicativo do Teams. Lembre-se de que os usuários só podem instalar aplicativos no contexto ao qual têm permissões, por exemplo, uma equipe de sua propriedade, um chat da qual eles fazem parte ou seu escopo pessoal.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gerenciar o acesso aos aplicativos do Microsoft Power Platform no centro de administração do Microsoft Teams

Como administrador, você pode controlar se os aplicativos do Microsoft Power Platform estão listados em **Built by your colleagues** na página Aplicativos no Teams. Você pode bloquear ou permitir coletivamente todos os aplicativos criados no Power Apps [](manage-apps.md) ou todos os aplicativos criados no Power Virtual Agents no nível da organização na página Gerenciar aplicativos ou para usuários específicos usando políticas de permissão de [aplicativo.](teams-app-permission-policies.md)

Os **aplicativos do Power Apps compartilhados** e aplicativos do Agente Virtual do **Power** Compartilhado na loja de aplicativos da sua organização representam todos os aplicativos criados nessa plataforma específica. Se você bloquear um ou ambos os aplicativos no nível da organização ou para usuários específicos, esses usuários não poderão ver nenhum aplicativo dessas plataformas em Built **por** seus colegas e não poderão instalá-los no Teams.  

Lembre-se de que você pode controlar o acesso a todos os aplicativos criados no Power Apps e no Power Virtual Agents, mas não pode permitir ou bloquear aplicativos individuais. Os criadores decidem quem pode acessar os aplicativos que eles criam por meio do recurso de compartilhamento no Power Apps e no Power Virtual Agents. Se um criador compartilhou um aplicativo que criou no Power Virtual Agents com um usuário e você bloqueou os Aplicativos de Agentes Virtuais do **Power** Compartilhado para esse usuário, o usuário não poderá ver ou instalar aplicativos dessa plataforma no Teams.

Se um usuário tiver permissão para acessar aplicativos do Power Apps ou agentes virtuais do Power e, em seguida, impedir que o usuário acesse aplicativos de uma ou ambas as plataformas, o usuário ainda poderá acessar e usar aplicativos do Microsoft Power Platforms instalados antes de bloquear o aplicativo ou aplicativos. No entanto, o usuário não pode mais ver ou instalar aplicativos dessas plataformas em **Built by your colleagues**.

> [!NOTE]
> A **configuração** permitir interação com aplicativos [](manage-apps.md) personalizados em toda a organização na página Gerenciar aplicativos se aplica a todos em sua organização e rege se eles podem interagir com aplicativos personalizados. As configurações de aplicativos em toda a organização regem o comportamento de todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários. Por padrão, essa configuração é ativada. Se essa configuração estiver desligada, os usuários em sua organização não poderão ver ou instalar aplicativos personalizados, incluindo aplicativos do Microsoft Power Platform. Para saber mais, consulte [Gerenciar configurações de aplicativos](manage-apps.md#manage-org-wide-app-settings)em toda a organização.

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Permitir ou bloquear aplicativos do Microsoft Power Platform para sua organização

Por padrão, **aplicativos de energia compartilhado** e aplicativos de agente **virtual** de energia compartilhado são permitidos para todos os usuários do Teams em sua organização. Você pode bloqueá-los ou permitir no nível da organização na página Gerenciar [aplicativos](manage-apps.md) do Centro de administração do Microsoft Teams.  

1. Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **aplicativos do Teams**  >  **Gerenciar aplicativos.** Você deve ser um administrador global ou administrador de serviço do Teams para acessar a página.
2. Na lista de aplicativos, faça um dos seguintes.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Captura de tela da página Gerenciar aplicativos, mostrando aplicativos compartilhados do Microsoft Power Platform":::

    - Para bloquear aplicativos criados no Power Apps ou agentes virtuais  do Power para todos os usuários em sua organização, pesquise aplicativos de energia compartilhado ou aplicativos de agente **virtual** de energia compartilhado, selecione-o e clique em **Bloquear**.
    - Para permitir aplicativos criados no Power Apps ou agentes virtuais do Power para todos os usuários em sua organização, pesquise por Aplicativos do **Power Compartilhado** ou Aplicativos de Agente Virtual Do **Power** Compartilhado, selecione-o e clique em **Permitir**.

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Permitir ou bloquear aplicativos do Microsoft Power Platform para usuários específicos

Para permitir ou impedir que usuários específicos em sua organização acessem aplicativos criados no Power Apps ou no Power Virtual Agents, crie e atribua uma ou mais políticas de permissão de aplicativo [personalizadas.](teams-app-permission-policies.md) 

Por exemplo, para impedir que usuários específicos acessem aplicativos criados no Power Apps, crie uma política de permissão de aplicativo personalizada para bloquear Aplicativos Do **Power** Compartilhados e atribua a política a esses usuários.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Captura de tela da política de permissão personalizada de aplicativo de exemplo com aplicativos do Power Compartilhado bloqueados":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Usar logs de auditoria para investigar a atividade de instalação do Microsoft Power Platform

Você pode usar logs de auditoria do Teams para investigar  eventos em que os usuários instalaram aplicativos do Microsoft Power Platform na seção Criada por seus colegas da página Aplicativos no Teams. Para fazer isso, pesquise no log de [auditoria](https://docs.microsoft.com/microsoftteams/audit-log-events) o evento Do **Teams** do aplicativo Instalado (na operação **AppInstalled)** para um usuário ou conjunto de usuários. Para encontrar aplicativos instalados de **Built por** seus colegas, procure o valor **TemplatedInstance** na **propriedade AppDistributionMode** em detalhes de um determinado registro. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Captura de tela do valor TemplatedInstance na propriedade AppDistributionMode":::

> [!NOTE]
> Você pode exportar registros de auditoria no formato CSV para facilitar a filtragem.

## <a name="related-topics"></a>Tópicos relacionados

- [Compartilhar um aplicativo de tela no Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [Compartilhar seu bot com outros usuários](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Gerenciar aplicativos no centro de administração do Microsoft Teams](manage-apps.md)
- [Gerenciar políticas de permissões de aplicativo no Teams](teams-app-permission-policies.md)
- [Publicar um aplicativo personalizado enviado por meio da API de Envio de Aplicativos do Teams](submit-approve-custom-apps.md)
