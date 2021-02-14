---
title: Gerenciar a transição do Teams para o novo Centro de administração do Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Saiba como gerenciar as configurações de usuário e locatário do Teams durante a transição do Teams no Centro de administração do Microsoft 365 para o novo centro de administração do Teams.
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

A nova experiência do centro de administração fornecerá uma experiência unificada para gerenciar o Teams e o Skype for Business. Estamos fornecendo funcionalidade adicional, informações de ponta a ponta e a capacidade de gerenciar as configurações do Teams em um nível de usuário.

![Captura de tela do Centro de administração do Microsoft Teams.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>Configurações migradas para o novo centro de administração do Microsoft Teams

A tabela a seguir identifica as seções da experiência do Teams que foram migradas e mostra a relação entre as configurações atuais e as políticas no novo portal de administração.

|Seção do Teams no Centro de administração do Microsoft 365  |Nome da configuração (nível do locatário)  |Política do centro de administração do Microsoft Teams   |Nível: Locatário ou Usuário   |
|---------|---------|---------|---------|
|Geral     |Mostrar organograma em perfil pessoal        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Inquilino       |
|Geral     |Usar o Skype for Business para destinatários que não têm o Teams         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Integração de email     |Permitir que os usuários enviem emails para canais         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Integração de email     |Permitir lista de contatos         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Inquilino         |
|Armazenamento em nuvem personalizado     |Caixa         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Armazenamento em nuvem personalizado     |Dropbox        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Armazenamento em nuvem personalizado     |Egnyte        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Armazenamento em nuvem personalizado     |Google Drive        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Armazenamento em nuvem personalizado     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Inquilino         |
|Configurações por tipo de usuário/licença     |Ativar ou desativar o Microsoft Teams para todos os usuários          |Preterido<sup>1</sup>        |         |
|Equipes e canais     |         |Redireciona para o Gerenciamento de Grupo do Azure Active Directory (mesmo que a experiência atual).              |Usuário         |
|Equipes e canais     |         |Redireciona para o Gerenciamento de Grupo do AAD (mesmo que a experiência atual).             |Usuário          |
|Aplicativos|Habilitar novos aplicativos externos por padrão|Configurações de aplicativos para toda a organização|Inquilino|
|Aplicativos|Permitir aplicativos externos|Configurações de aplicativos para toda a organização|Inquilino|
|Aplicativos|Permitir o sideload de aplicativos<sup>externos 2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|Usuário|
|Aplicativos|Aplicativos<sup>padrão 3</sup>|TeamsAppPermissionPolicy|Usuário|
|Aplicativos|Aplicativos<sup>externos 3</sup>|TeamsAppPermissionPolicy|Usuário|
|Chamadas e Reuniões     |Permitir o agendamento de reuniões privadas         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e Reuniões     |Permitir reunião de canal Ad-hoc         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e Reuniões     |Permitir o agendamento de reuniões de canal         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e Reuniões     |Permitir vídeos em reuniões         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e Reuniões     |Permitir o compartilhamento de tela em reuniões         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Chamadas e Reuniões     |Permitir chamada privada         |[TeamsCallingPolicy ](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Usuário          |
|Mensagens     |Habilitar Giphy para que os usuários possam adicionar GIFs a conversas         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Classificação de conteúdo         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Habilitar memes que os usuários podem editar e adicionar às conversas         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Habilitar adesivos que os usuários podem editar e adicionar às conversas         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permitir que os proprietários excluam todas as mensagens         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permitir que os usuários editem suas próprias mensagens         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permitir que os usuários excluam suas próprias mensagens         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permite que os usuários conversem em particular         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |

<sup>1</sup> Preterido para Convidado. A habilitação/desabilitação de Convidado agora pode ser gerenciada no Centro de administração do Microsoft Teams. A habilitação/desabilitação do Teams for Business Enterprise, do Edu Student e do Edu Faculty será preterida em breve. Isso deve ser gerenciado atribuindo licenças no Centro de administração do Microsoft 365. Consulte [Gerenciar o acesso do usuário ao Microsoft Teams.](user-access.md)
<br><br>
<sup>2</sup> O sideload é dividido da seguinte forma:

- Permitir que um usuário desempaque aplicativos que podem ser gerenciados em um nível de usuário no [TeamsAppSetupPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)
- Permita que os usuários em um locatário interajam com aplicativos personalizados que podem ser gerenciados em um nível de locatário nas configurações de aplicativos de toda a organização.

<sup>3</sup> Aplicativos padrão e aplicativos externos podem ser habilitados e desabilitados no nível do usuário no TeamsAppPermissionPolicy. Além disso, os aplicativos podem ser bloqueados no nível do locatário nas configurações de aplicativos em toda a organização, o que substitui as configurações do usuário e do locatário.

> [!NOTE]
> Você continuará a usar o painel Grupos no Centro de administração do Microsoft 365 para configurações relacionadas ao Teams e aos canais. As configurações de Aplicativos permanecerão na área do Teams do Centro de administração do Microsoft 365 e serão migradas mais tarde.

## <a name="manage-settings-during-the-migration"></a>Gerenciar configurações durante a migração

Você pode continuar modificando as configurações no Centro de administração do Microsoft 365 e no Centro de administração do Skype for Business até que a migração de uma seção seja concluída para seu locatário.

A tabela a seguir mostra onde você pode gerenciar recursos durante a migração.

|Recurso  |Centro de administração do Microsoft Teams                      |Centro de administração do Skype for Business (herdada)  |Centro de administração do Microsoft 365  |
|---------|:---------:|:---------:|:---------:|
|Políticas de mensagens, reuniões e eventos ao vivo do Teams     |     X    |         |         |
|Política de atualização do Teams     |    X     |         |         |
|Configurações de convidado para Mensagens, Reuniões e Voz     |   X      |         |         |
|Gerenciamento de ciclo de vida do Teams   |    X    |      |       |
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

Quando a migração dessas configurações estiver concluída, as desabilitaremos no Centro de administração do Microsoft 365 e no Centro de administração do Skype for Business, e elas poderão ser gerenciadas no novo centro de administração do Microsoft Teams.
