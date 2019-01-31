---
title: Usar suplemento de Reunião do Microsoft Teams no Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 10/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Normal
search.appverid: MET150
description: O Microsoft Teams instala um suplemento no Outlook para que os usuários possam agendar uma reunião do Teams pelo Outlook.
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba75e2efa5ce96a30f868bef44349468753abeec
ms.sourcegitcommit: 20defe18ac1d2b21853bd6d5f0772cd3f35e53e9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2019
ms.locfileid: "29686461"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="2c49e-103">Usar o suplemento de Reunião do Teams no Outlook</span><span class="sxs-lookup"><span data-stu-id="2c49e-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="2c49e-104">O suplemento de Reunião do Teams é instalado automaticamente para os usuários que têm o Microsoft Teams e o Office 2013 ou o Office 2016 instalados em seus computadores Windows.</span><span class="sxs-lookup"><span data-stu-id="2c49e-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="2c49e-105">Os usuários verão o suplemento de Reunião do Teams na faixa de opções Calendário do Outlook.</span><span class="sxs-lookup"><span data-stu-id="2c49e-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Captura de tela do suplemento do Teams na faixa de opções do Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> <span data-ttu-id="2c49e-107">Os usuários do Windows 7 devem instalar a [atualização para Universal C Runtime no Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) para o suplemento de reunião de equipes trabalhem.</span><span class="sxs-lookup"><span data-stu-id="2c49e-107">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>

<span data-ttu-id="2c49e-108">Se o suplemento de Reunião do Teams não for exibido, instrua os usuários a fechar o Outlook e o Teams e reiniciar o cliente Teams primeiro, depois entrar no Teams e então reiniciar o cliente Outlook, exatamente nessa ordem.</span><span class="sxs-lookup"><span data-stu-id="2c49e-108">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="2c49e-109">O suplemento de Reunião do Teams para o Outlook ainda não está disponível para usuários do Mac.</span><span class="sxs-lookup"><span data-stu-id="2c49e-109">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="2c49e-110">Requisitos de autenticação</span><span class="sxs-lookup"><span data-stu-id="2c49e-110">Authentication requirements</span></span>

<span data-ttu-id="2c49e-111">O suplemento de Reunião do Teams requer que os usuários entrem no Teams usando a autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="2c49e-111">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="2c49e-112">Se os usuários não utilizarem esse método para entrar, poderão usar o cliente Teams, mas não conseguirão agendar reuniões online do Teams usando o suplemento do Outlook.</span><span class="sxs-lookup"><span data-stu-id="2c49e-112">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="2c49e-113">Você pode corrigir isso da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2c49e-113">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="2c49e-114">Se a autenticação moderna não estiver configurada para a sua organização, você deverá fazer isso.</span><span class="sxs-lookup"><span data-stu-id="2c49e-114">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="2c49e-115">Se a autenticação moderna estiver configurada, mas os usuários cancelaram a caixa de diálogo, você deverá instruí-los para entrar novamente usando a autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="2c49e-115">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="2c49e-116">Para saber mais sobre como configurar a autenticação, veja [Modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2c49e-116">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="2c49e-117">Habilitar reuniões privadas</span><span class="sxs-lookup"><span data-stu-id="2c49e-117">Enable private meetings</span></span>

