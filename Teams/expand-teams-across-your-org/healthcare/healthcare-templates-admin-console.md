---
title: Criar uma equipe usando modelos de saúde
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Use modelos de equipe no centro de administração ou com o Microsoft Graph para criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f90ddfa9682c7000c4698977c51a39c9631ff9b1
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684348"
---
# <a name="use-a-healthcare-team-templates"></a><span data-ttu-id="66215-103">Usar modelos de equipe de saúde</span><span class="sxs-lookup"><span data-stu-id="66215-103">Use a healthcare team templates</span></span>

<span data-ttu-id="66215-104">Os modelos permitem que você crie equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="66215-104">Templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="66215-105">Para organizações de saúde, os modelos podem ser especialmente poderosos, pois fornecem estrutura para que os usuários se orientem com como usar efetivamente Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66215-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Microsoft Teams.</span></span> <span data-ttu-id="66215-106">Os modelos também permitem que os administradores implantem equipes consistentes em suas organizações.</span><span class="sxs-lookup"><span data-stu-id="66215-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="66215-107">Este artigo é para você, se você for responsável por planejar, implantar e gerenciar várias equipes em sua organização de assistência médica.</span><span class="sxs-lookup"><span data-stu-id="66215-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="66215-108">Escolha um método para criar equipes com os modelos de saúde da equipe:</span><span class="sxs-lookup"><span data-stu-id="66215-108">Choose a method for creating teams with the team healthcare templates:</span></span>

| <span data-ttu-id="66215-109">Quem</span><span class="sxs-lookup"><span data-stu-id="66215-109">Who</span></span> | <span data-ttu-id="66215-110">Método a ser usado:</span><span class="sxs-lookup"><span data-stu-id="66215-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="66215-111">Administradores e profissionais de TI</span><span class="sxs-lookup"><span data-stu-id="66215-111">Admins and IT Professionals</span></span> | <span data-ttu-id="66215-112">[Use o Teams de administração](#use-the-team-templates-in-the-admin-center) para criar equipes com base nos modelos de equipe de saúde.</span><span class="sxs-lookup"><span data-stu-id="66215-112">[Use the Teams admin center](#use-the-team-templates-in-the-admin-center) to create teams based on the healthcare team templates.</span></span>|
| <span data-ttu-id="66215-113">Os desenvolvedores e integradores de sistemas</span><span class="sxs-lookup"><span data-stu-id="66215-113">Developers and systems integrators</span></span> | <span data-ttu-id="66215-114">[Use o microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) para criar uma equipe com base nos modelos de equipe de saúde.</span><span class="sxs-lookup"><span data-stu-id="66215-114">[Use the Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) to create a team based on the healthcare team templates.</span></span> |

## <a name="use-the-team-templates-in-the-admin-center"></a><span data-ttu-id="66215-115">Usar os modelos de equipe no centro de administração</span><span class="sxs-lookup"><span data-stu-id="66215-115">Use the team templates in the admin center</span></span>

<span data-ttu-id="66215-116">Microsoft Teams os administradores podem usar o Teams de administração para criar equipes com os modelos de equipe.</span><span class="sxs-lookup"><span data-stu-id="66215-116">Microsoft Teams admins can use the Teams admin center to create teams with the team templates.</span></span> <span data-ttu-id="66215-117">Atualmente, oferecemos dois modelos de assistência médica de terceiros que você pode usar para diversas situações.</span><span class="sxs-lookup"><span data-stu-id="66215-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="66215-118">Para saber mais sobre modelos de equipe em geral, consulte [Começar a usar modelos de equipe no centro de administração](../../get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="66215-118">To learn more about team templates in general, see [Get started with team templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="66215-119">Colabore no atendimento aos pacientes</span><span class="sxs-lookup"><span data-stu-id="66215-119">Collaborate on patient care</span></span>

 <span data-ttu-id="66215-120">Simplifique a comunicação e a colaboração dos serviços de saúde dentro de um departamento, um ou mais.</span><span class="sxs-lookup"><span data-stu-id="66215-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="66215-121">O modelo pode ser usado para facilitar o gerenciamento dos pacientes e as necessidades operacionais de um paciente.</span><span class="sxs-lookup"><span data-stu-id="66215-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="66215-122">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="66215-122">Base template type</span></span> |<span data-ttu-id="66215-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="66215-123">baseTemplateId</span></span>| <span data-ttu-id="66215-124">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="66215-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="66215-125">Colabore no atendimento aos pacientes</span><span class="sxs-lookup"><span data-stu-id="66215-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="66215-126">Canais:</span><span class="sxs-lookup"><span data-stu-id="66215-126">Channels:</span></span><ul><li><span data-ttu-id="66215-127">Geral</span><span class="sxs-lookup"><span data-stu-id="66215-127">General</span></span></li><li><span data-ttu-id="66215-128">Comunicados</span><span class="sxs-lookup"><span data-stu-id="66215-128">Announcements</span></span></li><li><span data-ttu-id="66215-129">Insuidades</span><span class="sxs-lookup"><span data-stu-id="66215-129">Huddles</span></span></li><li><span data-ttu-id="66215-130">Rodadas</span><span class="sxs-lookup"><span data-stu-id="66215-130">Rounds</span></span></li><li><span data-ttu-id="66215-131">Estrelada</span><span class="sxs-lookup"><span data-stu-id="66215-131">Staffing</span></span></li><li><span data-ttu-id="66215-132">Treinamento</span><span class="sxs-lookup"><span data-stu-id="66215-132">Training</span></span></li></ul> <span data-ttu-id="66215-133">Apps:</span><span class="sxs-lookup"><span data-stu-id="66215-133">Apps:</span></span> <ul><li><span data-ttu-id="66215-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="66215-134">Wiki</span></span></li><li><span data-ttu-id="66215-135">Listas</span><span class="sxs-lookup"><span data-stu-id="66215-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="66215-136">Hospital</span><span class="sxs-lookup"><span data-stu-id="66215-136">Hospital</span></span>

