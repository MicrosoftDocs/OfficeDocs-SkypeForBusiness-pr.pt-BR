---
title: Gerenciar o aplicativo Bookings no Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
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
ms.openlocfilehash: f11739784dcb9897bf9a3fcbffdadc8aea00d3e0
ms.sourcegitcommit: c4ec82b7d8a820362b6b0276470b0dea95a628df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66819286"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Gerenciar o aplicativo Bookings no Microsoft Teams

O aplicativo Bookings no Microsoft Teams oferece uma maneira simples de agendar compromissos presenciais e virtuais. Por exemplo, visitas à saúde, consultas financeiras, entrevistas, atendimento ao cliente e horário comercial de educação. Para saber mais, confira [Compromissos virtuais com o Teams e o aplicativo Bookings](/microsoft-365/frontline/bookings-virtual-visits).

Os agendadores podem gerenciar vários calendários de departamentos e funcionários e comunicações com participantes internos e externos, de uma única experiência. Os compromissos virtuais são realizados por meio de reuniões do Microsoft Teams que oferecem recursos robustos de videoconferência.

> [!NOTE]
> Somente os agendadores precisam ter o aplicativo de Bookings instalado no Teams. A equipe que realiza ou participa de compromissos virtuais não precisa do aplicativo. Eles podem simplesmente ingressar em compromissos do calendário do Outlook ou do Teams ou do link de reunião do Teams em seu email de confirmação de reserva.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Pré-requisitos para usar o aplicativo Bookings no Teams

* A caixa de correio do Exchange está Exchange Online. Não há suporte Exchange Server caixas de correio locais.
* Microsoft Bookings está disponível para a organização.
* Os usuários têm uma licença apropriada. Office 365 A3, A5, E1, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 e Business Standard têm suporte.
* Todos os usuários do aplicativo Bookings e todos os funcionários que participam das reuniões têm uma licença que dá suporte ao agendamento de reuniões do Teams.
* [Pré-requisitos de software e navegador](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilidade do Bookings no Teams

Microsoft Bookings aplicativo para Teams está disponível na área de trabalho e na Web. Ele pode ser encontrado em [Aplicativos no Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e em **Gerenciar Aplicativos** no centro de administração do Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Controle o acesso ao Bookings na sua organização

Há várias formas de controlar quem tem acesso ao aplicativo Bookings e aos recursos específicos do aplicativo. Você pode disponibilizar Microsoft Bookings aplicativo ou desabilitá-lo Centro de administração do Microsoft 365. Como alternativa, você pode criar uma política de aplicativo do Bookings para permitir que usuários selecionados criem calendários do Bookings. Consulte [Obter acesso ao Microsoft Bookings](/microsoft-365/bookings/get-access).

Você também pode criar [uma política de configuração de aplicativo do Teams para fixar o aplicativo Bookings para usuários selecionados](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Configurações de política de reunião recomendadas

Para habilitar a melhor experiência para o Bookings, crie uma política de reunião  do Teams para admitir automaticamente Todos em sua organização e atribuir a política à sua equipe. A política permite que a equipe ingresse no compromisso automaticamente e habilite a experiência de lobby para participantes externos. Veja [como admitir automaticamente as pessoas em reuniões](meeting-policies-participants-and-guests.md#automatically-admit-people).

Para obter mais informações sobre políticas de reunião, consulte [Gerenciar políticas de](meeting-policies-in-teams.md) reunião no Teams e [políticas de reunião e expiração de reunião no Teams](meeting-expiration.md).

## <a name="optional-staff-approvals-setting"></a>Configuração opcional de aprovação de funcionários

Você pode exigir que a equipe aceite antes que o Bookings compartilhe suas informações de disponibilidade de agendamento e antes que outras pessoas possam agendar um compromisso com eles.

Para habilitar essa configuração, acesse **Centro de administração do Microsoft 365** \> **Configurações** \> **e selecione** **Reservas**.

Com essa configuração ativada, a equipe recebe um email no qual é solicitado a aprovar a associação a um calendário de reserva.  

Esse recurso está sendo implementado gradualmente no mundo todo para os clientes do Microsoft 365 e Office 365. Se todas as opções ainda não estiverem disponíveis em seu ambiente, verifique novamente em breve.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Alterando seu domínio padrão ao configurar a caixa de correio do Bookings

Ao configurar uma caixa de correio do Bookings, é usado o domínio de e-mail padrão da sua organização do Microsoft 365 ou do Office 365. No entanto, o domínio padrão pode causar problemas ao enviar convites de reunião para destinatários externos. Por exemplo, seu convite pode ser sinalizado como spam e movido para a pasta lixo eletrônico do destinatário, para que o destinatário nunca veja seu convite.

Recomendamos que você altere o domínio padrão antes de criar sua caixa de correio do Bookings. Consulte as [perguntas frequentes sobre domínios](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Se você precisar alterar o domínio padrão depois de criar sua caixa de correio do Bookings, use o PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Consulte a documentação do PowerShell para [definir o](/powershell/module/exchange/mailboxes/set-mailbox) cmdlet Caixa de Correio.

> [!NOTE]
> Se você estiver usando uma configuração híbrida do Exchange, recomendamos que você teste completamente o fluxo de emails entre o Exchange local e o Exchange Online ao alterar o domínio padrão.

## <a name="send-feedback"></a>Enviar comentários

Apreciamos seus comentários em:

* Experiência do usuário ou facilidade de uso
* Lacunas de recursos ou funcionalidade ausente
* Bugs ou problemas
  
Para enviar comentários, selecione a **opção Ajuda** na parte inferior da barra de navegação esquerda do Teams e, em seguida, selecione Relatar **um Problema para** **TODOS os** problemas. Indique no início do relatório de comentários que você está enviando comentários sobre "Reservas" para que possamos identificar facilmente os problemas do Bookings.

## <a name="related-articles"></a>Artigos relacionados

[Gerenciar a experiência de ingresso para compromissos virtuais do Teams em navegadores](/microsoft-365/frontline/browser-join)


  [Documentação do Bookings para usuários finais](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
