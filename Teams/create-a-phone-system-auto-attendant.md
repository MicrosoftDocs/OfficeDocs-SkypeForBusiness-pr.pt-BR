---
title: Configurar um atendimento automático para Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Saiba como configurar e testar os atendimentos automáticos para Microsoft Teams.
ms.openlocfilehash: 2aef87d1a7885df01b02a5708ac1079ea8021add
ms.sourcegitcommit: 745b37921a878f1b524a274bfb2fd0732716a5c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2021
ms.locfileid: "52498786"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="a8361-103">Configurar um atendimento automático</span><span class="sxs-lookup"><span data-stu-id="a8361-103">Set up an auto attendant</span></span>

<span data-ttu-id="a8361-104">Os atendentes automáticos permitem que as pessoas liguem para sua organização e naveguem por um sistema de menus para falar com o departamento certo, fila de chamada, pessoa ou operador.</span><span class="sxs-lookup"><span data-stu-id="a8361-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="a8361-105">Você pode criar assistentes automáticos para sua organização com o Microsoft Teams de administração ou com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8361-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="a8361-106">Leia Plan for Teams auto attendants and [call queues](plan-auto-attendant-call-queue.md) [](plan-auto-attendant-call-queue.md#getting-started) e siga as etapas de início antes de seguir os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="a8361-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="a8361-107">Os atendimentos automáticos podem direcionar chamadas, com base na entrada dos chamadores, para um dos seguintes destinos: <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="a8361-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="a8361-108">**Operador** - o operador definido para o atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="a8361-108">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="a8361-109">Definir um operador é opcional.</span><span class="sxs-lookup"><span data-stu-id="a8361-109">Defining an operator is optional.</span></span> <span data-ttu-id="a8361-110">O operador pode ser definido como qualquer um dos outros destinos nesta lista.</span><span class="sxs-lookup"><span data-stu-id="a8361-110">The operator can be defined as any of the other destinations in this list.</span></span>
- <span data-ttu-id="a8361-111">**Pessoa na organização** - uma pessoa em sua organização que pode receber chamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="a8361-111">**Person in the organization** - a person in your organization who can receive voice calls.</span></span> <span data-ttu-id="a8361-112">Essa pessoa pode ser um usuário online ou um usuário hospedado no local usando Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a8361-112">This person can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="a8361-113">**Aplicativo de voz** - outro atendimento automático ou uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="a8361-113">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="a8361-114">(Escolha a conta de recurso associada ao atendimento automático ou fila de chamada ao escolher esse destino.)</span><span class="sxs-lookup"><span data-stu-id="a8361-114">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="a8361-115">**Caixa** postal - a caixa de correio de voz associada a um grupo Microsoft 365 que você especificar.</span><span class="sxs-lookup"><span data-stu-id="a8361-115">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="a8361-116">**Número de telefone externo** - qualquer número de telefone.</span><span class="sxs-lookup"><span data-stu-id="a8361-116">**External phone number** - any phone number.</span></span> <span data-ttu-id="a8361-117">(Consulte [detalhes técnicos de transferência externa](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span><span class="sxs-lookup"><span data-stu-id="a8361-117">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="a8361-118">**Comunicado (Arquivo de áudio)** - Reproduzir um arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="a8361-118">**Announcement (Audio file)** - Play an audio file.</span></span> <span data-ttu-id="a8361-119">Uma mensagem de anúncio gravada que você carrega salva como áudio em . WAV, .MP3 ou . Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="a8361-119">A recorded announcement message you upload that's saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="a8361-120">A gravação não pode ser maior do que 5 MB.</span><span class="sxs-lookup"><span data-stu-id="a8361-120">The recording can be no larger than 5 MB.</span></span> <span data-ttu-id="a8361-121">O sistema reproduz o comunicado e retorna ao menu de atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="a8361-121">The system plays the announcement, and then returns to the auto attendant menu.</span></span>
- <span data-ttu-id="a8361-122">**Comunicado (Digitado)** - Digite uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="a8361-122">**Announcement (Typed)** - Type in a message.</span></span> <span data-ttu-id="a8361-123">Texto que você deseja que o sistema leia.</span><span class="sxs-lookup"><span data-stu-id="a8361-123">Text you want the system to read.</span></span> <span data-ttu-id="a8361-124">Você pode inserir até 1000 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a8361-124">You can enter up to 1000 characters.</span></span> <span data-ttu-id="a8361-125">O sistema reproduz o comunicado e retorna ao menu de atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="a8361-125">The system plays the announcement, and then returns to the auto attendant menu.</span></span>

