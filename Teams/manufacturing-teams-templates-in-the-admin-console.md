---
title: Começar a usar modelos de fabricação do Teams no centro de administração
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
description: Saiba como usar. Modelos do Teams para criar estruturas de equipe projetadas para necessidades de fabricação, fornecendo configurações, canais e aplicativos pré-instalados predefinidos usando o centro de administração.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 51a28e997e5c7c0b36fb49cd0bb46768b7808a29
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662216"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-center"></a><span data-ttu-id="9f4c2-104">Usar modelos de fabricação do Teams no centro de administração</span><span class="sxs-lookup"><span data-stu-id="9f4c2-104">Use Teams manufacturing templates in the admin center</span></span>

<span data-ttu-id="9f4c2-105">Os modelos do Teams permitem que você crie equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="9f4c2-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="9f4c2-106">Os modelos do Teams têm definições predefinida de estruturas de equipe projetadas em torno das necessidades de fabricação.</span><span class="sxs-lookup"><span data-stu-id="9f4c2-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="9f4c2-107">Você também pode estender os modelos do Teams para criar equipes adaptadas às suas necessidades organizacionais específicas.</span><span class="sxs-lookup"><span data-stu-id="9f4c2-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="9f4c2-108">Neste artigo, apresentamos cada um dos modelos do Teams e recomendamos como usá-los.</span><span class="sxs-lookup"><span data-stu-id="9f4c2-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="9f4c2-109">Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em sua organização de fabricação.</span><span class="sxs-lookup"><span data-stu-id="9f4c2-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="9f4c2-110">Você já implantou o serviço do Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9f4c2-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="9f4c2-111">Se você ainda não tiver lançado o Teams, comece lendo o livro Como [lançar o Microsoft Teams.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="9f4c2-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="9f4c2-112">Para saber mais sobre modelos de equipe em geral, consulte [Começar a usar modelos do Teams.](get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="9f4c2-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="9f4c2-113">Qualidade e segurança</span><span class="sxs-lookup"><span data-stu-id="9f4c2-113">Quality and safety</span></span>

<span data-ttu-id="9f4c2-114">Centralizar a comunicação, o acesso a recursos e operações de plantas com uma equipe de Fábrica.</span><span class="sxs-lookup"><span data-stu-id="9f4c2-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="9f4c2-115">Inclua documentos de política e procedimento, vídeos de treinamento, avisos de segurança, processos de troca de turnos.</span><span class="sxs-lookup"><span data-stu-id="9f4c2-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="9f4c2-116">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="9f4c2-116">Base template type</span></span>|<span data-ttu-id="9f4c2-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="9f4c2-117">baseTemplateId</span></span>| <span data-ttu-id="9f4c2-118">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="9f4c2-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="9f4c2-119">Qualidade e segurança</span><span class="sxs-lookup"><span data-stu-id="9f4c2-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="9f4c2-120">Canais:</span><span class="sxs-lookup"><span data-stu-id="9f4c2-120">Channels:</span></span> <ul><li><span data-ttu-id="9f4c2-121">Geral</span><span class="sxs-lookup"><span data-stu-id="9f4c2-121">General</span></span><li><span data-ttu-id="9f4c2-122">Anúncios</span><span class="sxs-lookup"><span data-stu-id="9f4c2-122">Announcements</span></span></li><li><span data-ttu-id="9f4c2-123">Linha 1</span><span class="sxs-lookup"><span data-stu-id="9f4c2-123">Line 1</span></span></li><li><span data-ttu-id="9f4c2-124">Linha 2</span><span class="sxs-lookup"><span data-stu-id="9f4c2-124">Line 2</span></span></li><li><span data-ttu-id="9f4c2-125">Linha 3</span><span class="sxs-lookup"><span data-stu-id="9f4c2-125">Line 3</span></span></li><li><span data-ttu-id="9f4c2-126">Segurança</span><span class="sxs-lookup"><span data-stu-id="9f4c2-126">Safety</span></span></li><li><span data-ttu-id="9f4c2-127">Treinamento</span><span class="sxs-lookup"><span data-stu-id="9f4c2-127">Training</span></span></li><li><span data-ttu-id="9f4c2-128">Manutenção</span><span class="sxs-lookup"><span data-stu-id="9f4c2-128">Maintenance</span></span></li><li><span data-ttu-id="9f4c2-129">Coisas divertidas</span><span class="sxs-lookup"><span data-stu-id="9f4c2-129">Fun stuff</span></span></li></ul> <span data-ttu-id="9f4c2-130">Apps:</span><span class="sxs-lookup"><span data-stu-id="9f4c2-130">Apps:</span></span> <ul><li><span data-ttu-id="9f4c2-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="9f4c2-131">Wiki</span></span></li><li><span data-ttu-id="9f4c2-132">Planner</span><span class="sxs-lookup"><span data-stu-id="9f4c2-132">Planner</span></span></li></ul>|
||||
