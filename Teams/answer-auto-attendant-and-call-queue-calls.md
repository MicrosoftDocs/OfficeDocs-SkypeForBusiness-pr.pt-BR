---
title: Atender chamadas do atendedor automático e da fila de chamadas diretamente no Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/20/2018
ms.topic: conceptual
ms.service: msteams
description: Descreve os atendedores automáticos de sistema telefônico e filas de chamada e explica como você pode atender essas chamadas em equipes.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91c0d1ae8034766759baa9b832cbefd399306fd2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875974"
---
<a name="answer-auto-attendant-and-call-queue-calls-directly-from-teams"></a><span data-ttu-id="032d7-103">Atender chamadas do atendedor automático e da fila de chamadas diretamente no Teams</span><span class="sxs-lookup"><span data-stu-id="032d7-103">Answer auto attendant and call queue calls directly from Teams</span></span>
===========================================================

<span data-ttu-id="032d7-104">Os usuários de equipes podem receber e atenda as chamadas do Skype para Business Online atendedor automático e filas de chamadas diretamente do seu cliente de equipes.</span><span class="sxs-lookup"><span data-stu-id="032d7-104">Teams users can receive and answer calls from Skype for Business Online auto attendant and call queues directly from their Teams client.</span></span> <span data-ttu-id="032d7-105">Para usuários de equipes, o recurso de atendedor automático agora está disponível no mercado e a capacidade de fila de chamada está no modo de visualização.</span><span class="sxs-lookup"><span data-stu-id="032d7-105">For Teams users, the auto attendant feature is now generally available, and the call queue capability is in preview.</span></span> 

## <a name="what-are-auto-attendants-and-call-queues"></a><span data-ttu-id="032d7-106">Cite atendedores automáticos de um e filas de chamada?</span><span class="sxs-lookup"><span data-stu-id="032d7-106">What are auto attendants and call queues?</span></span>

<span data-ttu-id="032d7-107">Atendedores automáticos da telefone sistema fornecem uma série de prompts de voz ou um arquivo de áudio que os chamadores ouvem, em vez de um operador humano quando ele liga para uma organização.</span><span class="sxs-lookup"><span data-stu-id="032d7-107">Phone System auto attendants provide a series of voice prompts or an audio file that callers hear instead of a human operator when they call in to an organization.</span></span> <span data-ttu-id="032d7-108">Um atendedor automático permite que os chamadores se movam pelo sistema de menus, façam chamadas ou localizem usuários usando um teclado de telefone (DTMF) ou entradas de voz usando reconhecimento de voz.</span><span class="sxs-lookup"><span data-stu-id="032d7-108">An auto attendant lets callers move through the menu system, place calls, or locate users by using a phone keypad (DTMF) or voice inputs using speech recognition.</span></span>

<span data-ttu-id="032d7-109">Telefonema de sistema filas incluem saudações que são usadas quando alguém chama um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de pesquisar para o próximo operador chamada disponíveis lidar com a chamada enquanto as pessoas que chamada está escutando a música em espera.</span><span class="sxs-lookup"><span data-stu-id="032d7-109">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="032d7-110">Você pode criar uma fila de chamadas única ou múltiplas para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="032d7-110">You can create single or multiple call queues for your organization.</span></span>

## <a name="handling-an-auto-attendant-or-call-queue-call"></a><span data-ttu-id="032d7-111">Manipulação de uma chamada de fila de chamada e atendente automático</span><span class="sxs-lookup"><span data-stu-id="032d7-111">Handling an auto attendant or call queue call</span></span>

<span data-ttu-id="032d7-112">Os usuários poderão diferenciar as chamadas de entrada a partir de uma fila de espera chamada e atendente automático antes que eles atender a chamada.</span><span class="sxs-lookup"><span data-stu-id="032d7-112">Users will be able to differentiate incoming calls from an auto attendant or call queue before they answer the call.</span></span> <span data-ttu-id="032d7-113">Junto com o nome e/ou número do chamador, cada chamada incluirá informações sobre quem o chamador estava tentando fazer contato, proporcionando aos usuários um melhor contexto para abordar o chamador.</span><span class="sxs-lookup"><span data-stu-id="032d7-113">Along with the name and/or number of the caller, each call will include information about who the caller was trying to reach, giving users a better context for addressing the caller.</span></span>

<span data-ttu-id="032d7-114">A ilustração a seguir mostra como uma chamada de entrada a partir de uma fila de espera chamada e atendente automático será exibido para um usuário.</span><span class="sxs-lookup"><span data-stu-id="032d7-114">The following illustration shows how an incoming call from an auto attendant or call queue will appear to a user.</span></span>

