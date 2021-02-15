---
title: Comportamento de aplicativos do Teams para usuários não padrão
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como os aplicativos no Microsoft Teams se comportam para usuários não padrão.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 683ba9a20c51a23fa1468c07407a389c23dba507
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237491"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="592e2-103">Comportamento de aplicativos do Microsoft Teams para usuários não padrão</span><span class="sxs-lookup"><span data-stu-id="592e2-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="592e2-104">Este artigo descreve como os aplicativos no Teams se comportam quando usuários convidados, externos (federados) e anônimos estão presentes em um contexto do Teams.</span><span class="sxs-lookup"><span data-stu-id="592e2-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="592e2-105">Um **usuário convidado** é alguém que não é um funcionário, aluno ou membro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="592e2-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="592e2-106">Eles não têm uma conta escolar nem de trabalho com a sua organização.</span><span class="sxs-lookup"><span data-stu-id="592e2-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="592e2-107">Um **usuário externo (federado)** pertence a outro domínio e não tem acesso às equipes ou recursos de equipe da sua organização.</span><span class="sxs-lookup"><span data-stu-id="592e2-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

>[!Note]
> <span data-ttu-id="592e2-108">Para obter uma comparação mais detalhada de convidados versus usuários externos, [consulte se comunicar com usuários de outras organizações.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)</span><span class="sxs-lookup"><span data-stu-id="592e2-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations).</span></span>

- <span data-ttu-id="592e2-109">Um **usuário anônimo** é um conceito nas reuniões do Teams em que o usuário ingressou na reunião por meio de um link.</span><span class="sxs-lookup"><span data-stu-id="592e2-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="592e2-110">O usuário não entrou com a conta da Microsoft ou da organização.</span><span class="sxs-lookup"><span data-stu-id="592e2-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-user-access"></a><span data-ttu-id="592e2-111">Acesso de usuário convidado</span><span class="sxs-lookup"><span data-stu-id="592e2-111">Guest user access</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="592e2-112">Instalar, atualizar e excluir para usuários convidados</span><span class="sxs-lookup"><span data-stu-id="592e2-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="592e2-113">Os convidados não podem instalar, atualizar ou excluir aplicativos em um contexto compartilhado, como chat, canal ou reunião.</span><span class="sxs-lookup"><span data-stu-id="592e2-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting.</span></span> <span data-ttu-id="592e2-114">Eles podem instalar, atualizar ou excluir aplicativos no escopo pessoal usando extensões de mensagem e links diretos.</span><span class="sxs-lookup"><span data-stu-id="592e2-114">They can install, update, or delete apps to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="592e2-115">Os convidados não têm acesso à loja de aplicativos do Teams.</span><span class="sxs-lookup"><span data-stu-id="592e2-115">Guests don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="592e2-116">Comportamento e política de uso para usuários convidados</span><span class="sxs-lookup"><span data-stu-id="592e2-116">Usage behavior and policy for guest users</span></span>

<span data-ttu-id="592e2-117">Os convidados podem usar um aplicativo se o aplicativo foi instalado por um usuário nativo.</span><span class="sxs-lookup"><span data-stu-id="592e2-117">Guests can use an app if the app was installed by a native user.</span></span>

<span data-ttu-id="592e2-118">Os bots podem enviar mensagens proativas aos usuários convidados, mas os convidados não podem interagir com o bot.</span><span class="sxs-lookup"><span data-stu-id="592e2-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="592e2-119">Os convidados não podem enviar mensagens para o bot 1:1, @ mencionar o bot ou interagir com cartões adaptáveis que se comunicam com o bot.</span><span class="sxs-lookup"><span data-stu-id="592e2-119">Guests can't message the bot 1:1, @ mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

