---
title: Gerenciar Teams transição para o novo Teams de administração
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como gerenciar as configurações de todos os locatários e usuários para Teams durante a transição do Teams no Centro de administração do Microsoft 365 para o novo centro de administração Teams.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: 727aa58f3e7a91336355730ce5f0a552ea09fdc9
ms.sourcegitcommit: b2566e64e02cb51d18836630d3aa9b6f27b924da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59491731"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Gerenciar equipes durante a transição para o novo centro de administração do Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Qual é o novo Microsoft Teams de administração  

A nova experiência do centro de administração fornecerá uma experiência unificada para gerenciar Teams e Skype for Business. Estamos fornecendo funcionalidade adicional, informações de ponta a ponta e a capacidade de gerenciar Teams configurações em um nível de usuário.

![Captura de tela do Microsoft Teams de administração.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Configurações migrado para o novo Microsoft Teams de administração

A tabela a seguir identifica as seções da experiência Teams que foram migradas e mostra a relação entre as configurações atuais e as políticas no novo portal de administração.

|Seção de Teams no Centro de administração do Microsoft 365  |Nome da configuração (nível de locatário)  |Microsoft Teams de centro de administração   |Nível: Locatário ou Usuário   |
|---------|---------|---------|---------|
|Geral     |Mostrar gráfico organizacional no perfil pessoal        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  Locatário       |
|Geral     |Use Skype for Business para destinatários que não têm Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Locatário         |
|Integração de email     |Permitir que os usuários enviem emails para canais         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Locatário         |
|Integração de email     |Permitir lista de envios         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |Locatário         |
|Armazenamento em nuvem personalizado     |Box         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Locatário         |
|Armazenamento em nuvem personalizado     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Locatário         |
|Armazenamento em nuvem personalizado     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Locatário         |
|Armazenamento em nuvem personalizado     |Google Drive        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Locatário         |
|Armazenamento em nuvem personalizado     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Locatário         |
|Configurações por tipo de usuário/licença     |Ativar Microsoft Teams para todos os usuários          |Preterido<sup>1</sup>        |         |
|Equipes e canais     |         |Redireciona para Azure Active Directory Gerenciamento de Grupo (o mesmo que a experiência atual).              |Usuário         |
|Equipes e canais     |         |Redireciona para o Gerenciamento de Grupo do AAD (mesmo que a experiência atual).             |Usuário          |
|Aplicativos|Habilitar novos aplicativos externos por padrão|Configurações de aplicativos em toda a organização|Locatário|
|Aplicativos|Permitir aplicativos externos|Configurações de aplicativos em toda a organização|Locatário|
|Aplicativos|Permitir sideload de aplicativos<sup>externos 2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|Usuário|
|Aplicativos|Aplicativos<sup>padrão 3</sup>|TeamsAppPermissionPolicy|Usuário|
|Aplicativos|Aplicativos<sup>externos 3</sup>|TeamsAppPermissionPolicy|Usuário|
|Chamadas e reuniões     |Permitir o agendamento de reuniões privadas         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuário          |
|Chamadas e reuniões     |Permitir reunião de canal ad hoc         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuário          |
|Chamadas e reuniões     |Permitir o agendamento de reuniões de canal         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuário          |
|Chamadas e reuniões     |Permitir vídeos em reuniões         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuário          |
|Chamadas e reuniões     |Permitir compartilhamento de tela em reuniões         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuário          |
|Chamadas e reuniões     |Permitir chamada privada         |[TeamsCallingPolicy ](/powershell/module/skype/set-csteamscallingpolicy)        |Usuário          |
|Mensagens     |Habilitar Giphy para que os usuários possam adicionar GIFs a conversas         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |
|Mensagens     |Classificação de conteúdo         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |
|Mensagens     |Habilitar memes que os usuários podem editar e adicionar a conversas         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |
|Mensagens     |Habilitar adesivos que os usuários podem editar e adicionar a conversas         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |
|Mensagens     |Permitir que os proprietários excluam todas as mensagens         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |
|Mensagens     |Permitir que os usuários editem suas próprias mensagens         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |
|Mensagens     |Permitir que os usuários excluam suas próprias mensagens         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |
|Mensagens     |Permite que os usuários conversem em particular         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |

<sup>1</sup> Preterido para Convidado. A habilitação/desabilitação do Convidado agora pode ser gerenciada no Microsoft Teams de administração. A habilitação/desabilitação Teams para Empresas Enterprise, Estudante Edu e Professores Edu serão preterida em breve. Isso deve ser gerenciado atribuindo licenças no Centro de administração do Microsoft 365. Consulte [Gerenciar o acesso do usuário Microsoft Teams](user-access.md).
<br><br>
<sup>2</sup> Sideloading é dividido da seguinte forma:

- Permitir que um usuário sideload de aplicativos que podem ser gerenciados em um nível de usuário no [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy).
- Permitir que os usuários em um locatário interajam com aplicativos personalizados que podem ser gerenciados em um nível de locatário em configurações de aplicativos em toda a organização.

<sup>3</sup> Aplicativos padrão e aplicativos externos podem ser habilitados e desabilitados no nível do usuário no TeamsAppPermissionPolicy. Além disso, os aplicativos podem ser bloqueados no nível do locatário em configurações de aplicativos em toda a organização que substituem qualquer configuração de usuário e de nível de locatário.

> [!NOTE]
> Você continuará a usar o painel Grupos no Centro de administração do Microsoft 365 para configuração relacionada a Teams e canais. Configurações para Aplicativos permanecerá na área Teams do Centro de administração do Microsoft 365 e será migrada posteriormente.

## <a name="manage-settings-during-the-migration"></a>Gerenciar configurações durante a migração

Você pode continuar a modificar as configurações no Centro de administração do Microsoft 365 e no centro de administração Skype for Business até que a migração de uma seção seja concluída para seu locatário.

A tabela a seguir mostra onde você pode gerenciar recursos durante a migração.

|Recurso  |Microsoft Teams de administração                      |Skype for Business de administração (herdado)  |Centro de administração do Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Teams Políticas de mensagens, reuniões e eventos ao vivo     |     X    |         |         |
|Teams Política de atualização     |    X     |         |         |
|Configurações de convidado para Mensagens, Reuniões e Voz     |   X      |         |         |
|Teams Gerenciamento de Ciclo de Vida   |    X    |      |       |
|Teams Configurações   |    X    |      |       |
|Configurações de acesso externo     |    X    |      |       |
|Gerenciamento de usuários    |         |         |    X     |
|Audioconferência     |    X     |    X     |         |
|Planos de chamada     |    X    |    X     |         |
|Sistema de Telefonia    |    X    |     X    |         |
|Telefone gerenciamento de números     |    X    |   X      |         |
|Licenciamento para recursos de voz na nuvem     |         |         |    X     |
|Atendedores automáticos     |    X    |          |         |
|Filas de chamadas     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Gerenciar configurações após a migração

Quando a migração dessas configurações for concluída, as desabilitaremos no Centro de administração do Microsoft 365 e no centro de administração do Skype for Business e elas poderão ser gerenciadas no novo centro de administração Microsoft Teams.
