---
title: Introdução aos modelos de fabricação do teams no console de administração
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
description: Saiba como usar os modelos do teams para criar estruturas de equipe projetadas para as necessidades de fabricação fornecendo configurações, canais e aplicativos pré-instalados predefinidos usando o console de administração.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 919bfc1bc3e13985ac90484cd203bf93201babd2
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171025"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="6e5b5-103">Usar modelos de fabricação do teams no console de administração</span><span class="sxs-lookup"><span data-stu-id="6e5b5-103">Use Teams manufacturing templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="6e5b5-104">Os modelos de equipe permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="6e5b5-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="6e5b5-105">Os modelos de equipe têm definições predefinidas de estruturas de equipe projetadas com base em necessidades de fabricação.</span><span class="sxs-lookup"><span data-stu-id="6e5b5-105">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="6e5b5-106">Você também pode estender os modelos de equipe para criar equipes que sejam adequadas às suas necessidades organizacionais específicas.</span><span class="sxs-lookup"><span data-stu-id="6e5b5-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="6e5b5-107">Neste artigo, apresentaremos cada um dos modelos de equipe e como recomendamos usá-los.</span><span class="sxs-lookup"><span data-stu-id="6e5b5-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="6e5b5-108">Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em toda a organização de fabricação.</span><span class="sxs-lookup"><span data-stu-id="6e5b5-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="6e5b5-109">Presumimos que você já tenha implantado o serviço do Microsoft Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6e5b5-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="6e5b5-110">Se você ainda não distribuiu o Microsoft Teams, comece lendo o guia [como implantar o Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6e5b5-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="6e5b5-111">Para saber mais sobre os modelos de equipe em geral, consulte [introdução aos modelos](get-started-with-teams-templates-in-the-admin-console.md)do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6e5b5-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="6e5b5-112">Qualidade e segurança</span><span class="sxs-lookup"><span data-stu-id="6e5b5-112">Quality and safety</span></span>

<span data-ttu-id="6e5b5-113">Centralize a comunicação, o acesso a recursos e as operações de fábrica com uma equipe de fábrica.</span><span class="sxs-lookup"><span data-stu-id="6e5b5-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="6e5b5-114">Inclua documentos de política e de procedimento, vídeos de treinamento, notificações de segurança, processos entrega de mudança.</span><span class="sxs-lookup"><span data-stu-id="6e5b5-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="6e5b5-115">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="6e5b5-115">Base template type</span></span>|<span data-ttu-id="6e5b5-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6e5b5-116">baseTemplateId</span></span> | <span data-ttu-id="6e5b5-117">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="6e5b5-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="6e5b5-118">Qualidade e segurança</span><span class="sxs-lookup"><span data-stu-id="6e5b5-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="6e5b5-119">Canais</span><span class="sxs-lookup"><span data-stu-id="6e5b5-119">Channels:</span></span> <ul><li><span data-ttu-id="6e5b5-120">Geral</span><span class="sxs-lookup"><span data-stu-id="6e5b5-120">General</span></span><li><span data-ttu-id="6e5b5-121">Comunicados</span><span class="sxs-lookup"><span data-stu-id="6e5b5-121">Announcements</span></span></li><li><span data-ttu-id="6e5b5-122">Linha 1</span><span class="sxs-lookup"><span data-stu-id="6e5b5-122">Line 1</span></span></li><li><span data-ttu-id="6e5b5-123">Linha 2</span><span class="sxs-lookup"><span data-stu-id="6e5b5-123">Line 2</span></span></li><li><span data-ttu-id="6e5b5-124">Linha 3</span><span class="sxs-lookup"><span data-stu-id="6e5b5-124">Line 3</span></span></li><li><span data-ttu-id="6e5b5-125">Segurança</span><span class="sxs-lookup"><span data-stu-id="6e5b5-125">Safety</span></span></li><li><span data-ttu-id="6e5b5-126">Treinamento</span><span class="sxs-lookup"><span data-stu-id="6e5b5-126">Training</span></span></li><li><span data-ttu-id="6e5b5-127">Manutenção</span><span class="sxs-lookup"><span data-stu-id="6e5b5-127">Maintenance</span></span></li><li><span data-ttu-id="6e5b5-128">Coisas divertidas</span><span class="sxs-lookup"><span data-stu-id="6e5b5-128">Fun stuff</span></span></li></ul> <span data-ttu-id="6e5b5-129">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="6e5b5-129">Apps:</span></span> <ul><li><span data-ttu-id="6e5b5-130">Wiki</span><span class="sxs-lookup"><span data-stu-id="6e5b5-130">Wiki</span></span></li></ul>|
||||
