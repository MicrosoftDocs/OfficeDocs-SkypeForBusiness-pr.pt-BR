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
ms.openlocfilehash: e65e0b8c4af7397ebe0b152d2f977b2bf8cbb667
ms.sourcegitcommit: f0e5da6136656261567ffe0fa3f2fedd901209a8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "51891258"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="333b3-103">Visitas virtuais com o Microsoft Teams e o aplicativo Bookings</span><span class="sxs-lookup"><span data-stu-id="333b3-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="333b3-104">O aplicativo Bookings no Microsoft Teams oferece uma maneira simples de agendar compromissos presenciais e virtuais, como visitas médicas, consultas financeiras, entrevistas, atendimento ao cliente, horário comercial e muito mais.</span><span class="sxs-lookup"><span data-stu-id="333b3-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="333b3-105">Os agendadores podem gerenciar vários calendários de departamentos e de funcionários, assim como comunicações com os participantes internos e externos em uma única experiência.</span><span class="sxs-lookup"><span data-stu-id="333b3-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="333b3-106">Os próprios compromissos virtuais são realizados através do Microsoft Teams Meetings, que oferece recursos consistentes de videoconferência.</span><span class="sxs-lookup"><span data-stu-id="333b3-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="333b3-107">Somente os agendadores precisam ter o aplicativo de Bookings instalado no Teams.</span><span class="sxs-lookup"><span data-stu-id="333b3-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="333b3-108">Os funcionários que estão realizando ou participando de compromissos virtuais não precisam do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="333b3-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="333b3-109">Eles podem ingressar em compromissos pelo calendário do Outlook ou do Teams ou por um link no e-mail de confirmação da reserva.</span><span class="sxs-lookup"><span data-stu-id="333b3-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="333b3-110">Pré-requisitos para usar o aplicativo Bookings no Teams</span><span class="sxs-lookup"><span data-stu-id="333b3-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="333b3-111">A caixa de correio do Exchange deve estar no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="333b3-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="333b3-112">Não há suporte para as caixas de correio do Exchange Server locais.</span><span class="sxs-lookup"><span data-stu-id="333b3-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="333b3-113">O Microsoft Bookings deve ser ativado para a organização.</span><span class="sxs-lookup"><span data-stu-id="333b3-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="333b3-114">Os usuários devem ter uma licença apropriada\*.</span><span class="sxs-lookup"><span data-stu-id="333b3-114">Users must have an appropriate license.</span></span> <span data-ttu-id="333b3-115">Há suporte para o Office 365 A3, A5, E3 e E5, além do Microsoft 365 Business Premium, Microsoft 365 Business Standard, A3, A5, E3 e E5.</span><span class="sxs-lookup"><span data-stu-id="333b3-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Premium, Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="333b3-116">Todos os usuários do aplicativo Bookings e todos os funcionários que participam das reuniões devem ter uma licença que ofereça suporte ao agendamento de Reunião no Teams.</span><span class="sxs-lookup"><span data-stu-id="333b3-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="333b3-117">Seus sistemas devem atender a todos os [Pré-requisitos de software e de navegador](hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="333b3-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="333b3-118">Disponibilidade do Bookings no Teams</span><span class="sxs-lookup"><span data-stu-id="333b3-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="333b3-119">O aplicativo Microsoft Bookings do Teams está disponível na área de trabalho e na Web.</span><span class="sxs-lookup"><span data-stu-id="333b3-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="333b3-120">Ele pode ser encontrado em [Aplicativos no Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) e em **Gerenciar aplicativos** no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="333b3-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="333b3-121">Controle o acesso ao Bookings na sua organização</span><span class="sxs-lookup"><span data-stu-id="333b3-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="333b3-122">Há várias formas de controlar quem tem acesso ao aplicativo Bookings e aos recursos específicos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="333b3-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="333b3-123">Para saber como ativar ou desativar o Microsoft Bookings no Centro de administração do Microsoft 365, assim como criar uma política do aplicativo Bookings para permitir que os usuários selecionados criem calendários do Bookings, consulte [Obter acesso ao Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span><span class="sxs-lookup"><span data-stu-id="333b3-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="333b3-124">Você também pode saber como [Criar uma política do aplicativo Teams para fixar o aplicativo Bookings aos usuários selecionados](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="333b3-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="333b3-125">Configurações recomendadas da política de reunião</span><span class="sxs-lookup"><span data-stu-id="333b3-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="333b3-126">Para habilitar a melhor experiência de uso do Bookings, crie uma política de reunião de equipe para admitir automaticamente **Todos na sua organização**.</span><span class="sxs-lookup"><span data-stu-id="333b3-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="333b3-127">Isso permitirá que os funcionários possam participar automaticamente do encontro e permitir a experiência de lobby dos participantes externos.</span><span class="sxs-lookup"><span data-stu-id="333b3-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="333b3-128">Você pode saber mais sobre como [admitir automaticamente as pessoas nas reuniões](meeting-policies-participants-and-guests.md#automatically-admit-people).</span><span class="sxs-lookup"><span data-stu-id="333b3-128">You can learn more about [automatically admitting people to meetings](meeting-policies-participants-and-guests.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="333b3-129">Configuração opcional de aprovação de funcionários</span><span class="sxs-lookup"><span data-stu-id="333b3-129">Optional staff approvals setting</span></span>

<span data-ttu-id="333b3-130">Como uma configuração de privacidade extra, você pode pedir que os funcionários optem por participar antes que suas informações de disponibilidade de horário sejam compartilhadas pelo Bookings e antes que eles possam agendar um compromisso.</span><span class="sxs-lookup"><span data-stu-id="333b3-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="333b3-131">Para habilitar essa configuração, acesse **Centro de administração do Microsoft 365** \> **Configurações** \> **Configurações** e selecione **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="333b3-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="333b3-132">Com essa configuração ativada, os funcionários receberão um e-mail solicitando que aprovem a adesão a um calendário de reservas.</span><span class="sxs-lookup"><span data-stu-id="333b3-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="333b3-133">Esse recurso está sendo implementado gradualmente no mundo todo para os clientes do Microsoft 365 e Office 365.</span><span class="sxs-lookup"><span data-stu-id="333b3-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="333b3-134">Se todas as opções ainda não estiverem disponíveis no seu ambiente, verifique novamente em breve.</span><span class="sxs-lookup"><span data-stu-id="333b3-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="333b3-135">Alterar seu domínio padrão ao configurar as caixas de correio do Bookings</span><span class="sxs-lookup"><span data-stu-id="333b3-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="333b3-136">Ao configurar uma caixa de correio do Bookings, é usado o domínio de e-mail padrão da sua organização do Microsoft 365 ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="333b3-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="333b3-137">Entretanto, isso pode gerar problemas ao enviar convites de reuniões aos destinatários externos; seu convite pode ser marcado como spam e movido para a pasta de lixo eletrônico do destinatário, de modo que ele talvez nunca veja seu convite.</span><span class="sxs-lookup"><span data-stu-id="333b3-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="333b3-138">Recomendamos que você altere o domínio padrão antes de criar sua caixa de correio do Bookings.</span><span class="sxs-lookup"><span data-stu-id="333b3-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="333b3-139">Para obter mais informações sobre como fazer isso, consulte [Perguntas frequentes sobre domínios](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="333b3-139">For information on how to do this, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="333b3-140">Se você tiver que alterar o domínio padrão depois que sua caixa de correio do Bookings já tiver sido criada, você pode fazê-lo com o Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="333b3-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="333b3-141">Para obter mais informações, consulte a documentação do Windows PowerShell quanto ao cmdlet [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="333b3-141">For more information, see the PowerShell documentation for the [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="333b3-142">Se você estiver usando uma configuração híbrida do Exchange, recomendamos que você teste minuciosamente o fluxo de correio entre o Exchange no local e o Exchange Online ao mudar o domínio padrão.</span><span class="sxs-lookup"><span data-stu-id="333b3-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="333b3-143">Enviar comentários</span><span class="sxs-lookup"><span data-stu-id="333b3-143">Sending feedback</span></span>

<span data-ttu-id="333b3-144">Apreciamos seus comentários em:</span><span class="sxs-lookup"><span data-stu-id="333b3-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="333b3-145">Experiência do usuário ou facilidade de uso</span><span class="sxs-lookup"><span data-stu-id="333b3-145">User experience or ease of use</span></span>
  - <span data-ttu-id="333b3-146">Lacunas de recursos ou funcionalidade ausente</span><span class="sxs-lookup"><span data-stu-id="333b3-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="333b3-147">Bugs ou problemas</span><span class="sxs-lookup"><span data-stu-id="333b3-147">Bugs or issues</span></span>
  
<span data-ttu-id="333b3-148">Para enviar comentários, clique no botão **Ajuda** perto da parte inferior da barra de navegação esquerda do Teams e clique em **Relatar um problema** para **TODOS** os problemas.</span><span class="sxs-lookup"><span data-stu-id="333b3-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="333b3-149">Observe no início do seu relatório de comentários que você está enviando comentários sobre "Reservas" para que possamos identificar facilmente os problemas do Bookings.</span><span class="sxs-lookup"><span data-stu-id="333b3-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="333b3-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="333b3-150">Related topics</span></span>

<span data-ttu-id="333b3-151">
  [Documentação do Bookings para usuários finais](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)</span><span class="sxs-lookup"><span data-stu-id="333b3-151">[Bookings documentation for end users](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)</span></span>