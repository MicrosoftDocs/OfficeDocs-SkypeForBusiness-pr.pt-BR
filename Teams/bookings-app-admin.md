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
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Saiba como gerenciar o aplicativo Bookings no Teams para usuários em sua organização.
ms.openlocfilehash: 692cf8500b47d903986542082c328b4a8be2237d
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2022
ms.locfileid: "63050907"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Gerenciar o aplicativo Bookings em Microsoft Teams

O aplicativo Bookings no Microsoft Teams oferece uma maneira simples de agendar compromissos pessoalmente e virtuais. Por exemplo, visitas de saúde, consultas financeiras, entrevistas, suporte ao cliente e horário de escritório educacional. Para saber mais, confira [Visitas virtuais com Teams e o aplicativo Bookings](expand-teams-across-your-org/bookings-virtual-visits.md).

Os agendadores podem gerenciar vários calendários de departamentos e funcionários e comunicações com participantes internos e externos, a partir de uma única experiência. Os compromissos virtuais são realizados Microsoft Teams reuniões que oferecem recursos robustos de videoconferência.

> [!NOTE]
> Somente os agendadores precisam ter o aplicativo de Bookings instalado no Teams. A equipe que conduz ou participa de compromissos virtuais não precisa do aplicativo. Eles podem simplesmente ingressar em compromissos de seu calendário Outlook ou Teams ou do link de reunião Teams no email de confirmação de reserva.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Pré-requisitos para usar o aplicativo Bookings no Teams

* A Exchange caixa de correio está Exchange Online. Não há suporte Exchange Server caixas de correio locais.
* O Microsoft Bookings está disponível para a organização.
* Os usuários têm uma licença apropriada. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 e Business Standard são suportados.
* Todos os usuários do aplicativo Bookings e todos os funcionários que participam das reuniões têm uma licença que dá suporte Teams agendamento de reuniões.
* [Pré-requisitos de software e navegador](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilidade do Bookings no Teams

O aplicativo do Microsoft Bookings para Teams está disponível na área de trabalho e na Web. Ele pode ser encontrado em [Aplicativos no Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e em **Gerenciar Aplicativos** no Teams de administração.

### <a name="control-access-to-bookings-within-your-organization"></a>Controle o acesso ao Bookings na sua organização

Há várias formas de controlar quem tem acesso ao aplicativo Bookings e aos recursos específicos do aplicativo. Você pode disponibilizar o aplicativo do Microsoft Bookings ou desabilitá-lo Centro de administração do Microsoft 365. Como alternativa, você pode criar uma política de aplicativo do Bookings para permitir que os usuários selecionados criem calendários do Bookings. Consulte [Obter acesso ao Microsoft Bookings](/microsoft-365/bookings/get-access).

Você também pode [criar uma Teams de configuração de aplicativos para fixar o aplicativo Bookings para usuários selecionados](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Configurações de política de reunião recomendadas

Para habilitar a melhor experiência para o Bookings, crie uma política de Teams de reunião para  admitir automaticamente Todos em sua organização e atribuir a política à sua equipe. A política permite que a equipe participe do compromisso automaticamente e habilita a experiência de lobby para participantes externos. Veja [como admitir automaticamente as pessoas em reuniões](meeting-policies-participants-and-guests.md#automatically-admit-people).

## <a name="optional-staff-approvals-setting"></a>Configuração opcional de aprovação de funcionários

Você pode exigir que os funcionários optem antes que o Bookings compartilhe suas informações de disponibilidade de agendamento e antes que outras pessoas possam agendar um compromisso com eles.

Para habilitar essa configuração, vá **para Centro de administração do Microsoft 365** \> **Configurações** \> **Configurações** e selecione **Bookings**.

Com essa configuração configurada, a equipe recebe um email no qual eles são solicitados a aprovar a associação a um calendário de reserva.  

Esse recurso está sendo implementado gradualmente no mundo todo para os clientes do Microsoft 365 e Office 365. Se todas as opções ainda não estão disponíveis em seu ambiente, volte em breve.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Alterar seu domínio padrão ao configurar a caixa de correio do Bookings

Ao configurar uma caixa de correio do Bookings, é usado o domínio de e-mail padrão da sua organização do Microsoft 365 ou do Office 365. No entanto, o domínio padrão pode causar problemas ao enviar convites de reunião para destinatários externos. Por exemplo, seu convite pode ser sinalizado como spam e movido para a pasta de lixo eletrônico do destinatário, para que o destinatário nunca veja seu convite.

Recomendamos que você altere o domínio padrão antes de criar sua caixa de correio do Bookings. Consulte [a Perguntas frequentes sobre domínios](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Se você precisar alterar o domínio padrão depois de criar sua caixa de correio do Bookings, use o PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Consulte a documentação do PowerShell para Definir o cmdlet [Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Se você estiver usando uma configuração híbrida Exchange, recomendamos testar completamente o fluxo de emails entre o Exchange local e o Exchange Online ao alterar o domínio padrão.

## <a name="send-feedback"></a>Enviar comentários

Apreciamos seus comentários em:

* Experiência do usuário ou facilidade de uso
* Lacunas de recursos ou funcionalidade ausente
* Bugs ou problemas
  
Para enviar comentários, selecione a opção **Ajuda** na parte inferior da barra de navegação Teams esquerda e selecione **Relatar um** problema para **todos os** problemas. Indique no início do relatório de comentários que você está enviando comentários sobre "Bookings" para que possamos identificar facilmente problemas do Bookings.

## <a name="related-articles"></a>Artigos relacionados

[Gerenciar a experiência de junção para Teams virtuais em navegadores móveis](expand-teams-across-your-org/mobile-browser-join.md)


  [Documentação do Bookings para usuários finais](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
