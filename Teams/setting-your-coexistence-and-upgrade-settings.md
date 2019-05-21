---
title: Definir suas configurações de coexistência e atualização
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: Este artigo vai ajudá-lo a escolher o modo de coexistência e definir outras configurações de coexistência.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 55ed1396cd9c16b96e7d230429ccf25c1802473e
ms.sourcegitcommit: a47f0841b9a14ede65171a817ecb7ebc72f209e5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2019
ms.locfileid: "34298659"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="ee164-103">Definir suas configurações de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="ee164-103">Setting your coexistence and upgrade settings</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="ee164-104">Ao atualizar os usuários do Skype for Business para usar o Microsoft Teams, você tem várias opções para ajudá-lo a fazer dele um processo perfeito para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="ee164-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="ee164-105">Você tem a opção de fazer as configurações de coexistência e atualização para todos os usuários de sua organização ao mesmo tempo ou pode fazer alterações nas configurações de um único ou conjunto de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ee164-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="ee164-106">Observe que as versões mais antigas dos clientes do Skype for Business podem não respeitar essas configurações.</span><span class="sxs-lookup"><span data-stu-id="ee164-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="ee164-107">Para obter mais informações sobre as versões do cliente Skype for Business, acesse a [página de downloads e atualizações do Skype for Business](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates).</span><span class="sxs-lookup"><span data-stu-id="ee164-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="ee164-108">Você pode obter uma compreensão melhor dos tipos de modos disponíveis para você lendo [compreender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business com o](teams-and-skypeforbusiness-coexistence-and-interoperability.md) [Skype for Business](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="ee164-108">You can get a better understanding of the types of modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="ee164-109">Definir opções de atualização para todos os usuários em sua organização</span><span class="sxs-lookup"><span data-stu-id="ee164-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="ee164-110">![Teams-logo-30x30. png](media/teams-logo-30x30.png) **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="ee164-110">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ee164-111">Na navegação à esquerda, vá para a**atualização de equipes**de **configurações** > em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="ee164-111">In the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="ee164-112">Na parte superior da página de **atualização** do Teams, faça as seguintes alterações se elas funcionarem para você.</span><span class="sxs-lookup"><span data-stu-id="ee164-112">At the top of the **Teams upgrade** page, make the following changes if they will work for you.</span></span>
    - <span data-ttu-id="ee164-113">Defina o \*\*\*\* modo de coexistência.</span><span class="sxs-lookup"><span data-stu-id="ee164-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="ee164-114">**Ilhas** – Use essa configuração se quiser que os usuários possam usar o Skype for Business e o Teams simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="ee164-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="ee164-115">**Skype para empresas apenas** – Use esta configuração se quiser que os usuários usem o Skype for Business apenas.</span><span class="sxs-lookup"><span data-stu-id="ee164-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="ee164-116">**Somente equipes** (na visualização para algumas organizações) – Use essa configuração se desejar que os usuários usem apenas as equipes.</span><span class="sxs-lookup"><span data-stu-id="ee164-116">**Teams only** (in preview for some organizations) - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="ee164-117">Observe que, mesmo com essa configuração, os usuários ainda podem ingressar em reuniões hospedadas no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ee164-117">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>
    - <span data-ttu-id="ee164-118">Defina **notificar os usuários do Skype for Business de que o Microsoft Teams está disponível para atualização**.</span><span class="sxs-lookup"><span data-stu-id="ee164-118">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="ee164-119">Se você ativar esse recurso, ele informará aos usuários do Skype for Business que eles logo serão atualizados para o aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="ee164-119">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>
    - <span data-ttu-id="ee164-120">Defina o **aplicativo preferencial para que os usuários ingressem em reuniões do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="ee164-120">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="ee164-121">Essa configuração determina qual aplicativo é usado para ingressar em reuniões do Skype for Business e é respeitado independentemente do valor do modo de coexistência.</span><span class="sxs-lookup"><span data-stu-id="ee164-121">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="ee164-122">**Aplicativo reuniões do Skype**</span><span class="sxs-lookup"><span data-stu-id="ee164-122">**Skype Meetings app**</span></span>
      - <span data-ttu-id="ee164-123">**Skype for Business com recursos limitados**</span><span class="sxs-lookup"><span data-stu-id="ee164-123">**Skype for Business with limited features**</span></span>
    - <span data-ttu-id="ee164-124">Defina se **o aplicativo Teams deve ser baixado em segundo plano para usuários do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="ee164-124">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="ee164-125">Essa configuração faz o download silencioso do aplicativo Teams para usuários que executam o Skype for Business no Windows.</span><span class="sxs-lookup"><span data-stu-id="ee164-125">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="ee164-126">Ele será aceito apenas se o modo de coexistência do usuário for Teams only ou se as notificações de atualização pendente estiverem habilitadas no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ee164-126">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
3. <span data-ttu-id="ee164-127">Clique em **salvar** depois de fazer as alterações.</span><span class="sxs-lookup"><span data-stu-id="ee164-127">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="ee164-128">Definir opções de atualização para um único usuário em sua organização</span><span class="sxs-lookup"><span data-stu-id="ee164-128">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="ee164-129">![Teams-logo-30x30. png](media/teams-logo-30x30.png) **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="ee164-129">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ee164-130">No painel de navegação esquerdo, vá para **usuários**e selecione o usuário na lista.</span><span class="sxs-lookup"><span data-stu-id="ee164-130">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="ee164-131">Na guia **conta** do usuário, em **atualização**do Microsoft Teams, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ee164-131">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="ee164-132">Você pode definir o **modo**de coexistência.</span><span class="sxs-lookup"><span data-stu-id="ee164-132">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="ee164-133">Escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="ee164-133">Choose from the following options:</span></span>
     - <span data-ttu-id="ee164-134">**Use as configurações de toda a organização** – Use essa configuração se quiser que o usuário use as configurações nas configurações de **toda a organização** .</span><span class="sxs-lookup"><span data-stu-id="ee164-134">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="ee164-135">**Ilhas** – Use essa configuração se quiser que o usuário possa usar o Skype for Business e o Teams.</span><span class="sxs-lookup"><span data-stu-id="ee164-135">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="ee164-136">**Skype para empresas somente** – Use esta configuração se quiser que o usuário use o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ee164-136">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span> 
     - <span data-ttu-id="ee164-137">**Somente para equipes** – Use essa configuração se quiser que o usuário use apenas as equipes.</span><span class="sxs-lookup"><span data-stu-id="ee164-137">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="ee164-138">O usuário ainda poderá ingressar em reuniões do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ee164-138">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="ee164-139">Se você selecionar qualquer **modo** de coexistência diferente de **usar as configurações de toda a organização**, terá a opção de habilitar notificações no aplicativo Skype for Business do usuário que a atualização para o Microsoft Teams estará disponível em breve.</span><span class="sxs-lookup"><span data-stu-id="ee164-139">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="ee164-140">Você pode habilitar essa notificação para o usuário ativando a opção **notificar o usuário do Skype for Business** .</span><span class="sxs-lookup"><span data-stu-id="ee164-140">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="ee164-141">Clique em **salvar** depois de fazer as alterações.</span><span class="sxs-lookup"><span data-stu-id="ee164-141">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="ee164-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ee164-142">Related topics</span></span>
[<span data-ttu-id="ee164-143">Planejar a jornada</span><span class="sxs-lookup"><span data-stu-id="ee164-143">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="ee164-144">Compreender a coexistência e atualizar a viagem para o Skype for Business e o Teams</span><span class="sxs-lookup"><span data-stu-id="ee164-144">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="ee164-145">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ee164-145">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)
