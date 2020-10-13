---
title: Usar modelos de varejo do teams no centro de administração
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
description: Saiba como usar os modelos do teams para criar estruturas de equipe projetadas para as necessidades do revendedor fornecendo configurações, canais e aplicativos pré-instalados predefinidos usando o centro de administração.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40e21687aa3d14b0cb9d51d4ba5f856eada3c538
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424561"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="46b2f-103">Usar modelos de varejo do teams no centro de administração</span><span class="sxs-lookup"><span data-stu-id="46b2f-103">Use Teams retail templates in the admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="46b2f-104">Os modelos de equipe permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="46b2f-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="46b2f-105">Os modelos de equipe têm definições predefinidas de estruturas de equipe projetadas com base nas necessidades do revendedor.</span><span class="sxs-lookup"><span data-stu-id="46b2f-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="46b2f-106">Você pode usar modelos do teams para criar rapidamente os tipos de equipes que funcionam bem para varejistas e implantá-las em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="46b2f-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="46b2f-107">Você também pode estender os modelos de equipe para criar equipes que sejam adequadas às suas necessidades organizacionais específicas.</span><span class="sxs-lookup"><span data-stu-id="46b2f-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="46b2f-108">Neste artigo, apresentaremos cada um dos modelos de equipe e como recomendamos usá-los.</span><span class="sxs-lookup"><span data-stu-id="46b2f-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="46b2f-109">Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em toda a organização de varejo.</span><span class="sxs-lookup"><span data-stu-id="46b2f-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="46b2f-110">Presumimos que você já tenha implantado o serviço do Microsoft Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="46b2f-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="46b2f-111">Se você ainda não distribuiu o Microsoft Teams, comece lendo o guia [como implantar o Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="46b2f-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="46b2f-112">Para saber mais sobre os modelos de equipe em geral, consulte [introdução aos modelos](get-started-with-teams-templates-in-the-admin-console.md)do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="46b2f-112">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="46b2f-113">Organizar uma loja</span><span class="sxs-lookup"><span data-stu-id="46b2f-113">Organize a store</span></span>

<span data-ttu-id="46b2f-114">Reúna seus funcionários de varejo em uma experiência central para gerenciar tarefas, compartilhar documentos e solucionar problemas com o cliente.</span><span class="sxs-lookup"><span data-stu-id="46b2f-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="46b2f-115">Integre aplicativos adicionais para simplificar o início da mudança & processos finais.</span><span class="sxs-lookup"><span data-stu-id="46b2f-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="46b2f-116">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="46b2f-116">Base template type</span></span> |<span data-ttu-id="46b2f-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="46b2f-117">baseTemplateId</span></span> | <span data-ttu-id="46b2f-118">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="46b2f-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="46b2f-119">Organizar uma loja</span><span class="sxs-lookup"><span data-stu-id="46b2f-119">Organize a store</span></span>| `retailStore`|<span data-ttu-id="46b2f-120">Canais</span><span class="sxs-lookup"><span data-stu-id="46b2f-120">Channels:</span></span> <ul><li><span data-ttu-id="46b2f-121">Geral</span><span class="sxs-lookup"><span data-stu-id="46b2f-121">General</span></span><li><span data-ttu-id="46b2f-122">Deslocar entrega</span><span class="sxs-lookup"><span data-stu-id="46b2f-122">Shift handoff</span></span></li><li><span data-ttu-id="46b2f-123">Aprendizagem</span><span class="sxs-lookup"><span data-stu-id="46b2f-123">Learning</span></span></li></ul> <span data-ttu-id="46b2f-124">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="46b2f-124">Apps:</span></span> <ul><li><span data-ttu-id="46b2f-125">Wiki</span><span class="sxs-lookup"><span data-stu-id="46b2f-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="46b2f-126">Colaboração do gerente</span><span class="sxs-lookup"><span data-stu-id="46b2f-126">Manager Collaboration</span></span>

<span data-ttu-id="46b2f-127">O modelo de colaboração do gerente é ideal para criar uma equipe para um conjunto de gerentes colaborar em lojas/regiões etc. Por exemplo, se a sua organização tiver regiões, você pode criar uma equipe de colaboração do gerente para a região da Califórnia e incluir todos os gerentes da loja nessa região, bem como o gerente regional dessa região.</span><span class="sxs-lookup"><span data-stu-id="46b2f-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="46b2f-128">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="46b2f-128">Base template type</span></span>| <span data-ttu-id="46b2f-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="46b2f-129">baseTemplateId</span></span> | <span data-ttu-id="46b2f-130">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="46b2f-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="46b2f-131">Colaboração do gerente de varejo</span><span class="sxs-lookup"><span data-stu-id="46b2f-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="46b2f-132">Canais</span><span class="sxs-lookup"><span data-stu-id="46b2f-132">Channels:</span></span> <ul><li><span data-ttu-id="46b2f-133">Geral</span><span class="sxs-lookup"><span data-stu-id="46b2f-133">General</span></span><li><span data-ttu-id="46b2f-134">Operações</span><span class="sxs-lookup"><span data-stu-id="46b2f-134">Operations</span></span></li><li><span data-ttu-id="46b2f-135">Aprendizagem</span><span class="sxs-lookup"><span data-stu-id="46b2f-135">Learning</span></span></li></ul> <span data-ttu-id="46b2f-136">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="46b2f-136">Apps:</span></span> <ul><li><span data-ttu-id="46b2f-137">Wiki</span><span class="sxs-lookup"><span data-stu-id="46b2f-137">Wiki</span></span></li></ul>|
||||
