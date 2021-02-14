---
title: Modelos para organizações de saúde
author: serdarsoysal
ms.author: serdars
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
description: Use modelos do Microsoft Teams com o Microsoft Graph para criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4c2e10efbff98150b120d1c026d4d810629333f2
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790403"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="113ac-103">Começar a usar modelos do Teams para organizações de saúde</span><span class="sxs-lookup"><span data-stu-id="113ac-103">Get started with Teams templates for healthcare organizations</span></span>

<span data-ttu-id="113ac-104">Os modelos do Microsoft Teams permitem que você crie equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="113ac-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="113ac-105">Para organizações de saúde, os modelos podem ser especialmente poderosos, pois fornecem estrutura para os usuários se orientarem sobre como usar o Teams de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="113ac-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="113ac-106">Os modelos também permitem que os administradores implantem equipes consistentes em suas organizações.</span><span class="sxs-lookup"><span data-stu-id="113ac-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="113ac-107">Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em sua organização de saúde.</span><span class="sxs-lookup"><span data-stu-id="113ac-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="113ac-108">Atualmente, oferecemos dois modelos de serviços de saúde de primeira mão que você pode usar para várias situações.</span><span class="sxs-lookup"><span data-stu-id="113ac-108">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="113ac-109">Para saber mais sobre modelos de equipe em geral, consulte [Começar a usar os modelos do Teams.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="113ac-109">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="113ac-110">Modelo de modelo de</span><span class="sxs-lookup"><span data-stu-id="113ac-110">Ward template</span></span>

<span data-ttu-id="113ac-111">O modelo de modelo de modelo de modelo é destinado à comunicação e à colaboração dentro de uma nave, um vagem ou um departamento.</span><span class="sxs-lookup"><span data-stu-id="113ac-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="113ac-112">O modelo pode ser usado para facilitar o gerenciamento de pacientes, bem como as necessidades operacionais de um paciente.</span><span class="sxs-lookup"><span data-stu-id="113ac-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="113ac-113">Por exemplo, os comunicados de reunião podem ser postados no canal *Comunicados* e os turnos podem ser gerenciados *no Staffing.*</span><span class="sxs-lookup"><span data-stu-id="113ac-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="113ac-114">Se você estiver tentando simplificar suas operações de resgate, então este modelo é para você.</span><span class="sxs-lookup"><span data-stu-id="113ac-114">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="113ac-115">Tipo de Modelo Base</span><span class="sxs-lookup"><span data-stu-id="113ac-115">Base Template Type</span></span> |<span data-ttu-id="113ac-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="113ac-116">baseTemplateId</span></span> |<span data-ttu-id="113ac-117">Canais de modelo de linha de base</span><span class="sxs-lookup"><span data-stu-id="113ac-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="113ac-118">Saúde – Ltda</span><span class="sxs-lookup"><span data-stu-id="113ac-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="113ac-119">Anúncios\*</span><span class="sxs-lookup"><span data-stu-id="113ac-119">Announcements\*</span></span> <br> <span data-ttu-id="113ac-120">Desaconsudores\*</span><span class="sxs-lookup"><span data-stu-id="113ac-120">Huddles\*</span></span> <br> <span data-ttu-id="113ac-121">Rodadas\*</span><span class="sxs-lookup"><span data-stu-id="113ac-121">Rounds\*</span></span> <br> <span data-ttu-id="113ac-122">Pessoal\*</span><span class="sxs-lookup"><span data-stu-id="113ac-122">Staffing\*</span></span> <br> <span data-ttu-id="113ac-123">Treinamento\*</span><span class="sxs-lookup"><span data-stu-id="113ac-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="113ac-124">\* Favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="113ac-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="113ac-125">Modelo de hospital</span><span class="sxs-lookup"><span data-stu-id="113ac-125">Hospital template</span></span>

<span data-ttu-id="113ac-126">O modelo de hospital é destinado à comunicação e à colaboração entre vários nós, vagens e departamentos dentro de um hospital.</span><span class="sxs-lookup"><span data-stu-id="113ac-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="113ac-127">Incluídos neste modelo, há vários canais operacionais, incluindo *Comunicados,* Pré-operatórios e Desmados, mas também fornecemos um script abaixo que estende o modelo com uma variedade de canais centrados em departamentos ou especialidades adicionais aos quais você pode adicionar, excluir ou editar ao seu gosto.</span><span class="sxs-lookup"><span data-stu-id="113ac-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="113ac-128">Por exemplo, se você tiver um departamento de Endocrinologia, mas não precisar de um canal para *Oftalmologia,* o script poderá ser adaptado para incluir um canal *de Endocrinologia* e remover o canal  *oftalmologia.*</span><span class="sxs-lookup"><span data-stu-id="113ac-128">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="113ac-129">Recomendamos que esses canais especiais ou modelados por ela não sejam favoritos automaticamente para evitar a saturação da notificação.</span><span class="sxs-lookup"><span data-stu-id="113ac-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="113ac-130">Os usuários geralmente favoritam todos os canais que eles acham relevantes.</span><span class="sxs-lookup"><span data-stu-id="113ac-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="113ac-131">Tipo de Modelo Base</span><span class="sxs-lookup"><span data-stu-id="113ac-131">Base Template Type</span></span> |<span data-ttu-id="113ac-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="113ac-132">baseTemplateId</span></span> |<span data-ttu-id="113ac-133">Canais de modelo de linha de base</span><span class="sxs-lookup"><span data-stu-id="113ac-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="113ac-134">Saúde – Hospital</span><span class="sxs-lookup"><span data-stu-id="113ac-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="113ac-135">Anúncios\*</span><span class="sxs-lookup"><span data-stu-id="113ac-135">Announcements\*</span></span> <br> <span data-ttu-id="113ac-136">Conformidade\*</span><span class="sxs-lookup"><span data-stu-id="113ac-136">Compliance\*</span></span> <br> <span data-ttu-id="113ac-137">Custódia</span><span class="sxs-lookup"><span data-stu-id="113ac-137">Custodial</span></span> <br> <span data-ttu-id="113ac-138">Recursos Humanos</span><span class="sxs-lookup"><span data-stu-id="113ac-138">Human Resources</span></span> <br> <span data-ttu-id="113ac-139">Farmácia</span><span class="sxs-lookup"><span data-stu-id="113ac-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="113ac-140">\* Favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="113ac-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="113ac-141">Como usar modelos de primeira mão</span><span class="sxs-lookup"><span data-stu-id="113ac-141">How to use first-party templates</span></span>

<span data-ttu-id="113ac-142">Para usar esses modelos, basta alterar a propriedade "template@odata.bind" no corpo da solicitação de 'padrão' para os TemplateIDs acima.</span><span class="sxs-lookup"><span data-stu-id="113ac-142">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="113ac-143">Para obter mais informações sobre como implantar modelos do Teams, consulte o artigo do Microsoft Graph sobre como [criar uma Equipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="113ac-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="113ac-144">Os canais no modelo serão criados automaticamente na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="113ac-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="113ac-145">Exemplo: Script de extensão de modelo de hospital</span><span class="sxs-lookup"><span data-stu-id="113ac-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="113ac-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="113ac-146">Related topics</span></span>

[<span data-ttu-id="113ac-147">Introdução aos modelos do Teams</span><span class="sxs-lookup"><span data-stu-id="113ac-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="113ac-148">Introdução ao Teams para Organizações de Saúde</span><span class="sxs-lookup"><span data-stu-id="113ac-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)

[<span data-ttu-id="113ac-149">Começar a usar modelos do Teams no console de administração</span><span class="sxs-lookup"><span data-stu-id="113ac-149">Get started with Teams templates in the admin console</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
