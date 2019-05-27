---
title: Usar suplemento de Reunião do Microsoft Teams no Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: O Microsoft Teams instala um suplemento no Outlook para que os usuários possam agendar uma reunião do Teams pelo Outlook.
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 801c4f43e9aafa7fe8331d85b601afd584505164
ms.sourcegitcommit: e5cb24ad166268392e692d3d1b92125646e5d66e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "34417439"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="50b11-103">Usar o suplemento de Reunião do Teams no Outlook</span><span class="sxs-lookup"><span data-stu-id="50b11-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="50b11-104">O suplemento de Reunião do Teams é instalado automaticamente para os usuários que têm o Microsoft Teams e o Office 2013 ou o Office 2016 instalados em seus computadores Windows.</span><span class="sxs-lookup"><span data-stu-id="50b11-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="50b11-105">Os usuários verão o suplemento de Reunião do Teams na faixa de opções Calendário do Outlook.</span><span class="sxs-lookup"><span data-stu-id="50b11-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Captura de tela do suplemento do Teams na faixa de opções do Outlook.](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> <span data-ttu-id="50b11-107">Os usuários do Windows 7 devem instalar a [atualização para o Universal C Runtime no Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) para que o suplemento de Reunião do Teams funcione.</span><span class="sxs-lookup"><span data-stu-id="50b11-107">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>

<span data-ttu-id="50b11-108">Se o suplemento de Reunião do Teams não for exibido, instrua os usuários a fechar o Outlook e o Teams e reiniciar o cliente Teams primeiro, depois entrar no Teams e então reiniciar o cliente Outlook, exatamente nessa ordem.</span><span class="sxs-lookup"><span data-stu-id="50b11-108">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="50b11-109">O botão reunião do teams no Outlook para Mac aparecerá na faixa de opções do Outlook para Mac se o Outlook estiver executando o Build de produção 16,20 e posterior.</span><span class="sxs-lookup"><span data-stu-id="50b11-109">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running Production Build 16.20 and later.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="50b11-110">Requisitos de autenticação</span><span class="sxs-lookup"><span data-stu-id="50b11-110">Authentication requirements</span></span>

