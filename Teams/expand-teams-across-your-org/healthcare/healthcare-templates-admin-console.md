---
title: Criar uma equipe usando modelos de saúde do Teams
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
description: Use modelos do Microsoft Teams no centro de administração ou com o Microsoft Graph para criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260303"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a><span data-ttu-id="797e2-103">Criar uma equipe usando modelos de saúde do Teams</span><span class="sxs-lookup"><span data-stu-id="797e2-103">Create a team using Teams healthcare templates</span></span>

<span data-ttu-id="797e2-104">Os modelos do Microsoft Teams permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="797e2-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="797e2-105">Para organizações de saúde, os modelos podem ser especialmente poderosos, pois fornecem estrutura para os usuários se orientarem sobre como usar o Teams de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="797e2-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="797e2-106">Os modelos também permitem que os administradores implantem equipes consistentes em suas organizações.</span><span class="sxs-lookup"><span data-stu-id="797e2-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="797e2-107">Este artigo é para você se você for responsável por planejar, implantar e gerenciar várias equipes em sua organização de saúde.</span><span class="sxs-lookup"><span data-stu-id="797e2-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="797e2-108">Escolha um método para criar equipes com os modelos de saúde do Teams:</span><span class="sxs-lookup"><span data-stu-id="797e2-108">Choose a method for creating teams with the Teams healthcare templates:</span></span>

