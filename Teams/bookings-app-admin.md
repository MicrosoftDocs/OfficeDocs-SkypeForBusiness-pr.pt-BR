---
title: Visitas virtuais com o Microsoft Teams e o aplicativo de reservas
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Microsoft Teams e visitas virtuais com o aplicativo bookings
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125744"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visitas virtuais com o Microsoft Teams e o aplicativo de reservas

O aplicativo de reservas do Microsoft Teams oferece uma maneira simples de agendar compromissos presenciais e virtuais, como visitas à saúde, consultas financeiras, entrevistas, suporte ao cliente, treinamento de horas de escritório e muito mais.

Os agendadores podem gerenciar vários calendários de departamentos e funcionários, bem como comunicações com participantes internos e externos, a partir de uma única experiência. Os compromissos virtuais propriamente ditos são mantidos por meio das reuniões do Microsoft Teams, o que oferece recursos robustos de videoconferência.

> [!NOTE]
> Somente agendadores precisam ter o aplicativo bookings instalado no Teams. A condução da equipe ou a participação em compromissos virtuais não precisam do aplicativo. Eles podem simplesmente participar de compromissos do calendário do Outlook ou do teams ou de um link no e-mail de confirmação de reservas.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Pré-requisitos para usar o aplicativo reservas no Teams

- A caixa de correio do Exchange deve estar no Exchange Online. Não há suporte para as caixas de correio do Exchange Server locais.

- O Microsoft bookings deve estar ativado para a organização.

- Os usuários devem ter uma licença adequada. O Office 365 a3, a5, E3 e e5, bem como o Microsoft 365 Business Standard, a3, a5, E3 e E5 são suportados.

- Todos os usuários do aplicativo reservas e todas as equipes participantes de reuniões devem ter uma licença que dê suporte ao agendamento de reunião de equipe.

- Seus sistemas devem atender todos os [pré-requisitos do software e do navegador](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilidade de reservas no Microsoft Teams

O aplicativo Microsoft bookings para Teams está disponível na área de trabalho e na Web. Ele pode ser encontrado em [aplicativos no Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e em **gerenciar aplicativos** no centro de administração do teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Controlar o acesso a reservas em sua organização

Há várias maneiras de controlar quem tem acesso ao aplicativo de reservas e a recursos específicos do aplicativo. Para saber como ativar ou desativar o Microsoft bookings no centro de administração do Microsoft 365, bem como criar uma política de aplicativo de livros para permitir que os usuários selecionados criem calendários de livros, consulte [obter acesso a Microsoft bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce). Você também pode aprender a [criar uma política do aplicativo Teams para fixar o aplicativo de reservas para usuários selecionados](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Configurações de política de reunião recomendadas

Para habilitar a melhor experiência para reservas, crie uma política de reunião de equipe para admitir automaticamente **todos em sua organização**. Isso permitirá que a equipe ingresse no compromisso automaticamente e habilite a experiência de lobby para participantes externos. Você pode saber mais sobre como [admitting automaticamente as pessoas para reuniões](meeting-policies-in-teams.md#automatically-admit-people).

### <a name="optional-staff-approvals-setting"></a>Configuração de aprovações de equipe opcionais

Como uma configuração de privacidade adicional, você pode optar por exigir que a equipe opte antes de as informações de disponibilidade do cronograma sejam compartilhadas por meio de reservas e antes de serem reservadas para um compromisso.  

Para habilitar essa configuração, vá para configurações de configurações **do centro de administração do Microsoft 365** \>  \> e, em seguida, selecione **reservas**.

Com essa configuração ativada, a equipe receberá um email em que será solicitado a aprovar a associação a um calendário de reservas.  

Esse recurso está gradualmente sendo implantado em todo o mundo para os clientes do Microsoft 365 e do Office 365. Se todas as opções ainda não estiverem disponíveis no seu ambiente, verifique novamente em breve.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Alterar seu domínio padrão ao configurar as caixas de correio de livros

Ao configurar uma caixa de correio de livro, é usado o domínio de email padrão da sua organização do Microsoft 365 ou do Office 365. No entanto, isso pode causar problemas ao enviar convites de reunião para destinatários externos; seu convite pode ser sinalizado como spam e movido para a pasta lixo eletrônico do destinatário, para que o destinatário nunca veja seu convite.

Recomendamos que você altere o domínio padrão antes de criar sua caixa de correio de livros. Para saber mais sobre como fazer isso, Confira as [perguntas frequentes sobre domínios](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Se você precisar alterar o domínio padrão após a criação de uma caixa de correio de livros, você pode fazer isso com o PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Para obter mais informações, consulte a documentação do PowerShell para o cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Se você estiver usando uma configuração híbrida do Exchange, recomendamos que teste exaustivamente o fluxo de email entre o Exchange local e o Exchange Online ao alterar o domínio padrão.

## <a name="sending-feedback"></a>Enviar comentários

Agradecemos seus comentários sobre:

  - Experiência do usuário ou facilidade de uso
  - Lacunas de recursos ou funcionalidade ausente
  - Erros ou problemas
  
Para enviar comentários, clique no botão **ajuda** próximo à parte inferior da barra de navegação do teams à esquerda e, em seguida, clique em **relatar um problema** para **todos os** problemas. Observe o início do seu relatório de comentários que você está enviando comentários sobre "reservas" para que possamos identificar facilmente os problemas relacionados a reservas.

## <a name="related-topics"></a>Tópicos relacionados

[Documentação de livros para usuários finais](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
