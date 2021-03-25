---
title: Configuração da Reunião Criar Novo ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
ROBOTS: NOINDEX, NOFOLLOW
description: As definições de configuração de reunião definem a experiência de ingresso do usuário em conferências agendadas por usuários. Essas configurações se aplicam apenas às reuniões agendadas. Eles não se aplicam a reuniões ad hoc criadas clicando na opção Reunir Agora no cliente.
ms.openlocfilehash: 3d37b1894531a62f605f083cbe1e2f36953f2ff2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121125"
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a><span data-ttu-id="e2c8e-105">Configuração de Reunião: Criar Novo ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="e2c8e-105">Meeting Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="e2c8e-106">As definições de configuração de reunião definem a experiência de ingresso do usuário em conferências agendadas por usuários.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-106">Meeting configuration settings define the user join experience for conferences scheduled by users.</span></span> <span data-ttu-id="e2c8e-107">Essas configurações se aplicam apenas às reuniões agendadas.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="e2c8e-108">Eles não se aplicam a reuniões ad hoc criadas clicando na opção **Reunir Agora** no cliente.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-108">They do not apply to ad-hoc meetings created by clicking the **Meet Now** option in the client.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e2c8e-109">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="e2c8e-109">UI Reference</span></span>

<span data-ttu-id="e2c8e-110">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="e2c8e-111">**Escopo** Identifica o escopo da configuração de reunião que você está criando ou modificando: global, site ou pool.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-111">**Scope** Identifies the scope of the meeting configuration that you are creating or modifying: global, site, or pool.</span></span>

- <span data-ttu-id="e2c8e-112">**Nome** As configurações de reunião são nomeadas por padrão e o nome não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-112">**Name** Meeting configurations are named by default, and the name cannot be changed.</span></span>

- <span data-ttu-id="e2c8e-113">**Chamadores PSTN ignoram lobby** Marque essa caixa de seleção para admitir automaticamente os usuários que estão discando na conferência por meio de uma linha telefônica PSTN (rede telefônica pública comutado).</span><span class="sxs-lookup"><span data-stu-id="e2c8e-113">**PSTN callers bypass lobby** Select this check box to automatically admit users who are dialing in to the conference over a public switched telephone network (PSTN) phone line.</span></span> <span data-ttu-id="e2c8e-114">Desmarque essa caixa de seleção para encaminhar os chamadores PSTN ao lobby de conferência, no qual esperam até que um apresentar da conferência conceda acesso à conferência.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-114">Clear this check box to route PSTN callers to the conference lobby, where they are on hold until a conference presenter grants them access to the conference.</span></span>

- <span data-ttu-id="e2c8e-115">**Designar como apresentador** Selecione a categoria de usuários (além do organizador da reunião) que são automaticamente designados como apresentadores quando inserem em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-115">**Designate as presenter** Select the category of users (besides the meeting organizer) who are automatically designated as presenters when they join a conference.</span></span> <span data-ttu-id="e2c8e-116">Independentemente dessa configuração, os apresentadores podem ser explicitamente designados como apresentadores quando a conferência é agendada ou podem ser explicitamente promovidos a apresentadores durante a conferência.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-116">Regardless of this setting, presenters can be explicitly designated as presenters when the conference is scheduled, or they can be explicitly promoted to presenter during the conference.</span></span> <span data-ttu-id="e2c8e-117">As opções são:</span><span class="sxs-lookup"><span data-stu-id="e2c8e-117">The options are:</span></span>

  - <span data-ttu-id="e2c8e-118">**Nenhum** Selecione essa opção se ninguém além do organizador for designado automaticamente como apresentador.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-118">**None** Select this option if no one other than the organizer is automatically designated as a presenter.</span></span>

  - <span data-ttu-id="e2c8e-119">**Empresa** Selecione essa opção para designar automaticamente somente membros da sua organização como apresentadores.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-119">**Company** Select this option to automatically designate only members of your organization as presenters.</span></span>

  - <span data-ttu-id="e2c8e-120">**Todos** Selecione essa opção para designar automaticamente qualquer pessoa para ser apresentador.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-120">**Everyone** Select this option to automatically designate anyone to be a presenter.</span></span>

- <span data-ttu-id="e2c8e-121">**Tipo de conferência atribuído por padrão** Essa configuração controla se o Outlook Conferencing Addin sempre agenda conferências usando a conferência atribuída do organizador, o que significa que as conferências agendadas sempre têm a mesma URL de junção e informações de áudio.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-121">**Assigned conference type by default** This setting controls whether the Outlook Conferencing Addin always schedules conferences by using the organizer's assigned conference, which means that scheduled conferences always have the same join URL and audio information.</span></span> <span data-ttu-id="e2c8e-122">Marque essa caixa de seleção para que as conferências agendadas sempre usem o mesmo URL de ingresso.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-122">Select this check box to have scheduled conferences always use the same join URL.</span></span> <span data-ttu-id="e2c8e-123">Desmarque essa caixa de seleção para usar URL de ingresso diferente para cada conferência.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-123">Clear this check box to use a different join URL for each conference.</span></span>

- <span data-ttu-id="e2c8e-124">**Admitir usuários anônimos por padrão** Marque essa caixa de seleção se usuários anônimos (ou seja, não autenticados) podem participar de conferências por padrão.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-124">**Admit anonymous users by default** Select this check box if anonymous (that is, unauthenticated) users are allowed to attend conferences by default.</span></span> <span data-ttu-id="e2c8e-125">Desmarque essa caixa de seleção se os usuários anônimos não tiverem permissão de participar de conferências por padrão.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-125">Clear this check box if anonymous users are not allowed to attend conferences by default.</span></span>

- <span data-ttu-id="e2c8e-126">**URL de logotipo** Digite a URL que tem a imagem a ser usada para convites de conferência personalizados.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-126">**Logo URL** Type the URL that has the image to be used for custom conference invitations.</span></span>

- <span data-ttu-id="e2c8e-127">**URL da Ajuda** Digite a URL de um site onde os usuários podem obter assistência para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-127">**Help URL** Type the URL for a website where users can obtain assistance for joining the conference.</span></span>

- <span data-ttu-id="e2c8e-128">**URL de texto legal** Digite a URL de um site que tenha as informações legais e avisos de isenção de responsabilidade para a conferência.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-128">**Legal text URL** Type the URL for a website that has the legal information and disclaimers for the conference.</span></span>

- <span data-ttu-id="e2c8e-129">**Texto do rodapé personalizado** Digite o texto a ser usado em convites de conferência personalizados.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-129">**Custom footer text** Type the text to be used on custom conference invitations.</span></span>

<span data-ttu-id="e2c8e-130">Para obter detalhes sobre como trabalhar com configurações de reunião, consulte [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-130">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) in the Operations documentation.</span></span> <span data-ttu-id="e2c8e-131">Para obter detalhes sobre como definir as configurações de reunião para reuniões de grande porte, consulte [Setting Up Support for Large Meetings](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) na documentação Planejamento.</span><span class="sxs-lookup"><span data-stu-id="e2c8e-131">For details about setting meeting configurations for large meetings, see [Setting Up Support for Large Meetings](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-support-for-large-meetings) in the Planning documentation.</span></span>