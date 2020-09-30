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
description: Saiba como usar. Modelos de equipe para criar estruturas de equipe projetadas para as necessidades de fabricação fornecendo configurações, canais e aplicativos pré-instalados predefinidos usando o console de administração.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb7769a193e95f31db8ffb02b6120babfa05c661
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308394"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="7e0a3-104">Usar modelos de fabricação do teams no console de administração</span><span class="sxs-lookup"><span data-stu-id="7e0a3-104">Use Teams manufacturing templates in the admin console</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="7e0a3-105">Os modelos de equipe permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="7e0a3-106">Os modelos de equipe têm definições predefinidas de estruturas de equipe projetadas com base em necessidades de fabricação.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="7e0a3-107">Você também pode estender os modelos de equipe para criar equipes que sejam adequadas às suas necessidades organizacionais específicas.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="7e0a3-108">Neste artigo, apresentamos cada um dos modelos de equipe e recomendamos usá-los.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="7e0a3-109">Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em toda a organização de fabricação.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="7e0a3-110">Você já implantou o serviço Microsoft Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="7e0a3-111">Se você ainda não distribuiu o Microsoft Teams, comece lendo o guia [como implantar o Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7e0a3-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="7e0a3-112">Para saber mais sobre os modelos de equipe em geral, confira [introdução aos modelos](get-started-with-teams-templates-in-the-admin-console.md)do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="7e0a3-113">Qualidade e segurança</span><span class="sxs-lookup"><span data-stu-id="7e0a3-113">Quality and safety</span></span>

<span data-ttu-id="7e0a3-114">Centralize a comunicação, o acesso a recursos e as operações de fábrica com uma equipe de fábrica.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="7e0a3-115">Inclua documentos de política e de procedimento, vídeos de treinamento, notificações de segurança, processos entrega de mudança.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="7e0a3-116">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="7e0a3-116">Base template type</span></span>|<span data-ttu-id="7e0a3-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7e0a3-117">baseTemplateId</span></span> | <span data-ttu-id="7e0a3-118">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="7e0a3-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="7e0a3-119">Qualidade e segurança</span><span class="sxs-lookup"><span data-stu-id="7e0a3-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="7e0a3-120">Canais</span><span class="sxs-lookup"><span data-stu-id="7e0a3-120">Channels:</span></span> <ul><li><span data-ttu-id="7e0a3-121">Geral</span><span class="sxs-lookup"><span data-stu-id="7e0a3-121">General</span></span><li><span data-ttu-id="7e0a3-122">Comunicados</span><span class="sxs-lookup"><span data-stu-id="7e0a3-122">Announcements</span></span></li><li><span data-ttu-id="7e0a3-123">Linha 1</span><span class="sxs-lookup"><span data-stu-id="7e0a3-123">Line 1</span></span></li><li><span data-ttu-id="7e0a3-124">Linha 2</span><span class="sxs-lookup"><span data-stu-id="7e0a3-124">Line 2</span></span></li><li><span data-ttu-id="7e0a3-125">Linha 3</span><span class="sxs-lookup"><span data-stu-id="7e0a3-125">Line 3</span></span></li><li><span data-ttu-id="7e0a3-126">Segurança</span><span class="sxs-lookup"><span data-stu-id="7e0a3-126">Safety</span></span></li><li><span data-ttu-id="7e0a3-127">Treinamento</span><span class="sxs-lookup"><span data-stu-id="7e0a3-127">Training</span></span></li><li><span data-ttu-id="7e0a3-128">Manutenção</span><span class="sxs-lookup"><span data-stu-id="7e0a3-128">Maintenance</span></span></li><li><span data-ttu-id="7e0a3-129">Coisas divertidas</span><span class="sxs-lookup"><span data-stu-id="7e0a3-129">Fun stuff</span></span></li></ul> <span data-ttu-id="7e0a3-130">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="7e0a3-130">Apps:</span></span> <ul><li><span data-ttu-id="7e0a3-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="7e0a3-131">Wiki</span></span></li></ul>|
||||
