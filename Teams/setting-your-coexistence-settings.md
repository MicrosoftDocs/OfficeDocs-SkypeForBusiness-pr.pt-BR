---
title: Definindo as configurações de coexistência
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: Isso ajudará a selecionar o modo de coexistência e definir outras configurações de coexistência.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: add6436d66c088d6ffa14867cc03268cb082f0b3
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
---
# <a name="setting-your-coexistence-settings"></a><span data-ttu-id="c3aa9-103">Definindo as configurações de coexistência</span><span class="sxs-lookup"><span data-stu-id="c3aa9-103">Setting your coexistence settings</span></span>


> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<Intro text here>

[<span data-ttu-id="c3aa9-104">Entender a coexistência e atualizar modos Skype for Business e equipes</span><span class="sxs-lookup"><span data-stu-id="c3aa9-104">Understand coexistence and upgrade modes for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

## <a name="setting-your-upgrade-options-for-your-users"></a><span data-ttu-id="c3aa9-105">Definindo suas opções de atualização para seus usuários</span><span class="sxs-lookup"><span data-stu-id="c3aa9-105">Setting your upgrade options for your users</span></span>

<span data-ttu-id="c3aa9-106">![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="c3aa9-106">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="c3aa9-107">No painel de navegação esquerdo, vá para **configurações de toda a organização** > **equipes de atualização**.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-107">In the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="c3aa9-108">Na parte superior da página **página atualização de equipes** , faça as seguintes alterações se eles funcionará para você.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-108">At the top of the **Teams upgrade page** page, make the following changes if they will work for you.</span></span>
- <span data-ttu-id="c3aa9-109">Definir o modo de **coexistência**</span><span class="sxs-lookup"><span data-stu-id="c3aa9-109">Set the **Coexistence** mode</span></span>
    - <span data-ttu-id="c3aa9-110">**Ilhas** - use esta configuração quando você tem alguns usuários em Skype para alguns usuários que usam equipes e de negócios.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-110">**Islands** - use this setting when you have some users on Skype for Business and some users that use Teams.</span></span>
    - <span data-ttu-id="c3aa9-111">**Skype para negócios apenas** - use esta configuração se você tiver apenas Skype para usuários comerciais.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-111">**Skype for Business only** - use this setting if you only have Skype for Business users.</span></span>
    - <span data-ttu-id="c3aa9-112">**Equipes apenas** - use esta configuração se você tiver apenas os usuários de equipes.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-112">**Teams only** - use this setting if you only have Teams users.</span></span>
- <span data-ttu-id="c3aa9-113">Definir **Skype notificar para usuários comerciais que às equipes está disponível para atualização.**</span><span class="sxs-lookup"><span data-stu-id="c3aa9-113">Set **Notify Skype for Business users that Teams is available for upgrade.**</span></span>
    - <span data-ttu-id="c3aa9-114">Se você ativar isso, ele informará o Skype para usuários corporativos que podem ser atualizados para o aplicativo de equipes.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-114">If you turn this on, it will tell the Skype for Business users that they can upgrade to the Teams app.</span></span>
- <span data-ttu-id="c3aa9-115">Defina o **aplicativo preferencial para os usuários ingressem Skype para reuniões de negócios** essa configuração determina qual app é usado para ingressar em Skype para reuniões de negócios e é respeitada independente do valor do modo de coexistência.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-115">Set the **Preferred app for users to join Skype for Business meetings**  This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
    - <span data-ttu-id="c3aa9-116">**Reuniões do Skype app (padrão)**</span><span class="sxs-lookup"><span data-stu-id="c3aa9-116">**Skype Meetings app (default)**</span></span>
    - <span data-ttu-id="c3aa9-117">**Skype for Business com os recursos limitados**</span><span class="sxs-lookup"><span data-stu-id="c3aa9-117">**Skype for Business with limited features**</span></span>
- <span data-ttu-id="c3aa9-118">Defina se para **baixar o aplicativo de equipes em segundo plano para Skype para usuários comerciais** esta configuração silenciosamente baixa o aplicativo de equipes para usuários que executam o Skype for Business no Windows.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-118">Set whether to **Download the Teams app in the background for Skype for Business users**  This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="c3aa9-119">Ela é respeitada somente se o modo de coexistência para o usuário é apenas para equipes ou se as notificações de atualização pendente estão habilitadas no Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-119">It is honored only if coexistence mode for the user is Teams Only, or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
1. <span data-ttu-id="c3aa9-120">Clique em **Salvar** depois de fazer as alterações.</span><span class="sxs-lookup"><span data-stu-id="c3aa9-120">Click **Save** after you make your changes.</span></span>


### <a name="related-topics"></a><span data-ttu-id="c3aa9-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c3aa9-121">Related topics</span></span>
<span data-ttu-id="c3aa9-122">[Planejar a jornada](upgrade-plan-journey.md)
[entender a coexistência e atualizar modos para Skype para equipes e de negócios](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="c3aa9-122">[Plan the journey](upgrade-plan-journey.md)
[Understand coexistence and upgrade modes for Skype for Business and Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span></span>