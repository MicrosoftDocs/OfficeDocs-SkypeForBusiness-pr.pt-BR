---
title: Atender chamadas de atendedor automático e fila de chamadas
ms.reviewer: waseemh
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Descreve atendedores automáticos da nuvem e filas de chamadas e explica como você pode responder a essas chamadas no Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d630ea41915cb89013e407a6fa0b1cc21cb21abf
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137431"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="66239-103">Atender chamadas do atendedor automático e da fila de chamadas diretamente no Teams</span><span class="sxs-lookup"><span data-stu-id="66239-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="66239-104">Os usuários do teams podem receber e atender chamadas de atendedores automáticos da nuvem e filas de chamadas diretamente do cliente de suas equipes.</span><span class="sxs-lookup"><span data-stu-id="66239-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span> <span data-ttu-id="66239-105">Para usuários do Teams, o recurso atendedor automático agora está disponível geralmente, e o recurso de fila de chamadas está em visualização.</span><span class="sxs-lookup"><span data-stu-id="66239-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="66239-106">O que são atendedores automáticos e filas de chamadas?</span><span class="sxs-lookup"><span data-stu-id="66239-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="66239-107">Os atendedores automáticos na nuvem fornecem uma série de prompts de voz ou um arquivo de áudio que os chamadores ouvem em vez de uma operadora humana quando eles chamam para uma organização.</span><span class="sxs-lookup"><span data-stu-id="66239-107">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="66239-108">Um atendedor automático permite que os chamadores se movam pelo sistema de menus, façam chamadas ou localizem usuários usando um teclado de telefone (DTMF) ou entradas de voz usando reconhecimento de voz.</span><span class="sxs-lookup"><span data-stu-id="66239-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="66239-109">As filas de chamadas na nuvem incluem Saudações que são usadas quando alguém liga para um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de Pesquisar o próximo agente de chamada disponível para manipular a chamada, enquanto as pessoas que ligam estão ouvindo música em espera.</span><span class="sxs-lookup"><span data-stu-id="66239-109">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="66239-110">Você pode criar uma ou várias filas de chamadas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="66239-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="66239-111">Manipulando um atendedor automático ou chamada em fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="66239-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="66239-112">Os usuários poderão diferenciar as chamadas recebidas de um atendedor automático ou da fila de chamadas antes de atenderem a chamada.</span><span class="sxs-lookup"><span data-stu-id="66239-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="66239-113">Juntamente com o nome e/ou o número do chamador, cada chamada incluirá informações sobre quem o chamador estava tentando alcançar, dando aos usuários um contexto melhor para o endereçamento do chamador.</span><span class="sxs-lookup"><span data-stu-id="66239-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="66239-114">A ilustração a seguir mostra como uma chamada de entrada de um atendedor automático ou fila de chamadas aparecerá para um usuário.</span><span class="sxs-lookup"><span data-stu-id="66239-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Captura de tela de uma notificação de chamada recebida](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="66239-116">Quando um atendedor automático ou uma chamada de fila de chamada for respondido, o usuário poderá processar a chamada como qualquer outra chamada &#x2014; ela pode adicionar ou enviar uma conferência para outro usuário ou transferir a chamada para outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="66239-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="66239-117">Além disso, as chamadas de atendedor automático serão encaminhadas com base na configuração do usuário.</span><span class="sxs-lookup"><span data-stu-id="66239-117">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="66239-118">As chamadas da fila de chamadas não são encaminhadas com base na configuração do usuário.</span><span class="sxs-lookup"><span data-stu-id="66239-118">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="66239-119">Isso é para garantir que os chamadores permaneçam na fila até que um agente possa atender a chamada, e o chamador não seja encaminhado inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="66239-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="66239-120">Clientes com suporte</span><span class="sxs-lookup"><span data-stu-id="66239-120">Supported clients</span></span>

<span data-ttu-id="66239-121">O suporte para o atendedor automático e as chamadas da fila de chamadas está disponível nos seguintes clientes:</span><span class="sxs-lookup"><span data-stu-id="66239-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="66239-122">Microsoft Teams Windows Client (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="66239-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="66239-123">Cliente Mac do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66239-123">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="66239-124">Aplicativo iPhone do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66239-124">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="66239-125">Aplicativo Android do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66239-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="66239-126">Configurar o atendedor automático e o suporte à fila de chamadas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66239-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="66239-127">Para receber chamadas de atendedor automático e fila de chamadas no Microsoft Teams, você precisa configurar a política de interoperabilidade e a política de atualização.</span><span class="sxs-lookup"><span data-stu-id="66239-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="66239-128">Revise [a migração e a interoperabilidade de organizações que usam o Skype for Business em equipe](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="66239-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="66239-129">Se você não tiver o atendedor automático e/ou a fila de chamadas configurada e quiser fazer isso, consulte [configurar um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md) e [criar uma fila de chamadas na nuvem](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="66239-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="66239-130">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="66239-130">Related topics</span></span>

-    [<span data-ttu-id="66239-131">O que é o sistema telefônico no Office 365</span><span class="sxs-lookup"><span data-stu-id="66239-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="66239-132">Criar uma fila de chamada do Cloud</span><span class="sxs-lookup"><span data-stu-id="66239-132">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="66239-133">Quais são os atendedores automáticos do Cloud?</span><span class="sxs-lookup"><span data-stu-id="66239-133">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="66239-134">Configurar um atendedor automático do Cloud</span><span class="sxs-lookup"><span data-stu-id="66239-134">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

