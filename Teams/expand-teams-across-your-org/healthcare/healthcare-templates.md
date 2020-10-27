---
title: Modelos para organizações de assistência médica
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Use os modelos do Microsoft Teams com o Microsoft Graph para criar equipes rápida e facilmente fornecendo um modelo predefinido de configurações, canais e aplicativos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 63376c68d8267aaa49b4bdf4033d5ebfaa0a446f
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766694"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="30469-103">Introdução aos modelos do teams para organizações de assistência médica</span><span class="sxs-lookup"><span data-stu-id="30469-103">Get started with Teams templates for healthcare organizations</span></span>

<span data-ttu-id="30469-104">Os modelos do Microsoft Teams permitem criar equipes de forma rápida e fácil, fornecendo um modelo predefinido de configurações, canais e aplicativos pré-instalados.</span><span class="sxs-lookup"><span data-stu-id="30469-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="30469-105">Para organizações de assistência médica, os modelos podem ser eficientes, pois fornecem estrutura para que os usuários se orientem com o modo de usar o Teams de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="30469-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="30469-106">Os modelos também permitem que os administradores implantem equipes consistentes em suas organizações.</span><span class="sxs-lookup"><span data-stu-id="30469-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="30469-107">Este artigo é para você se for responsável por planejar, implantar e gerenciar várias equipes em toda a organização de assistência médica.</span><span class="sxs-lookup"><span data-stu-id="30469-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="30469-108">Atualmente, oferecemos dois modelos de saúde de primeira mão que você pode usar para várias situações.</span><span class="sxs-lookup"><span data-stu-id="30469-108">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="30469-109">Para saber mais sobre os modelos de equipe em geral, consulte [introdução aos modelos](../../get-started-with-teams-templates.md)do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="30469-109">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="30469-110">Modelo de versões anteriores</span><span class="sxs-lookup"><span data-stu-id="30469-110">Ward template</span></span>

<span data-ttu-id="30469-111">O modelo para a era destinado à comunicação e à colaboração em um departamento, um pod ou um departamento.</span><span class="sxs-lookup"><span data-stu-id="30469-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="30469-112">O modelo pode ser usado para facilitar o gerenciamento de pacientes, bem como as necessidades operacionais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="30469-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="30469-113">Por exemplo, os comunicados para o fim podem ser publicados no canal de *anúncios* e os turnos podem ser gerenciados na *equipe* .</span><span class="sxs-lookup"><span data-stu-id="30469-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing* .</span></span> <span data-ttu-id="30469-114">Se você pretende simplificar as operações de sua era para você, este modelo é para você.</span><span class="sxs-lookup"><span data-stu-id="30469-114">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="30469-115">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="30469-115">Base Template Type</span></span> |<span data-ttu-id="30469-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="30469-116">baseTemplateId</span></span> |<span data-ttu-id="30469-117">Canais de modelo de linha de base</span><span class="sxs-lookup"><span data-stu-id="30469-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="30469-118">Saúde para a frente</span><span class="sxs-lookup"><span data-stu-id="30469-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="30469-119">Comunicados\*</span><span class="sxs-lookup"><span data-stu-id="30469-119">Announcements\*</span></span> <br> <span data-ttu-id="30469-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="30469-120">Huddles\*</span></span> <br> <span data-ttu-id="30469-121">Arredonda\*</span><span class="sxs-lookup"><span data-stu-id="30469-121">Rounds\*</span></span> <br> <span data-ttu-id="30469-122">Especificam\*</span><span class="sxs-lookup"><span data-stu-id="30469-122">Staffing\*</span></span> <br> <span data-ttu-id="30469-123">Treinamento\*</span><span class="sxs-lookup"><span data-stu-id="30469-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="30469-124">\* Favoritos automaticamente</span><span class="sxs-lookup"><span data-stu-id="30469-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="30469-125">Modelo do hospital</span><span class="sxs-lookup"><span data-stu-id="30469-125">Hospital template</span></span>