| <span data-ttu-id="797e2-109">Woh</span><span class="sxs-lookup"><span data-stu-id="797e2-109">Who</span></span> | <span data-ttu-id="797e2-110">Método a ser usado:</span><span class="sxs-lookup"><span data-stu-id="797e2-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="797e2-111">Administradores e profissionais de TI</span><span class="sxs-lookup"><span data-stu-id="797e2-111">Admins and IT Professionals</span></span> | <span data-ttu-id="797e2-112">[Use o Centro de administração do Teams](#use-the-teams-templates-in-the-teams-admin-center) para criar equipes com base nos modelos do Teams de saúde.</span><span class="sxs-lookup"><span data-stu-id="797e2-112">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the healthcare Teams templates.</span></span>|
| <span data-ttu-id="797e2-113">Desenvolvedores e integradores de sistemas</span><span class="sxs-lookup"><span data-stu-id="797e2-113">Developers and systems integrators</span></span> | <span data-ttu-id="797e2-114">[Use o Microsoft Graph para](#use-the-teams-templates-with-the-microsoft-graph) criar equipes com base nos modelos do Teams de saúde.</span><span class="sxs-lookup"><span data-stu-id="797e2-114">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the healthcare Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="797e2-115">Usar os modelos do Teams no Centro de administração do Teams</span><span class="sxs-lookup"><span data-stu-id="797e2-115">Use the Teams templates in the Teams admin center</span></span>

<span data-ttu-id="797e2-116">Os administradores do Microsoft Teams podem usar o Centro de administração do Teams para criar equipes com os modelos do Teams.</span><span class="sxs-lookup"><span data-stu-id="797e2-116">Microsoft Teams admins can use the Teams admin center to create teams with the Teams templates.</span></span> <span data-ttu-id="797e2-117">Atualmente, oferecemos dois modelos de serviços de saúde de primeira mão que você pode usar para várias situações.</span><span class="sxs-lookup"><span data-stu-id="797e2-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="797e2-118">Para saber mais sobre modelos de equipe em geral, consulte Começar a usar os modelos [do Teams no centro de administração.](../../get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="797e2-118">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="797e2-119">Colaborar no atendimento ao paciente</span><span class="sxs-lookup"><span data-stu-id="797e2-119">Collaborate on patient care</span></span>

 <span data-ttu-id="797e2-120">Simplifique a comunicação e a colaboração em um departamento, um módulo ou um departamento de saúde.</span><span class="sxs-lookup"><span data-stu-id="797e2-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="797e2-121">O modelo pode ser usado para facilitar o gerenciamento de pacientes e as necessidades operacionais de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="797e2-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="797e2-122">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="797e2-122">Base template type</span></span> |<span data-ttu-id="797e2-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="797e2-123">baseTemplateId</span></span>| <span data-ttu-id="797e2-124">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="797e2-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="797e2-125">Colaborar no atendimento ao paciente</span><span class="sxs-lookup"><span data-stu-id="797e2-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="797e2-126">Canais:</span><span class="sxs-lookup"><span data-stu-id="797e2-126">Channels:</span></span><ul><li><span data-ttu-id="797e2-127">Geral</span><span class="sxs-lookup"><span data-stu-id="797e2-127">General</span></span></li><li><span data-ttu-id="797e2-128">Anúncios</span><span class="sxs-lookup"><span data-stu-id="797e2-128">Announcements</span></span></li><li><span data-ttu-id="797e2-129">Desaconsudores</span><span class="sxs-lookup"><span data-stu-id="797e2-129">Huddles</span></span></li><li><span data-ttu-id="797e2-130">Rodadas</span><span class="sxs-lookup"><span data-stu-id="797e2-130">Rounds</span></span></li><li><span data-ttu-id="797e2-131">Pessoal</span><span class="sxs-lookup"><span data-stu-id="797e2-131">Staffing</span></span></li><li><span data-ttu-id="797e2-132">Treinamento</span><span class="sxs-lookup"><span data-stu-id="797e2-132">Training</span></span></li></ul> <span data-ttu-id="797e2-133">Apps:</span><span class="sxs-lookup"><span data-stu-id="797e2-133">Apps:</span></span> <ul><li><span data-ttu-id="797e2-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="797e2-134">Wiki</span></span></li><li><span data-ttu-id="797e2-135">Listas</span><span class="sxs-lookup"><span data-stu-id="797e2-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="797e2-136">Hospital</span><span class="sxs-lookup"><span data-stu-id="797e2-136">Hospital</span></span>

<span data-ttu-id="797e2-137">Simplifique a comunicação e a colaboração entre várias equipes, vagens e departamentos dentro de um hospital.</span><span class="sxs-lookup"><span data-stu-id="797e2-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="797e2-138">Este modelo inclui um conjunto de canais base para operações hospitalares e pode ser estendido por conta própria para incluir especialidades, ad hoc.</span><span class="sxs-lookup"><span data-stu-id="797e2-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="797e2-139">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="797e2-139">Base template type</span></span> |<span data-ttu-id="797e2-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="797e2-140">baseTemplateId</span></span> | <span data-ttu-id="797e2-141">Propriedades que vêm com este modelo base</span><span class="sxs-lookup"><span data-stu-id="797e2-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="797e2-142">Hospital</span><span class="sxs-lookup"><span data-stu-id="797e2-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="797e2-143">Canais:</span><span class="sxs-lookup"><span data-stu-id="797e2-143">Channels:</span></span> <ul><li><span data-ttu-id="797e2-144">Geral</span><span class="sxs-lookup"><span data-stu-id="797e2-144">General</span></span></li><li><span data-ttu-id="797e2-145">Anúncios</span><span class="sxs-lookup"><span data-stu-id="797e2-145">Announcements</span></span></li><li><span data-ttu-id="797e2-146">Conformidade</span><span class="sxs-lookup"><span data-stu-id="797e2-146">Compliance</span></span></li><li><span data-ttu-id="797e2-147">Custódia</span><span class="sxs-lookup"><span data-stu-id="797e2-147">Custodial</span></span></li><li><span data-ttu-id="797e2-148">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="797e2-148">Human resources</span></span></li><li><span data-ttu-id="797e2-149">Farmácia</span><span class="sxs-lookup"><span data-stu-id="797e2-149">Pharmacy</span></span></li></ul> <span data-ttu-id="797e2-150">Apps:</span><span class="sxs-lookup"><span data-stu-id="797e2-150">Apps:</span></span> <ul><li><span data-ttu-id="797e2-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="797e2-151">Wiki</span></span></li><li><span data-ttu-id="797e2-152">Listas</span><span class="sxs-lookup"><span data-stu-id="797e2-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="797e2-153">Usar os modelos do Teams com o Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="797e2-153">Use the Teams templates with the Microsoft Graph</span></span>

<span data-ttu-id="797e2-154">Os desenvolvedores podem usar o Microsoft Graph para criar equipes com os modelos do Teams.</span><span class="sxs-lookup"><span data-stu-id="797e2-154">Developers can use the Microsoft Graph to create teams with the Teams templates.</span></span> <span data-ttu-id="797e2-155">Atualmente, oferecemos dois modelos de serviços de saúde de primeira mão que você pode usar para várias situações.</span><span class="sxs-lookup"><span data-stu-id="797e2-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="797e2-156">Para saber mais sobre modelos de equipe em geral, consulte [Começar a usar os modelos do Teams.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="797e2-156">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="797e2-157">E para obter informações sobre modelos do Teams e o Microsoft Graph, consulte a visão geral da [API do Microsoft Teams](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) e o tipo de recurso [TeamsTemplate.](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="797e2-157">And for information about Teams templates and the Microsoft Graph, see [Microsoft Teams API overview](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="797e2-158">Modelo de modelo de</span><span class="sxs-lookup"><span data-stu-id="797e2-158">Ward template</span></span>

<span data-ttu-id="797e2-159">O modelo de modelo de modelo de modelo é destinado à comunicação e à colaboração dentro de uma nave, um vagem ou um departamento.</span><span class="sxs-lookup"><span data-stu-id="797e2-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="797e2-160">O modelo pode ser usado para facilitar o gerenciamento de pacientes, bem como as necessidades operacionais de um paciente.</span><span class="sxs-lookup"><span data-stu-id="797e2-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="797e2-161">Por exemplo, os comunicados de reunião podem ser postados no canal *Comunicados* e os turnos podem ser gerenciados *na Equipe.*</span><span class="sxs-lookup"><span data-stu-id="797e2-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="797e2-162">Se você está tentando simplificar suas operações de resgate, então este modelo é para você.</span><span class="sxs-lookup"><span data-stu-id="797e2-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="797e2-163">Tipo de Modelo Base</span><span class="sxs-lookup"><span data-stu-id="797e2-163">Base Template Type</span></span> |<span data-ttu-id="797e2-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="797e2-164">baseTemplateId</span></span> |<span data-ttu-id="797e2-165">Canais de modelo de linha de base</span><span class="sxs-lookup"><span data-stu-id="797e2-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="797e2-166">Saúde – Ltda</span><span class="sxs-lookup"><span data-stu-id="797e2-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="797e2-167">Anúncios\*</span><span class="sxs-lookup"><span data-stu-id="797e2-167">Announcements\*</span></span> <br> <span data-ttu-id="797e2-168">Desaconsudores\*</span><span class="sxs-lookup"><span data-stu-id="797e2-168">Huddles\*</span></span> <br> <span data-ttu-id="797e2-169">Rodadas\*</span><span class="sxs-lookup"><span data-stu-id="797e2-169">Rounds\*</span></span> <br> <span data-ttu-id="797e2-170">Pessoal\*</span><span class="sxs-lookup"><span data-stu-id="797e2-170">Staffing\*</span></span> <br> <span data-ttu-id="797e2-171">Treinamento\*</span><span class="sxs-lookup"><span data-stu-id="797e2-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="797e2-172">\* Favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="797e2-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="797e2-173">Modelo de hospital</span><span class="sxs-lookup"><span data-stu-id="797e2-173">Hospital template</span></span>

<span data-ttu-id="797e2-174">O modelo de hospital é destinado à comunicação e à colaboração entre vários nós, vagens e departamentos dentro de um hospital.</span><span class="sxs-lookup"><span data-stu-id="797e2-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="797e2-175">Incluídos neste modelo, há vários canais operacionais, incluindo *Comunicados,* Pré-operatórios e Desmados, mas também fornecemos um script abaixo que estende o modelo com uma variedade de departamentos adicionais ou canais centrados em especial que você pode adicionar, excluir ou editar ao seu gosto.</span><span class="sxs-lookup"><span data-stu-id="797e2-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="797e2-176">Por exemplo, se você tiver um departamento de Endocrinologia, mas não precisar de um canal para *Oftalmologia,* o script poderá ser adaptado para incluir um canal *de Endocrinologia* e remover o canal  *oftalmologia.*</span><span class="sxs-lookup"><span data-stu-id="797e2-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="797e2-177">Recomendamos que esses canais especializados ou modelados por ela não sejam favoritos automaticamente para evitar saturação da notificação.</span><span class="sxs-lookup"><span data-stu-id="797e2-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="797e2-178">Os usuários geralmente favoritam todos os canais que eles acham relevantes.</span><span class="sxs-lookup"><span data-stu-id="797e2-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="797e2-179">Tipo de Modelo Base</span><span class="sxs-lookup"><span data-stu-id="797e2-179">Base Template Type</span></span> |<span data-ttu-id="797e2-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="797e2-180">baseTemplateId</span></span> |<span data-ttu-id="797e2-181">Canais de modelo de linha de base</span><span class="sxs-lookup"><span data-stu-id="797e2-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="797e2-182">Saúde – Hospital</span><span class="sxs-lookup"><span data-stu-id="797e2-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="797e2-183">Anúncios\*</span><span class="sxs-lookup"><span data-stu-id="797e2-183">Announcements\*</span></span> <br> <span data-ttu-id="797e2-184">Conformidade\*</span><span class="sxs-lookup"><span data-stu-id="797e2-184">Compliance\*</span></span> <br> <span data-ttu-id="797e2-185">Custódia</span><span class="sxs-lookup"><span data-stu-id="797e2-185">Custodial</span></span> <br> <span data-ttu-id="797e2-186">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="797e2-186">Human Resources</span></span> <br> <span data-ttu-id="797e2-187">Farmácia</span><span class="sxs-lookup"><span data-stu-id="797e2-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="797e2-188">\* Favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="797e2-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="797e2-189">Como usar modelos de primeira</span><span class="sxs-lookup"><span data-stu-id="797e2-189">How to use first-party templates</span></span>

<span data-ttu-id="797e2-190">Para usar esses modelos, basta alterar a propriedade "template@odata.bind" no corpo da solicitação de 'padrão' para os TemplateIDs acima.</span><span class="sxs-lookup"><span data-stu-id="797e2-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="797e2-191">Para obter mais informações sobre como implantar modelos do Teams, consulte o artigo do Microsoft Graph sobre como [criar uma Equipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="797e2-191">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="797e2-192">Os canais no modelo serão criados automaticamente na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="797e2-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="797e2-193">Exemplo: Script de extensão de modelo de hospital</span><span class="sxs-lookup"><span data-stu-id="797e2-193">Example: Hospital template extension script</span></span>

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

### <a name="related-topics"></a><span data-ttu-id="797e2-194">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="797e2-194">Related topics</span></span>

[<span data-ttu-id="797e2-195">Introdução aos modelos do Teams</span><span class="sxs-lookup"><span data-stu-id="797e2-195">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="797e2-196">Introdução ao Teams para Organizações de Saúde</span><span class="sxs-lookup"><span data-stu-id="797e2-196">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
