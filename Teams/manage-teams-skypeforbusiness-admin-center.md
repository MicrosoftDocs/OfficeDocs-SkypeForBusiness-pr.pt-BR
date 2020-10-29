---
title: Gerenciar equipes em transição para o novo centro de administração do teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Saiba como gerenciar as configurações de todos os locatários e usuários para equipes durante a transição do teams no centro de administração do Microsoft 365 para o novo centro de administração do teams.
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
ms.openlocfilehash: ee63c3d49a8c4b4bf047f0df3910bec39a4d5541
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790413"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Gerenciar equipes durante a transição para o novo centro de administração do Microsoft Teams
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>O que é o novo centro de administração do Microsoft Teams  

A nova experiência com o centro de administração fornecerá uma experiência unificada para gerenciar tanto o Microsoft Teams quanto o Skype for Business. Estamos fornecendo funcionalidade adicional, ideias completas e a capacidade de gerenciar as configurações do teams em um nível de usuário.

![Captura de tela do centro de administração do Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Configurações migradas para o novo centro de administração do Microsoft Teams

A tabela a seguir identifica as seções da experiência do teams que foram migradas e mostra a relação entre as configurações atuais e as políticas no novo portal de administração.

|Seção do teams no centro de administração do Microsoft 365  |Nome da configuração (nível do locatário)  |Política do centro de administração do Microsoft Teams   |Nível: locatário ou usuário   |
|---------|---------|---------|---------|
|Geral     |Mostrar gráfico organizacional no perfil pessoal        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Locatário       |
|Geral     |Usar o Skype for Business para destinatários que não têm equipes         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Integração de email     |Permitir que os usuários enviem emails a canais         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Integração de email     |Permitir lista de remetentes         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Locatário         |
|Armazenamento em nuvem personalizado     |Caixas         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Armazenamento em nuvem personalizado     |Dropbox        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Armazenamento em nuvem personalizado     |Egnyte        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Armazenamento em nuvem personalizado     |Google Drive        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Armazenamento em nuvem personalizado     |Sharefile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Configurações por tipo de usuário/licença     |Ativar ou desativar o Microsoft Teams para todos os usuários          |Substituído<sup>1</sup>        |         |
|Equipes e canais     |         |Redireciona para o gerenciamento de grupos do Active Directory do Azure (mesmo que a experiência atual).              |Usuário         |
|Equipes e canais     |         |Redireciona para o gerenciamento de grupos AAD (mesmo que a experiência atual).             |Usuário          |
|Aplicativos|Habilitar novos aplicativos externos por padrão|Configurações do aplicativo de toda a organização|Locatário|
|Aplicativos|Permitir aplicativos externos|Configurações do aplicativo de toda a organização|Locatário|
|Aplicativos|Permitir Sideload de aplicativos externos<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Usuário|
|Aplicativos|Aplicativos padrão<sup>3</sup>|TeamsAppPermissionPolicy|Usuário|
|Aplicativos|Aplicativos externos<sup>3</sup>|TeamsAppPermissionPolicy|Usuário|
|Chamadas e reuniões     |Permitir o agendamento de reuniões privadas         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e reuniões     |Permitir o canal ad-hoc Meetup         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e reuniões     |Permitir o agendamento de reuniões de canal         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e reuniões     |Permitir vídeos em reuniões         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e reuniões     |Permitir o compartilhamento de tela em reuniões         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e reuniões     |Permitir chamadas privadas         |[TeamsCallingPolicy ](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Usuário          |
|Mensagens     |Habilite o Giphy para que os usuários possam adicionar GIFs a conversas         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Classificação de conteúdo         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Habilite o memes que os usuários podem editar e adicionar às conversas         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Habilitar adesivos que os usuários podem editar e adicionar às conversas         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permitir que os proprietários excluam todas as mensagens         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permitir que os usuários editem suas próprias mensagens         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permitir que os usuários excluam suas próprias mensagens         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permite que os usuários conversem de forma privada         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |

<sup>1</sup> substituído por convidado. Habilitar/desabilitar o convidado agora pode ser gerenciado no centro de administração do Microsoft Teams. Habilitar/desabilitar Teams for Business Enterprise, aluno edu e docentes edu serão preteridos em breve. Isso deve ser gerenciado por meio da atribuição de licenças no centro de administração do Microsoft 365. Consulte [gerenciar o acesso do usuário ao Microsoft Teams](user-access.md).
<br><br>
<sup>2</sup> o Sideload é dividido da seguinte maneira:

- Permitir que um usuário Sideload aplicativos que podem ser gerenciados em um nível de usuário no [TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps).
- Permita que os usuários de um locatário interajam com aplicativos personalizados que podem ser gerenciados em um nível de locatário em configurações de aplicativo de toda a organização.

<sup>3</sup> aplicativos padrão e aplicativos externos podem ser habilitados e desabilitados no nível do usuário no TeamsAppPermissionPolicy. Além disso, os aplicativos podem ser bloqueados no nível do locatário em configurações de aplicativo de toda a organização, que substitui todas as configurações do usuário e do nível do locatário.

> [!NOTE]
> Você continuará a usar o painel de grupos no centro de administração do Microsoft 365 para obter a configuração relacionada a equipes e canais. As configurações para aplicativos permanecerão na área Teams do centro de administração do Microsoft 365 e serão migradas mais tarde.

## <a name="manage-settings-during-the-migration"></a>Gerenciar configurações durante a migração

Você pode continuar modificando as configurações no centro de administração do Microsoft 365 e no centro de administração do Skype for Business até que a migração de uma seção seja concluída para o seu locatário.

A tabela a seguir mostra onde você pode gerenciar recursos durante a migração.

|Recurso  |Centro de administração do Microsoft Teams                      |Centro de administração do Skype for Business (Herdado)  |Centro de administração do Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Políticas de mensagens, reuniões e eventos dinâmicos do teams     |     X    |         |         |
|Política de atualização de equipes     |    X     |         |         |
|Configurações de convidado para mensagens, reuniões e voz     |   X      |         |         |
|Gerenciamento do ciclo de vida do teams   |    X    |      |       |
|Configurações do teams   |    X    |      |       |
|Configurações de acesso externo     |    X    |      |       |
|Gerenciamento de usuários    |         |         |    X     |
|Audioconferência     |    X     |    X     |         |
|Planos de chamada     |    X    |    X     |         |
|Sistema de Telefonia    |    X    |     X    |         |
|Gerenciamento de número de telefone     |    X    |   X      |         |
|Licenciamento para recursos de voz na nuvem     |         |         |    X     |
|Atendedores automáticos     |    X    |          |         |
|Filas de chamadas     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Gerenciar as configurações após a migração

Quando a migração dessas configurações for concluída, desabilitá-las no centro de administração do Microsoft 365 e no centro de administração do Skype for Business, e elas poderão ser gerenciadas no novo centro de administração do Microsoft Teams.
