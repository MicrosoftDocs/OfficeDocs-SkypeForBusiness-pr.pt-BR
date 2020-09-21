---
title: Introdução aos modelos financeiros do teams usando o console de administração
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar modelos de equipe para criar estruturas de equipe projetadas para necessidades financeiras fornecendo configurações, canais e aplicativos pré-instalados predefinidos usando o console de administração.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 270e03d58a89cf35132f254d2dd1af55d894e8d0
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2020
ms.locfileid: "48135979"
---
# <a name="use-teams-financial-templates-in-the-admin-console"></a><span data-ttu-id="9fe2c-103">Usar modelos financeiros do teams no console de administração</span><span class="sxs-lookup"><span data-stu-id="9fe2c-103">Use Teams financial templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="9fe2c-104">Os modelos de equipe permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="9fe2c-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="9fe2c-105">Os modelos de equipe têm definições predefinidas de estruturas de equipe projetadas em relação às necessidades financeiras.</span><span class="sxs-lookup"><span data-stu-id="9fe2c-105">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="9fe2c-106">Você também pode estender os modelos de equipe para criar equipes que sejam adequadas às suas necessidades organizacionais específicas.</span><span class="sxs-lookup"><span data-stu-id="9fe2c-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="9fe2c-107">Neste artigo, apresentaremos cada um dos modelos de equipe e como recomendamos usá-los.</span><span class="sxs-lookup"><span data-stu-id="9fe2c-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="9fe2c-108">Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em toda a sua organização financeira.</span><span class="sxs-lookup"><span data-stu-id="9fe2c-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="9fe2c-109">Presumimos que você já tenha implantado o serviço do Microsoft Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9fe2c-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="9fe2c-110">Se você ainda não distribuiu o Microsoft Teams, comece lendo o guia [como implantar o Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9fe2c-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="9fe2c-111">Para saber mais sobre os modelos de equipe em geral, consulte [introdução aos modelos](get-started-with-teams-templates-in-the-admin-console.md)do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9fe2c-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="9fe2c-112">Crise global ou evento</span><span class="sxs-lookup"><span data-stu-id="9fe2c-112">Global crisis or event</span></span>

<span data-ttu-id="9fe2c-113">Centralize a colaboração para sua equipe de crise nas unidades de negócios e ajude a criar planos de continuidade de negócios, compartilhar dicas de trabalho remotas, acompanhar a comunicação do cliente e manter todos em um círculo com anúncios e notícias.</span><span class="sxs-lookup"><span data-stu-id="9fe2c-113">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="9fe2c-114">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="9fe2c-114">Base template type</span></span>|<span data-ttu-id="9fe2c-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="9fe2c-115">baseTemplateId</span></span> | <span data-ttu-id="9fe2c-116">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="9fe2c-116">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="9fe2c-117">Colaborar em uma crise global ou em um evento</span><span class="sxs-lookup"><span data-stu-id="9fe2c-117">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="9fe2c-118">Canais</span><span class="sxs-lookup"><span data-stu-id="9fe2c-118">Channels:</span></span> <ul><li><span data-ttu-id="9fe2c-119">Geral</span><span class="sxs-lookup"><span data-stu-id="9fe2c-119">General</span></span><li><span data-ttu-id="9fe2c-120">Comunicados</span><span class="sxs-lookup"><span data-stu-id="9fe2c-120">Announcements</span></span></li><li><span data-ttu-id="9fe2c-121">Notícias do mundo</span><span class="sxs-lookup"><span data-stu-id="9fe2c-121">World news</span></span></li><li><span data-ttu-id="9fe2c-122">Continuidade de negócios</span><span class="sxs-lookup"><span data-stu-id="9fe2c-122">Business continuity</span></span></li><li><span data-ttu-id="9fe2c-123">Trabalho remoto</span><span class="sxs-lookup"><span data-stu-id="9fe2c-123">Remote working</span></span></li><li><span data-ttu-id="9fe2c-124">Comms internas</span><span class="sxs-lookup"><span data-stu-id="9fe2c-124">Internal comms</span></span></li><li><span data-ttu-id="9fe2c-125">Comentários externos</span><span class="sxs-lookup"><span data-stu-id="9fe2c-125">External comms</span></span></li><li><span data-ttu-id="9fe2c-126">Reclamações do cliente</span><span class="sxs-lookup"><span data-stu-id="9fe2c-126">Customer complaints</span></span></li><li><span data-ttu-id="9fe2c-127">Parabéns</span><span class="sxs-lookup"><span data-stu-id="9fe2c-127">Kudos</span></span></li><li><span data-ttu-id="9fe2c-128">Atualização executiva</span><span class="sxs-lookup"><span data-stu-id="9fe2c-128">Executive update</span></span></li></ul><span data-ttu-id="9fe2c-129">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="9fe2c-129">Apps:</span></span> <ul><li><span data-ttu-id="9fe2c-130">Elogia</span><span class="sxs-lookup"><span data-stu-id="9fe2c-130">Praise</span></span></li><li><span data-ttu-id="9fe2c-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="9fe2c-131">Wiki</span></span></li><li><span data-ttu-id="9fe2c-132">Site</span><span class="sxs-lookup"><span data-stu-id="9fe2c-132">Website</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="9fe2c-133">Colaborar dentro de um Branch bancário</span><span class="sxs-lookup"><span data-stu-id="9fe2c-133">Collaborate within a bank branch</span></span>