<span data-ttu-id="66215-137">Simplifique a comunicação e a colaboração entre vários funcionários, funcionários e departamentos dentro de um hospital.</span><span class="sxs-lookup"><span data-stu-id="66215-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="66215-138">Esse modelo inclui um conjunto de canais base para operações hospital e pode ser autoprofundado para incluir especialidades, ad-hoc.</span><span class="sxs-lookup"><span data-stu-id="66215-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="66215-139">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="66215-139">Base template type</span></span> |<span data-ttu-id="66215-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="66215-140">baseTemplateId</span></span> | <span data-ttu-id="66215-141">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="66215-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="66215-142">Hospital</span><span class="sxs-lookup"><span data-stu-id="66215-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="66215-143">Canais:</span><span class="sxs-lookup"><span data-stu-id="66215-143">Channels:</span></span> <ul><li><span data-ttu-id="66215-144">Geral</span><span class="sxs-lookup"><span data-stu-id="66215-144">General</span></span></li><li><span data-ttu-id="66215-145">Comunicados</span><span class="sxs-lookup"><span data-stu-id="66215-145">Announcements</span></span></li><li><span data-ttu-id="66215-146">Conformidade</span><span class="sxs-lookup"><span data-stu-id="66215-146">Compliance</span></span></li><li><span data-ttu-id="66215-147">Custódia</span><span class="sxs-lookup"><span data-stu-id="66215-147">Custodial</span></span></li><li><span data-ttu-id="66215-148">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="66215-148">Human resources</span></span></li><li><span data-ttu-id="66215-149">Farmácia</span><span class="sxs-lookup"><span data-stu-id="66215-149">Pharmacy</span></span></li></ul> <span data-ttu-id="66215-150">Apps:</span><span class="sxs-lookup"><span data-stu-id="66215-150">Apps:</span></span> <ul><li><span data-ttu-id="66215-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="66215-151">Wiki</span></span></li><li><span data-ttu-id="66215-152">Listas</span><span class="sxs-lookup"><span data-stu-id="66215-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-team-templates-with-the-microsoft-graph"></a><span data-ttu-id="66215-153">Use os modelos de equipe com o microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="66215-153">Use the team templates with the Microsoft Graph</span></span>

<span data-ttu-id="66215-154">Os desenvolvedores podem usar o microsoft Graph para criar equipes com os modelos de equipe.</span><span class="sxs-lookup"><span data-stu-id="66215-154">Developers can use the Microsoft Graph to create teams with the team templates.</span></span> <span data-ttu-id="66215-155">Atualmente, oferecemos dois modelos de assistência médica de terceiros que você pode usar para diversas situações.</span><span class="sxs-lookup"><span data-stu-id="66215-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="66215-156">Para saber mais sobre modelos de equipe em geral, consulte [Começar a usar modelos de equipe.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="66215-156">To learn more about team templates in general, see [Get started with team templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="66215-157">E para obter informações sobre modelos de equipe e o microsoft Graph, [consulte Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0) visão geral da API e tipo de recurso [teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="66215-157">And for information about team templates and the Microsoft Graph, see [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="66215-158">Modelo de modelo de modelo</span><span class="sxs-lookup"><span data-stu-id="66215-158">Ward template</span></span>