<span data-ttu-id="a8361-126">Você será solicitado a escolher uma dessas opções em vários estágios ao configurar um atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="a8361-126">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

> [!NOTE]
> <span data-ttu-id="a8361-127">Ao escolher a Caixa Postal como destino, duas opções adicionais estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="a8361-127">When choosing Voicemail as a destination, two additional options are available:</span></span>
> - <span data-ttu-id="a8361-128">**Transcrição** (Padrão: Desligado) - quando habilitada, a mensagem de caixa postal será transcrita e incluída como parte do email.</span><span class="sxs-lookup"><span data-stu-id="a8361-128">**Transcription** (Default: Off) - when enabled, the voicemail message will be transcribed and included as part of the email.</span></span>
> - <span data-ttu-id="a8361-129">**Suprimir Saudação** (Padrão: Desligado) - quando habilitada, a mensagem padrão do sistema "Deixe uma mensagem após o tom.</span><span class="sxs-lookup"><span data-stu-id="a8361-129">**Suppress Greeting** (Default: Off) - when enabled, the standard system message "Please leave a message after the tone.</span></span> <span data-ttu-id="a8361-130">Quando terminar, desligue ou pressione a tecla hash para obter mais opções."</span><span class="sxs-lookup"><span data-stu-id="a8361-130">When you have finished please hang up or press the hash key for more options."</span></span> <span data-ttu-id="a8361-131">será suprimido.</span><span class="sxs-lookup"><span data-stu-id="a8361-131">will be suppressed.</span></span>

<span data-ttu-id="a8361-132">Para configurar um atendimento automático, no centro de administração Teams, **expanda Voz,** selecione **Assistentes automáticos** e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a8361-132">To set up an auto attendant, in the Teams admin center, expand **Voice**, select **Auto attendants**, and then select **Add**.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="a8361-133">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="a8361-133">Video demonstration</span></span>

<span data-ttu-id="a8361-134">Este vídeo mostra um exemplo básico de como criar um assistente automático no Teams.</span><span class="sxs-lookup"><span data-stu-id="a8361-134">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a><span data-ttu-id="a8361-135">Informações gerais</span><span class="sxs-lookup"><span data-stu-id="a8361-135">General info</span></span>