<span data-ttu-id="30469-126">O modelo hospital destina-se à comunicação e colaboração entre vários departamentos, pods e departamentos em um hospital.</span><span class="sxs-lookup"><span data-stu-id="30469-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="30469-127">Neste modelo, há vários canais operacionais, incluindo *anúncios* , *custodial* e *Farmácias* , mas também fornecemos um script abaixo que estende o modelo com uma variedade de canais complementares de departamento ou especialidade que você pode adicionar, excluir ou editar de preferência.</span><span class="sxs-lookup"><span data-stu-id="30469-127">Included in this template are several operational channels including *Announcements* , *Custodial* , and *Pharmacy* , but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="30469-128">Por exemplo, se você tiver um departamento *Endocrinology* , mas não precisa de um canal para *ophthalmology* , o script poderá ser adaptado para incluir um canal de *Endocrinology* e remover o canal de *ophthalmology* .</span><span class="sxs-lookup"><span data-stu-id="30469-128">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology* , then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="30469-129">Recomendamos que esses canais de especialidade ou modelo não sejam favoritos automaticamente para evitar a saturação da notificação.</span><span class="sxs-lookup"><span data-stu-id="30469-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="30469-130">Os usuários geralmente têm favorito todos os canais que encontrarem relevantes.</span><span class="sxs-lookup"><span data-stu-id="30469-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="30469-131">Tipo de modelo base</span><span class="sxs-lookup"><span data-stu-id="30469-131">Base Template Type</span></span> |<span data-ttu-id="30469-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="30469-132">baseTemplateId</span></span> |<span data-ttu-id="30469-133">Canais de modelo de linha de base</span><span class="sxs-lookup"><span data-stu-id="30469-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="30469-134">Assistência médica – hospital</span><span class="sxs-lookup"><span data-stu-id="30469-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="30469-135">Comunicados\*</span><span class="sxs-lookup"><span data-stu-id="30469-135">Announcements\*</span></span> <br> <span data-ttu-id="30469-136">Conformidade\*</span><span class="sxs-lookup"><span data-stu-id="30469-136">Compliance\*</span></span> <br> <span data-ttu-id="30469-137">Custodial</span><span class="sxs-lookup"><span data-stu-id="30469-137">Custodial</span></span> <br> <span data-ttu-id="30469-138">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="30469-138">Human Resources</span></span> <br> <span data-ttu-id="30469-139">Farmácia</span><span class="sxs-lookup"><span data-stu-id="30469-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="30469-140">\* Favoritos automaticamente</span><span class="sxs-lookup"><span data-stu-id="30469-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="30469-141">Como usar modelos de primeira empresa</span><span class="sxs-lookup"><span data-stu-id="30469-141">How to use first-party templates</span></span>

<span data-ttu-id="30469-142">Para usar esses modelos, basta alterar a propriedade ' template@odata. BIND ' no corpo da solicitação de ' Standard ' para a TemplateIDs acima.</span><span class="sxs-lookup"><span data-stu-id="30469-142">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="30469-143">Para obter mais informações sobre como implantar modelos de equipe, consulte o artigo Microsoft Graph sobre como [criar uma equipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="30469-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="30469-144">Os canais no modelo serão automaticamente criados na guia geral.</span><span class="sxs-lookup"><span data-stu-id="30469-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="30469-145">Exemplo: script de extensão de modelo hospital</span><span class="sxs-lookup"><span data-stu-id="30469-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="30469-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="30469-146">Related topics</span></span>

[<span data-ttu-id="30469-147">Introdução aos modelos do Teams</span><span class="sxs-lookup"><span data-stu-id="30469-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="30469-148">Introdução ao Teams para Organizações de Saúde</span><span class="sxs-lookup"><span data-stu-id="30469-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)

[<span data-ttu-id="30469-149">Introdução aos modelos do Microsoft Teams no console de administração</span><span class="sxs-lookup"><span data-stu-id="30469-149">Get started with Teams templates in the admin console</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