![Notificação de chamada recebida](media/answer-auto-attendant-and-call-queue-calls-image1.png)

<span data-ttu-id="032d7-116">Depois que uma chamada de fila de chamada e atendente automático for atendida, o usuário pode processar a chamada como qualquer outra chamada & #x 2014; eles podem adicionar ou conferência de outro usuário ou transferir a chamada para outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="032d7-116">Once an auto attendant or call queue call is answered, the user can process the call like any other call &#x2014; they can add or conference in another user or transfer the call to another party.</span></span> <span data-ttu-id="032d7-117">Além disso, as chamadas de atendedor automático serão encaminhadas com base na configuração do usuário.</span><span class="sxs-lookup"><span data-stu-id="032d7-117">Also, auto attendant calls will be forwarded based on the user’s configuration.</span></span>

> [!NOTE] 
> <span data-ttu-id="032d7-118">Chamadas de fila de chamada não são encaminhadas com base na configuração do usuário.</span><span class="sxs-lookup"><span data-stu-id="032d7-118">Call queue calls are not forwarded based on the user’s configuration.</span></span> <span data-ttu-id="032d7-119">Isso é para garantir que os chamadores permanecem na fila de espera até que um operador pode atender a chamada e o chamador não é encaminhado inesperadamente.</span><span class="sxs-lookup"><span data-stu-id="032d7-119">This is to ensure callers remain in the queue until an agent can answer the call and the caller isn’t forwarded unexpectedly.</span></span>

## <a name="supported-clients"></a><span data-ttu-id="032d7-120">Clientes suportados</span><span class="sxs-lookup"><span data-stu-id="032d7-120">Supported clients</span></span>

<span data-ttu-id="032d7-121">Suporte para chamadas de fila de chamada e atendedor automático está disponível nos seguintes clientes:</span><span class="sxs-lookup"><span data-stu-id="032d7-121">Support for auto attendant and call queue calls is available in the following clients:</span></span>

-   <span data-ttu-id="032d7-122">Cliente do Microsoft Windows de equipes (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="032d7-122">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>
-   <span data-ttu-id="032d7-123">Cliente do Microsoft equipes Mac</span><span class="sxs-lookup"><span data-stu-id="032d7-123">Microsoft Teams Mac client</span></span>
-   <span data-ttu-id="032d7-124">Microsoft Teams iPhone app</span><span class="sxs-lookup"><span data-stu-id="032d7-124">Microsoft Teams iPhone app</span></span>
-   <span data-ttu-id="032d7-125">App Android de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="032d7-125">Microsoft Teams Android app</span></span>

## <a name="configure-auto-attendant-and-call-queue-support-for-microsoft-teams"></a><span data-ttu-id="032d7-126">Configurar o suporte de fila attendant e chamada de automático for Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="032d7-126">Configure auto attendant and call queue support for Microsoft Teams</span></span>

<span data-ttu-id="032d7-127">Para receber o atendedor automático e chamar as chamadas de fila em Teams da Microsoft, você precisa configurar sua política de interoperabilidade e atualização de política.</span><span class="sxs-lookup"><span data-stu-id="032d7-127">To receive auto attendant and call queue calls on Microsoft Teams, you need to configure your interoperability policy and upgrade policy.</span></span> <span data-ttu-id="032d7-128">Analise a [migração e interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="032d7-128">Please review [Migration and interoperability for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span> <span data-ttu-id="032d7-129">Se você não tiver o atendedor automático e/ou chamada fila configurado e gostaria de fazê-lo, consulte [Configurar um atendedor automático de sistema telefônico](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) e [criar uma fila de chamada do sistema telefônico](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span><span class="sxs-lookup"><span data-stu-id="032d7-129">If you do not have auto attendant and/or call queue configured and would like to do so, see [Set up a Phone System auto attendant](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant) and [Create a Phone System call queue](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).</span></span>

## <a name="related-topics"></a><span data-ttu-id="032d7-130">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="032d7-130">Related topics</span></span>

-   [<span data-ttu-id="032d7-131">Qual é o sistema telefônico no Office 365</span><span class="sxs-lookup"><span data-stu-id="032d7-131">What is Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
-   [<span data-ttu-id="032d7-132">Criar uma fila de chamada no Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="032d7-132">Create a Phone System call queue</span></span>](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)
-   [<span data-ttu-id="032d7-133">O que são atendedores automáticos do Sistema de Telefonia?</span><span class="sxs-lookup"><span data-stu-id="032d7-133">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)
-   [<span data-ttu-id="032d7-134">Configurar os atendedores automáticos do Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="032d7-134">Set up a Phone System auto attendant</span></span>](https://docs.microsoft.com/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

