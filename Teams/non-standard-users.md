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
ms.openlocfilehash: d7b79371cdc8ff5109bf67b1c78639106a83a95e
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796638"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="186e3-103">Microsoft Teams de aplicativos para usuários não padrão</span><span class="sxs-lookup"><span data-stu-id="186e3-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="186e3-104">Este artigo descreve como os aplicativos no Teams se comportam quando usuários convidados, externos (federados) e anônimos estão presentes em um contexto Teams local.</span><span class="sxs-lookup"><span data-stu-id="186e3-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="186e3-105">Um **usuário convidado** é alguém que não é um funcionário, aluno ou membro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="186e3-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="186e3-106">Eles não têm uma conta escolar nem de trabalho com a sua organização.</span><span class="sxs-lookup"><span data-stu-id="186e3-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="186e3-107">Um **usuário externo (federado)** pertence a outro domínio e não tem acesso às equipes ou recursos de equipe da sua organização.</span><span class="sxs-lookup"><span data-stu-id="186e3-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="186e3-108">Para obter uma comparação mais detalhada de convidados versus usuários externos, [consulte se comunicar com usuários de outras organizações.](./communicate-with-users-from-other-organizations.md)</span><span class="sxs-lookup"><span data-stu-id="186e3-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="186e3-109">Um **usuário anônimo** é um conceito em reuniões Teams em que o usuário ingressou na reunião por meio de um link.</span><span class="sxs-lookup"><span data-stu-id="186e3-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="186e3-110">O usuário não fez logont com a conta da Microsoft ou da organização.</span><span class="sxs-lookup"><span data-stu-id="186e3-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-users"></a><span data-ttu-id="186e3-111">Usuários convidados</span><span class="sxs-lookup"><span data-stu-id="186e3-111">Guest users</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="186e3-112">Instalar, atualizar e excluir usuários convidados</span><span class="sxs-lookup"><span data-stu-id="186e3-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="186e3-113">Os convidados não podem instalar, atualizar ou excluir aplicativos em um contexto compartilhado, como chat, canal ou reunião, mas podem usar extensões de mensagens e links diretos.</span><span class="sxs-lookup"><span data-stu-id="186e3-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting, but they can to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="186e3-114">Os convidados não têm acesso ao Teams de aplicativos do Teams da área de trabalho, mas podem acessá-lo com um link direto.</span><span class="sxs-lookup"><span data-stu-id="186e3-114">Guests don't have access to the Teams app store from the Teams desktop application, but they can access it with a direct link.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="186e3-115">Comportamento e política de uso para usuários convidados</span><span class="sxs-lookup"><span data-stu-id="186e3-115">Usage behavior and policy for guest users</span></span> 

<span data-ttu-id="186e3-116">Os convidados podem usar um aplicativo se o aplicativo foi instalado por um usuário nativo.</span><span class="sxs-lookup"><span data-stu-id="186e3-116">Guests can use an app if the app was installed by a native user.</span></span>

#### <a name="bots-installed-to-a-channel"></a><span data-ttu-id="186e3-117">Bots instalados em um canal</span><span class="sxs-lookup"><span data-stu-id="186e3-117">Bots installed to a channel</span></span>

<span data-ttu-id="186e3-118">Os bots podem enviar mensagens proativas aos usuários convidados, mas os convidados não podem interagir com o bot.</span><span class="sxs-lookup"><span data-stu-id="186e3-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="186e3-119">Os convidados não podem enviar mensagens ao bot um para um, mencionar o bot ou interagir com cartões adaptáveis que se comunicam com o bot.</span><span class="sxs-lookup"><span data-stu-id="186e3-119">Guests can't message the bot one-to-one, mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

#### <a name="personal-bots-installed-with-policies"></a><span data-ttu-id="186e3-120">Bots pessoais instalados com políticas</span><span class="sxs-lookup"><span data-stu-id="186e3-120">Personal bots installed with policies</span></span>

- <span data-ttu-id="186e3-121">Os convidados aderirão às políticas de permissão globais e em toda a organização definidas para o locatário do host para qualquer aplicativo.</span><span class="sxs-lookup"><span data-stu-id="186e3-121">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="186e3-122">Se um aplicativo for bloqueado para toda a organização host, os convidados também não poderão usar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="186e3-122">If an app is blocked for the whole host organization, then guests can't use the app either.</span></span>
- <span data-ttu-id="186e3-123">Qualquer bot incluído na política de configuração de aplicativo padrão global também será instalado para convidados.</span><span class="sxs-lookup"><span data-stu-id="186e3-123">Any bot included in the global default app setup policy will also be installed for guests.</span></span>
- <span data-ttu-id="186e3-124">Depois que um bot é instalado, os bots podem se comunicar proativamente com convidados e os convidados podem se comunicar novamente com bots.</span><span class="sxs-lookup"><span data-stu-id="186e3-124">After a bot is installed, bots can proactively communicate with guests and guests can communicate back with bots.</span></span>
- <span data-ttu-id="186e3-125">Não é possível remover um convidado da política de configuração de aplicativo padrão global.</span><span class="sxs-lookup"><span data-stu-id="186e3-125">You can't remove a guest from the global default app setup policy.</span></span>
- <span data-ttu-id="186e3-126">Para evitar que os convidados acessem bots, você pode criar mais políticas de configuração de aplicativos, atribuí-las a usuários internos e instalar bots com as políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="186e3-126">To avoid guest from accessing bots, you can create more app setup policies, assign them to internal users, and install bots with the custom policies.</span></span>

