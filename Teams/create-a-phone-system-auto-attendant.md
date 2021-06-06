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
description: Saiba como configurar e testar os atendimentos automáticos para grandes organizações em Microsoft Teams.
ms.openlocfilehash: cc4d0de8fd1d6c643f23b6e8215f0f7a343b2a8f
ms.sourcegitcommit: 17d0108fb4d36a3f56144460683f53d77a8a0a7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52777793"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="fed70-103">Configurar um atendimento automático</span><span class="sxs-lookup"><span data-stu-id="fed70-103">Set up an auto attendant</span></span>

<span data-ttu-id="fed70-104">Os atendentes automáticos permitem que as pessoas liguem para sua organização e naveguem por um sistema de menus para falar com o departamento certo, fila de chamada, pessoa ou operador.</span><span class="sxs-lookup"><span data-stu-id="fed70-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="fed70-105">Você pode criar assistentes automáticos para sua organização com o Microsoft Teams de administração ou com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fed70-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

> [!TIP]
> <span data-ttu-id="fed70-106">Este artigo é para grandes organizações.</span><span class="sxs-lookup"><span data-stu-id="fed70-106">This article is for large organizations.</span></span> <span data-ttu-id="fed70-107">Se sua organização for uma pequena empresa, leia [Configurar um atendimento automático - tutorial de pequenas](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) empresas.</span><span class="sxs-lookup"><span data-stu-id="fed70-107">If your organization is a small business, read [Set up an auto attendant - small business tutorial](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb) instead.</span></span>

