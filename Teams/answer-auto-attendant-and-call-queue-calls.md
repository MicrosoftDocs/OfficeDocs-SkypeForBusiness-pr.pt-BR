---
title: Atender chamadas de atendemento automático e fila de chamadas
ms.reviewer: waseemh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Descreve os atendedores automáticos e filas de chamadas na nuvem e explica como você pode atender a essas chamadas no Teams.
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
ms.openlocfilehash: 95719bc95cc752888964a5f404e6f8050ebf3fa4
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766855"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="64731-103">Atender chamadas do atendedor automático e da fila de chamadas diretamente no Teams</span><span class="sxs-lookup"><span data-stu-id="64731-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="64731-104">Os usuários do Teams podem receber e atender chamadas de atendedores automáticos na nuvem e filas de chamadas diretamente do cliente do Teams.</span><span class="sxs-lookup"><span data-stu-id="64731-104">Teams users can receive and answer calls from Cloud auto attendants and call queues directly from their Teams client.</span></span>

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="64731-105">O que são os atendimentos automáticos e filas de chamada?</span><span class="sxs-lookup"><span data-stu-id="64731-105">What are auto attendants and call queues?</span></span>

<span data-ttu-id="64731-106">Os participantes automáticos da nuvem fornecem uma série de avisos de voz ou um arquivo de áudio que os chamadores ouvem em vez de um operador humano quando eles ligarem para uma organização.</span><span class="sxs-lookup"><span data-stu-id="64731-106">Cloud auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="64731-107">Um atendedor automático permite que os chamadores se movam pelo sistema de menus, façam chamadas ou localizem usuários usando um teclado de telefone (DTMF) ou entradas de voz usando reconhecimento de voz.</span><span class="sxs-lookup"><span data-stu-id="64731-107">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="64731-108">As filas de chamadas na nuvem incluem saudações que são usadas quando alguém liga para um número de telefone de sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de procurar o próximo agente de chamada disponível para lidar com a chamada enquanto as pessoas que telefonam estão ouvindo música em espera.</span><span class="sxs-lookup"><span data-stu-id="64731-108">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="64731-109">Você pode criar uma ou várias filas de chamadas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="64731-109">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="64731-110">Lidar com um atender automático ou chamada na fila de chamada</span><span class="sxs-lookup"><span data-stu-id="64731-110">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="64731-111">Os usuários poderão diferenciar as chamadas recebidas de um atendedores automáticos ou fila de chamadas antes de atenderem a chamada.</span><span class="sxs-lookup"><span data-stu-id="64731-111">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="64731-112">Juntamente com o nome e/ou o número do chamador, cada chamada incluirá informações sobre quem o chamador estava tentando falar, dando aos usuários um contexto melhor para endereçamento ao chamador.</span><span class="sxs-lookup"><span data-stu-id="64731-112">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="64731-113">A ilustração a seguir mostra como uma chamada recebida de um atendimento automático ou fila de chamadas aparecerá para um usuário.</span><span class="sxs-lookup"><span data-stu-id="64731-113">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Captura de tela de uma notificação de chamada recebida](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="64731-115">Quando um atende-automático ou uma chamada na fila de chamada é atendida, o usuário pode processar a chamada como qualquer outra chamada &#x2014; pode adicionar ou fazer conferência em outro usuário ou transferir a chamada para outra parte.</span><span class="sxs-lookup"><span data-stu-id="64731-115">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="64731-116">Além disso, as chamadas de atendimento automático serão encaminhadas com base na configuração do usuário.</span><span class="sxs-lookup"><span data-stu-id="64731-116">Also, auto attendant calls will be forwarded based on the user's configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="64731-117">As chamadas na fila de chamadas não são encaminhadas com base na configuração do usuário.</span><span class="sxs-lookup"><span data-stu-id="64731-117">Call queue calls are not forwarded based on the user's configuration.</span></span> <span data-ttu-id="64731-118">Isso é para garantir que os chamadores permaneçam na fila até que um agente possa atender a chamada e o chamador não seja encaminhado inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="64731-118">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn't forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="64731-119">Clientes com suporte</span><span class="sxs-lookup"><span data-stu-id="64731-119">Supported clients</span></span>

<span data-ttu-id="64731-120">O suporte para chamadas de fila de chamadas e atendimento automático está disponível nos seguintes clientes:</span><span class="sxs-lookup"><span data-stu-id="64731-120">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-    <span data-ttu-id="64731-121">Cliente Microsoft Teams para Windows (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="64731-121">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-    <span data-ttu-id="64731-122">Cliente do Microsoft Teams Mac</span><span class="sxs-lookup"><span data-stu-id="64731-122">Microsoft Teams Mac client</span></span>
-    <span data-ttu-id="64731-123">Aplicativo Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="64731-123">Microsoft Teams iPhone app</span></span>
-    <span data-ttu-id="64731-124">Aplicativo Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="64731-124">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="64731-125">Configurar o suporte a atendimento automático e fila de chamada para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64731-125">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="64731-126">Para receber chamadas de atendimento automático e fila de chamadas no Microsoft Teams, você precisa configurar a política de interoperabilidade e a política de atualização.</span><span class="sxs-lookup"><span data-stu-id="64731-126">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="64731-127">Revise a [migração e a interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="64731-127">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="64731-128">Se você não tiver o atendimento automático e/ou fila de [](create-a-phone-system-auto-attendant.md) chamada configurado e gostaria de fazer isso, consulte Configurar um atendimento automático na nuvem e Criar uma fila [de chamada na nuvem.](create-a-phone-system-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="64731-128">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md) and [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="64731-129">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="64731-129">Known Issues</span></span>

<span data-ttu-id="64731-130">Quando os agentes da fila de chamadas recebem uma chamada em seu dispositivo móvel, as chamadas podem ficar em espera se o dispositivo estiver bloqueado.</span><span class="sxs-lookup"><span data-stu-id="64731-130">When a call queue agents receives a call on their mobile device, calls may go on hold if the device is locked.</span></span> <span data-ttu-id="64731-131">O usuário deve desbloquear o dispositivo primeiro e atender a chamada.</span><span class="sxs-lookup"><span data-stu-id="64731-131">User must unlock device first and then answer the call.</span></span>


## <a name="related-topics"></a><span data-ttu-id="64731-132">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="64731-132">Related topics</span></span>

-    [<span data-ttu-id="64731-133">O que é o Sistema telefônico no Microsoft 365 ou no Office 365</span><span class="sxs-lookup"><span data-stu-id="64731-133">What is Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
-    [<span data-ttu-id="64731-134">Criar uma fila de chamada do Cloud</span><span class="sxs-lookup"><span data-stu-id="64731-134">Create a Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
-    [<span data-ttu-id="64731-135">Quais são os atendedores automáticos do Cloud?</span><span class="sxs-lookup"><span data-stu-id="64731-135">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-    [<span data-ttu-id="64731-136">Configurar um atendedor automático do Cloud</span><span class="sxs-lookup"><span data-stu-id="64731-136">Set up a Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

