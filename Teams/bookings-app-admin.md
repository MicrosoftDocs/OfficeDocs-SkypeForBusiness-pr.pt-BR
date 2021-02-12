---
title: Visitas virtuais com o Microsoft Teams e o aplicativo Bookings
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
description: Microsoft Teams e visitas virtuais com o aplicativo Bookings
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125744"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visitas virtuais com o Microsoft Teams e o aplicativo Bookings

O aplicativo Bookings no Microsoft Teams oferece uma maneira simples de agendar compromissos presenciais e virtuais, como consultas médicas, consultas financeiras, entrevistas, suporte ao cliente, horários de escritório de educação e muito mais.

Os agendadores podem gerenciar vários calendários de departamentos e funcionários, bem como comunicações com participantes internos e externos, a partir de uma única experiência. Os próprios compromissos virtuais são realizados por meio de Reuniões do Microsoft Teams, que oferece recursos robustos de videoconferência.

> [!NOTE]
> Somente agendadores precisam ter o aplicativo Bookings instalado no Teams. A equipe que conduz ou participa de compromissos virtuais não precisa do aplicativo. Eles podem simplesmente ingressar em compromissos no calendário do Outlook ou do Teams ou em um link no email de confirmação de reserva.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Pré-requisitos para usar o aplicativo Bookings no Teams

- A caixa de correio do Exchange deve estar no Exchange Online. Não há suporte para caixas de correio locais do Exchange Server.

- O Microsoft Bookings deve ser ligado para a organização.

- Os usuários devem ter uma licença apropriada. Há suporte para o Office 365 A3, A5, E3 e E5, além do Microsoft 365 Business Standard, A3, A5, E3 e E5.

- Todos os usuários do aplicativo Bookings e todos os funcionários participantes das reuniões devem ter uma licença compatível com o agendamento de Reunião do Teams.

- Seus sistemas devem atender a todos os [pré-requisitos de Software](hardware-requirements-for-the-teams-app.md)e navegador.

## <a name="availability-of-bookings-in-teams"></a>Disponibilidade do Bookings no Teams

O aplicativo Microsoft Bookings para Teams está disponível na área de trabalho e na Web. Ele pode ser encontrado em [Aplicativos no Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e em **Gerenciar Aplicativos** no Centro de Administração do Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Controlar o acesso ao Bookings em sua organização

Há várias maneiras de controlar quem tem acesso ao aplicativo Bookings e a recursos específicos do aplicativo. Para saber como ativar ou desativar o Microsoft Bookings no Centro de administração do Microsoft 365, bem como criar uma política de aplicativo do Bookings para permitir que os usuários selecionados criem calendários do Bookings, consulte Obter acesso ao [Microsoft Bookings.](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce) Você também pode aprender a criar uma política de [aplicativo do Teams para fixar o aplicativo Bookings para usuários selecionados.](teams-app-setup-policies.md)

## <a name="recommended-meeting-policy-settings"></a>Configurações de Política de Reunião Recomendadas

Para habilitar a melhor experiência para o Bookings, crie uma política de reunião de equipe para admitir automaticamente **Todos em sua organização.** Isso permitirá que os funcionários insuem o compromisso automaticamente e habilitam a experiência de lobby para participantes externos. Você pode saber mais sobre como [automaticamente enviar pessoas às reuniões.](meeting-policies-in-teams.md#automatically-admit-people)

### <a name="optional-staff-approvals-setting"></a>Configuração opcional de aprovações de funcionários

Como uma configuração de privacidade extra, você pode optar por exigir que os funcionários optem por participar antes que suas informações de disponibilidade do cronograma sejam compartilhadas por meio do Bookings e antes que eles possam ser reservados para um compromisso.  

Para habilitar essa configuração, vá para Configurações do Centro de administração do **Microsoft 365** \>  \> e selecione **Bookings.**

Com essa configuração configurada, os funcionários receberão um email no qual serão solicitados a aprovar a associação a um calendário de reserva.  

Este recurso está sendo gradualmente lançado em todo o mundo para clientes do Microsoft 365 e do Office 365. Se todas as opções ainda não estão disponíveis em seu ambiente, verifique novamente em breve.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Alterando seu domínio padrão ao configurar caixas de correio do Bookings

Ao configurar uma caixa de correio do Bookings, o domínio de email padrão da sua organização do Microsoft 365 ou do Office 365 é usado. No entanto, isso pode causar problemas ao enviar convites de reunião para destinatários externos; seu convite pode ser sinalizado como spam e movido para a pasta lixo eletrônico do destinatário, para que o destinatário nunca veja seu convite.

Recomendamos que você altere o domínio padrão antes de criar sua caixa de correio do Bookings. Para obter informações sobre como fazer isso, consulte as [perguntas frequentes sobre Domínios.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)

Se você precisar alterar o domínio padrão depois que sua caixa de correio do Bookings já tiver sido criada, você poderá fazer isso com o PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Para obter mais informações, consulte a documentação do PowerShell para o cmdlet [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)

> [!NOTE]
> Se você estiver usando uma configuração híbrida do Exchange, recomendamos que você teste completamente o fluxo de emails entre o Exchange local e o Exchange Online ao alterar o domínio padrão.

## <a name="sending-feedback"></a>Enviar comentários

Seus comentários são bem-vindos sobre:

  - Experiência do usuário ou facilidade de uso
  - Lacunas de recursos ou funcionalidade ausente
  - Bugs ou problemas
  
Para enviar comentários, clique no **botão Ajuda** próximo à parte inferior da barra de navegação esquerda do Teams e clique em Relatar um **Problema para** TODOS **os** problemas. Observe no início do seu relatório de comentários que você está enviando comentários sobre o "Bookings" para que possamos identificar facilmente os problemas do Bookings.

## <a name="related-topics"></a>Tópicos relacionados

[Documentação do Bookings para usuários finais](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