<span data-ttu-id="2c49e-118">Permitir o agendamento para reuniões privadas deve ser habilitada no & equipes Skype para Business Admin Center para o plug-in para obter implantado.</span><span class="sxs-lookup"><span data-stu-id="2c49e-118">Allow scheduling for private meetings must be enabled in the Teams & Skype for Business Admin Center for the plug-in to get deployed.</span></span> <span data-ttu-id="2c49e-119">No Centro de administração, vá para **reuniões** > **Políticas de reunião**e na seção **Geral** , alternar **Permitir o agendamento de reuniões privadas** para diante.)</span><span class="sxs-lookup"><span data-stu-id="2c49e-119">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Captura de tela das configurações no & equipes Skype para Business Admin Center.](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="2c49e-121">O cliente Teams instala o suplemento correto, determinando se os usuários precisam da versão de 32 ou de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="2c49e-121">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="2c49e-122">Talvez os usuários precisem reiniciar o Outlook após uma instalação ou atualização do Teams para obter o suplemento mais recente.</span><span class="sxs-lookup"><span data-stu-id="2c49e-122">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="2c49e-123">Outras considerações</span><span class="sxs-lookup"><span data-stu-id="2c49e-123">Other considerations</span></span>

<span data-ttu-id="2c49e-124">O suplemento de Reunião do Teams ainda está desenvolvendo funcionalidades, então esteja ciente do seguinte:</span><span class="sxs-lookup"><span data-stu-id="2c49e-124">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="2c49e-125">Alguns recursos de reunião online, como a gravação, a votação e o quadro de comunicações, ainda não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2c49e-125">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="2c49e-126">As opções de reunião ainda não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2c49e-126">Meeting options are currently not available.</span></span>
- <span data-ttu-id="2c49e-127">O suplemento destina-se a reuniões agendadas com participantes específicos, não a reuniões em um canal.</span><span class="sxs-lookup"><span data-stu-id="2c49e-127">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="2c49e-128">As reuniões do canal devem ser agendadas dentro do Teams.</span><span class="sxs-lookup"><span data-stu-id="2c49e-128">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="2c49e-129">Atualmente, o suplemento de Reunião do Teams no Outlook está disponível apenas para usuários do Windows, mas o suporte para Mac será disponibilizado em breve.</span><span class="sxs-lookup"><span data-stu-id="2c49e-129">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="2c49e-130">O suplemento não funcionará se houver um proxy de autenticação no caminho de rede do computador do usuário e dos serviços do Teams.</span><span class="sxs-lookup"><span data-stu-id="2c49e-130">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="2c49e-131">O add-in está sendo distribuído incrementalmente e pode não estar disponível para a sua organização ainda.</span><span class="sxs-lookup"><span data-stu-id="2c49e-131">The add-in is being rolled out incrementally and might not be available for your organization yet.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2c49e-132">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="2c49e-132">Troubleshooting</span></span>

<span data-ttu-id="2c49e-133">Se você não conseguir a reunião de equipes suplemento para Outlook a fim de instalar, tente essas etapas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="2c49e-133">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="2c49e-134">Certifique-se de que tiverem sido aplicadas a todas as atualizações disponíveis para o cliente de desktop do Outlook</span><span class="sxs-lookup"><span data-stu-id="2c49e-134">Ensure all available updates for Outlook desktop client have been applied</span></span> 
- <span data-ttu-id="2c49e-135">Reinicie o cliente de área de trabalho de equipes.</span><span class="sxs-lookup"><span data-stu-id="2c49e-135">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="2c49e-136">Sair e entrar novamente para o cliente de desktop equipes.</span><span class="sxs-lookup"><span data-stu-id="2c49e-136">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="2c49e-137">Reinicie o cliente de desktop do Outlook.</span><span class="sxs-lookup"><span data-stu-id="2c49e-137">Restart the Outlook desktop client.</span></span> <span data-ttu-id="2c49e-138">(Certifique-se de que o Outlook não está em execução no modo de admin.)</span><span class="sxs-lookup"><span data-stu-id="2c49e-138">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="2c49e-139">Verifique se que o nome da conta de usuário que fez logon não contém espaços.</span><span class="sxs-lookup"><span data-stu-id="2c49e-139">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="2c49e-140">(Isso é um problema conhecido e será corrigido em uma atualização futura.)</span><span class="sxs-lookup"><span data-stu-id="2c49e-140">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="2c49e-141">Certifique-se de logon único (SSO) está habilitado.</span><span class="sxs-lookup"><span data-stu-id="2c49e-141">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="2c49e-142">Para obter orientações gerais sobre como desabilitar suplementos, veja [Exibir, gerenciar e instalar suplemento nos programas do Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="2c49e-142">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="2c49e-143">Saiba mais sobre [reuniões e chamadas no Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span><span class="sxs-lookup"><span data-stu-id="2c49e-143">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

