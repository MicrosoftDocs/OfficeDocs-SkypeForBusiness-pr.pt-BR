---
title: Teams de aplicativos para usuários não padrão
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como os aplicativos Microsoft Teams se comportam para usuários não padrão.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: c27a73928e0740eb325c269fd5ac625fa4c43086
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628920"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="a7434-103">Microsoft Teams de aplicativos para usuários não padrão</span><span class="sxs-lookup"><span data-stu-id="a7434-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="a7434-104">Este artigo descreve como os aplicativos no Teams se comportam quando usuários convidados, externos (federados) e anônimos estão presentes em um contexto Teams local.</span><span class="sxs-lookup"><span data-stu-id="a7434-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="a7434-105">Um **usuário convidado** é alguém que não é um funcionário, aluno ou membro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="a7434-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="a7434-106">Eles não têm uma conta escolar nem de trabalho com a sua organização.</span><span class="sxs-lookup"><span data-stu-id="a7434-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="a7434-107">Um **usuário externo (federado)** pertence a outro domínio e não tem acesso às equipes ou recursos de equipe da sua organização.</span><span class="sxs-lookup"><span data-stu-id="a7434-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="a7434-108">Para obter uma comparação mais detalhada de convidados versus usuários externos, [consulte se comunicar com usuários de outras organizações.](./communicate-with-users-from-other-organizations.md)</span><span class="sxs-lookup"><span data-stu-id="a7434-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="a7434-109">Um **usuário anônimo** é um conceito em reuniões Teams em que o usuário ingressou na reunião por meio de um link.</span><span class="sxs-lookup"><span data-stu-id="a7434-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="a7434-110">O usuário não fez logont com a conta da Microsoft ou da organização.</span><span class="sxs-lookup"><span data-stu-id="a7434-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-users"></a><span data-ttu-id="a7434-111">Usuários convidados</span><span class="sxs-lookup"><span data-stu-id="a7434-111">Guest users</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="a7434-112">Instalar, atualizar e excluir usuários convidados</span><span class="sxs-lookup"><span data-stu-id="a7434-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="a7434-113">Os convidados não podem instalar, atualizar ou excluir aplicativos em um contexto compartilhado, como chat, canal ou reunião, mas podem usar extensões de mensagens e links diretos.</span><span class="sxs-lookup"><span data-stu-id="a7434-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting, but they can to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="a7434-114">Os convidados não têm acesso ao Teams de aplicativos do Teams da área de trabalho, mas podem acessá-lo com um link direto.</span><span class="sxs-lookup"><span data-stu-id="a7434-114">Guests don't have access to the Teams app store from the Teams desktop application, but they can access it with a direct link.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="a7434-115">Comportamento e política de uso para usuários convidados</span><span class="sxs-lookup"><span data-stu-id="a7434-115">Usage behavior and policy for guest users</span></span> 

<span data-ttu-id="a7434-116">Os convidados podem usar um aplicativo se o aplicativo foi instalado por um usuário nativo.</span><span class="sxs-lookup"><span data-stu-id="a7434-116">Guests can use an app if the app was installed by a native user.</span></span>

#### <a name="bots-installed-to-a-channel"></a><span data-ttu-id="a7434-117">Bots instalados em um canal</span><span class="sxs-lookup"><span data-stu-id="a7434-117">Bots installed to a channel</span></span>

<span data-ttu-id="a7434-118">Os bots podem enviar mensagens proativas aos usuários convidados, mas os convidados não podem interagir com o bot.</span><span class="sxs-lookup"><span data-stu-id="a7434-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="a7434-119">Os convidados não podem enviar mensagens ao bot um para um, mencionar o bot ou interagir com cartões adaptáveis que se comunicam com o bot.</span><span class="sxs-lookup"><span data-stu-id="a7434-119">Guests can't message the bot one-to-one, mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

#### <a name="personal-bots-installed-with-policies"></a><span data-ttu-id="a7434-120">Bots pessoais instalados com políticas</span><span class="sxs-lookup"><span data-stu-id="a7434-120">Personal bots installed with policies</span></span>