<span data-ttu-id="592e2-120">Os convidados seguirão as políticas de permissão globais e de toda a organização definidas para o locatário host de qualquer aplicativo.</span><span class="sxs-lookup"><span data-stu-id="592e2-120">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="592e2-121">(Em outras palavras, se um aplicativo estiver bloqueado para toda a organização host, os convidados também não poderão usar o aplicativo.)</span><span class="sxs-lookup"><span data-stu-id="592e2-121">(In other words, if an app is blocked for the whole host organization, then guests can't use the app either.)</span></span>

<span data-ttu-id="592e2-122">As políticas de configuração não se aplicam aos usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="592e2-122">Setup policies don't apply to guest users.</span></span> <span data-ttu-id="592e2-123">Isso significa que o aplicativo fixado pelo administrador da política padrão não afeta os usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="592e2-123">This means admin pinned app from the default policy doesn't affect guest users.</span></span>

## <a name="external-federated-user-access"></a><span data-ttu-id="592e2-124">Acesso de usuário externo (federado)</span><span class="sxs-lookup"><span data-stu-id="592e2-124">External (Federated) user access</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="592e2-125">Instalar, atualizar e excluir para usuários externos</span><span class="sxs-lookup"><span data-stu-id="592e2-125">Install, update, and delete for external users</span></span>

<span data-ttu-id="592e2-126">Os usuários externos não podem instalar, atualizar ou excluir aplicativos em qualquer contexto, como um chat, um canal ou uma reunião pessoal.</span><span class="sxs-lookup"><span data-stu-id="592e2-126">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="592e2-127">Eles não têm acesso à loja de aplicativos do Teams.</span><span class="sxs-lookup"><span data-stu-id="592e2-127">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="592e2-128">Comportamento e política de uso para usuários externos</span><span class="sxs-lookup"><span data-stu-id="592e2-128">Usage behavior and policy for external users</span></span>

<span data-ttu-id="592e2-129">Os usuários externos não podem usar os aplicativos do Teams e, quando um usuário externo é adicionado a um contexto com usuários nativos, todos os usuários , nativos e externos, não podem mais usar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="592e2-129">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>

<span data-ttu-id="592e2-130">Os usuários externos não são afetados pelas políticas de aplicativos, pois não podem usar os aplicativos do Teams.</span><span class="sxs-lookup"><span data-stu-id="592e2-130">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-user-in-meetings-access"></a><span data-ttu-id="592e2-131">Usuário anônimo no acesso a reuniões</span><span class="sxs-lookup"><span data-stu-id="592e2-131">Anonymous user in meetings access</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="592e2-132">Instalar, atualizar e excluir usuários anônimos</span><span class="sxs-lookup"><span data-stu-id="592e2-132">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="592e2-133">Os usuários anônimos não podem instalar, atualizar ou excluir aplicativos em reuniões.</span><span class="sxs-lookup"><span data-stu-id="592e2-133">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="592e2-134">Comportamento e política de uso para usuários anônimos</span><span class="sxs-lookup"><span data-stu-id="592e2-134">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="592e2-135">Os usuários anônimos não podem usar aplicativos diretamente em reuniões.</span><span class="sxs-lookup"><span data-stu-id="592e2-135">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="592e2-136">Os usuários nativos podem continuar a usar aplicativos de reuniões se os usuários anônimos estão presentes.</span><span class="sxs-lookup"><span data-stu-id="592e2-136">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="592e2-137">Se um aplicativo enviar um cartão adaptável no chat, os usuários anônimos poderão interagir com o cartão.</span><span class="sxs-lookup"><span data-stu-id="592e2-137">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span>

<span data-ttu-id="592e2-138">Os usuários anônimos herdarão a política de permissão padrão global em nível de usuário.</span><span class="sxs-lookup"><span data-stu-id="592e2-138">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="592e2-139">Esse controle permite que usuários anônimos interajam com aplicativos em reuniões do Teams, desde que a política de permissão no nível do usuário tenha habilitado o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="592e2-139">This control allows anonymous users to interact with apps in Teams meetings as long as the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="592e2-140">Os usuários anônimos só podem interagir com aplicativos que já estão disponíveis em uma reunião e não podem adquirir e/ou gerenciar esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="592e2-140">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
