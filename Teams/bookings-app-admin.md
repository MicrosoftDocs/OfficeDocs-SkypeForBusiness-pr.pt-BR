---
title: Gerenciar o Bookings aplicativo no Microsoft Teams
author: mkbond007
ms.author: mabond
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
ms.openlocfilehash: 92c5a986ff745cd8010d310f1f716538c303c2c8
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646440"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Gerenciar o Bookings aplicativo no Microsoft Teams

O Bookings aplicativo em Microsoft Teams oferece uma maneira simples de agendar compromissos presenciais e virtuais. Por exemplo, visitas à saúde, consultas financeiras, entrevistas, atendimento ao cliente e horário comercial de educação. Para saber mais, confira [Compromissos virtuais com Teams e o Bookings aplicativo](expand-teams-across-your-org/bookings-virtual-visits.md).

Os agendadores podem gerenciar vários calendários de departamentos e funcionários e comunicações com participantes internos e externos, de uma única experiência. Os compromissos virtuais são realizados por meio Microsoft Teams reuniões que oferecem recursos robustos de videoconferência.

> [!NOTE]
> Somente os agendadores precisam ter o aplicativo de Bookings instalado no Teams. A equipe que realiza ou participa de compromissos virtuais não precisa do aplicativo. Eles podem simplesmente ingressar em compromissos de seu Outlook ou Teams calendário ou do link de reunião do Teams em seu email de confirmação de reserva.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Pré-requisitos para usar o aplicativo Bookings no Teams

* A Exchange de correio está em Exchange Online. Não há suporte Exchange Server caixas de correio locais.
* Microsoft Bookings está disponível para a organização.
* Os usuários têm uma licença apropriada. Office 365 A3, A5, E1, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 e Business Standard têm suporte.
* Todos os usuários do aplicativo Bookings e toda a equipe que participa das reuniões têm uma licença que dá suporte Teams agendamento de reunião.
* [Pré-requisitos de software e navegador](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilidade do Bookings no Teams

Microsoft Bookings aplicativo para Teams está disponível na área de trabalho e na Web. Ele pode ser encontrado em [Aplicativos no Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) **e em Gerenciar Aplicativos** no Teams de administração.

### <a name="control-access-to-bookings-within-your-organization"></a>Controle o acesso ao Bookings na sua organização

Há várias formas de controlar quem tem acesso ao aplicativo Bookings e aos recursos específicos do aplicativo. Você pode disponibilizar Microsoft Bookings aplicativo ou desabilitá-lo Centro de administração do Microsoft 365. Como alternativa, você pode criar uma política Bookings aplicativo para permitir que usuários selecionados criem Bookings calendários. Consulte [Obter acesso ao Microsoft Bookings](/microsoft-365/bookings/get-access).

Você também pode [criar uma política Teams configuração do aplicativo para fixar o Bookings aplicativo para usuários selecionados](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Configurações de política de reunião recomendadas

Para habilitar a melhor experiência para Bookings, crie uma política de Teams de reunião para admitir automaticamente  Todos em sua organização e atribuir a política à sua equipe. A política permite que a equipe ingresse no compromisso automaticamente e habilite a experiência de lobby para participantes externos. Veja [como admitir automaticamente as pessoas em reuniões](meeting-policies-participants-and-guests.md#automatically-admit-people).

## <a name="optional-staff-approvals-setting"></a>Configuração opcional de aprovação de funcionários

Você pode exigir que a equipe aceite antes de Bookings suas informações de disponibilidade de agendamento e antes que outras pessoas possam agendar um compromisso com eles.

Para habilitar essa configuração, **acesse Centro de administração do Microsoft 365** \> **Configurações** \> **Configurações** e selecione **Bookings**.

Com essa configuração ativada, a equipe recebe um email no qual é solicitado a aprovar a associação a um calendário de reserva.  

Esse recurso está sendo implementado gradualmente no mundo todo para os clientes do Microsoft 365 e Office 365. Se todas as opções ainda não estiverem disponíveis em seu ambiente, verifique novamente em breve.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Alterando seu domínio padrão ao configurar uma Bookings caixa de correio

Ao configurar uma caixa de correio do Bookings, é usado o domínio de e-mail padrão da sua organização do Microsoft 365 ou do Office 365. No entanto, o domínio padrão pode causar problemas ao enviar convites de reunião para destinatários externos. Por exemplo, seu convite pode ser sinalizado como spam e movido para a pasta lixo eletrônico do destinatário, para que o destinatário nunca veja seu convite.

Recomendamos que você altere o domínio padrão antes de criar sua Bookings de correio. Consulte as [perguntas frequentes sobre domínios](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Se você precisar alterar o domínio padrão depois de criar sua caixa de correio Bookings, use o PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Consulte a documentação do PowerShell para [definir o](/powershell/module/exchange/mailboxes/set-mailbox) cmdlet Caixa de Correio.

> [!NOTE]
> Se você estiver usando uma configuração híbrida do Exchange, recomendamos que você teste completamente o fluxo de email entre o Exchange local e o Exchange Online ao alterar o domínio padrão.

## <a name="send-feedback"></a>Enviar comentários

Apreciamos seus comentários em:

* Experiência do usuário ou facilidade de uso
* Lacunas de recursos ou funcionalidade ausente
* Bugs ou problemas
  
Para enviar comentários, selecione a **opção Ajuda** na parte inferior da barra Teams de navegação esquerda e, em seguida, selecione Relatar **um** Problema para **TODOS os** problemas. Indique no início do relatório de comentários que você está enviando comentários sobre "Bookings" para que possamos identificar facilmente Bookings problemas.

## <a name="related-articles"></a>Artigos relacionados

[Gerenciar a experiência de junção Teams compromissos virtuais em navegadores](expand-teams-across-your-org/browser-join.md)


  [Documentação do Bookings para usuários finais](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