<span data-ttu-id="9fe2c-134">Centralizar a colaboração para os funcionários da sua agência bancária em Huddles, reuniões com clientes, processos corporativos como colaboração de hipotecas e manter todos em um círculo com anúncios e parabéns.</span><span class="sxs-lookup"><span data-stu-id="9fe2c-134">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="9fe2c-135">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="9fe2c-135">Base template type</span></span> |<span data-ttu-id="9fe2c-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="9fe2c-136">baseTemplateId</span></span>| <span data-ttu-id="9fe2c-137">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="9fe2c-137">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="9fe2c-138">Colaborar dentro de um Branch bancário</span><span class="sxs-lookup"><span data-stu-id="9fe2c-138">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="9fe2c-139">Canais</span><span class="sxs-lookup"><span data-stu-id="9fe2c-139">Channels:</span></span> <ul><li><span data-ttu-id="9fe2c-140">Geral</span><span class="sxs-lookup"><span data-stu-id="9fe2c-140">General</span></span><li><span data-ttu-id="9fe2c-141">Comunicados</span><span class="sxs-lookup"><span data-stu-id="9fe2c-141">Announcements</span></span></li><li><span data-ttu-id="9fe2c-142">Huddles</span><span class="sxs-lookup"><span data-stu-id="9fe2c-142">Huddles</span></span></li><li><span data-ttu-id="9fe2c-143">Reuniões do cliente</span><span class="sxs-lookup"><span data-stu-id="9fe2c-143">Customer meetings</span></span></li><li><span data-ttu-id="9fe2c-144">Treina</span><span class="sxs-lookup"><span data-stu-id="9fe2c-144">Coaching</span></span></li><li><span data-ttu-id="9fe2c-145">Desenvolvimento de habilidades</span><span class="sxs-lookup"><span data-stu-id="9fe2c-145">Skills development</span></span></li><li><span data-ttu-id="9fe2c-146">Processamento de empréstimos</span><span class="sxs-lookup"><span data-stu-id="9fe2c-146">Loan processing</span></span></li><li><span data-ttu-id="9fe2c-147">Reclamações do cliente</span><span class="sxs-lookup"><span data-stu-id="9fe2c-147">Customer complaints</span></span></li><li><span data-ttu-id="9fe2c-148">Parabéns</span><span class="sxs-lookup"><span data-stu-id="9fe2c-148">Kudos</span></span></li><li><span data-ttu-id="9fe2c-149">Coisas divertidas</span><span class="sxs-lookup"><span data-stu-id="9fe2c-149">Fun stuff</span></span></li><li><span data-ttu-id="9fe2c-150">Conformidade</span><span class="sxs-lookup"><span data-stu-id="9fe2c-150">Compliance</span></span></li></ul>|
||||

