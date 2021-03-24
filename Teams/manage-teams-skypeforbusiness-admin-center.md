---
title: Gerenciar a transição do Teams para o novo centro de administração do Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Saiba como gerenciar configurações de locatários e usuários para o Teams durante a transição do Teams no centro de administração do Microsoft 365 para o novo centro de administração do Teams.
localization_priority: Normal
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
ms.openlocfilehash: 875db7be64e23b32f5f758f9f5a701199c068528
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100897"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Gerenciar equipes durante a transição para o novo centro de administração do Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Qual é o novo centro de administração do Microsoft Teams  

A nova experiência do centro de administração fornecerá uma experiência unificada para gerenciar o Teams e o Skype for Business. Estamos fornecendo funcionalidade adicional, informações de ponta a ponta e a capacidade de gerenciar as configurações do Teams em um nível de usuário.

![Captura de tela do centro de administração do Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Configurações migradas para o novo centro de administração do Microsoft Teams

A tabela a seguir identifica as seções da experiência do Teams que foram migradas e mostra a relação entre as configurações atuais e as políticas no novo portal de administração.

|Seção do Teams no Centro de administração do Microsoft 365  |Nome da configuração (nível de locatário)  |Política do centro de administração do Microsoft Teams   |Nível: Locatário ou Usuário   |
|---------|---------|---------|---------|
|Geral     |Mostrar gráfico organizacional no perfil pessoal        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Locatário       |
|Geral     |Usar o Skype for Business para destinatários que não têm o Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Integração de email     |Permitir que os usuários enviem emails para canais         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Integração de email     |Permitir lista de envios         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Locatário         |
|Armazenamento em nuvem personalizado     |Box         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Armazenamento em nuvem personalizado     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Armazenamento em nuvem personalizado     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Armazenamento em nuvem personalizado     |Google Drive        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Armazenamento em nuvem personalizado     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Configurações por tipo de usuário/licença     |Ativar ou desativar o Microsoft Teams para todos os usuários          |Preterido<sup>1</sup>        |         |
|Equipes e canais     |         |Redireciona para o Azure Active Directory Group Management (mesmo que a experiência atual).              |Usuário         |
|Equipes e canais     |         |Redireciona para o Gerenciamento de Grupo do AAD (mesmo que a experiência atual).             |Usuário          |
|Aplicativos|Habilitar novos aplicativos externos por padrão|Configurações de aplicativos em toda a organização|Locatário|
|Aplicativos|Permitir aplicativos externos|Configurações de aplicativos em toda a organização|Locatário|
|Aplicativos|Permitir sideload de aplicativos<sup>externos 2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Usuário|
|Aplicativos|Aplicativos<sup>padrão 3</sup>|TeamsAppPermissionPolicy|Usuário|
|Aplicativos|Aplicativos<sup>externos 3</sup>|TeamsAppPermissionPolicy|Usuário|
|Chamadas e reuniões     |Permitir o agendamento de reuniões privadas         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e reuniões     |Permitir reunião de canal ad hoc         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e reuniões     |Permitir o agendamento de reuniões de canal         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e reuniões     |Permitir vídeos em reuniões         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e reuniões     |Permitir compartilhamento de tela em reuniões         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e reuniões     |Permitir chamada privada         |[TeamsCallingPolicy ](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Usuário          |
|Mensagens     |Habilitar Giphy para que os usuários possam adicionar GIFs a conversas         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Classificação de conteúdo         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Habilitar memes que os usuários podem editar e adicionar a conversas         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Habilitar adesivos que os usuários podem editar e adicionar a conversas         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permitir que os proprietários excluam todas as mensagens         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permitir que os usuários editem suas próprias mensagens         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permitir que os usuários excluam suas próprias mensagens         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permite que os usuários conversem em particular         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |

<sup>1</sup> Preterido para Convidado. A habilitação/desabilitação do Convidado agora pode ser gerenciada no centro de administração do Microsoft Teams. Habilitando/desabilitando o Teams for Business Enterprise, o Aluno Edu e o Edu Faculty serão preterido em breve. Isso deve ser gerenciado atribuindo licenças no Centro de administração do Microsoft 365. Consulte [Gerenciar o acesso do usuário ao Microsoft Teams](user-access.md).
<br><br>
<sup>2</sup> Sideloading é dividido da seguinte forma:

- Permitir que um usuário sideload de aplicativos que podem ser gerenciados em um nível de usuário no [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps).
- Permitir que os usuários em um locatário interajam com aplicativos personalizados que podem ser gerenciados em um nível de locatário em configurações de aplicativos em toda a organização.

<sup>3</sup> Aplicativos padrão e aplicativos externos podem ser habilitados e desabilitados no nível do usuário no TeamsAppPermissionPolicy. Além disso, os aplicativos podem ser bloqueados no nível do locatário em configurações de aplicativos em toda a organização que substituem qualquer configuração de usuário e de nível de locatário.

> [!NOTE]
> Você continuará a usar o painel Grupos no Centro de administração do Microsoft 365 para configuração relacionada ao Teams e canais. As configurações para Aplicativos permanecerão na área do Teams do Centro de administração do Microsoft 365 e serão migradas posteriormente.

## <a name="manage-settings-during-the-migration"></a>Gerenciar configurações durante a migração

Você pode continuar a modificar configurações no Centro de administração do Microsoft 365 e no Centro de administração do Skype for Business até que a migração de uma seção seja concluída para o locatário.

A tabela a seguir mostra onde você pode gerenciar recursos durante a migração.

|Recurso  |Centro de administração do Microsoft Teams                      |Centro de administração do Skype for Business (herdada)  |Centro de administração do Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Políticas de mensagens, reuniões e eventos ao vivo do Teams     |     X    |         |         |
|Política de atualização do Teams     |    X     |         |         |
|Configurações de convidado para Mensagens, Reuniões e Voz     |   X      |         |         |
|Gerenciamento do Ciclo de Vida do Teams   |    X    |      |       |
|Configurações do Teams   |    X    |      |       |
|Configurações de acesso externo     |    X    |      |       |
|Gerenciamento de usuários    |         |         |    X     |
|Audioconferência     |    X     |    X     |         |
|Planos de chamada     |    X    |    X     |         |
|Sistema de Telefonia    |    X    |     X    |         |
|Gerenciamento de números de telefone     |    X    |   X      |         |
|Licenciamento para recursos de voz na nuvem     |         |         |    X     |
|Atendedores automáticos     |    X    |          |         |
|Filas de chamadas     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Gerenciar configurações após a migração

Quando a migração dessas configurações for concluída, as desabilitaremos no centro de administração do Microsoft 365 e no Centro de administração do Skype for Business e elas poderão ser gerenciadas no novo centro de administração do Microsoft Teams.