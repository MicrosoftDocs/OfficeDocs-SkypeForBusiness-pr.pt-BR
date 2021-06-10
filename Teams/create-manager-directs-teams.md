---
title: Criar equipes de gerente de pessoas Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Saiba como usar um script do PowerShell para criar uma equipe para cada gerente com seus directs como membros da equipe.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa7c82ec584791107e5d269ee40bccba272d20b4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094407"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="991f8-103">Criar equipes de gerente de pessoas Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="991f8-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="991f8-104">Ao lançar o Microsoft Teams, em vez de iniciar com uma "lousa em branco" (sem equipes ou canais), é recomendável configurar uma estrutura base de equipes e canais.</span><span class="sxs-lookup"><span data-stu-id="991f8-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="991f8-105">Isso ajuda a evitar a "expansão de equipe", em que os usuários criam várias equipes quando devem criar canais em equipes existentes.</span><span class="sxs-lookup"><span data-stu-id="991f8-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="991f8-106">Para ajudá-lo a começar com uma estrutura de equipes e canais bem projetada, criamos um script do PowerShell que cria uma equipe para cada um dos gerentes de pessoas de primeira e segunda linha, com os relatórios diretos de cada gerente como membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="991f8-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="991f8-107">Esse é um script "point-in-time" (ele não atualiza automaticamente suas equipes ou canais quando as pessoas são adicionadas ou removidas de uma organização).</span><span class="sxs-lookup"><span data-stu-id="991f8-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="991f8-108">Mas é uma ferramenta valiosa que você pode usar para impor alguma ordem em sua estrutura Teams desde o início.</span><span class="sxs-lookup"><span data-stu-id="991f8-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="991f8-109">Este script lê o Azure AD, obtém uma lista de gerentes e seus relatórios diretos.</span><span class="sxs-lookup"><span data-stu-id="991f8-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="991f8-110">Ele usa essa lista para criar uma equipe por gerente de pessoas.</span><span class="sxs-lookup"><span data-stu-id="991f8-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="991f8-111">Como usar o script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="991f8-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="991f8-112">Comece executando os gerentes de exportação e o script de [directs](scripts/powershell-script-create-teams-from-managers-export-managers.md) (o que supõe que você já tenha executado os módulos [Conexão-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) e [Conexão-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell).</span><span class="sxs-lookup"><span data-stu-id="991f8-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="991f8-113">O *script Exportar gerentes* e seus directs cria um arquivo delimitado por tabulação (ExportedManagerDirects.txt) que lista todos os gerentes com seus relatórios diretos.</span><span class="sxs-lookup"><span data-stu-id="991f8-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="991f8-114">Em seguida, execute o [script Criar novas equipes de gerente de pessoas.](scripts/powershell-script-create-teams-from-managers-new-teams.md)</span><span class="sxs-lookup"><span data-stu-id="991f8-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="991f8-115">Esse script lê no arquivo ExportedManagerDirects.txt e cria uma equipe para cada gerente, com os relatórios diretos desse gerente como membros.</span><span class="sxs-lookup"><span data-stu-id="991f8-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="991f8-116">Se qualquer gerente ou direto não estiver habilitado para Teams, o script os ignorará e não criará uma equipe.</span><span class="sxs-lookup"><span data-stu-id="991f8-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="991f8-117">(Revise o relatório e, em seguida, reprise o script depois que você Teams para qualquer pessoa que precise dele.</span><span class="sxs-lookup"><span data-stu-id="991f8-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="991f8-118">O script não criará uma segunda equipe para qualquer gerente para o que já tenha criado uma equipe.)</span><span class="sxs-lookup"><span data-stu-id="991f8-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="991f8-119">Para cada equipe, o script cria um canal Geral e "Apenas por diversão".</span><span class="sxs-lookup"><span data-stu-id="991f8-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="991f8-120">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="991f8-120">Best practices</span></span>

- <span data-ttu-id="991f8-121">Peça a cada gerente de pessoas para adicionar o site de comunicações de crise da sua organização como uma guia para o canal Geral de cada equipe.</span><span class="sxs-lookup"><span data-stu-id="991f8-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="991f8-122">Confira o novo aplicativo de Comunicações de Crise lendo esta postagem de blog de 8 de março de 2020: Coordenar comunicações de crise usando [Microsoft Teams + Plataforma Power](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span><span class="sxs-lookup"><span data-stu-id="991f8-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="991f8-123">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="991f8-123">Related topics</span></span>

[<span data-ttu-id="991f8-124">Práticas recomendadas para organizar equipes</span><span class="sxs-lookup"><span data-stu-id="991f8-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="991f8-125">Crie uma equipe englobando toda a organização no Teams</span><span class="sxs-lookup"><span data-stu-id="991f8-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)