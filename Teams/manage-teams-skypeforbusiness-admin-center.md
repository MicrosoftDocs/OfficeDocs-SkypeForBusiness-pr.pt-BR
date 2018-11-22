---
title: Gerenciar equipes durante a transição para o novo Teams Microsoft & Skype para Business Admin Center
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Compreender como gerenciar todo o inquilino e configurações de usuário para as equipes durante a transição das equipes de experiência com o Centro de administração do Office 365 para o novo Teams Microsoft & Skype para Business Admin Center.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: b3305efee9636dfff391fc9a851227cf215b719a
ms.sourcegitcommit: e93b12f5ebaad1140d7df798b5e0647197b9213d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2018
ms.locfileid: "26649529"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>Gerenciar equipes durante a transição para o novo Teams Microsoft & Skype para Business Admin Center
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams--skype-for-business-admin-center"></a>O que é o novo Teams Microsoft & Skype para centro de administração de negócios?  

A nova experiência do Centro de administração fornecerá a você uma experiência unificada para gerenciar equipes e Skype para negócios. Oferecemos funcionalidade adicional, ideias de ponta a ponta e a capacidade de gerenciar configurações de equipes em um nível de usuário.

![Captura de tela do Skype para Business Admin Center & equipes da Microsoft.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams--skype-for-business-admin-center"></a>Configurações migradas para o novo Teams Microsoft & Skype para Business Admin Center

A tabela a seguir identifica as seções da experiência de equipes que foram migradas e mostra a relação entre as configurações atuais e as políticas no novo portal de administração.

|Seção de equipes no Centro de administração do Office 365  |Nome da configuração (nível de locatário)  |Microsoft Teams & Skype para política do Centro de administração de negócios   |Nível: Locatário ou usuário   |
|---------|---------|---------|---------|
|Geral     |Mostrar bate-papo organizacional no perfil pessoal        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  Locatário       |
|Geral     |Use Skype for Business para destinatários que não têm equipes         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Integração de e-mails     |Permitir que os usuários enviar emails a canais         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Integração de e-mails     |Permite que os remetentes lista         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |Locatário         |
|Armazenamento em nuvem personalizado     |Caixa         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Armazenamento em nuvem personalizado     |Pasta de recados        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Armazenamento em nuvem personalizado     |Unidade do Google        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Armazenamento em nuvem personalizado     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |Locatário         |
|Configurações por tipo de licença de usuário /     |Ativar o Microsoft Teams ativada ou desativada para todos os usuários          |Preteridos<sup>1</sup>        |         |
|Equipes e canais     |         |Redireciona para o Windows Azure Active Directory grupo Management (mesmo que a experiência atual).              |Usuário         |
|Equipes e canais     |         |Redireciona para gerenciamento de grupo AAD (mesmo que a experiência atual).             |Usuário          |
|Reuniões e chamadas     |Permitir o agendamento de reuniões privadas         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Reuniões e chamadas     |Permitir meetup de canal da Ad hoc         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Reuniões e chamadas     |Permitir o agendamento de reuniões de canal         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Reuniões e chamadas     |Permitir que os vídeos em reuniões         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Reuniões e chamadas     |Permitir compartilhamento em reuniões de tela         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |Usuário          |
|Reuniões e chamadas     |Permitir chamadas particulares         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |Usuário          |
|Mensagens     |Habilitar Giphy, de forma que os usuários podem adicionar gifs para conversas         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Classificação de conteúdo         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Habilitar memes que os usuários podem editar e adicionar a conversas         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Habilitar adesivos que os usuários podem editar e adicionar a conversas         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permitir que os proprietários de excluir todas as mensagens         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permitir que usuários editem suas próprias mensagens         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permitir que os usuários excluam suas próprias mensagens         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |
|Mensagens     |Permite que os usuários chat em particular         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |Usuário         |

<sup>1</sup> reduzido para o convidado. Habilitar/desabilitar convidado agora podem ser gerenciado no Microsoft Teams & Skype para Business Admin Center. Habilitar/desabilitar Teams para empresa de negócios, Edu aluno, e Corpo Docente do Edu será preterido em breve. Isso deve ser gerenciado pela atribuição de licenças no Centro de administração do Office 365. Consulte [Gerenciar o acesso de usuário às equipes da Microsoft](user-access.md).

> [!NOTE]
> Você vai continuar a usar o painel de grupos no Centro de administração do Office 365 para configuração relacionada ao equipes e canais. As configurações para aplicativos permanecerão na área de equipes do Centro de administração do Office 365 e serão migradas mais tarde. 

## <a name="manage-settings-during-the-migration"></a>Gerenciar configurações durante a migração

Você pode continuar modificar as configurações no Centro de administração do Office 365 e o Skype para centro de administração de negócios até que a migração para uma seção está concluída para o seu locatário. 

A tabela a seguir mostra onde você pode gerenciar recursos durante a migração.

|Recurso  |As equipes da Microsoft & Skype para Business Admin Center                       |Skype para o Centro de administração de negócios (herdado)  |Centro de administração do Office 365  |
|---------|:---------:|:---------:|:---------:|
|As equipes de políticas de mensagens, reuniões e eventos do Live     |     X    |         |         |
|Política de atualização de equipes     |    X     |         |         |
|Configurações de convidado para mensagens, reuniões e voz     |   X      |         |         |
|Gerenciamento do ciclo de vida de equipes   |    X    |      |       |
|Configurações de equipes   |    X    |      |       |
|Configurações de acesso externo     |    X    |      |       |
|Gerenciamento de usuário    |         |         |    X     |    
|Serviços de audioconferência     |    X     |    X     |         |
|Planos de Chamadas     |         |    X     |         |
|Sistema de Telefonia    |         |     X    |         |
|Gerenciamento de número de telefone     |         |   X      |         |
|Licenciamento para recursos de voz de nuvem     |         |         |    X     |
|Atendedores automáticos     |         |    X     |         |
|Filas de chamadas     |         |    X     |         |

## <a name="manage-settings-after-the-migration"></a>Gerenciar configurações após a migração

Quando a migração dessas configurações estiver concluída, vai desabilitamos-los no Centro de administração do Office 365 e o Skype para centro de administração de negócios e, em seguida, podem ser gerenciadas no novo Teams Microsoft & Skype para Business Admin Center.