- <span data-ttu-id="a7434-121">Os convidados aderirão às políticas de permissão globais e em toda a organização definidas para o locatário do host para qualquer aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a7434-121">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="a7434-122">Se um aplicativo for bloqueado para toda a organização host, os convidados também não poderão usar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a7434-122">If an app is blocked for the whole host organization, then guests can't use the app either.</span></span>
- <span data-ttu-id="a7434-123">Qualquer bot incluído na política de configuração de aplicativo padrão global também será instalado para convidados.</span><span class="sxs-lookup"><span data-stu-id="a7434-123">Any bot included in the global default app setup policy will also be installed for guests.</span></span>
- <span data-ttu-id="a7434-124">Depois que um bot é instalado, os bots podem se comunicar proativamente com convidados e os convidados podem se comunicar novamente com bots.</span><span class="sxs-lookup"><span data-stu-id="a7434-124">After a bot is installed, bots can proactively communicate with guests and guests can communicate back with bots.</span></span>
- <span data-ttu-id="a7434-125">Não é possível remover um convidado da política de configuração de aplicativo padrão global.</span><span class="sxs-lookup"><span data-stu-id="a7434-125">You can't remove a guest from the global default app setup policy.</span></span>
- <span data-ttu-id="a7434-126">Para evitar que os convidados acessem bots, você pode criar mais políticas de configuração de aplicativos, atribuí-las a usuários internos e instalar bots com as políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="a7434-126">To avoid guest from accessing bots, you can create more app setup policies, assign them to internal users, and install bots with the custom policies.</span></span>

## <a name="external-federated-users"></a><span data-ttu-id="a7434-127">Usuários externos (federados)</span><span class="sxs-lookup"><span data-stu-id="a7434-127">External (Federated) users</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="a7434-128">Instalar, atualizar e excluir usuários externos</span><span class="sxs-lookup"><span data-stu-id="a7434-128">Install, update, and delete for external users</span></span>

<span data-ttu-id="a7434-129">Os usuários externos não podem instalar, atualizar ou excluir aplicativos em qualquer contexto, como um pessoal, chat, canal ou reunião.</span><span class="sxs-lookup"><span data-stu-id="a7434-129">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="a7434-130">Eles não têm acesso ao Teams app store.</span><span class="sxs-lookup"><span data-stu-id="a7434-130">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="a7434-131">Comportamento e política de uso para usuários externos</span><span class="sxs-lookup"><span data-stu-id="a7434-131">Usage behavior and policy for external users</span></span>

- <span data-ttu-id="a7434-132">Os usuários externos não podem usar nenhum aplicativo Teams e, quando um usuário externo é adicionado a um contexto com usuários nativos, todos os usuários – nativos e externos – não podem mais usar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a7434-132">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>
- <span data-ttu-id="a7434-133">Os usuários externos não são afetados pelas políticas de aplicativos, pois não podem usar Teams aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a7434-133">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-users"></a><span data-ttu-id="a7434-134">Usuários anônimos</span><span class="sxs-lookup"><span data-stu-id="a7434-134">Anonymous users</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="a7434-135">Instalar, atualizar e excluir usuários anônimos</span><span class="sxs-lookup"><span data-stu-id="a7434-135">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="a7434-136">Os usuários anônimos não podem instalar, atualizar ou excluir aplicativos em reuniões.</span><span class="sxs-lookup"><span data-stu-id="a7434-136">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="a7434-137">Comportamento e política de uso para usuários anônimos</span><span class="sxs-lookup"><span data-stu-id="a7434-137">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="a7434-138">Os usuários anônimos não podem usar aplicativos diretamente em reuniões.</span><span class="sxs-lookup"><span data-stu-id="a7434-138">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="a7434-139">Os usuários nativos podem continuar a usar aplicativos de reuniões se os usuários anônimos estão presentes.</span><span class="sxs-lookup"><span data-stu-id="a7434-139">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="a7434-140">Se um aplicativo enviar um cartão adaptável no chat, os usuários anônimos poderão interagir com o cartão.</span><span class="sxs-lookup"><span data-stu-id="a7434-140">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span> <span data-ttu-id="a7434-141">Para obter mais informações, leia [Permitir que usuários anônimos participem de reuniões.](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)</span><span class="sxs-lookup"><span data-stu-id="a7434-141">For more information, read [Allow anonymous users to join meetings](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="a7434-142">Os usuários anônimos herdarão a política de permissão padrão global no nível do usuário.</span><span class="sxs-lookup"><span data-stu-id="a7434-142">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="a7434-143">Eles podem interagir com aplicativos Teams reuniões se a política de permissão no nível do usuário habilitar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a7434-143">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="a7434-144">Os usuários anônimos só podem interagir com aplicativos que já estão disponíveis em uma reunião e não podem adquirir e/ou gerenciar esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a7434-144">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
