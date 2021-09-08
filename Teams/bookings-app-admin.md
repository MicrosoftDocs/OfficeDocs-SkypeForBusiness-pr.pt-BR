---
title: Visitas virtuais com o Microsoft Teams e o aplicativo Bookings
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
description: Microsoft Teams e visitas virtuais com o aplicativo Bookings
ms.openlocfilehash: cf6154099db5b6c6b52b9d82b4e58cd6c00c07b3
ms.sourcegitcommit: 1c2364fbefd95151f0847a35e8bc7c4c1b3892f5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2021
ms.locfileid: "58935857"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visitas virtuais com o Microsoft Teams e o aplicativo Bookings

O aplicativo Bookings no Microsoft Teams oferece uma maneira simples de agendar compromissos presenciais e virtuais, como visitas médicas, consultas financeiras, entrevistas, atendimento ao cliente, horário comercial e muito mais.

Os agendadores podem gerenciar vários calendários de departamentos e de funcionários, assim como comunicações com os participantes internos e externos em uma única experiência. Os próprios compromissos virtuais são realizados através do Microsoft Teams Meetings, que oferece recursos consistentes de videoconferência.

> [!NOTE]
> Somente os agendadores precisam ter o aplicativo de Bookings instalado no Teams. Os funcionários que estão realizando ou participando de compromissos virtuais não precisam do aplicativo. Eles podem ingressar em compromissos pelo calendário do Outlook ou do Teams ou por um link no e-mail de confirmação da reserva.

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a>Pré-requisitos para usar o aplicativo Bookings no Teams

- A caixa de correio do Exchange deve estar no Exchange Online. Não há suporte para as caixas de correio do Exchange Server locais.

- O Microsoft Bookings deve ser ativado para a organização.

- Os usuários devem ter uma licença apropriada*. Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3 e E5, Business Standard são suportados.

- Todos os usuários do aplicativo Bookings e todos os funcionários que participam das reuniões devem ter uma licença que ofereça suporte ao agendamento de Reunião no Teams.

- Seus sistemas devem atender a todos os [Pré-requisitos de software e de navegador](hardware-requirements-for-the-teams-app.md).

## <a name="availability-of-bookings-in-teams"></a>Disponibilidade do Bookings no Teams

O aplicativo Microsoft Bookings do Teams está disponível na área de trabalho e na Web. Ele pode ser encontrado em [Aplicativos no Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e em **Gerenciar aplicativos** no Centro de administração do Teams.

### <a name="control-access-to-bookings-within-your-organization"></a>Controle o acesso ao Bookings na sua organização

Há várias formas de controlar quem tem acesso ao aplicativo Bookings e aos recursos específicos do aplicativo. Para saber como ativar ou desativar o Microsoft Bookings no Centro de administração do Microsoft 365, assim como criar uma política do aplicativo Bookings para permitir que os usuários selecionados criem calendários do Bookings, consulte [Obter acesso ao Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce). Você também pode saber como [Criar uma política do aplicativo Teams para fixar o aplicativo Bookings aos usuários selecionados](teams-app-setup-policies.md).

## <a name="recommended-meeting-policy-settings"></a>Configurações recomendadas da política de reunião

Para habilitar a melhor experiência de uso do Bookings, crie uma política de reunião de equipe para admitir automaticamente **Todos na sua organização**. Isso permitirá que os funcionários possam participar automaticamente do encontro e permitir a experiência de lobby dos participantes externos. Você pode saber mais sobre como [admitir automaticamente as pessoas nas reuniões](meeting-policies-participants-and-guests.md#automatically-admit-people).

### <a name="optional-staff-approvals-setting"></a>Configuração opcional de aprovação de funcionários

Como uma configuração de privacidade extra, você pode pedir que os funcionários optem por participar antes que suas informações de disponibilidade de horário sejam compartilhadas pelo Bookings e antes que eles possam agendar um compromisso.  

Para habilitar essa configuração, acesse **Centro de administração do Microsoft 365** \> **Configurações** \> **Configurações** e selecione **Bookings**.

Com essa configuração ativada, os funcionários receberão um e-mail solicitando que aprovem a adesão a um calendário de reservas.  

Esse recurso está sendo implementado gradualmente no mundo todo para os clientes do Microsoft 365 e Office 365. Se todas as opções ainda não estiverem disponíveis no seu ambiente, verifique novamente em breve.

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a>Alterar seu domínio padrão ao configurar as caixas de correio do Bookings

Ao configurar uma caixa de correio do Bookings, é usado o domínio de e-mail padrão da sua organização do Microsoft 365 ou do Office 365. Entretanto, isso pode gerar problemas ao enviar convites de reuniões aos destinatários externos; seu convite pode ser marcado como spam e movido para a pasta de lixo eletrônico do destinatário, de modo que ele talvez nunca veja seu convite.

Recomendamos que você altere o domínio padrão antes de criar sua caixa de correio do Bookings. Para obter mais informações sobre como fazer isso, consulte [Perguntas frequentes sobre domínios](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).

Se você tiver que alterar o domínio padrão depois que sua caixa de correio do Bookings já tiver sido criada, você pode fazê-lo com o Windows PowerShell:

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

Para obter mais informações, consulte a documentação do Windows PowerShell quanto ao cmdlet [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Se você estiver usando uma configuração híbrida do Exchange, recomendamos que você teste minuciosamente o fluxo de correio entre o Exchange no local e o Exchange Online ao mudar o domínio padrão.

## <a name="sending-feedback"></a>Enviar comentários

Apreciamos seus comentários em:

  - Experiência do usuário ou facilidade de uso
  - Lacunas de recursos ou funcionalidade ausente
  - Bugs ou problemas
  
Para enviar comentários, clique no botão **Ajuda** perto da parte inferior da barra de navegação esquerda do Teams e clique em **Relatar um problema** para **TODOS** os problemas. Observe no início do seu relatório de comentários que você está enviando comentários sobre "Reservas" para que possamos identificar facilmente os problemas do Bookings.

## <a name="related-topics"></a>Tópicos relacionados

[Gerenciar a experiência de junção para Teams virtuais em navegadores móveis](expand-teams-across-your-org/mobile-browser-join.md)


  [Documentação do Bookings para usuários finais](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
