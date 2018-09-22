---
title: Atender atendedor automático e chamadas de fila de chamadas diretamente a partir de equipes
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: article
ms.service: msteams
description: Descreve os atendedores automáticos de sistema telefônico e filas de chamada e explica como você pode atender essas chamadas em equipes.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b176131cd8c491916f8b934daa763e62a9bf2a8
ms.sourcegitcommit: 17f6d3ac603ee5bc47785e566a052dc2625ccf76
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2018
ms.locfileid: "24064970"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="dc360-103">Atender atendedor automático e chamadas de fila de chamadas diretamente a partir de equipes</span><span class="sxs-lookup"><span data-stu-id="dc360-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="dc360-104">Os usuários de equipes podem receber e atenda as chamadas do Skype para Business Online atendedor automático e filas de chamadas diretamente do seu cliente de equipes.</span><span class="sxs-lookup"><span data-stu-id="dc360-104">Teams users can receive and answer calls from Skype for Business Online auto attendant and call queues directly from their Teams client.</span></span> <span data-ttu-id="dc360-105">Para usuários de equipes, o recurso de atendedor automático agora está disponível no mercado e a capacidade de fila de chamada está no modo de visualização.</span><span class="sxs-lookup"><span data-stu-id="dc360-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="dc360-106">Cite atendedores automáticos de um e filas de chamada?</span><span class="sxs-lookup"><span data-stu-id="dc360-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="dc360-107">Atendedores automáticos da telefone sistema fornecem uma série de prompts de voz ou um arquivo de áudio que os chamadores ouvem, em vez de um operador humano quando ele liga para uma organização.</span><span class="sxs-lookup"><span data-stu-id="dc360-107">Phone System auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="dc360-108">Um atendedor automático permite que os chamadores se movam pelo sistema de menus, façam chamadas ou localizem usuários usando um teclado de telefone (DTMF) ou entradas de voz usando reconhecimento de voz.</span><span class="sxs-lookup"><span data-stu-id="dc360-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="dc360-109">Telefonema de sistema filas incluem saudações que são usadas quando alguém chama um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de pesquisar para o próximo operador chamada disponíveis lidar com a chamada enquanto as pessoas que chamada está escutando a música em espera.</span><span class="sxs-lookup"><span data-stu-id="dc360-109">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="dc360-110">Você pode criar uma fila de chamadas única ou múltiplas para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="dc360-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="dc360-111">Manipulação de uma chamada de fila de chamada e atendente automático</span><span class="sxs-lookup"><span data-stu-id="dc360-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="dc360-112">Os usuários poderão diferenciar as chamadas de entrada a partir de uma fila de espera chamada e atendente automático antes que eles atender a chamada.</span><span class="sxs-lookup"><span data-stu-id="dc360-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="dc360-113">Junto com o nome e/ou número do chamador, cada chamada incluirá informações sobre quem o chamador estava tentando fazer contato, proporcionando aos usuários um melhor contexto para abordar o chamador.</span><span class="sxs-lookup"><span data-stu-id="dc360-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="dc360-114">A ilustração a seguir mostra como uma chamada de entrada a partir de uma fila de espera chamada e atendente automático será exibido para um usuário.</span><span class="sxs-lookup"><span data-stu-id="dc360-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Notificação de chamada recebida](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="dc360-116">Depois que uma chamada de fila de chamada e atendente automático for atendida, o usuário pode processar a chamada como qualquer chamada & #x 2014; eles podem adicionar ou conferência de outro usuário ou transferir a chamada para outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="dc360-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="dc360-117">Além disso, as chamadas de atendedor automático serão encaminhadas com base na configuração do usuário.</span><span class="sxs-lookup"><span data-stu-id="dc360-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="dc360-118">Chamadas de fila de chamada não são encaminhadas com base na configuração do usuário.</span><span class="sxs-lookup"><span data-stu-id="dc360-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="dc360-119">Isso é para garantir que os chamadores permanecem na fila de espera até que um operador pode atender a chamada e o chamador não é encaminhado inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="dc360-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="dc360-120">Clientes suportados</span><span class="sxs-lookup"><span data-stu-id="dc360-120">Supported clients</span></span>

<span data-ttu-id="dc360-121">Suporte para chamadas de fila de chamada e atendedor automático está disponível nos seguintes clientes:</span><span class="sxs-lookup"><span data-stu-id="dc360-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="dc360-122">Cliente do Windows para Microsoft Teams (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="dc360-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="dc360-123">Cliente Mac para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc360-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="dc360-124">Aplicativo do Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="dc360-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="dc360-125">Aplicativo do Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="dc360-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="dc360-126">Configurar o suporte de fila attendant e chamada de automático for Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc360-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="dc360-127">Para receber o atendedor automático e chamar as chamadas de fila em Teams da Microsoft, você precisa configurar sua política de interoperabilidade e atualização de política.</span><span class="sxs-lookup"><span data-stu-id="dc360-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="dc360-128">Analise a [migração e interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="dc360-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="dc360-129">Se você não tiver o atendedor automático e/ou chamada fila configurado e gostaria de fazê-lo, consulte [Configurar um atendedor automático de sistema telefônico](https://docs.microsoft.com/en-us/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) e [criar uma fila de chamada do sistema telefônico](https://docs.microsoft.com/en-us/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span><span class="sxs-lookup"><span data-stu-id="dc360-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Phone System auto attendant](https://docs.microsoft.com/en-us/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) and [Create a Phone System call queue](https://docs.microsoft.com/en-us/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dc360-130">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="dc360-130">Related topics</span></span>

-   [<span data-ttu-id="dc360-131">Qual é o sistema telefônico no Office 365</span><span class="sxs-lookup"><span data-stu-id="dc360-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="dc360-132">Criar uma fila de chamadas do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="dc360-132">Create a Phone System call queue</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [<span data-ttu-id="dc360-133">O que são atendedores automáticos do Sistema de Telefonia?</span><span class="sxs-lookup"><span data-stu-id="dc360-133">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="dc360-134">Configurar o atendedor automático do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="dc360-134">Set up a Phone System auto attendant</span></span>](https://docs.microsoft.com/en-us/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