<span data-ttu-id="fed70-108">Leia Plan for Teams auto attendants and [call queues](plan-auto-attendant-call-queue.md) [](plan-auto-attendant-call-queue.md#getting-started) e siga as etapas de início antes de seguir os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="fed70-108">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="fed70-109">Os atendimentos automáticos podem direcionar chamadas, com base na entrada dos chamadores, para um dos seguintes destinos: <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="fed70-109">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="fed70-110">**Operador** - o operador definido para o atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="fed70-110">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="fed70-111">Definir um operador é opcional.</span><span class="sxs-lookup"><span data-stu-id="fed70-111">Defining an operator is optional.</span></span> <span data-ttu-id="fed70-112">O operador pode ser definido como qualquer um dos outros destinos nesta lista.</span><span class="sxs-lookup"><span data-stu-id="fed70-112">The operator can be defined as any of the other destinations in this list.</span></span>
- <span data-ttu-id="fed70-113">**Pessoa na organização** - uma pessoa em sua organização que pode receber chamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="fed70-113">**Person in the organization** - a person in your organization who can receive voice calls.</span></span> <span data-ttu-id="fed70-114">Essa pessoa pode ser um usuário online ou um usuário hospedado no local usando Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fed70-114">This person can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="fed70-115">**Aplicativo de voz** - outro atendimento automático ou uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fed70-115">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="fed70-116">(Escolha a conta de recurso associada ao atendimento automático ou fila de chamada ao escolher esse destino.)</span><span class="sxs-lookup"><span data-stu-id="fed70-116">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="fed70-117">**Caixa** postal - a caixa de correio de voz associada a um grupo Microsoft 365 que você especificar.</span><span class="sxs-lookup"><span data-stu-id="fed70-117">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span> <span data-ttu-id="fed70-118">Você pode escolher se deseja transcrições de caixa postal e o "Por favor, deixe uma mensagem após o tom".</span><span class="sxs-lookup"><span data-stu-id="fed70-118">You can choose if you want voicemail transcriptions and the "Please leave a message after the tone."</span></span> <span data-ttu-id="fed70-119">prompt do sistema.</span><span class="sxs-lookup"><span data-stu-id="fed70-119">system prompt.</span></span>
- <span data-ttu-id="fed70-120">**Número de telefone externo** - qualquer número de telefone.</span><span class="sxs-lookup"><span data-stu-id="fed70-120">**External phone number** - any phone number.</span></span> <span data-ttu-id="fed70-121">(Consulte [detalhes técnicos de transferência externa](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span><span class="sxs-lookup"><span data-stu-id="fed70-121">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="fed70-122">**Comunicado (Arquivo de áudio)** - Reproduzir um arquivo de áudio.</span><span class="sxs-lookup"><span data-stu-id="fed70-122">**Announcement (Audio file)** - Play an audio file.</span></span> <span data-ttu-id="fed70-123">Uma mensagem de anúncio gravada que você carrega salva como áudio em . WAV, .MP3 ou . Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="fed70-123">A recorded announcement message you upload that's saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="fed70-124">A gravação não pode ser maior do que 5 MB.</span><span class="sxs-lookup"><span data-stu-id="fed70-124">The recording can be no larger than 5 MB.</span></span> <span data-ttu-id="fed70-125">O sistema reproduz o comunicado e retorna ao menu de atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="fed70-125">The system plays the announcement, and then returns to the auto attendant menu.</span></span>
- <span data-ttu-id="fed70-126">**Comunicado (Digitado)** - Digite uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="fed70-126">**Announcement (Typed)** - Type in a message.</span></span> <span data-ttu-id="fed70-127">Texto que você deseja que o sistema leia.</span><span class="sxs-lookup"><span data-stu-id="fed70-127">Text you want the system to read.</span></span> <span data-ttu-id="fed70-128">Você pode inserir até 1000 caracteres.</span><span class="sxs-lookup"><span data-stu-id="fed70-128">You can enter up to 1000 characters.</span></span> <span data-ttu-id="fed70-129">O sistema reproduz o comunicado e retorna ao menu de atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="fed70-129">The system plays the announcement, and then returns to the auto attendant menu.</span></span>

<span data-ttu-id="fed70-130">Você será solicitado a escolher uma dessas opções em vários estágios ao configurar um atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="fed70-130">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="fed70-131">Para configurar um atendimento automático, no centro de administração Teams, **expanda Voz,** selecione **Assistentes automáticos** e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fed70-131">To set up an auto attendant, in the Teams admin center, expand **Voice**, select **Auto attendants**, and then select **Add**.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="fed70-132">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="fed70-132">Video demonstration</span></span>

<span data-ttu-id="fed70-133">Este vídeo mostra um exemplo básico de como criar um assistente automático no Teams.</span><span class="sxs-lookup"><span data-stu-id="fed70-133">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

## <a name="general-info"></a><span data-ttu-id="fed70-134">Informações gerais</span><span class="sxs-lookup"><span data-stu-id="fed70-134">General info</span></span>

![Captura de tela das configurações de atendimento automático para nome, operador, fuso horário, idioma e entradas de voz](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="fed70-136">Digite um nome para o atendimento automático na caixa na parte superior.</span><span class="sxs-lookup"><span data-stu-id="fed70-136">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="fed70-137">Para designar um operador, especifique o destino das chamadas para o operador.</span><span class="sxs-lookup"><span data-stu-id="fed70-137">To designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="fed70-138">Essa designação é opcional (mas recomendada).</span><span class="sxs-lookup"><span data-stu-id="fed70-138">This designation is optional (but recommended).</span></span> <span data-ttu-id="fed70-139">De definir **a opção** Operador para permitir que os chamadores saiam dos menus e fale com uma pessoa designada.</span><span class="sxs-lookup"><span data-stu-id="fed70-139">Set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="fed70-140">Especifique o fuso horário desse atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="fed70-140">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="fed70-141">O fuso horário é usado para calcular o horário comercial se você criar um fluxo de chamada [separado para o horário.](#call-flow-for-after-hours)</span><span class="sxs-lookup"><span data-stu-id="fed70-141">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="fed70-142">[Especifique um idioma com suporte](create-a-phone-system-auto-attendant-languages.md) para esse atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="fed70-142">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="fed70-143">Esse é o idioma que será usado para prompts de voz gerados pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="fed70-143">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="fed70-144">Escolha se deseja habilitar entradas de voz.</span><span class="sxs-lookup"><span data-stu-id="fed70-144">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="fed70-145">Quando habilitada, o nome de cada opção de menu se torna uma palavra-chave de reconhecimento de fala.</span><span class="sxs-lookup"><span data-stu-id="fed70-145">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="fed70-146">Por exemplo, os chamadores podem dizer "Um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "Vendas" para selecionar a opção de menu chamada "Vendas".</span><span class="sxs-lookup"><span data-stu-id="fed70-146">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

   > [!NOTE]
   > <span data-ttu-id="fed70-147">Se você escolher um idioma na Etapa 4 que não suporte entradas de voz, essa opção será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="fed70-147">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="fed70-148">Selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="fed70-148">Select **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="fed70-149">Fluxo de chamada</span><span class="sxs-lookup"><span data-stu-id="fed70-149">Call flow</span></span>

![Captura de tela das configurações da mensagem de saudação](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="fed70-151">Escolha se deseja reproduzir uma saudação quando o atendente automático atender uma chamada.</span><span class="sxs-lookup"><span data-stu-id="fed70-151">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="fed70-152">Se você selecionar **Reproduzir um arquivo de** áudio, poderá usar o botão de arquivo **Upload** para carregar uma mensagem de saudação gravada salva como áudio em . WAV, .MP3 ou . Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="fed70-152">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="fed70-153">A gravação não pode ser maior do que 5 MB.</span><span class="sxs-lookup"><span data-stu-id="fed70-153">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="fed70-154">Se você selecionar **Digitar uma mensagem de** saudação, o sistema lerá o texto que você digitar (até 1000 caracteres) quando o atende automaticamente atender a uma chamada.</span><span class="sxs-lookup"><span data-stu-id="fed70-154">If you select **Type a greeting message** the system will read the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Captura de tela das configurações de roteamento de chamadas](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="fed70-156">Escolha como você deseja rotear a chamada.</span><span class="sxs-lookup"><span data-stu-id="fed70-156">Choose how you want to route the call.</span></span>

<span data-ttu-id="fed70-157">Se você selecionar **Desconectar,** o atendimento automático desligará a chamada.</span><span class="sxs-lookup"><span data-stu-id="fed70-157">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="fed70-158">Se você selecionar **Redirecionar chamada,** poderá escolher um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fed70-158">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="fed70-159">Se você selecionar Opções de menu  Reproduzir, poderá  optar por Reproduzir um arquivo de áudio ou Digitar uma mensagem de saudação e escolher entre opções de **menu** e pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="fed70-159">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="fed70-160">Opções de menu</span><span class="sxs-lookup"><span data-stu-id="fed70-160">Menu options</span></span>

![Captura de tela das opções de teclas de discagem](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="fed70-162">Para opções de discagem, atribua as teclas de 0 a 9 no teclado do telefone a um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="fed70-162">For dialing options, assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="fed70-163">(As chaves \* (Repetir) e \# (Voltar) são reservados pelo sistema e não podem ser reatribuídos.)</span><span class="sxs-lookup"><span data-stu-id="fed70-163">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="fed70-164">Os mapeamentos de chaves não têm que ser contínuos.</span><span class="sxs-lookup"><span data-stu-id="fed70-164">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="fed70-165">É possível criar um menu com as teclas 0, 1 e 3 mapeadas para opções, enquanto a tecla número 2 não é usada.</span><span class="sxs-lookup"><span data-stu-id="fed70-165">It's possible to create a menu with keys 0, 1, and 3 mapped to options, while the number 2 key isn't used.</span></span>

<span data-ttu-id="fed70-166">Recomendamos o mapeamento da chave zero para o operador se você configurou uma.</span><span class="sxs-lookup"><span data-stu-id="fed70-166">We recommend mapping the zero key to the operator if you've configured one.</span></span> <span data-ttu-id="fed70-167">Se o operador não estiver definido como nenhuma chave, o comando de voz "Operator" também será desabilitado.</span><span class="sxs-lookup"><span data-stu-id="fed70-167">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="fed70-168">Para cada opção de menu, especifique as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="fed70-168">For each menu option, specify the following settings:</span></span>

- <span data-ttu-id="fed70-169">**Tecla de** discagem - a chave no teclado do telefone para acessar essa opção.</span><span class="sxs-lookup"><span data-stu-id="fed70-169">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="fed70-170">Se as entradas de voz estão disponíveis, os chamadores também podem dizer esse número para acessar a opção.</span><span class="sxs-lookup"><span data-stu-id="fed70-170">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="fed70-171">**Comando de** voz - define o comando de voz que um chamador pode dar para acessar essa opção, se as entradas de voz estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="fed70-171">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="fed70-172">Ele pode conter várias palavras como "Atendimento ao Cliente" ou "Operações e Motivos".</span><span class="sxs-lookup"><span data-stu-id="fed70-172">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="fed70-173">Por exemplo, o chamador pode pressionar 2, dizer "dois" ou dizer "Vendas" para selecionar a opção mapeada para as duas teclas.</span><span class="sxs-lookup"><span data-stu-id="fed70-173">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the two keys.</span></span> <span data-ttu-id="fed70-174">Este texto também é renderizado por texto em fala para o prompt de confirmação do serviço, que pode ser algo como "Transferir sua chamada para vendas".</span><span class="sxs-lookup"><span data-stu-id="fed70-174">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="fed70-175">**Redirecionar para** - o destino de roteamento de chamadas usado quando os chamadores escolhem essa opção.</span><span class="sxs-lookup"><span data-stu-id="fed70-175">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="fed70-176">Se você estiver redirecionando para um atendimento automático ou fila de chamada, escolha a conta de recurso associada a ela.</span><span class="sxs-lookup"><span data-stu-id="fed70-176">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="fed70-177">Pesquisa de diretório</span><span class="sxs-lookup"><span data-stu-id="fed70-177">Directory search</span></span>

<span data-ttu-id="fed70-178">Se você atribuir chaves de discagem a destinos, recomendamos que você escolha **Nenhuma** para **pesquisa de diretório.**</span><span class="sxs-lookup"><span data-stu-id="fed70-178">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="fed70-179">Se um chamador tentar discar um nome ou extensão usando chaves atribuídas a destinos específicos, ele poderá ser roteado inesperadamente para um destino antes de concluir a inserção do nome ou extensão.</span><span class="sxs-lookup"><span data-stu-id="fed70-179">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they might be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="fed70-180">Recomendamos que você crie um atendimento automático separado para pesquisa de diretório e tenha seu link principal de atendimento automático com uma chave de discagem.</span><span class="sxs-lookup"><span data-stu-id="fed70-180">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it with a dial key.</span></span>

<span data-ttu-id="fed70-181">Se você não atribuiu chaves de discagem, escolha uma opção para pesquisa **de diretório.**</span><span class="sxs-lookup"><span data-stu-id="fed70-181">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="fed70-182">**Discar por nome** - Se você habilitar essa opção, os chamadores poderão dizer o nome do usuário ou digitá-lo no teclado do telefone.</span><span class="sxs-lookup"><span data-stu-id="fed70-182">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="fed70-183">Qualquer usuário online ou qualquer usuário hospedado no local usando Skype for Business Server, é um usuário qualificado e pode ser encontrado com Dial por nome.</span><span class="sxs-lookup"><span data-stu-id="fed70-183">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="fed70-184">(Você pode definir quem é e não está incluído no diretório na página [de](#dial-scope) escopo discar.)</span><span class="sxs-lookup"><span data-stu-id="fed70-184">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="fed70-185">**Discar por extensão** - Se você habilitar essa opção, os chamadores poderão se conectar aos usuários em sua organização discando sua extensão de telefone.</span><span class="sxs-lookup"><span data-stu-id="fed70-185">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="fed70-186">Qualquer usuário online ou qualquer usuário hospedado no local usando o Skype for Business Server, é um usuário qualificado e pode ser encontrado com **Dial por extensão.**</span><span class="sxs-lookup"><span data-stu-id="fed70-186">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="fed70-187">(Você pode definir quem é e não está incluído no diretório na página [de](#dial-scope) escopo discar.)</span><span class="sxs-lookup"><span data-stu-id="fed70-187">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="fed70-188">Os usuários que você deseja disponibilizar para Discagem por Extensão precisam ter uma extensão especificada como parte de um dos seguintes atributos de telefones definidos no Active Directory ou no Azure Active Directory (Consulte Adicionar usuários [individualmente](/microsoft-365/admin/add-users/add-users) ou em massa para obter mais informações.)</span><span class="sxs-lookup"><span data-stu-id="fed70-188">Users you want to make available for Dial By Extension need to have an extension specified as part of one of the following phones attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="fed70-189">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="fed70-189">OfficePhone</span></span>
- <span data-ttu-id="fed70-190">HomePhone</span><span class="sxs-lookup"><span data-stu-id="fed70-190">HomePhone</span></span>
- <span data-ttu-id="fed70-191">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="fed70-191">Mobile/MobilePhone</span></span>
- <span data-ttu-id="fed70-192">PhoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="fed70-192">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="fed70-193">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="fed70-193">OtherTelephone</span></span>

<span data-ttu-id="fed70-194">O formato necessário para inserir a extensão no campo número de telefone do usuário pode ser um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="fed70-194">The required format to enter the extension in the user phone number field can be one of the following formats:</span></span>

- <span data-ttu-id="fed70-195">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="fed70-195">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="fed70-196">*+\<phone number>x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="fed70-196">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="fed70-197">*x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="fed70-197">*x\<extension>*</span></span>

- <span data-ttu-id="fed70-198">Exemplo 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="fed70-198">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="fed70-199">Exemplo 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="fed70-199">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="fed70-200">Exemplo 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="fed70-200">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="fed70-201">Você pode definir a extensão no centro de administração [Microsoft 365](https://admin.microsoft.com/) ou no Azure Active Directory [de administração.](https://aad.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="fed70-201">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="fed70-202">Pode levar até 12 horas antes que as alterações sejam disponibilizadas para os atendimentos automáticos e filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="fed70-202">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="fed70-203">Se você quiser usar os recursos  **Discar** por nome e Discar por extensão, você pode atribuir uma chave de discagem no seu atendimento automático principal para alcançar um atendimento automático habilitado para Discagem **pelo nome**.</span><span class="sxs-lookup"><span data-stu-id="fed70-203">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="fed70-204">Nesse atendimento automático, você pode atribuir a tecla 1 (que não tem letras associadas a ela) para alcançar o atendimento automático **Discar** por extensão.</span><span class="sxs-lookup"><span data-stu-id="fed70-204">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="fed70-205">Depois de selecionar uma opção **de pesquisa diretório,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="fed70-205">Once you have selected a **Directory search** option, select **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="fed70-206">Fluxo de chamada para depois do horário</span><span class="sxs-lookup"><span data-stu-id="fed70-206">Call flow for after hours</span></span>

![Captura de tela das configurações de dia e hora após o expediente](media/auto-attendant-business-hours.png)

<span data-ttu-id="fed70-208">O horário comercial pode ser definido para cada atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="fed70-208">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="fed70-209">Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão.</span><span class="sxs-lookup"><span data-stu-id="fed70-209">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="fed70-210">O horário comercial pode ser definido com pausas no tempo durante o dia e todas as horas que não estão definidas como horário comercial são consideradas após o horário.</span><span class="sxs-lookup"><span data-stu-id="fed70-210">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="fed70-211">Você pode definir diferentes opções de tratamento de chamadas de entrada e saudações para o pós-horário.</span><span class="sxs-lookup"><span data-stu-id="fed70-211">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="fed70-212">Dependendo de como você configurou seus atendimentos automáticos e filas de chamadas, talvez seja necessário especificar apenas o roteamento de chamadas após o horário para os atendimentos automáticos com números de telefone diretos.</span><span class="sxs-lookup"><span data-stu-id="fed70-212">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="fed70-213">Se você quiser roteamento de chamadas separado para chamadores após o horário, especifique seu horário comercial para cada dia.</span><span class="sxs-lookup"><span data-stu-id="fed70-213">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="fed70-214">Selecione **Adicionar novo horário** para especificar vários conjuntos de horas para um determinado dia, por exemplo, para especificar uma pausa de almoço.</span><span class="sxs-lookup"><span data-stu-id="fed70-214">Select **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="fed70-215">Depois de especificar seu horário comercial, escolha suas opções de roteamento de chamadas para o horário de expediente.</span><span class="sxs-lookup"><span data-stu-id="fed70-215">Once you've specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="fed70-216">As mesmas opções estão disponíveis para o roteamento de chamadas de horário comercial especificado acima.</span><span class="sxs-lookup"><span data-stu-id="fed70-216">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="fed70-217">Selecione **Próximo** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="fed70-217">Select **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="fed70-218">Fluxos de chamada durante feriados</span><span class="sxs-lookup"><span data-stu-id="fed70-218">Call flows during holidays</span></span>

![Captura de tela das configurações de saudação de feriados e feriados](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="fed70-220">O seu atendimento automático pode ter um fluxo de chamada para cada Feriado que [você definiu](set-up-holidays-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="fed70-220">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="fed70-221">Você pode adicionar até 20 feriados agendados para cada atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="fed70-221">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="fed70-222">Na página Configurações de chamada de feriado, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fed70-222">On the Holiday call settings page, select **Add**.</span></span>

2. <span data-ttu-id="fed70-223">Digite um nome para essa configuração de feriado.</span><span class="sxs-lookup"><span data-stu-id="fed70-223">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="fed70-224">No menu **suspenso Feriado,** escolha o feriado que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="fed70-224">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="fed70-225">Escolha o tipo de saudação que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="fed70-225">Choose the type of greeting that you want to use.</span></span>

    ![Captura de tela das configurações de ação de chamada de feriado](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="fed70-227">Escolha se deseja **desconectar ou** **redirecionar** a chamada.</span><span class="sxs-lookup"><span data-stu-id="fed70-227">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="fed70-228">Se você optou por redirecionar, escolha o destino de roteamento de chamadas para a chamada.</span><span class="sxs-lookup"><span data-stu-id="fed70-228">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="fed70-229">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fed70-229">Select **Save**.</span></span>

![Captura de tela das configurações de feriados com feriados listados](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="fed70-231">Repita o procedimento conforme necessário para cada feriado adicional.</span><span class="sxs-lookup"><span data-stu-id="fed70-231">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="fed70-232">Quando você adicionou todos os feriados, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="fed70-232">When you've added all your holidays, select **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="fed70-233">Escopo de discagem</span><span class="sxs-lookup"><span data-stu-id="fed70-233">Dial scope</span></span>

![Captura de tela do escopo de discagem incluem e excluem opções](media/auto-attendant-dial-scope.png)

<span data-ttu-id="fed70-235">O *escopo de* discagem define quais usuários estão disponíveis no diretório quando um chamador usa discagem por nome ou discagem por extensão.</span><span class="sxs-lookup"><span data-stu-id="fed70-235">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="fed70-236">O padrão de **Todos os usuários online** inclui todos os usuários em sua organização que são usuários online ou hospedados no local usando Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fed70-236">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="fed70-237">Você pode incluir ou excluir  usuários específicos  selecionando Grupo de usuários personalizado em **Incluir** ou Excluir e escolher um ou mais grupos de Microsoft 365, listas de distribuição ou grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="fed70-237">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="fed70-238">Por exemplo, talvez você queira excluir executivos em sua organização do diretório de discagem.</span><span class="sxs-lookup"><span data-stu-id="fed70-238">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="fed70-239">(Se um usuário estiver em ambas as listas, ele será excluído do diretório.)</span><span class="sxs-lookup"><span data-stu-id="fed70-239">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="fed70-240">Pode levar até 36 horas para que um novo usuário tenha seu nome listado no diretório.</span><span class="sxs-lookup"><span data-stu-id="fed70-240">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="fed70-241">Quando terminar de definir o escopo de discagem, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="fed70-241">When you're done setting the dial scope, select **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="fed70-242">Contas de recursos</span><span class="sxs-lookup"><span data-stu-id="fed70-242">Resource accounts</span></span>

<span data-ttu-id="fed70-243">Todos os atendentes automáticos devem ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="fed70-243">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="fed70-244">Os atendentes automáticos de primeiro nível precisarão de pelo menos uma conta de recurso que tenha um número de serviço associado.</span><span class="sxs-lookup"><span data-stu-id="fed70-244">First-level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="fed70-245">Se desejar, você pode atribuir várias contas de recurso a um atendimento automático, cada uma com um número de serviço separado.</span><span class="sxs-lookup"><span data-stu-id="fed70-245">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Captura de tela do painel adicionar contas de conta de recurso](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="fed70-247">Para adicionar uma conta de recurso, selecione **Adicionar conta** e procure a conta que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="fed70-247">To add a resource account, select **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="fed70-248">Selecione **Adicionar** e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="fed70-248">Select **Add**, and then select **Add**.</span></span>

![Captura de tela da lista de contas de recursos mostrando a conta de recurso com o número de serviço atribuído](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="fed70-250">Quando terminar de adicionar contas de serviço, selecione **Enviar** para concluir a configuração do atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="fed70-250">When you have finished adding service accounts, select **Submit** to complete auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="fed70-251">Transferências de número de telefone externo - detalhes técnicos</span><span class="sxs-lookup"><span data-stu-id="fed70-251">External phone number transfers - technical details</span></span>

<span data-ttu-id="fed70-252">Consulte os [Pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) para permitir que os atendimentos automáticos transfira chamadas externamente.</span><span class="sxs-lookup"><span data-stu-id="fed70-252">Refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="fed70-253">Além disso:</span><span class="sxs-lookup"><span data-stu-id="fed70-253">In addition:</span></span>

- <span data-ttu-id="fed70-254">Para uma conta de recurso com uma licença [de](calling-plans-for-office-365.md)Plano de Chamada , o número de telefone de transferência externa deve ser inserido no formato E.164 (+[código do país][código de área][número de telefone]).</span><span class="sxs-lookup"><span data-stu-id="fed70-254">For a resource account with a [Calling Plan license](calling-plans-for-office-365.md), the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="fed70-255">Para uma conta de recurso com uma política Sistema de Telefonia de roteamento de voz online de Licença e Roteamento Direto, o formato de número de telefone de transferência externa depende das configurações do Controlador de Borda de Sessão [(SBC).](direct-routing-connect-the-sbc.md)</span><span class="sxs-lookup"><span data-stu-id="fed70-255">For a resource account with a Phone System License and Direct Routing online voice routing policy, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="fed70-256">O número de telefone de saída exibido é determinado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="fed70-256">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="fed70-257">Para números do Plano de Chamadas, o número de telefone do chamador original é exibido.</span><span class="sxs-lookup"><span data-stu-id="fed70-257">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="fed70-258">Para números de Roteamento Direto, o número enviado é baseado na configuração P-Asserted-Identity (PAI) no SBC, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="fed70-258">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="fed70-259">Se definido como Desabilitado, o número de telefone do chamador original será exibido.</span><span class="sxs-lookup"><span data-stu-id="fed70-259">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="fed70-260">Essa é a configuração padrão e recomendada.</span><span class="sxs-lookup"><span data-stu-id="fed70-260">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="fed70-261">Se definido como Habilitado, o número de telefone da conta de recurso será exibido.</span><span class="sxs-lookup"><span data-stu-id="fed70-261">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="fed70-262">Em um Skype for Business híbrido, para transferir uma chamada de atendimento automático para a PSTN, crie um novo usuário local com encaminhamento de chamada definido para o número PSTN.</span><span class="sxs-lookup"><span data-stu-id="fed70-262">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="fed70-263">O usuário deve estar habilitado para Enterprise Voice e ter uma política de voz atribuída.</span><span class="sxs-lookup"><span data-stu-id="fed70-263">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="fed70-264">Para saber mais, confira [Transferência de chamada de atendimento automático para PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span><span class="sxs-lookup"><span data-stu-id="fed70-264">To learn more, see [Auto attendant call transfer to PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="fed70-265">Criar um atendimento automático com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="fed70-265">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="fed70-266">Você também pode usar o PowerShell para criar e configurar os atendimentos automáticos.</span><span class="sxs-lookup"><span data-stu-id="fed70-266">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="fed70-267">Aqui estão os cmdlets que você precisa para gerenciar um atendimento automático:</span><span class="sxs-lookup"><span data-stu-id="fed70-267">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="fed70-268">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="fed70-268">New-CsAutoAttendant</span></span>](/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="fed70-269">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="fed70-269">Set-CsAutoAttendant</span></span>](/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="fed70-270">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="fed70-270">Get-CsAutoAttendant</span></span>](/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="fed70-271">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="fed70-271">Get-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="fed70-272">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="fed70-272">Remove-CsAutoAttendant</span></span>](/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="fed70-273">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="fed70-273">New-CsAutoAttendantMenu</span></span>](/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="fed70-274">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="fed70-274">New-CsOnlineAudioFile</span></span>](/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="fed70-275">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="fed70-275">New-CsAutoAttendantCallFlow</span></span>](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="fed70-276">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="fed70-276">Export-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="fed70-277">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="fed70-277">New-CsOnlineTimeRange</span></span>](/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="fed70-278">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="fed70-278">New-CsOnlineDateTimeRange</span></span>](/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="fed70-279">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="fed70-279">New-CsOnlineSchedule</span></span>](/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="fed70-280">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="fed70-280">Get-CsAutoAttendantSupportedTimeZone</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="fed70-281">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="fed70-281">New-CsAutoAttendantCallHandlingAssociation</span></span>](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="fed70-282">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="fed70-282">Get-CsAutoAttendantSupportedLanguage</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="fed70-283">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="fed70-283">Import-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="fed70-284">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="fed70-284">New-CsAutoAttendantCallableEntity</span></span>](/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="fed70-285">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fed70-285">Related topics</span></span>

[<span data-ttu-id="fed70-286">Veja o que você obtém com o Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="fed70-286">Here's what you get with Phone System</span></span>](./here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="fed70-287">Obter números de telefone de serviço</span><span class="sxs-lookup"><span data-stu-id="fed70-287">Getting service phone numbers</span></span>](./getting-service-phone-numbers.md)

[<span data-ttu-id="fed70-288">Disponibilidade de Audioconferência e Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="fed70-288">Country and region availability for Audio Conferencing and Calling Plans</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="fed70-289">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fed70-289">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