## <a name="external-federated-users"></a><span data-ttu-id="186e3-127">Usuários externos (federados)</span><span class="sxs-lookup"><span data-stu-id="186e3-127">External (Federated) users</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="186e3-128">Instalar, atualizar e excluir usuários externos</span><span class="sxs-lookup"><span data-stu-id="186e3-128">Install, update, and delete for external users</span></span>

<span data-ttu-id="186e3-129">Os usuários externos não podem instalar, atualizar ou excluir aplicativos em qualquer contexto, como um pessoal, chat, canal ou reunião.</span><span class="sxs-lookup"><span data-stu-id="186e3-129">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="186e3-130">Eles não têm acesso ao Teams de aplicativos da organização de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="186e3-130">They don't have access to the Teams app store of the hosting organization.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="186e3-131">Comportamento e política de uso para usuários externos</span><span class="sxs-lookup"><span data-stu-id="186e3-131">Usage behavior and policy for external users</span></span>

- <span data-ttu-id="186e3-132">Pessoas de outras organizações aderem à política global (padrão em toda a organização) da organização de hospedagem</span><span class="sxs-lookup"><span data-stu-id="186e3-132">People from other organizations adhere to the hosting organization's global (org-wide default) policy</span></span>
- <span data-ttu-id="186e3-133">Os usuários na organização de hospedagem podem adicionar aplicativos em chats de reunião com pessoas de outras organizações.</span><span class="sxs-lookup"><span data-stu-id="186e3-133">Users in the hosting organization can add apps in meeting chats with people from other organizations.</span></span> <span data-ttu-id="186e3-134">As pessoas de outras organizações não podem adicionar aplicativos em chats de reunião, mas podem interagir com bots, guias e extensões de mensagens depois de adicionadas ao chat.</span><span class="sxs-lookup"><span data-stu-id="186e3-134">People from other organizations cannot add apps in meeting chats but can interact with bots, tabs and message extensions once added to the chat.</span></span>
- <span data-ttu-id="186e3-135">Depois que um bot é instalado em um chat de reunião, ele pode se comunicar proativamente com pessoas de outras organizações nesse chat e essas pessoas podem se comunicar com o bot.</span><span class="sxs-lookup"><span data-stu-id="186e3-135">After a bot is installed in a meeting chat, it can proactively communicate with people from other organizations in that chat and those people can communicate with bot.</span></span>
- <span data-ttu-id="186e3-136">As políticas de dados da organização de hospedagem, bem como as práticas de compartilhamento de dados de quaisquer aplicativos de terceiros compartilhados pela organização desse usuário, são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="186e3-136">The data policies of the hosting organization, as well as the data sharing practices of any third-party apps shared by that user's organization, are applied.</span></span>

## <a name="anonymous-users"></a><span data-ttu-id="186e3-137">Usuários anônimos</span><span class="sxs-lookup"><span data-stu-id="186e3-137">Anonymous users</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="186e3-138">Instalar, atualizar e excluir usuários anônimos</span><span class="sxs-lookup"><span data-stu-id="186e3-138">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="186e3-139">Os usuários anônimos não podem instalar, atualizar ou excluir aplicativos em reuniões.</span><span class="sxs-lookup"><span data-stu-id="186e3-139">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="186e3-140">Comportamento e política de uso para usuários anônimos</span><span class="sxs-lookup"><span data-stu-id="186e3-140">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="186e3-141">Os usuários anônimos não podem usar aplicativos diretamente em reuniões.</span><span class="sxs-lookup"><span data-stu-id="186e3-141">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="186e3-142">Os usuários nativos podem continuar a usar aplicativos de reuniões se os usuários anônimos estão presentes.</span><span class="sxs-lookup"><span data-stu-id="186e3-142">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="186e3-143">Se um aplicativo enviar um cartão adaptável no chat, os usuários anônimos poderão interagir com o cartão.</span><span class="sxs-lookup"><span data-stu-id="186e3-143">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span> <span data-ttu-id="186e3-144">Para obter mais informações, leia [Permitir que usuários anônimos participem de reuniões.](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)</span><span class="sxs-lookup"><span data-stu-id="186e3-144">For more information, read [Allow anonymous users to join meetings](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="186e3-145">Os usuários anônimos herdarão a política de permissão padrão global no nível do usuário.</span><span class="sxs-lookup"><span data-stu-id="186e3-145">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="186e3-146">Eles podem interagir com aplicativos Teams reuniões se a política de permissão no nível do usuário habilitar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="186e3-146">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="186e3-147">Os usuários anônimos só podem interagir com aplicativos que já estão disponíveis em uma reunião e não podem adquirir e/ou gerenciar esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="186e3-147">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