<span data-ttu-id="50b11-111">O suplemento de Reunião do Teams requer que os usuários entrem no Teams usando a autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="50b11-111">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="50b11-112">Se os usuários não utilizarem esse método para entrar, poderão usar o cliente Teams, mas não conseguirão agendar reuniões online do Teams usando o suplemento do Outlook.</span><span class="sxs-lookup"><span data-stu-id="50b11-112">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="50b11-113">Você pode corrigir isso da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="50b11-113">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="50b11-114">Se a autenticação moderna não estiver configurada para a sua organização, você deverá fazer isso.</span><span class="sxs-lookup"><span data-stu-id="50b11-114">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="50b11-115">Se a autenticação moderna estiver configurada, mas os usuários cancelaram a caixa de diálogo, você deverá instruí-los para entrar novamente usando a autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="50b11-115">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="50b11-116">Para saber mais sobre como configurar a autenticação, veja [Modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="50b11-116">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="50b11-117">Habilitar reuniões privadas</span><span class="sxs-lookup"><span data-stu-id="50b11-117">Enable private meetings</span></span>

<span data-ttu-id="50b11-118">**Permitir agendamento de reuniões particulares** deve estar habilitado no centro de administração do Microsoft Teams para que o plug-in seja implantado.</span><span class="sxs-lookup"><span data-stu-id="50b11-118">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the plug-in to get deployed.</span></span> <span data-ttu-id="50b11-119">No centro de administração, vá para **Reuniões** > **Políticas de Reunião**, e na seção **Geral**, ative **Permitir agendamento de reuniões particulares** para Ativado.)</span><span class="sxs-lookup"><span data-stu-id="50b11-119">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Captura de tela das configurações no centro de administração do Microsoft Teams.](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="50b11-121">O cliente Teams instala o suplemento correto, determinando se os usuários precisam da versão de 32 ou de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="50b11-121">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="50b11-122">Talvez os usuários precisem reiniciar o Outlook após uma instalação ou atualização do Teams para obter o suplemento mais recente.</span><span class="sxs-lookup"><span data-stu-id="50b11-122">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="50b11-123">Outras considerações</span><span class="sxs-lookup"><span data-stu-id="50b11-123">Other considerations</span></span>

<span data-ttu-id="50b11-124">O suplemento de Reunião do Teams ainda está desenvolvendo funcionalidades, então esteja ciente do seguinte:</span><span class="sxs-lookup"><span data-stu-id="50b11-124">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="50b11-125">A sondagem ainda não está disponível.</span><span class="sxs-lookup"><span data-stu-id="50b11-125">Polling isn't yet available.</span></span>
- <span data-ttu-id="50b11-126">O quadro de comunicações está começando a ser revertido.</span><span class="sxs-lookup"><span data-stu-id="50b11-126">Whiteboard is starting to roll out.</span></span>
- <span data-ttu-id="50b11-127">As opções de reunião ainda não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="50b11-127">Meeting options are currently not available.</span></span>
- <span data-ttu-id="50b11-128">No momento, você pode apenas convidar pessoas da sua empresa, pois ainda não é possível o ingresso de usuários externos nas reuniões.</span><span class="sxs-lookup"><span data-stu-id="50b11-128">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="50b11-129">O suplemento destina-se a reuniões agendadas com participantes específicos, não a reuniões em um canal.</span><span class="sxs-lookup"><span data-stu-id="50b11-129">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="50b11-130">As reuniões do canal devem ser agendadas dentro do Teams.</span><span class="sxs-lookup"><span data-stu-id="50b11-130">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="50b11-131">Atualmente, o suplemento de Reunião do Teams no Outlook está disponível apenas para usuários do Windows, mas o suporte para Mac será disponibilizado em breve.</span><span class="sxs-lookup"><span data-stu-id="50b11-131">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="50b11-132">O suplemento não funcionará se houver um proxy de autenticação no caminho de rede do computador do usuário e dos serviços do Teams.</span><span class="sxs-lookup"><span data-stu-id="50b11-132">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="50b11-133">O suplemento está sendo implementado de forma incremental e pode não estar disponível para sua organização ainda.</span><span class="sxs-lookup"><span data-stu-id="50b11-133">The add-in is being rolled out incrementally and might not be available for your organization yet.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="50b11-134">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="50b11-134">Troubleshooting</span></span>

<span data-ttu-id="50b11-135">Se você não conseguir instalar o suplemento Teams Meeting para o Outlook, tente estas etapas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="50b11-135">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="50b11-136">Garantir que todas as atualizações disponíveis para o cliente de Outlook desktop tenham sido aplicadas</span><span class="sxs-lookup"><span data-stu-id="50b11-136">Ensure all available updates for Outlook desktop client have been applied</span></span> 
- <span data-ttu-id="50b11-137">Reinicie o cliente de área de trabalho do Teams.</span><span class="sxs-lookup"><span data-stu-id="50b11-137">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="50b11-138">Saia e entre novamente no cliente de área de trabalho do Teams.</span><span class="sxs-lookup"><span data-stu-id="50b11-138">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="50b11-139">Reinicie o cliente para área de trabalho do Outlook.</span><span class="sxs-lookup"><span data-stu-id="50b11-139">Restart the Outlook desktop client.</span></span> <span data-ttu-id="50b11-140">(Certifique-se de que o Outlook não esteja sendo executado no modo de administrador.)</span><span class="sxs-lookup"><span data-stu-id="50b11-140">(Make sure Outlook isn’t running in admin mode.)</span></span>
- <span data-ttu-id="50b11-141">Certifique-se de que o nome da conta do usuário que efetuou logon não contenha espaços.</span><span class="sxs-lookup"><span data-stu-id="50b11-141">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="50b11-142">(Esse é um problema conhecido e será corrigido em uma atualização futura.)</span><span class="sxs-lookup"><span data-stu-id="50b11-142">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="50b11-143">Certifique-se de que o logon único (SSO) esteja ativado.</span><span class="sxs-lookup"><span data-stu-id="50b11-143">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="50b11-144">Para obter orientações gerais sobre como desabilitar suplementos, veja [Exibir, gerenciar e instalar suplemento nos programas do Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="50b11-144">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="50b11-145">Saiba mais sobre [reuniões e chamadas no Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span><span class="sxs-lookup"><span data-stu-id="50b11-145">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