![Captura de tela das configurações de atendimento automático para nome, operador, fuso horário, idioma e entradas de voz](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="a8361-137">Digite um nome para o atendimento automático na caixa na parte superior.</span><span class="sxs-lookup"><span data-stu-id="a8361-137">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="a8361-138">Para designar um operador, especifique o destino das chamadas para o operador.</span><span class="sxs-lookup"><span data-stu-id="a8361-138">To designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="a8361-139">Essa designação é opcional (mas recomendada).</span><span class="sxs-lookup"><span data-stu-id="a8361-139">This designation is optional (but recommended).</span></span> <span data-ttu-id="a8361-140">De definir **a opção** Operador para permitir que os chamadores saiam dos menus e fale com uma pessoa designada.</span><span class="sxs-lookup"><span data-stu-id="a8361-140">Set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="a8361-141">Especifique o fuso horário desse atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="a8361-141">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="a8361-142">O fuso horário é usado para calcular o horário comercial se você criar um fluxo de chamada [separado para o horário.](#call-flow-for-after-hours)</span><span class="sxs-lookup"><span data-stu-id="a8361-142">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="a8361-143">[Especifique um idioma com suporte](create-a-phone-system-auto-attendant-languages.md) para esse atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="a8361-143">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="a8361-144">Esse é o idioma que será usado para prompts de voz gerados pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="a8361-144">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="a8361-145">Escolha se deseja habilitar entradas de voz.</span><span class="sxs-lookup"><span data-stu-id="a8361-145">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="a8361-146">Quando habilitada, o nome de cada opção de menu se torna uma palavra-chave de reconhecimento de fala.</span><span class="sxs-lookup"><span data-stu-id="a8361-146">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="a8361-147">Por exemplo, os chamadores podem dizer "Um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "Vendas" para selecionar a opção de menu chamada "Vendas".</span><span class="sxs-lookup"><span data-stu-id="a8361-147">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

> [!NOTE]
> <span data-ttu-id="a8361-148">Se você escolher um idioma na Etapa 4 que não suporte entradas de voz, essa opção será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="a8361-148">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="a8361-149">Selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a8361-149">Select **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="a8361-150">Fluxo de chamada</span><span class="sxs-lookup"><span data-stu-id="a8361-150">Call flow</span></span>

![Captura de tela das configurações da mensagem de saudação](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="a8361-152">Escolha se deseja reproduzir uma saudação quando o atendente automático atender uma chamada.</span><span class="sxs-lookup"><span data-stu-id="a8361-152">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="a8361-153">Se você selecionar **Reproduzir um arquivo de** áudio, poderá usar o botão de arquivo **Upload** para carregar uma mensagem de saudação gravada salva como áudio em . WAV, .MP3 ou . Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="a8361-153">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="a8361-154">A gravação não pode ser maior do que 5 MB.</span><span class="sxs-lookup"><span data-stu-id="a8361-154">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="a8361-155">Se você selecionar **Digitar uma mensagem de** saudação, o sistema lerá o texto que você digitar (até 1000 caracteres) quando o atende automaticamente atender a uma chamada.</span><span class="sxs-lookup"><span data-stu-id="a8361-155">If you select **Type a greeting message** the system will read the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Captura de tela das configurações de roteamento de chamadas](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="a8361-157">Escolha como você deseja rotear a chamada.</span><span class="sxs-lookup"><span data-stu-id="a8361-157">Choose how you want to route the call.</span></span>

<span data-ttu-id="a8361-158">Se você selecionar **Desconectar,** o atendimento automático desligará a chamada.</span><span class="sxs-lookup"><span data-stu-id="a8361-158">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="a8361-159">Se você selecionar **Redirecionar chamada,** poderá escolher um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="a8361-159">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="a8361-160">Se você selecionar Opções de menu  Reproduzir, poderá  optar por Reproduzir um arquivo de áudio ou Digitar uma mensagem de saudação e escolher entre opções de **menu** e pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="a8361-160">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="a8361-161">Opções de menu</span><span class="sxs-lookup"><span data-stu-id="a8361-161">Menu options</span></span>

![Captura de tela das opções de teclas de discagem](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="a8361-163">Para opções de discagem, atribua as teclas de 0 a 9 no teclado do telefone a um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="a8361-163">For dialing options, assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="a8361-164">(As chaves \* (Repetir) e \# (Voltar) são reservados pelo sistema e não podem ser reatribuídos.)</span><span class="sxs-lookup"><span data-stu-id="a8361-164">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="a8361-165">Os mapeamentos de chaves não têm que ser contínuos.</span><span class="sxs-lookup"><span data-stu-id="a8361-165">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="a8361-166">É possível criar um menu com as teclas 0, 1 e 3 mapeadas para opções, enquanto a tecla número 2 não é usada.</span><span class="sxs-lookup"><span data-stu-id="a8361-166">It's possible to create a menu with keys 0, 1, and 3 mapped to options, while the number 2 key isn't used.</span></span>

<span data-ttu-id="a8361-167">Recomendamos o mapeamento da chave zero para o operador se você configurou uma.</span><span class="sxs-lookup"><span data-stu-id="a8361-167">We recommend mapping the zero key to the operator if you've configured one.</span></span> <span data-ttu-id="a8361-168">Se o operador não estiver definido como nenhuma chave, o comando de voz "Operator" também será desabilitado.</span><span class="sxs-lookup"><span data-stu-id="a8361-168">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="a8361-169">Para cada opção de menu, especifique as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a8361-169">For each menu option, specify the following settings:</span></span>

- <span data-ttu-id="a8361-170">**Tecla de** discagem - a chave no teclado do telefone para acessar essa opção.</span><span class="sxs-lookup"><span data-stu-id="a8361-170">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="a8361-171">Se as entradas de voz estão disponíveis, os chamadores também podem dizer esse número para acessar a opção.</span><span class="sxs-lookup"><span data-stu-id="a8361-171">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="a8361-172">**Comando de** voz - define o comando de voz que um chamador pode dar para acessar essa opção, se as entradas de voz estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="a8361-172">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="a8361-173">Ele pode conter várias palavras como "Atendimento ao Cliente" ou "Operações e Motivos".</span><span class="sxs-lookup"><span data-stu-id="a8361-173">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="a8361-174">Por exemplo, o chamador pode pressionar 2, dizer "dois" ou dizer "Vendas" para selecionar a opção mapeada para as duas teclas.</span><span class="sxs-lookup"><span data-stu-id="a8361-174">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the two keys.</span></span> <span data-ttu-id="a8361-175">Este texto também é renderizado por texto em fala para o prompt de confirmação do serviço, que pode ser algo como "Transferir sua chamada para vendas".</span><span class="sxs-lookup"><span data-stu-id="a8361-175">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="a8361-176">**Redirecionar para** - o destino de roteamento de chamadas usado quando os chamadores escolhem essa opção.</span><span class="sxs-lookup"><span data-stu-id="a8361-176">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="a8361-177">Se você estiver redirecionando para um atendimento automático ou fila de chamada, escolha a conta de recurso associada a ela.</span><span class="sxs-lookup"><span data-stu-id="a8361-177">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="a8361-178">Pesquisa de diretório</span><span class="sxs-lookup"><span data-stu-id="a8361-178">Directory search</span></span>

<span data-ttu-id="a8361-179">Se você atribuir chaves de discagem a destinos, recomendamos que você escolha **Nenhuma** para **pesquisa de diretório.**</span><span class="sxs-lookup"><span data-stu-id="a8361-179">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="a8361-180">Se um chamador tentar discar um nome ou extensão usando chaves atribuídas a destinos específicos, ele poderá ser roteado inesperadamente para um destino antes de concluir a inserção do nome ou extensão.</span><span class="sxs-lookup"><span data-stu-id="a8361-180">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they might be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="a8361-181">Recomendamos que você crie um atendimento automático separado para pesquisa de diretório e tenha seu link principal de atendimento automático com uma chave de discagem.</span><span class="sxs-lookup"><span data-stu-id="a8361-181">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it with a dial key.</span></span>

<span data-ttu-id="a8361-182">Se você não atribuiu chaves de discagem, escolha uma opção para pesquisa **de diretório.**</span><span class="sxs-lookup"><span data-stu-id="a8361-182">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="a8361-183">**Discar por nome** - Se você habilitar essa opção, os chamadores poderão dizer o nome do usuário ou digitá-lo no teclado do telefone.</span><span class="sxs-lookup"><span data-stu-id="a8361-183">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="a8361-184">Qualquer usuário online ou qualquer usuário hospedado no local usando Skype for Business Server, é um usuário qualificado e pode ser encontrado com Dial por nome.</span><span class="sxs-lookup"><span data-stu-id="a8361-184">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="a8361-185">(Você pode definir quem é e não está incluído no diretório na página [de](#dial-scope) escopo discar.)</span><span class="sxs-lookup"><span data-stu-id="a8361-185">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="a8361-186">**Discar por extensão** - Se você habilitar essa opção, os chamadores poderão se conectar aos usuários em sua organização discando sua extensão de telefone.</span><span class="sxs-lookup"><span data-stu-id="a8361-186">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="a8361-187">Qualquer usuário online ou qualquer usuário hospedado no local usando o Skype for Business Server, é um usuário qualificado e pode ser encontrado com **Dial por extensão.**</span><span class="sxs-lookup"><span data-stu-id="a8361-187">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="a8361-188">(Você pode definir quem é e não está incluído no diretório na página [de](#dial-scope) escopo discar.)</span><span class="sxs-lookup"><span data-stu-id="a8361-188">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="a8361-189">Os usuários que você deseja disponibilizar para Discagem por Extensão precisam ter uma extensão especificada como parte de um dos seguintes atributos de telefones definidos no Active Directory ou no Azure Active Directory (Consulte Adicionar usuários [individualmente](/microsoft-365/admin/add-users/add-users) ou em massa para obter mais informações.)</span><span class="sxs-lookup"><span data-stu-id="a8361-189">Users you want to make available for Dial By Extension need to have an extension specified as part of one of the following phones attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="a8361-190">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="a8361-190">OfficePhone</span></span>
- <span data-ttu-id="a8361-191">HomePhone</span><span class="sxs-lookup"><span data-stu-id="a8361-191">HomePhone</span></span>
- <span data-ttu-id="a8361-192">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="a8361-192">Mobile/MobilePhone</span></span>
- <span data-ttu-id="a8361-193">PhoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="a8361-193">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="a8361-194">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="a8361-194">OtherTelephone</span></span>

<span data-ttu-id="a8361-195">O formato necessário para inserir a extensão no campo número de telefone do usuário pode ser um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="a8361-195">The required format to enter the extension in the user phone number field can be one of the following formats:</span></span>

- <span data-ttu-id="a8361-196">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="a8361-196">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="a8361-197">*+\<phone number>x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="a8361-197">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="a8361-198">*x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="a8361-198">*x\<extension>*</span></span>

- <span data-ttu-id="a8361-199">Exemplo 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="a8361-199">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="a8361-200">Exemplo 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="a8361-200">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="a8361-201">Exemplo 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="a8361-201">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="a8361-202">Você pode definir a extensão no centro de administração [Microsoft 365](https://admin.microsoft.com/) ou no Azure Active Directory [de administração.](https://aad.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="a8361-202">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="a8361-203">Pode levar até 12 horas antes que as alterações sejam disponibilizadas para os atendimentos automáticos e filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="a8361-203">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="a8361-204">Se você quiser usar os recursos  **Discar** por nome e Discar por extensão, você pode atribuir uma chave de discagem no seu atendimento automático principal para alcançar um atendimento automático habilitado para Discagem **pelo nome**.</span><span class="sxs-lookup"><span data-stu-id="a8361-204">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="a8361-205">Nesse atendimento automático, você pode atribuir a tecla 1 (que não tem letras associadas a ela) para alcançar o atendimento automático **Discar** por extensão.</span><span class="sxs-lookup"><span data-stu-id="a8361-205">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="a8361-206">Depois de selecionar uma opção **de pesquisa diretório,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a8361-206">Once you have selected a **Directory search** option, select **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="a8361-207">Fluxo de chamada para depois do horário</span><span class="sxs-lookup"><span data-stu-id="a8361-207">Call flow for after hours</span></span>

![Captura de tela das configurações de dia e hora após o expediente](media/auto-attendant-business-hours.png)

<span data-ttu-id="a8361-209">O horário comercial pode ser definido para cada atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="a8361-209">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="a8361-210">Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão.</span><span class="sxs-lookup"><span data-stu-id="a8361-210">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="a8361-211">O horário comercial pode ser definido com pausas no tempo durante o dia e todas as horas que não estão definidas como horário comercial são consideradas após o horário.</span><span class="sxs-lookup"><span data-stu-id="a8361-211">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="a8361-212">Você pode definir diferentes opções de tratamento de chamadas de entrada e saudações para o pós-horário.</span><span class="sxs-lookup"><span data-stu-id="a8361-212">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="a8361-213">Dependendo de como você configurou seus atendimentos automáticos e filas de chamadas, talvez seja necessário especificar apenas o roteamento de chamadas após o horário para os atendimentos automáticos com números de telefone diretos.</span><span class="sxs-lookup"><span data-stu-id="a8361-213">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="a8361-214">Se você quiser roteamento de chamadas separado para chamadores após o horário, especifique seu horário comercial para cada dia.</span><span class="sxs-lookup"><span data-stu-id="a8361-214">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="a8361-215">Selecione **Adicionar novo horário** para especificar vários conjuntos de horas para um determinado dia, por exemplo, para especificar uma pausa de almoço.</span><span class="sxs-lookup"><span data-stu-id="a8361-215">Select **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="a8361-216">Depois de especificar seu horário comercial, escolha suas opções de roteamento de chamadas para o horário de expediente.</span><span class="sxs-lookup"><span data-stu-id="a8361-216">Once you've specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="a8361-217">As mesmas opções estão disponíveis para o roteamento de chamadas de horário comercial especificado acima.</span><span class="sxs-lookup"><span data-stu-id="a8361-217">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="a8361-218">Selecione **Próximo** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="a8361-218">Select **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="a8361-219">Fluxos de chamada durante feriados</span><span class="sxs-lookup"><span data-stu-id="a8361-219">Call flows during holidays</span></span>

![Captura de tela das configurações de saudação de feriados e feriados](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="a8361-221">O seu atendimento automático pode ter um fluxo de chamada para cada Feriado que [você definiu](set-up-holidays-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a8361-221">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="a8361-222">Você pode adicionar até 20 feriados agendados para cada atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="a8361-222">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="a8361-223">Na página Configurações de chamada de feriado, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a8361-223">On the Holiday call settings page, select **Add**.</span></span>

2. <span data-ttu-id="a8361-224">Digite um nome para essa configuração de feriado.</span><span class="sxs-lookup"><span data-stu-id="a8361-224">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="a8361-225">No menu **suspenso Feriado,** escolha o feriado que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="a8361-225">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="a8361-226">Escolha o tipo de saudação que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="a8361-226">Choose the type of greeting that you want to use.</span></span>

    ![Captura de tela das configurações de ação de chamada de feriado](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="a8361-228">Escolha se deseja **desconectar ou** **redirecionar** a chamada.</span><span class="sxs-lookup"><span data-stu-id="a8361-228">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="a8361-229">Se você optou por redirecionar, escolha o destino de roteamento de chamadas para a chamada.</span><span class="sxs-lookup"><span data-stu-id="a8361-229">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="a8361-230">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a8361-230">Select **Save**.</span></span>

![Captura de tela das configurações de feriados com feriados listados](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="a8361-232">Repita o procedimento conforme necessário para cada feriado adicional.</span><span class="sxs-lookup"><span data-stu-id="a8361-232">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="a8361-233">Quando você adicionou todos os feriados, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a8361-233">When you've added all your holidays, select **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="a8361-234">Escopo de discagem</span><span class="sxs-lookup"><span data-stu-id="a8361-234">Dial scope</span></span>

![Captura de tela do escopo de discagem incluem e excluem opções](media/auto-attendant-dial-scope.png)

<span data-ttu-id="a8361-236">O *escopo de* discagem define quais usuários estão disponíveis no diretório quando um chamador usa discagem por nome ou discagem por extensão.</span><span class="sxs-lookup"><span data-stu-id="a8361-236">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="a8361-237">O padrão de **Todos os usuários online** inclui todos os usuários em sua organização que são usuários online ou hospedados no local usando Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a8361-237">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="a8361-238">Você pode incluir ou excluir  usuários específicos  selecionando Grupo de usuários personalizado em **Incluir** ou Excluir e escolher um ou mais grupos de Microsoft 365, listas de distribuição ou grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="a8361-238">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="a8361-239">Por exemplo, talvez você queira excluir executivos em sua organização do diretório de discagem.</span><span class="sxs-lookup"><span data-stu-id="a8361-239">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="a8361-240">(Se um usuário estiver em ambas as listas, ele será excluído do diretório.)</span><span class="sxs-lookup"><span data-stu-id="a8361-240">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="a8361-241">Pode levar até 36 horas para que um novo usuário tenha seu nome listado no diretório.</span><span class="sxs-lookup"><span data-stu-id="a8361-241">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="a8361-242">Quando terminar de definir o escopo de discagem, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a8361-242">When you're done setting the dial scope, select **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="a8361-243">Contas de recursos</span><span class="sxs-lookup"><span data-stu-id="a8361-243">Resource accounts</span></span>

<span data-ttu-id="a8361-244">Todos os atendentes automáticos devem ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="a8361-244">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="a8361-245">Os atendentes automáticos de primeiro nível precisarão de pelo menos uma conta de recurso que tenha um número de serviço associado.</span><span class="sxs-lookup"><span data-stu-id="a8361-245">First-level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="a8361-246">Se desejar, você pode atribuir várias contas de recurso a um atendimento automático, cada uma com um número de serviço separado.</span><span class="sxs-lookup"><span data-stu-id="a8361-246">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Captura de tela do painel adicionar contas de conta de recurso](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="a8361-248">Para adicionar uma conta de recurso, selecione **Adicionar conta** e procure a conta que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="a8361-248">To add a resource account, select **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="a8361-249">Selecione **Adicionar** e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a8361-249">Select **Add**, and then select **Add**.</span></span>

![Captura de tela da lista de contas de recursos mostrando a conta de recurso com o número de serviço atribuído](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="a8361-251">Quando terminar de adicionar contas de serviço, selecione **Enviar** para concluir a configuração do atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="a8361-251">When you have finished adding service accounts, select **Submit** to complete auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="a8361-252">Transferências de número de telefone externo - detalhes técnicos</span><span class="sxs-lookup"><span data-stu-id="a8361-252">External phone number transfers - technical details</span></span>

<span data-ttu-id="a8361-253">Consulte os [Pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) para permitir que os atendimentos automáticos transfira chamadas externamente.</span><span class="sxs-lookup"><span data-stu-id="a8361-253">Refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="a8361-254">Além disso:</span><span class="sxs-lookup"><span data-stu-id="a8361-254">In addition:</span></span>

- <span data-ttu-id="a8361-255">Para uma conta de recurso com uma licença [de](calling-plans-for-office-365.md)Plano de Chamada , o número de telefone de transferência externa deve ser inserido no formato E.164 (+[código do país][código de área][número de telefone]).</span><span class="sxs-lookup"><span data-stu-id="a8361-255">For a resource account with a [Calling Plan license](calling-plans-for-office-365.md), the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="a8361-256">Para uma conta de recurso com uma política Sistema de Telefonia de roteamento de voz online de Licença e Roteamento Direto, o formato de número de telefone de transferência externa depende das configurações do Controlador de Borda de Sessão [(SBC).](direct-routing-connect-the-sbc.md)</span><span class="sxs-lookup"><span data-stu-id="a8361-256">For a resource account with a Phone System License and Direct Routing online voice routing policy, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="a8361-257">O número de telefone de saída exibido é determinado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="a8361-257">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="a8361-258">Para números do Plano de Chamadas, o número de telefone do chamador original é exibido.</span><span class="sxs-lookup"><span data-stu-id="a8361-258">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="a8361-259">Para números de Roteamento Direto, o número enviado é baseado na configuração P-Asserted-Identity (PAI) no SBC, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="a8361-259">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="a8361-260">Se definido como Desabilitado, o número de telefone do chamador original será exibido.</span><span class="sxs-lookup"><span data-stu-id="a8361-260">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="a8361-261">Essa é a configuração padrão e recomendada.</span><span class="sxs-lookup"><span data-stu-id="a8361-261">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="a8361-262">Se definido como Habilitado, o número de telefone da conta de recurso será exibido.</span><span class="sxs-lookup"><span data-stu-id="a8361-262">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="a8361-263">Em um Skype for Business híbrido, para transferir uma chamada de atendimento automático para a PSTN, crie um novo usuário local com encaminhamento de chamada definido para o número PSTN.</span><span class="sxs-lookup"><span data-stu-id="a8361-263">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="a8361-264">O usuário deve estar habilitado para Enterprise Voice e ter uma política de voz atribuída.</span><span class="sxs-lookup"><span data-stu-id="a8361-264">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="a8361-265">Para saber mais, confira [Transferência de chamada de atendimento automático para PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span><span class="sxs-lookup"><span data-stu-id="a8361-265">To learn more, see [Auto attendant call transfer to PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="a8361-266">Criar um atendimento automático com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8361-266">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="a8361-267">Você também pode usar o PowerShell para criar e configurar os atendimentos automáticos.</span><span class="sxs-lookup"><span data-stu-id="a8361-267">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="a8361-268">Aqui estão os cmdlets que você precisa para gerenciar um atendimento automático:</span><span class="sxs-lookup"><span data-stu-id="a8361-268">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="a8361-269">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="a8361-269">New-CsAutoAttendant</span></span>](/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="a8361-270">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="a8361-270">Set-CsAutoAttendant</span></span>](/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="a8361-271">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="a8361-271">Get-CsAutoAttendant</span></span>](/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="a8361-272">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="a8361-272">Get-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="a8361-273">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="a8361-273">Remove-CsAutoAttendant</span></span>](/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="a8361-274">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="a8361-274">New-CsAutoAttendantMenu</span></span>](/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="a8361-275">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="a8361-275">New-CsOnlineAudioFile</span></span>](/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="a8361-276">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="a8361-276">New-CsAutoAttendantCallFlow</span></span>](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="a8361-277">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="a8361-277">Export-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="a8361-278">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="a8361-278">New-CsOnlineTimeRange</span></span>](/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="a8361-279">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="a8361-279">New-CsOnlineDateTimeRange</span></span>](/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="a8361-280">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="a8361-280">New-CsOnlineSchedule</span></span>](/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="a8361-281">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="a8361-281">Get-CsAutoAttendantSupportedTimeZone</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="a8361-282">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="a8361-282">New-CsAutoAttendantCallHandlingAssociation</span></span>](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="a8361-283">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="a8361-283">Get-CsAutoAttendantSupportedLanguage</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="a8361-284">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="a8361-284">Import-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="a8361-285">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="a8361-285">New-CsAutoAttendantCallableEntity</span></span>](/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="a8361-286">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a8361-286">Related topics</span></span>

[<span data-ttu-id="a8361-287">Veja o que você obtém com o Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="a8361-287">Here's what you get with Phone System</span></span>](./here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="a8361-288">Obter números de telefone de serviço</span><span class="sxs-lookup"><span data-stu-id="a8361-288">Getting service phone numbers</span></span>](./getting-service-phone-numbers.md)

[<span data-ttu-id="a8361-289">Disponibilidade de Audioconferência e Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="a8361-289">Country and region availability for Audio Conferencing and Calling Plans</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="a8361-290">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a8361-290">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
