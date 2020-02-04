---
title: Configuração da reunião criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: As definições de configuração de reunião definem a experiência de ingresso do usuário em conferências agendadas por usuários. Essas configurações se aplicam apenas às reuniões agendadas. Elas não se aplicam à reuniões ad-hoc criadas clicando na opção Reunir Agora no cliente.
ms.openlocfilehash: e98ee52ccab9dbb541d8f09e448f9ac098501ca5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686364"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="e7067-105">Configuração da Reunião: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="e7067-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="e7067-p102">As definições de configuração de reunião definem a experiência de ingresso do usuário em conferências agendadas por usuários. Essas configurações se aplicam apenas às reuniões agendadas. Elas não se aplicam a reuniões ad-hoc criadas clicando na opção **Reunir Agora** no cliente.</span><span class="sxs-lookup"><span data-stu-id="e7067-p102">Meeting configuration settings define the user join experience for conferences scheduled by users. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e7067-109">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="e7067-109">UI Reference</span></span>

<span data-ttu-id="e7067-110">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="e7067-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="e7067-111">**Escopo** Identifica o escopo da configuração de reunião que você está criando ou modificando: global, site ou pool.</span><span class="sxs-lookup"><span data-stu-id="e7067-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="e7067-112">**Nome** As configurações de reunião são nomeadas por padrão, e o nome não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="e7067-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="e7067-113">Os **chamadores PSTN ignoram o lobby** Marque esta caixa de seleção para admitir automaticamente os usuários que estão discando para a conferência por meio de uma linha telefônica PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="e7067-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="e7067-114">Desmarque essa caixa de seleção para encaminhar os chamadores PSTN ao lobby de conferência, no qual esperam até que um apresentador da conferência conceda acesso à conferência.</span><span class="sxs-lookup"><span data-stu-id="e7067-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="e7067-115">**Designar como apresentador** Selecione a categoria de usuários (além do organizador da reunião) que são automaticamente designados como apresentadores quando eles ingressam em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="e7067-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="e7067-116">Independentemente dessa configuração, os apresentadores podem ser explicitamente designados como apresentadores quando a conferência é agendada ou podem ser explicitamente promovidos a apresentadores durante a conferência.</span><span class="sxs-lookup"><span data-stu-id="e7067-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="e7067-117">As opções são:</span><span class="sxs-lookup"><span data-stu-id="e7067-117">The options are:</span></span>

  - <span data-ttu-id="e7067-118">**Nenhuma delas** Selecione esta opção se ninguém diferente do organizador for automaticamente designado como apresentador.</span><span class="sxs-lookup"><span data-stu-id="e7067-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="e7067-119">**Empresa** Selecione esta opção para designar automaticamente os membros da sua organização como apresentadores.</span><span class="sxs-lookup"><span data-stu-id="e7067-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="e7067-120">**Todas as pessoas** Selecione esta opção para designar automaticamente qualquer pessoa para ser um apresentador.</span><span class="sxs-lookup"><span data-stu-id="e7067-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="e7067-121">**Tipo de conferência atribuído por padrão** Esta configuração controla se o suplemento de conferência do Outlook sempre agenda conferências usando a conferência atribuída do organizador, o que significa que as conferências agendadas sempre têm a mesma URL de junção e informações de áudio.</span><span class="sxs-lookup"><span data-stu-id="e7067-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="e7067-122">Marque essa caixa de seleção para que as conferências agendadas sempre usem a mesma URL de participação.</span><span class="sxs-lookup"><span data-stu-id="e7067-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="e7067-123">Desmarque essa caixa de seleção para usar uma URL de participação diferente para cada conferência.</span><span class="sxs-lookup"><span data-stu-id="e7067-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="e7067-124">**Admitir usuários anônimos por padrão** Marque esta caixa de seleção se os usuários anônimos (ou seja, não autenticados) tiverem permissão para participar de conferências por padrão.</span><span class="sxs-lookup"><span data-stu-id="e7067-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="e7067-125">Desmarque essa caixa de seleção se os usuários anônimos não tiverem permissão de participar de conferências por padrão.</span><span class="sxs-lookup"><span data-stu-id="e7067-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="e7067-126">**URL do logotipo** Digite a URL que tem a imagem a ser usada para convites de conferência personalizados.</span><span class="sxs-lookup"><span data-stu-id="e7067-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="e7067-127">**URL da ajuda** Digite a URL de um site em que os usuários podem obter assistência para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="e7067-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="e7067-128">**URL de texto legal** Digite a URL de um site que tenha as informações legais e os avisos de isenção de responsabilidade da conferência.</span><span class="sxs-lookup"><span data-stu-id="e7067-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="e7067-129">**Texto do rodapé personalizado** Digite o texto a ser usado em convites de conferência personalizados.</span><span class="sxs-lookup"><span data-stu-id="e7067-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="e7067-p107">Para obter detalhes sobre como trabalhar com configurações de reunião, consulte [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) na documentação Operações. Para obter detalhes sobre como definir as configurações de reunião para reuniões de grande porte, consulte  [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) na documentação Planejamento.</span><span class="sxs-lookup"><span data-stu-id="e7067-p107">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation. For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](https://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx) in the Planning documentation.</span></span>