<span data-ttu-id="66215-159">O modelo de design é destinado à comunicação e à colaboração dentro de um departamento, duas ou mais áreas.</span><span class="sxs-lookup"><span data-stu-id="66215-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="66215-160">O modelo pode ser usado para facilitar o gerenciamento dos pacientes, bem como para as necessidades operacionais de um paciente.</span><span class="sxs-lookup"><span data-stu-id="66215-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="66215-161">Por exemplo, comunicados completos podem ser postados no canal *Comunicados* e turnos podem ser gerenciados no *Equipe*.</span><span class="sxs-lookup"><span data-stu-id="66215-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="66215-162">Se você estiver tentando simplificar suas operações normais, este modelo é para você.</span><span class="sxs-lookup"><span data-stu-id="66215-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="66215-163">Tipo de Modelo Base</span><span class="sxs-lookup"><span data-stu-id="66215-163">Base Template Type</span></span> |<span data-ttu-id="66215-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="66215-164">baseTemplateId</span></span> |<span data-ttu-id="66215-165">Canais de modelo de linha de base</span><span class="sxs-lookup"><span data-stu-id="66215-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="66215-166">Assistência médica – Assist.</span><span class="sxs-lookup"><span data-stu-id="66215-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="66215-167">Anúncios\*</span><span class="sxs-lookup"><span data-stu-id="66215-167">Announcements\*</span></span> <br> <span data-ttu-id="66215-168">Insuidades\*</span><span class="sxs-lookup"><span data-stu-id="66215-168">Huddles\*</span></span> <br> <span data-ttu-id="66215-169">Rodadas\*</span><span class="sxs-lookup"><span data-stu-id="66215-169">Rounds\*</span></span> <br> <span data-ttu-id="66215-170">Pessoal\*</span><span class="sxs-lookup"><span data-stu-id="66215-170">Staffing\*</span></span> <br> <span data-ttu-id="66215-171">Treinamento\*</span><span class="sxs-lookup"><span data-stu-id="66215-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="66215-172">\* Favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="66215-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="66215-173">Modelo de hospital</span><span class="sxs-lookup"><span data-stu-id="66215-173">Hospital template</span></span>

<span data-ttu-id="66215-174">O modelo hospital é destinado à comunicação e colaboração entre vários funcionários, funcionários e departamentos em um hospital.</span><span class="sxs-lookup"><span data-stu-id="66215-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="66215-175">Incluídos neste modelo estão vários canais operacionais, incluindo *Anúncios*, *Custódia* e *Farmácia*, mas também fornecemos um script abaixo que estende o modelo com uma variedade de departamentos adicionais ou canais centrados em especialidades que você pode adicionar, excluir ou editar seu gosto.</span><span class="sxs-lookup"><span data-stu-id="66215-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="66215-176">Por exemplo, se você tem um departamento de *Endocrinologia*, mas não precisa de um canal para *Oftalmologia*, o script pode ser adaptado para incluir um canal de *Endocrinologia* e remover o canal de *Oftalmologia*.</span><span class="sxs-lookup"><span data-stu-id="66215-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="66215-177">Recomendamos que esses canais especializados ou modelados não sejam favoritos automaticamente para evitar saturação da notificação.</span><span class="sxs-lookup"><span data-stu-id="66215-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="66215-178">Os usuários geralmente favoritam os canais que acham relevantes.</span><span class="sxs-lookup"><span data-stu-id="66215-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="66215-179">Tipo de Modelo Base</span><span class="sxs-lookup"><span data-stu-id="66215-179">Base Template Type</span></span> |<span data-ttu-id="66215-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="66215-180">baseTemplateId</span></span> |<span data-ttu-id="66215-181">Canais de modelo de linha de base</span><span class="sxs-lookup"><span data-stu-id="66215-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="66215-182">Assistência médica – Hospital</span><span class="sxs-lookup"><span data-stu-id="66215-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="66215-183">Anúncios\*</span><span class="sxs-lookup"><span data-stu-id="66215-183">Announcements\*</span></span> <br> <span data-ttu-id="66215-184">Conformidade\*</span><span class="sxs-lookup"><span data-stu-id="66215-184">Compliance\*</span></span> <br> <span data-ttu-id="66215-185">Custódia</span><span class="sxs-lookup"><span data-stu-id="66215-185">Custodial</span></span> <br> <span data-ttu-id="66215-186">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="66215-186">Human Resources</span></span> <br> <span data-ttu-id="66215-187">Farmácia</span><span class="sxs-lookup"><span data-stu-id="66215-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="66215-188">\* Favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="66215-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="66215-189">Como usar modelos de terceiros</span><span class="sxs-lookup"><span data-stu-id="66215-189">How to use first-party templates</span></span>

<span data-ttu-id="66215-190">Para usar esses modelos, basta alterar a propriedade "template@odata.bind" no corpo da solicitação de "padrão" para as TemplateIDs acima.</span><span class="sxs-lookup"><span data-stu-id="66215-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="66215-191">Para obter mais informações sobre como implantar modelos de equipe, consulte o artigo do Microsoft Graph sobre como [criar uma equipe.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="66215-191">For more information on how to deploy team templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="66215-192">Os canais no modelo serão criados automaticamente na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="66215-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="66215-193">Exemplo: Script de extensão de modelo de hospital</span><span class="sxs-lookup"><span data-stu-id="66215-193">Example: Hospital template extension script</span></span>

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### <a name="related-topics"></a><span data-ttu-id="66215-194">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="66215-194">Related topics</span></span>

[<span data-ttu-id="66215-195">Começar a usar modelos de equipe</span><span class="sxs-lookup"><span data-stu-id="66215-195">Get started with team templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="66215-196">Começar com a equipe para organizações de saúde</span><span class="sxs-lookup"><span data-stu-id="66215-196">Get started with team for Healthcare organizations</span></span>](teams-in-hc.md)