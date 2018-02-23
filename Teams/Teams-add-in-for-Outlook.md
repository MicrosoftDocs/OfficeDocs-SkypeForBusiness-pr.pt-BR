---
title: "Usar suplemento de Reunião do Microsoft Teams no Outlook"
author: ChuckEdmonson
ms.author: chucked
manager: lolaj
ms.date: 01/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: "O Microsoft Teams instala um suplemento no Outlook para que os usuários possam agendar uma reunião do Teams pelo Outlook."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c8c8930787d74fdc0dddf2b7987a967e130721d2
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2018
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="406c7-103">Usar o suplemento de Reunião do Teams no Outlook</span><span class="sxs-lookup"><span data-stu-id="406c7-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="406c7-104">O suplemento de Reunião do Teams é instalado automaticamente para os usuários que têm o Microsoft Teams e o Office 2013 ou o Office 2016 instalados em seus computadores Windows.</span><span class="sxs-lookup"><span data-stu-id="406c7-104">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="406c7-105">Os usuários verão o suplemento de Reunião do Teams na faixa de opções Calendário do Outlook.</span><span class="sxs-lookup"><span data-stu-id="406c7-105">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span> 

![Captura de tela do suplemento do Teams na faixa de opções do Outlook.](media/Teams-add-in-for-Outlook.png)

<span data-ttu-id="406c7-107">Se o suplemento de Reunião do Teams não for exibido, instrua os usuários a fechar o Outlook e o Teams e reiniciar o cliente Teams primeiro, depois entrar no Teams e então reiniciar o cliente Outlook, exatamente nessa ordem.</span><span class="sxs-lookup"><span data-stu-id="406c7-107">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>

> [!NOTE]
> <span data-ttu-id="406c7-108">O suplemento de Reunião do Teams para o Outlook ainda não está disponível para usuários do Mac.</span><span class="sxs-lookup"><span data-stu-id="406c7-108">The Teams Meeting add-in for Outlook is currently not available for Mac users.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="406c7-109">Requisitos de autenticação</span><span class="sxs-lookup"><span data-stu-id="406c7-109">Authentication requirements</span></span>

<span data-ttu-id="406c7-110">O suplemento de Reunião do Teams requer que os usuários entrem no Teams usando a autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="406c7-110">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="406c7-111">Se os usuários não utilizarem esse método para entrar, poderão usar o cliente Teams, mas não conseguirão agendar reuniões online do Teams usando o suplemento do Outlook.</span><span class="sxs-lookup"><span data-stu-id="406c7-111">If users do not use this method to sign in, they’ll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="406c7-112">Você pode corrigir isso da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="406c7-112">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="406c7-113">Se a autenticação moderna não estiver configurada para a sua organização, você deverá fazer isso.</span><span class="sxs-lookup"><span data-stu-id="406c7-113">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="406c7-114">Se a autenticação moderna estiver configurada, mas os usuários cancelaram a caixa de diálogo, você deverá instruí-los para entrar novamente usando a autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="406c7-114">If Modern Authentication is configured, but they cancelled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="406c7-115">Para saber mais sobre como configurar a autenticação, veja [Modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="406c7-115">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="406c7-116">Habilitar reuniões privadas</span><span class="sxs-lookup"><span data-stu-id="406c7-116">Enable private meetings</span></span>

<span data-ttu-id="406c7-117">A permissão de agendamento de reuniões privadas deve ser habilitada no [Centro de administração do Office 365](https://portal.office.com/adminportal/home) para que o plug-in seja implantado.</span><span class="sxs-lookup"><span data-stu-id="406c7-117">Allow scheduling for private meetings must be enabled from the [Office 365 admin center](https://portal.office.com/adminportal/home) for the plug-in to get deployed.</span></span>

![Captura de tela das configurações da seção Chamadas e reuniões do Centro de administração do Office 365.](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="406c7-119">O cliente Teams instala o suplemento correto, determinando se os usuários precisam da versão de 32 ou de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="406c7-119">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="406c7-120">Talvez os usuários precisem reiniciar o Outlook após uma instalação ou atualização do Teams para obter o suplemento mais recente.</span><span class="sxs-lookup"><span data-stu-id="406c7-120">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="other-considerations"></a><span data-ttu-id="406c7-121">Outras considerações</span><span class="sxs-lookup"><span data-stu-id="406c7-121">Other planning considerations</span></span>

<span data-ttu-id="406c7-122">O suplemento de Reunião do Teams ainda está desenvolvendo funcionalidades, então esteja ciente do seguinte:</span><span class="sxs-lookup"><span data-stu-id="406c7-122">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>
- <span data-ttu-id="406c7-123">Alguns recursos de reunião online, como a gravação, a votação e o quadro de comunicações, ainda não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="406c7-123">Some online meeting features, such as recording, polling, and whiteboarding are not yet available.</span></span>
- <span data-ttu-id="406c7-124">As opções de reunião ainda não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="406c7-124">Meeting options are currently not available.</span></span>
- <span data-ttu-id="406c7-125">No momento, você pode apenas convidar pessoas da sua empresa, pois ainda não é possível o ingresso de usuários externos nas reuniões.</span><span class="sxs-lookup"><span data-stu-id="406c7-125">Currently, you can only invite people from within your company, as it is not yet possible for external users to join meetings.</span></span>
- <span data-ttu-id="406c7-126">O suplemento destina-se a reuniões agendadas com participantes específicos, não a reuniões em um canal.</span><span class="sxs-lookup"><span data-stu-id="406c7-126">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="406c7-127">As reuniões do canal devem ser agendadas dentro do Teams.</span><span class="sxs-lookup"><span data-stu-id="406c7-127">Channel meetings must be scheduled from within Teams.</span></span> <span data-ttu-id="406c7-128">Atualmente, o suplemento de Reunião do Teams no Outlook está disponível apenas para usuários do Windows, mas o suporte para Mac será disponibilizado em breve.</span><span class="sxs-lookup"><span data-stu-id="406c7-128">Currently, the Teams Meeting add-in in Outlook is only available for Windows users, but support for Mac is coming.</span></span>
- <span data-ttu-id="406c7-129">O suplemento não funcionará se houver um proxy de autenticação no caminho de rede do computador do usuário e dos serviços do Teams.</span><span class="sxs-lookup"><span data-stu-id="406c7-129">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>

<span data-ttu-id="406c7-130">Se você quiser que o suplemento de Reunião do Teams seja exibido para os usuários, será possível removê-lo.</span><span class="sxs-lookup"><span data-stu-id="406c7-130">If you do not want the Teams Meeting add-in to appear for users, you can remove it.</span></span> <span data-ttu-id="406c7-131">Para obter orientações gerais sobre como desabilitar suplementos, veja [Exibir, gerenciar e instalar suplemento nos programas do Office](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span><span class="sxs-lookup"><span data-stu-id="406c7-131">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="406c7-132">Saiba mais sobre [reuniões e chamadas no Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span><span class="sxs-lookup"><span data-stu-id="406c7-132">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

