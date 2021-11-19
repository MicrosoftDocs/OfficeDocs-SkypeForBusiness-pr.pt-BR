---
title: Gerenciar o aplicativo Bookings em Microsoft Teams
author: dmaguire
ms.author: serdars
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
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Saiba como gerenciar o aplicativo Bookings em Teams para usuários em sua organização.
ms.openlocfilehash: ae471bfee1901396ee3419380fcd7620e21231fe
ms.sourcegitcommit: 5c88a07f07f9faad294d614d507e43173efc5f46
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2021
ms.locfileid: "61111971"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Gerenciar o aplicativo Bookings em Microsoft Teams

O aplicativo Bookings no Microsoft Teams oferece uma maneira simples de agendar compromissos presenciais e virtuais, como visitas médicas, consultas financeiras, entrevistas, atendimento ao cliente, horário comercial e muito mais. Para saber mais, confira [Visitas virtuais com Teams e o aplicativo Bookings.](expand-teams-across-your-org/bookings-virtual-visits.md)

Os agendadores podem gerenciar vários calendários de departamentos e de funcionários, assim como comunicações com os participantes internos e externos em uma única experiência. Os próprios compromissos virtuais são realizados Microsoft Teams reuniões, que oferecem recursos robustos de videoconferência.

> [!NOTE]
> Somente os agendadores precisam ter o aplicativo de Bookings instalado no Teams. A equipe que conduz ou participa de compromissos virtuais não precisa do aplicativo. Eles podem simplesmente ingressar em compromissos de seu calendário Outlook ou Teams ou do link de reunião Teams no email de confirmação de reserva.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Pré-requisitos para usar o aplicativo Bookings no Teams

- A caixa de correio do Exchange deve estar no Exchange Online. Não há suporte Exchange Server caixas de correio locais.

- O Microsoft Bookings deve ser ativado para a organização.

- Os usuários devem ter uma licença apropriada*. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 e Business Standard são suportados.

- Todos os usuários do aplicativo Bookings e toda a equipe que participa das reuniões devem ter uma licença que suporte Teams agendamento de reuniões.

- Seus sistemas devem atender a todos os [pré-requisitos de software e navegador ](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilidade do Bookings no Teams

O aplicativo do Microsoft Bookings para Teams está disponível na área de trabalho e na Web. Ele pode ser encontrado em [Aplicativos no Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e em **Gerenciar Aplicativos** no Teams de administração.

### <a name="control-access-to-bookings-within-your-organization"></a>Controle o acesso ao Bookings na sua organização

Há várias formas de controlar quem tem acesso ao aplicativo Bookings e aos recursos específicos do aplicativo.

Para saber como ativar ou desativar o Microsoft Bookings no Centro de administração do Microsoft 365 e como criar uma política de aplicativo do Bookings para permitir que os usuários selecionados criem calendários do Bookings, consulte Obter acesso ao [Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).

Você também pode criar uma política Teams configuração de [aplicativos para fixar o aplicativo Bookings para usuários selecionados.](teams-app-setup-policies.md)

## <a name="recommended-meeting-policy-settings"></a>Configurações de política de reunião recomendadas

Para habilitar a melhor experiência para o Bookings,  crie uma política de Teams de reunião para admitir automaticamente Todos em sua organização e atribuir a política à sua equipe. Isso permite que a equipe participe do compromisso automaticamente e habilita a experiência de lobby para participantes externos. Saiba mais sobre como admitir [automaticamente as pessoas em reuniões.](meeting-policies-participants-and-guests.md#automatically-admit-people)

## <a name="optional-staff-approvals-setting"></a>Configuração opcional de aprovação de funcionários

Como uma configuração de privacidade extra, você pode pedir que os funcionários optem por participar antes que suas informações de disponibilidade de horário sejam compartilhadas pelo Bookings e antes que eles possam agendar um compromisso.  

Para habilitar essa configuração, vá **para Centro de administração do Microsoft 365** \> **Configurações** \> **Configurações** e selecione **Bookings**.

Com essa configuração configurada, os funcionários receberão um email no qual serão solicitados a aprovar a associação a um calendário de reserva.  

Esse recurso está sendo implementado gradualmente no mundo todo para os clientes do Microsoft 365 e Office 365. Se todas as opções ainda não estão disponíveis em seu ambiente, volte em breve.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Alterar seu domínio padrão ao configurar as caixas de correio do Bookings

Ao configurar uma caixa de correio do Bookings, é usado o domínio de e-mail padrão da sua organização do Microsoft 365 ou do Office 365. Entretanto, isso pode gerar problemas ao enviar convites de reuniões aos destinatários externos; seu convite pode ser marcado como spam e movido para a pasta de lixo eletrônico do destinatário, de modo que ele talvez nunca veja seu convite.

Recomendamos que você altere o domínio padrão antes de criar sua caixa de correio do Bookings. Para obter mais informações sobre como fazer isso, consulte [Perguntas frequentes sobre domínios](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Se você tiver que alterar o domínio padrão depois que sua caixa de correio do Bookings já tiver sido criada, você pode fazê-lo com o Windows PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Para obter mais informações, consulte a documentação do Windows PowerShell quanto ao cmdlet [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Se você estiver usando uma configuração híbrida Exchange, recomendamos testar completamente o fluxo de emails entre o Exchange local e o Exchange Online ao alterar o domínio padrão.

## <a name="sending-feedback"></a>Enviar comentários

Apreciamos seus comentários em:

  - Experiência do usuário ou facilidade de uso
  - Lacunas de recursos ou funcionalidade ausente
  - Bugs ou problemas
  
Para enviar comentários, selecione o botão **Ajuda** próximo à parte inferior da barra de navegação Teams esquerda e selecione **Relatar um** problema para **todos os** problemas. Indique no início do relatório de comentários que você está enviando comentários sobre "Bookings" para que possamos identificar facilmente problemas do Bookings.

## <a name="related-articles"></a>Artigos relacionados

[Gerenciar a experiência de junção para Teams virtuais em navegadores móveis](expand-teams-across-your-org/mobile-browser-join.md)


  [Documentação do Bookings para usuários finais](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
