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
ms.reviewer: ''
description: Microsoft Teams e visitas virtuais com o aplicativo bookings
ms.openlocfilehash: 684c442765b868ca96e9d1bf243817f9378f0b5d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790613"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="3d7dd-103">Visitas virtuais com o Microsoft Teams e o aplicativo de reservas</span><span class="sxs-lookup"><span data-stu-id="3d7dd-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="3d7dd-104">O aplicativo de reservas do Microsoft Teams oferece uma maneira simples de agendar compromissos presenciais e virtuais, como visitas à saúde, consultas financeiras, entrevistas, suporte ao cliente, treinamento de horas de escritório e muito mais.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="3d7dd-105">Os agendadores podem gerenciar vários calendários de departamentos e funcionários, bem como comunicações com participantes internos e externos, a partir de uma única experiência.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="3d7dd-106">Os compromissos virtuais propriamente ditos são mantidos por meio das reuniões do Microsoft Teams, o que oferece recursos robustos de videoconferência.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="3d7dd-107">Somente agendadores precisam ter o aplicativo bookings instalado no Teams.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="3d7dd-108">A condução da equipe ou a participação em compromissos virtuais não precisam do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="3d7dd-109">Eles podem simplesmente participar de compromissos do calendário do Outlook ou do teams ou de um link no e-mail de confirmação de reservas.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="3d7dd-110">Pré-requisitos para usar o aplicativo reservas no Teams</span><span class="sxs-lookup"><span data-stu-id="3d7dd-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="3d7dd-111">A caixa de correio do Exchange deve estar no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="3d7dd-112">Não há suporte para as caixas de correio do Exchange Server locais.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="3d7dd-113">O Microsoft bookings deve estar ativado para a organização.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="3d7dd-114">Os usuários devem ter uma licença adequada.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-114">Users must have an appropriate license.</span></span> <span data-ttu-id="3d7dd-115">O Office 365 a3, a5, E3 e e5, bem como o Microsoft 365 Business Standard, a3, a5, E3 e E5 são suportados.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="3d7dd-116">Todos os usuários do aplicativo reservas e todas as equipes participantes de reuniões devem ter uma licença que dê suporte ao agendamento de reunião de equipe.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="3d7dd-117">Seus sistemas devem atender todos os [pré-requisitos do software e do navegador](hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="3d7dd-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="3d7dd-118">Disponibilidade de reservas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3d7dd-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="3d7dd-119">O aplicativo Microsoft bookings para Teams está disponível na área de trabalho e na Web.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="3d7dd-120">Ele pode ser encontrado em [aplicativos no Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e em **gerenciar aplicativos** no centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="3d7dd-121">Controlar o acesso a reservas em sua organização</span><span class="sxs-lookup"><span data-stu-id="3d7dd-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="3d7dd-122">Há várias maneiras de controlar quem tem acesso ao aplicativo de reservas e a recursos específicos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="3d7dd-123">Para saber como ativar ou desativar o Microsoft bookings no centro de administração do Microsoft 365, bem como criar uma política de aplicativo de livros para permitir que os usuários selecionados criem calendários de livros, consulte [obter acesso a Microsoft bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span><span class="sxs-lookup"><span data-stu-id="3d7dd-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="3d7dd-124">Você também pode aprender a [criar uma política do aplicativo Teams para fixar o aplicativo de reservas para usuários selecionados](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3d7dd-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="3d7dd-125">Configurações de política de reunião recomendadas</span><span class="sxs-lookup"><span data-stu-id="3d7dd-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="3d7dd-126">Para habilitar a melhor experiência para reservas, crie uma política de reunião de equipe para admitir automaticamente **todos em sua organização** .</span><span class="sxs-lookup"><span data-stu-id="3d7dd-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization** .</span></span> <span data-ttu-id="3d7dd-127">Isso permitirá que a equipe ingresse no compromisso automaticamente e habilite a experiência de lobby para participantes externos.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="3d7dd-128">Você pode saber mais sobre como [admitting automaticamente as pessoas para reuniões](meeting-policies-in-teams.md#automatically-admit-people).</span><span class="sxs-lookup"><span data-stu-id="3d7dd-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="3d7dd-129">Configuração de aprovações de equipe opcionais</span><span class="sxs-lookup"><span data-stu-id="3d7dd-129">Optional staff approvals setting</span></span>

<span data-ttu-id="3d7dd-130">Como uma configuração de privacidade adicional, você pode optar por exigir que a equipe opte antes de as informações de disponibilidade do cronograma sejam compartilhadas por meio de reservas e antes de serem reservadas para um compromisso.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="3d7dd-131">Para habilitar essa configuração, vá para configurações de configurações **do centro de administração do Microsoft 365** \> **Settings** \> **Settings** e, em seguida, selecione **reservas** .</span><span class="sxs-lookup"><span data-stu-id="3d7dd-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings** , then select **Bookings** .</span></span>

<span data-ttu-id="3d7dd-132">Com essa configuração ativada, a equipe receberá um email em que será solicitado a aprovar a associação a um calendário de reservas.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="3d7dd-133">Esse recurso está gradualmente sendo implantado em todo o mundo para os clientes do Microsoft 365 e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="3d7dd-134">Se todas as opções ainda não estiverem disponíveis no seu ambiente, verifique novamente em breve.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="3d7dd-135">Alterar seu domínio padrão ao configurar as caixas de correio de livros</span><span class="sxs-lookup"><span data-stu-id="3d7dd-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="3d7dd-136">Ao configurar uma caixa de correio de livro, é usado o domínio de email padrão da sua organização do Microsoft 365 ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="3d7dd-137">No entanto, isso pode causar problemas ao enviar convites de reunião para destinatários externos; seu convite pode ser sinalizado como spam e movido para a pasta lixo eletrônico do destinatário, para que o destinatário nunca veja seu convite.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="3d7dd-138">Recomendamos que você altere o domínio padrão antes de criar sua caixa de correio de livros.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="3d7dd-139">Para saber mais sobre como fazer isso, Confira as [perguntas frequentes sobre domínios](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="3d7dd-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="3d7dd-140">Se você precisar alterar o domínio padrão após a criação de uma caixa de correio de livros, você pode fazer isso com o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="3d7dd-141">Para obter mais informações, consulte a documentação do PowerShell para o cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) .</span><span class="sxs-lookup"><span data-stu-id="3d7dd-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="3d7dd-142">Se você estiver usando uma configuração híbrida do Exchange, recomendamos que teste exaustivamente o fluxo de email entre o Exchange local e o Exchange Online ao alterar o domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="3d7dd-143">Enviar comentários</span><span class="sxs-lookup"><span data-stu-id="3d7dd-143">Sending feedback</span></span>

<span data-ttu-id="3d7dd-144">Agradecemos seus comentários sobre:</span><span class="sxs-lookup"><span data-stu-id="3d7dd-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="3d7dd-145">Experiência do usuário ou facilidade de uso</span><span class="sxs-lookup"><span data-stu-id="3d7dd-145">User experience or ease of use</span></span>
  - <span data-ttu-id="3d7dd-146">Lacunas de recursos ou funcionalidade ausente</span><span class="sxs-lookup"><span data-stu-id="3d7dd-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="3d7dd-147">Erros ou problemas</span><span class="sxs-lookup"><span data-stu-id="3d7dd-147">Bugs or issues</span></span>
  
<span data-ttu-id="3d7dd-148">Para enviar comentários, clique no botão **ajuda** próximo à parte inferior da barra de navegação do teams à esquerda e, em seguida, clique em **relatar um problema** para **todos os** problemas.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="3d7dd-149">Observe o início do seu relatório de comentários que você está enviando comentários sobre "reservas" para que possamos identificar facilmente os problemas relacionados a reservas.</span><span class="sxs-lookup"><span data-stu-id="3d7dd-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3d7dd-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3d7dd-150">Related topics</span></span>

[<span data-ttu-id="3d7dd-151">Documentação de livros para usuários finais</span><span class="sxs-lookup"><span data-stu-id="3d7dd-151">Bookings documentation for end users</span></span>](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
