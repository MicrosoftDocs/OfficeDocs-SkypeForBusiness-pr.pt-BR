---
title: Gerenciar o aplicativo Bookings no Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: how-to
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
- m365-frontline
- highpri
ms.reviewer: ''
description: Saiba como gerenciar o aplicativo Bookings no Teams para usuários em sua organização.
ms.openlocfilehash: 3b3db2fed9177c089a27b89264ec85425d4ffbbf
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784206"
---
# <a name="manage-the-bookings-app-in-microsoft-teams"></a>Gerenciar o aplicativo Bookings no Microsoft Teams

O aplicativo Bookings no Microsoft Teams oferece uma maneira simples de agendar compromissos virtuais e presenciais. Por exemplo, visitas à saúde, consultas financeiras, entrevistas, suporte ao cliente e horário do escritório de educação. Para saber mais, confira [Compromissos virtuais com o Teams e o aplicativo Bookings](/microsoft-365/frontline/bookings-virtual-visits).

Os agendadores podem gerenciar vários calendários e comunicações do departamento e da equipe com participantes internos e externos, a partir de uma única experiência. Compromissos virtuais são realizados por meio de reuniões do Microsoft Teams que oferecem recursos robustos de videoconferência.

> [!NOTE]
> Somente os agendadores precisam ter o aplicativo de Bookings instalado no Teams. Os funcionários que realizam ou participam de compromissos virtuais não precisam do aplicativo. Eles podem simplesmente ingressar em compromissos de seu calendário do Outlook ou do Teams ou do link de reunião do Teams em seu email de confirmação de reserva.

## <a name="prerequisites-to-use-the-bookings-app-in-teams"></a>Pré-requisitos para usar o aplicativo Bookings no Teams

* A caixa de correio do Exchange está em Exchange Online. Não há suporte para caixas de correio Exchange Server locais.
* Microsoft Bookings está disponível para a organização.
* Os usuários têm uma licença apropriada. há suporte Office 365 A3, A5, E1, E3, E5, F1, F3, Microsoft 365 A3, A5, E3, E5, F1, F3 e Business Standard.
* Todos os usuários do aplicativo Bookings e todos os funcionários que participam das reuniões têm uma licença que dá suporte ao agendamento de reuniões do Teams.
* [Pré-requisitos de software e navegador](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilidade do Bookings no Teams

Microsoft Bookings aplicativo do Teams está disponível na área de trabalho e na Web. Ele pode ser encontrado [em Aplicativos no Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e em **Gerenciar Aplicativos** no centro de administração do Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Controle o acesso ao Bookings na sua organização

Há várias formas de controlar quem tem acesso ao aplicativo Bookings e aos recursos específicos do aplicativo. Você pode disponibilizar Microsoft Bookings aplicativo ou desabilitá-lo de Centro de administração do Microsoft 365. Como alternativa, você pode criar uma política de aplicativo Bookings para permitir que usuários selecionados criem calendários de Reservas. Consulte [Obter acesso ao Microsoft Bookings](/microsoft-365/bookings/get-access).

Você também pode [criar uma política de configuração de aplicativo do Teams para fixar o aplicativo Bookings para usuários selecionados](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Configurações recomendadas da política de reunião

Para habilitar a melhor experiência para o Bookings, crie uma política de reunião do Teams para admitir automaticamente **Todos em sua organização** e atribuir a política à sua equipe. A política permite que os funcionários participem do compromisso automaticamente e habilitem a experiência de lobby para participantes externos. Veja [como admitir automaticamente as pessoas em reuniões](meeting-policies-participants-and-guests.md#automatically-admit-people).

Para obter mais informações sobre políticas de reunião, consulte [Gerenciar políticas de reunião nas políticas do Teams](meeting-policies-in-teams.md) e [reunião e expiração de reunião no Teams](meeting-expiration.md).

## <a name="optional-staff-approvals-setting"></a>Configuração opcional de aprovação de funcionários

Você pode exigir que a equipe opte por entrar antes que a Bookings compartilhe suas informações de disponibilidade de agendamento e antes que outras pessoas possam agendar um compromisso com eles.

Para habilitar essa configuração, vá para **Centro de administração do Microsoft 365** \> **Configurações** \> **Configurações** e selecione **Reservas**.

Com essa configuração ativada, os funcionários recebem um email no qual são solicitados a aprovar a associação a um calendário de reservas.  

Esse recurso está sendo implementado gradualmente no mundo todo para os clientes do Microsoft 365 e Office 365. Se todas as opções ainda não estiverem disponíveis em seu ambiente, verifique novamente em breve.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailbox"></a>Alterando seu domínio padrão ao configurar a caixa de correio Bookings

Ao configurar uma caixa de correio do Bookings, é usado o domínio de e-mail padrão da sua organização do Microsoft 365 ou do Office 365. No entanto, o domínio padrão pode causar problemas ao enviar convites de reunião para destinatários externos. Por exemplo, seu convite pode ser sinalizado como spam e movido para a pasta lixo eletrônico do destinatário, para que o destinatário nunca veja seu convite.

Recomendamos que você altere o domínio padrão antes de criar sua caixa de correio Bookings. Consulte as [perguntas frequentes sobre domínios](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-microsoft-365).

Se você precisar alterar o domínio padrão depois de criar sua caixa de correio Bookings, use o PowerShell.

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Consulte a documentação do PowerShell para definir o cmdlet [caixa de correio](/powershell/module/exchange/mailboxes/set-mailbox) .

> [!NOTE]
> Se você estiver usando uma configuração híbrida do Exchange, recomendamos testar completamente o fluxo de email entre o Exchange local e Exchange Online ao alterar o domínio padrão.

## <a name="send-feedback"></a>Enviar comentários

Apreciamos seus comentários em:

* Experiência do usuário ou facilidade de uso
* Lacunas de recursos ou funcionalidade ausente
* Bugs ou problemas
  
Para enviar comentários, selecione a opção **Ajuda** na parte inferior da barra de navegação esquerda do Teams e selecione **Relatar um problema** para **TODOS os** problemas. Indique no início do relatório de comentários que você está enviando comentários sobre "Reservas" para que possamos identificar facilmente problemas de Reservas.

## <a name="related-articles"></a>Artigos relacionados

[Gerenciar a experiência de junção para compromissos virtuais do Teams em navegadores](/microsoft-365/frontline/browser-join)


  [Documentação do Bookings para usuários finais](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
