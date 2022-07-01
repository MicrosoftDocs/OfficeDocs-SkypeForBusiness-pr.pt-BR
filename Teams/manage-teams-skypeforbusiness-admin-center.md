---
title: Gerenciar a transição do Teams para o novo centro de administração do Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como gerenciar configurações de usuário e de locatário para o Teams durante a transição do Teams no Centro de administração do Microsoft 365 para o novo centro de administração do Teams.
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
ms.openlocfilehash: 39566c490a5de37adc699c39c049717525bd5821
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563949"
---
# <a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>Gerenciar equipes durante a transição para o novo centro de administração do Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>Qual é o novo centro de administração do Microsoft Teams  

A nova experiência do centro de administração fornecerá uma experiência unificada para gerenciar o Teams e o Skype for Business. Estamos fornecendo funcionalidade adicional, insights de ponta a ponta e a capacidade de gerenciar as configurações do Teams em um nível de usuário.

![Captura de tela do centro de administração do Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Configurações migradas para o novo centro de administração do Microsoft Teams

A tabela a seguir identifica as seções da experiência do Teams que foram migradas e mostra a relação entre as configurações atuais e as políticas no novo portal de administração.

|Seção do Teams no Centro de administração do Microsoft 365  |Nome da configuração (nível de locatário)  |Política do Centro de administração do Microsoft Teams   |Nível: Locatário ou Usuário   |
|---------|---------|---------|---------|
|Geral     |Mostrar organograma no perfil pessoal        |  [TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)       |  Inquilino       |
|Geral     |Use Skype for Business para destinatários que não têm o Teams         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Integração de email     |Permitir que os usuários enviem emails para canais         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Integração de email     |Permitir lista de remetentes         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)        |Inquilino         |
|Armazenamento em nuvem personalizado     |Caixa         |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Armazenamento em nuvem personalizado     |Dropbox        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Armazenamento em nuvem personalizado     |Egnyte        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Armazenamento em nuvem personalizado     |Google Drive        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Armazenamento em nuvem personalizado     |ShareFile        |[TeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration)         |Inquilino         |
|Configurações por tipo de usuário/licença     |Ativar ou desativar o Microsoft Teams para todos os usuários          |Preterido<sup>1</sup>        |         |
|Equipes e canais     |         |Redireciona para o Gerenciamento de Grupos do Azure Active Directory (o mesmo que a experiência atual).              |Usuário         |
|Equipes e canais     |         |Redireciona para o Gerenciamento de Grupos do AAD (o mesmo que a experiência atual).             |Usuário          |
|Aplicativos|Habilitar novos aplicativos externos por padrão|Configurações de aplicativo em toda a organização|Inquilino|
|Aplicativos|Permitir aplicativos externos|Configurações de aplicativo em toda a organização|Inquilino|
|Aplicativos|Permitir sideload de aplicativos externos<sup>2</sup>|[TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy)|Usuário|
|Aplicativos|Aplicativos padrão<sup>3</sup>|TeamsAppPermissionPolicy|Usuário|
|Aplicativos|Aplicativos externos<sup>3</sup>|TeamsAppPermissionPolicy|Usuário|
|Chamadas e reuniões     |Permitir o agendamento de reuniões privadas         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuário          |
|Chamadas e reuniões     |Permitir reunião de canal ad hoc         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuário          |
|Chamadas e reuniões     |Permitir o agendamento de reuniões de canal         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuário          |
|Chamadas e reuniões     |Permitir vídeos em reuniões         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuário          |
|Chamadas e reuniões     |Permitir compartilhamento de tela em reuniões         |[TeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)         |Usuário          |
|Chamadas e reuniões     |Permitir chamada privada         |[TeamsCallingPolicy ](/powershell/module/skype/set-csteamscallingpolicy)        |Usuário          |
|Mensagens     |Habilitar o Giphy para que os usuários possam adicionar GIFs a conversas         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |
|Mensagens     |Classificação de conteúdo         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |
|Mensagens     |Habilitar memes que os usuários podem editar e adicionar a conversas         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |
|Mensagens     |Habilitar adesivos que os usuários podem editar e adicionar a conversas         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |
|Mensagens     |Permitir que os proprietários excluam todas as mensagens         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |
|Mensagens     |Permitir que os usuários editem suas próprias mensagens         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |
|Mensagens     |Permitir que os usuários excluam suas próprias mensagens         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |
|Mensagens     |Permite que os usuários conversem em particular         |[TeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy)         |Usuário         |

<sup>1</sup> Preterido para Convidado. Habilitar/desabilitar o Convidado agora pode ser gerenciado no centro de administração do Microsoft Teams. A habilitação/desabilitação do Teams for Business Enterprise, Edu Student e Edu Faculty será preterida em breve. Isso deve ser gerenciado atribuindo licenças no Centro de administração do Microsoft 365. Consulte [Gerenciar o acesso do usuário ao Microsoft Teams](user-access.md).
<br><br>
<sup>2</sup> O sideload é dividido da seguinte maneira:

- Permitir que um usuário realizar sideload de aplicativos que podem ser gerenciados em um nível de usuário no [TeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy).
- Permitir que os usuários em um locatário interajam com aplicativos personalizados que podem ser gerenciados em um nível de locatário nas configurações de aplicativo em toda a organização.

<sup>3 Aplicativos</sup> padrão e aplicativos externos podem ser habilitados e desabilitados no nível do usuário no TeamsAppPermissionPolicy. Além disso, os aplicativos podem ser bloqueados no nível do locatário nas configurações de aplicativo em toda a organização, o que substitui as configurações no nível do usuário e do locatário.

> [!NOTE]
> Você continuará a usar o painel Grupos no Centro de administração do Microsoft 365 para configuração relacionada ao Teams e aos canais. As configurações de Aplicativos permanecerão na área do Teams do Centro de administração do Microsoft 365 e serão migradas posteriormente.

## <a name="manage-settings-during-the-migration"></a>Gerenciar configurações durante a migração

Você pode continuar a modificar as configurações no Centro de administração do Microsoft 365 e no centro de administração do Skype for Business até que a migração para uma seção seja concluída para seu locatário.

A tabela a seguir mostra onde você pode gerenciar recursos durante a migração.

|Recurso  |Centro de administração do Microsoft Teams                      |Skype for Business de administração (herdado)  |Centro de administração do Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Políticas de Mensagens, Reuniões e Eventos ao Vivo do Teams     |     X    |         |         |
|Política de atualização do Teams     |    X     |         |         |
|Configurações de convidado para Mensagens, Reuniões e Voz     |   X      |         |         |
|Gerenciamento do ciclo de vida do Teams   |    X    |      |       |
|Configurações do Teams   |    X    |      |       |
|Configurações de acesso externo     |    X    |      |       |
|Gerenciamento de usuários    |         |         |    X     |
|Audioconferência     |    X     |    X     |         |
|Planos de chamadas     |    X    |    X     |         |
|Sistema de Telefonia    |    X    |     X    |         |
|Gerenciamento de números de telefone     |    X    |   X      |         |
|Licenciamento para recursos de voz na nuvem     |         |         |    X     |
|Atendedores automáticos     |    X    |          |         |
|Filas de chamadas     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>Gerenciar configurações após a migração

Quando a migração dessas configurações for concluída, as desabilitaremos no Centro de administração do Microsoft 365 e no centro de administração do Skype for Business e, em seguida, elas poderão ser gerenciadas no novo centro de administração do Microsoft Teams.
