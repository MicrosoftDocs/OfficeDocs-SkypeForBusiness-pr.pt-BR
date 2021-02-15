---
title: Configurar um assistente automático para o Microsoft Teams
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
description: Saiba como configurar e testar os participantes automáticos do Microsoft Teams.
ms.openlocfilehash: bffe66fc59dfeb2f7028f2d5520b45930d753d07
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196625"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="15d04-103">Configurar um assistente automático</span><span class="sxs-lookup"><span data-stu-id="15d04-103">Set up an auto attendant</span></span>

<span data-ttu-id="15d04-104">Os participantes automáticos permitem que as pessoas liguem para sua organização e naveguem por um sistema de menus para falar com o departamento correto, fila de chamada, pessoa ou operador.</span><span class="sxs-lookup"><span data-stu-id="15d04-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="15d04-105">Você pode criar assistentes automáticos para sua organização com o Centro de administração do Microsoft Teams ou com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15d04-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="15d04-106">Certifique-se de que você leu o Plano para [](plan-auto-attendant-call-queue.md#getting-started) os participantes automáticos do Teams e as [filas](plan-auto-attendant-call-queue.md) de chamada e seguiu as etapas de início antes de seguir os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="15d04-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="15d04-107">Os atenderes automáticos podem direcionar chamadas, com base na entrada dos chamadores, para um dos seguintes destinos: <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="15d04-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="15d04-108">**Pessoa na organização** - uma pessoa em sua organização que pode receber chamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="15d04-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="15d04-109">Pode ser um usuário online ou um usuário hospedado localmente usando o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="15d04-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="15d04-110">**Aplicativo de voz** – outro atendimento automático ou uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="15d04-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="15d04-111">(Escolha a conta de recurso associada ao atendimento automático ou fila de chamada ao escolher este destino.)</span><span class="sxs-lookup"><span data-stu-id="15d04-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="15d04-112">**Número de telefone externo** – qualquer número de telefone.</span><span class="sxs-lookup"><span data-stu-id="15d04-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="15d04-113">(Veja detalhes [técnicos da transferência externa).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)</span><span class="sxs-lookup"><span data-stu-id="15d04-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="15d04-114">**Caixa** postal : a caixa postal associada a um grupo do Microsoft 365 especificado por você.</span><span class="sxs-lookup"><span data-stu-id="15d04-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="15d04-115">**Operador** – o operador definido para o atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="15d04-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="15d04-116">Definir um operador é opcional.</span><span class="sxs-lookup"><span data-stu-id="15d04-116">Defining an operator is optional.</span></span> <span data-ttu-id="15d04-117">O operador pode ser definido como qualquer um dos outros destinos nesta lista.</span><span class="sxs-lookup"><span data-stu-id="15d04-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="15d04-118">Você será solicitado a escolher uma dessas opções em vários estágios enquanto configura um assistente automático.</span><span class="sxs-lookup"><span data-stu-id="15d04-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="15d04-119">Para configurar um atendimento automático, no Centro de administração do Teams, expanda o **Voice,** clique em **Assistentes Automáticos** e, em seguida, clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="15d04-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="15d04-120">Informações gerais</span><span class="sxs-lookup"><span data-stu-id="15d04-120">General info</span></span>

![Captura de tela das configurações do assistente automático para nome, operador, fuso horário, idioma e entradas de voz](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="15d04-122">Digite um nome para o assistente automático na caixa na parte superior.</span><span class="sxs-lookup"><span data-stu-id="15d04-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="15d04-123">Se você quiser designar um operador, especifique o destino das chamadas para o operador.</span><span class="sxs-lookup"><span data-stu-id="15d04-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="15d04-124">Isso é opcional (mas recomendado).</span><span class="sxs-lookup"><span data-stu-id="15d04-124">This is optional (but recommended).</span></span> <span data-ttu-id="15d04-125">Você pode definir a **opção** Operador para permitir que os chamadores saiam dos menus e fale com uma pessoa designada.</span><span class="sxs-lookup"><span data-stu-id="15d04-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="15d04-126">Especifique o fuso horário desse assistente automático.</span><span class="sxs-lookup"><span data-stu-id="15d04-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="15d04-127">O fuso horário é usado para calcular o horário comercial se você criar um fluxo de chamada [separado para o horário de expediente.](#call-flow-for-after-hours)</span><span class="sxs-lookup"><span data-stu-id="15d04-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="15d04-128">[Especifique um idioma com suporte](create-a-phone-system-auto-attendant-languages.md) para esse assistente automático.</span><span class="sxs-lookup"><span data-stu-id="15d04-128">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="15d04-129">Esse é o idioma que será usado para prompts de voz gerados pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="15d04-129">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="15d04-130">Escolha se deseja habilitar entradas de voz.</span><span class="sxs-lookup"><span data-stu-id="15d04-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="15d04-131">Quando habilitado, o nome de cada opção de menu se tornará uma palavra-chave de reconhecimento de fala.</span><span class="sxs-lookup"><span data-stu-id="15d04-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="15d04-132">Por exemplo, os chamadores podem dizer "Um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "Vendas" para selecionar a opção de menu chamada "Vendas".</span><span class="sxs-lookup"><span data-stu-id="15d04-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

> [!NOTE]
> <span data-ttu-id="15d04-133">Se você escolher um idioma na Etapa 4 que não dá suporte a entradas de voz, essa opção será desabilitada.</span><span class="sxs-lookup"><span data-stu-id="15d04-133">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="15d04-134">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="15d04-134">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="15d04-135">Fluxo de chamada</span><span class="sxs-lookup"><span data-stu-id="15d04-135">Call flow</span></span>

![Captura de tela das configurações da mensagem de saudação](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="15d04-137">Escolha se você deseja reproduzir uma saudação quando o atendente automático atender uma chamada.</span><span class="sxs-lookup"><span data-stu-id="15d04-137">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="15d04-138">Se você selecionar **Reproduzir um arquivo de áudio,** poderá usar o **botão** Carregar arquivo para carregar uma mensagem de saudação gravada salva como áudio. Wav. MP3 ou . Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="15d04-138">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="15d04-139">A gravação pode ter no máximo 5 MB.</span><span class="sxs-lookup"><span data-stu-id="15d04-139">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="15d04-140">Se você selecionar **Digitar** uma mensagem de saudação, o sistema lerá o texto que você digitar (até 1.000 caracteres) quando o atendente automático atender uma chamada.</span><span class="sxs-lookup"><span data-stu-id="15d04-140">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Captura de tela das configurações de roteamento de chamadas](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="15d04-142">Escolha como você deseja encaminhar a chamada.</span><span class="sxs-lookup"><span data-stu-id="15d04-142">Choose how you want to route the call.</span></span>

<span data-ttu-id="15d04-143">Se você selecionar **Desconectar,** o atendimento automático desligará a chamada.</span><span class="sxs-lookup"><span data-stu-id="15d04-143">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="15d04-144">Se você selecionar **Redirecionar chamada,** poderá escolher um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="15d04-144">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="15d04-145">Se você selecionar as opções do  menu Reproduzir, poderá optar por Reproduzir um arquivo de áudio ou Digitar em uma mensagem de saudação e escolher entre as opções de **menu** e **a** pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="15d04-145">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="15d04-146">Opções de menu</span><span class="sxs-lookup"><span data-stu-id="15d04-146">Menu options</span></span>

![Captura de tela das opções de tecla de discagem](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="15d04-148">Para opções de discagem, você pode atribuir as teclas de 0 a 9 no teclado de telefone a um dos destinos de roteamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="15d04-148">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="15d04-149">(As teclas \* (Repetir) e \# (Voltar) são reservados pelo sistema e não podem ser reatribuídos.)</span><span class="sxs-lookup"><span data-stu-id="15d04-149">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="15d04-150">Os mapeamentos de teclas não devem ser contínuos.</span><span class="sxs-lookup"><span data-stu-id="15d04-150">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="15d04-151">É possível, por exemplo, criar um menu com as teclas 0, 1 e 3 mapeadas para opções, enquanto a tecla 2 não é usada.</span><span class="sxs-lookup"><span data-stu-id="15d04-151">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="15d04-152">Recomendamos mapear a tecla 0 para o operador se você tiver configurado uma.</span><span class="sxs-lookup"><span data-stu-id="15d04-152">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="15d04-153">Se o operador não estiver definido como chave, o comando de voz "Operador" também será desabilitado.</span><span class="sxs-lookup"><span data-stu-id="15d04-153">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="15d04-154">Para cada opção de menu, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="15d04-154">For each menu option, specify the following:</span></span>

- <span data-ttu-id="15d04-155">**Tecla de** discagem – a chave no teclado de telefone para acessar essa opção.</span><span class="sxs-lookup"><span data-stu-id="15d04-155">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="15d04-156">Se as entradas de voz estão disponíveis, os chamadores também podem dizer esse número para acessar a opção.</span><span class="sxs-lookup"><span data-stu-id="15d04-156">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="15d04-157">**Comando de** voz – define o comando de voz que um chamador pode dar para acessar essa opção, se as entradas de voz estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="15d04-157">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="15d04-158">Ele pode conter várias palavras, como "Atendimento ao Cliente" ou "Operações e Bases".</span><span class="sxs-lookup"><span data-stu-id="15d04-158">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="15d04-159">Por exemplo, o chamador pode pressionar 2, dizer "dois" ou dizer "Vendas" para selecionar a opção mapeada para a tecla 2.</span><span class="sxs-lookup"><span data-stu-id="15d04-159">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="15d04-160">Esse texto também é renderizado por texto em fala para o prompt de confirmação do serviço, que pode ser algo como "Transferindo sua chamada para vendas".</span><span class="sxs-lookup"><span data-stu-id="15d04-160">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="15d04-161">**Redirecionar para** – o destino de roteamento de chamada usado quando os chamadores escolhem essa opção.</span><span class="sxs-lookup"><span data-stu-id="15d04-161">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="15d04-162">Se você estiver redirecionando para um atendimento automático ou fila de chamada, escolha a conta de recurso associada a ela.</span><span class="sxs-lookup"><span data-stu-id="15d04-162">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="15d04-163">Pesquisa de diretório</span><span class="sxs-lookup"><span data-stu-id="15d04-163">Directory search</span></span>

<span data-ttu-id="15d04-164">Se você atribuir teclas de discagem a destinos, recomendamos que você escolha **Nenhuma** para **pesquisa de diretório.**</span><span class="sxs-lookup"><span data-stu-id="15d04-164">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="15d04-165">Se um chamador tentar discar um nome ou extensão usando teclas atribuídas a destinos específicos, ele poderá ser roteado inesperadamente para um destino antes de terminar de inserir o nome ou a extensão.</span><span class="sxs-lookup"><span data-stu-id="15d04-165">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="15d04-166">Recomendamos que você crie um assistente automático separado para pesquisa de diretório e tenha o link do seu principal assistente automático para ele por meio de uma tecla de discagem.</span><span class="sxs-lookup"><span data-stu-id="15d04-166">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="15d04-167">Se você não atribuiu teclas de discagem, escolha uma opção para a **pesquisa de diretório.**</span><span class="sxs-lookup"><span data-stu-id="15d04-167">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="15d04-168">**Discar por nome** – Se você habilitar essa opção, os chamadores poderão dizer o nome do usuário ou digitá-lo no teclado do telefone.</span><span class="sxs-lookup"><span data-stu-id="15d04-168">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="15d04-169">Qualquer usuário online ou qualquer usuário hospedado localmente usando o Skype for Business Server é um usuário qualificado e pode ser encontrado com o Dial por nome.</span><span class="sxs-lookup"><span data-stu-id="15d04-169">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="15d04-170">(Você pode definir quem é e não está incluído no diretório na página de escopo [do Discar.)](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="15d04-170">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="15d04-171">**Discar por extensão** – Se você habilitar essa opção, os chamadores poderão se conectar aos usuários em sua organização discando a extensão do telefone.</span><span class="sxs-lookup"><span data-stu-id="15d04-171">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="15d04-172">Qualquer usuário online ou qualquer usuário hospedado localmente usando o Skype for Business Server é um usuário qualificado e pode ser encontrado com o **Dial por extensão.**</span><span class="sxs-lookup"><span data-stu-id="15d04-172">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="15d04-173">(Você pode definir quem é e não está incluído no diretório na página de escopo [do Discar.)](#dial-scope)</span><span class="sxs-lookup"><span data-stu-id="15d04-173">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="15d04-174">Os usuários que você deseja disponibilizar para Discar por Extensão precisam ter uma extensão especificada como parte de um dos seguintes atributos de telefone definidos no Active Directory ou no Azure Active Directory (consulte Adicionar usuários [individualmente](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) ou em massa para obter mais informações.)</span><span class="sxs-lookup"><span data-stu-id="15d04-174">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="15d04-175">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="15d04-175">OfficePhone</span></span>
- <span data-ttu-id="15d04-176">Homephone</span><span class="sxs-lookup"><span data-stu-id="15d04-176">HomePhone</span></span>
- <span data-ttu-id="15d04-177">Celular/Celular</span><span class="sxs-lookup"><span data-stu-id="15d04-177">Mobile/MobilePhone</span></span>
- <span data-ttu-id="15d04-178">Número De Telefone/Número De Telefone</span><span class="sxs-lookup"><span data-stu-id="15d04-178">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="15d04-179">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="15d04-179">OtherTelephone</span></span>

<span data-ttu-id="15d04-180">O formato necessário para inserir a extensão no campo de número de telefone do usuário é:</span><span class="sxs-lookup"><span data-stu-id="15d04-180">The required format to enter the extension in the user phone number field is either:</span></span>

- <span data-ttu-id="15d04-181">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="15d04-181">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="15d04-182">*+\<phone number>X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="15d04-182">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="15d04-183">*X\<extension>*</span><span class="sxs-lookup"><span data-stu-id="15d04-183">*x\<extension>*</span></span>

- <span data-ttu-id="15d04-184">Exemplo 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="15d04-184">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="15d04-185">Exemplo 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="15d04-185">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="15d04-186">Exemplo 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="15d04-186">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="15d04-187">Você pode definir a extensão no Centro de administração do [Microsoft 365](https://admin.microsoft.com/) ou no Centro de administração do [Azure Active Directory.](https://aad.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="15d04-187">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="15d04-188">Pode levar até 12 horas até que as alterações sejam disponibilizadas para os atendimentos automáticos e filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="15d04-188">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="15d04-189">Se quiser usar os  recursos Discar por nome e Discar por extensão, você pode atribuir uma tecla de discagem no seu atendimento automático principal para chegar a um assistente automático habilitado para Discar **por nome.** </span><span class="sxs-lookup"><span data-stu-id="15d04-189">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="15d04-190">Nesse atendimento automático, você pode atribuir a tecla 1 (que não tem letras associadas a ela) para chegar ao atendimento automático **discar** por extensão.</span><span class="sxs-lookup"><span data-stu-id="15d04-190">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="15d04-191">Depois de selecionar uma opção de pesquisa **de** diretório, clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="15d04-191">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="15d04-192">Fluxo de chamada para horas extras</span><span class="sxs-lookup"><span data-stu-id="15d04-192">Call flow for after hours</span></span>

![Captura de tela das configurações de dia e hora após o expediente](media/auto-attendant-business-hours.png)

<span data-ttu-id="15d04-194">O horário comercial pode ser definido para cada atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="15d04-194">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="15d04-195">Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão.</span><span class="sxs-lookup"><span data-stu-id="15d04-195">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="15d04-196">Os horários comerciais podem ser definidos com quebras de tempo durante o dia, e todas as horas que não são definidas como horários comerciais são consideradas horas extras.</span><span class="sxs-lookup"><span data-stu-id="15d04-196">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="15d04-197">Você pode definir diferentes opções de tratamento de chamadas de entrada e saudações para o horário de expediente.</span><span class="sxs-lookup"><span data-stu-id="15d04-197">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="15d04-198">Dependendo de como você configurou seus atenderes automáticos e filas de chamadas, talvez você só precise especificar o roteamento de chamadas após o expediente para os atender automaticamente com números de telefone diretos.</span><span class="sxs-lookup"><span data-stu-id="15d04-198">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="15d04-199">Se você quiser roteamento de chamadas separado para chamadores de horas extras, especifique seu horário comercial para cada dia.</span><span class="sxs-lookup"><span data-stu-id="15d04-199">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="15d04-200">Clique **em Adicionar novo horário** para especificar vários conjuntos de horas para um determinado dia, por exemplo, para especificar uma pausa para o almoço.</span><span class="sxs-lookup"><span data-stu-id="15d04-200">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="15d04-201">Depois de especificar seu horário comercial, escolha as opções de roteamento de chamadas para horas extras.</span><span class="sxs-lookup"><span data-stu-id="15d04-201">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="15d04-202">As mesmas opções estão disponíveis para o roteamento de chamadas de horário comercial especificado acima.</span><span class="sxs-lookup"><span data-stu-id="15d04-202">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="15d04-203">Clique **em** Próxima quando terminar.</span><span class="sxs-lookup"><span data-stu-id="15d04-203">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="15d04-204">Fluxos de chamada durante feriados</span><span class="sxs-lookup"><span data-stu-id="15d04-204">Call flows during holidays</span></span>

![Captura de tela das configurações de saudação de feriados e feriados](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="15d04-206">O seu chamador automático pode ter um fluxo de chamada para cada [Feriado que você tiver definido.](set-up-holidays-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="15d04-206">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="15d04-207">Você pode adicionar até 20 feriados agendados para cada atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="15d04-207">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="15d04-208">Na página de configurações de chamada de fim de ano, clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="15d04-208">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="15d04-209">Digite um nome para essa configuração de feriado.</span><span class="sxs-lookup"><span data-stu-id="15d04-209">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="15d04-210">Na lista **de** feriados, escolha o feriado que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="15d04-210">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="15d04-211">Escolha o tipo de saudação que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="15d04-211">Choose the type of greeting that you want to use.</span></span>

    ![Captura de tela das configurações de ação de chamada de fim de ano](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="15d04-213">Escolha se você deseja **desconectar** **ou redirecionar** a chamada.</span><span class="sxs-lookup"><span data-stu-id="15d04-213">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="15d04-214">Se você optar por redirecionar, escolha o destino de roteamento de chamadas para a chamada.</span><span class="sxs-lookup"><span data-stu-id="15d04-214">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="15d04-215">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="15d04-215">Click **Save**.</span></span>

![Captura de tela das configurações de feriados com feriados listados](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="15d04-217">Repita o procedimento conforme necessário para cada feriado adicional.</span><span class="sxs-lookup"><span data-stu-id="15d04-217">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="15d04-218">Quando você adicionar todos os feriados, clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="15d04-218">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="15d04-219">Escopo de discagem</span><span class="sxs-lookup"><span data-stu-id="15d04-219">Dial scope</span></span>

![Captura de tela das opções de inclusão e exclusão do escopo de discagem](media/auto-attendant-dial-scope.png)

<span data-ttu-id="15d04-221">O *escopo de* discagem define quais usuários estão disponíveis no diretório quando um chamador usa discagem por nome ou discagem por extensão.</span><span class="sxs-lookup"><span data-stu-id="15d04-221">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="15d04-222">O padrão de **Todos os usuários online** inclui todos os usuários da sua organização que são usuários online ou hospedados localmente usando o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="15d04-222">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="15d04-223">Você pode incluir ou excluir  usuários específicos  selecionando o grupo de usuários personalizado em Incluir ou Excluir e escolhendo um ou mais grupos, listas de distribuição ou grupos de segurança do Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="15d04-223">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="15d04-224">Por exemplo, talvez você queira excluir executivos de sua organização do diretório de discagem.</span><span class="sxs-lookup"><span data-stu-id="15d04-224">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="15d04-225">(Se um usuário estiver em ambas as listas, ele será excluído do diretório.)</span><span class="sxs-lookup"><span data-stu-id="15d04-225">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="15d04-226">Pode levar até 36 horas para que um novo usuário tenha seu nome listado no diretório.</span><span class="sxs-lookup"><span data-stu-id="15d04-226">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="15d04-227">Quando terminar de definir o escopo de discagem, clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="15d04-227">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="15d04-228">Contas de recursos</span><span class="sxs-lookup"><span data-stu-id="15d04-228">Resource accounts</span></span>

<span data-ttu-id="15d04-229">Todos os participantes automáticos devem ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="15d04-229">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="15d04-230">Os participantes automáticos de primeiro nível precisarão de pelo menos uma conta de recurso que tenha um número de serviço associado.</span><span class="sxs-lookup"><span data-stu-id="15d04-230">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="15d04-231">Se desejar, você pode atribuir várias contas de recurso a um atendimento automático, cada uma com um número de serviço separado.</span><span class="sxs-lookup"><span data-stu-id="15d04-231">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Captura de tela do painel adicionar contas da conta de recurso](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="15d04-233">Para adicionar uma conta de recurso, clique **em Adicionar conta** e pesquise a conta que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="15d04-233">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="15d04-234">Clique **em Adicionar** e, em seguida, clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="15d04-234">Click **Add**, and then click **Add**.</span></span>

![Captura de tela da lista de contas de recursos mostrando a conta de recurso com o número de serviço atribuído](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="15d04-236">Quando terminar de adicionar contas de serviço, clique em **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="15d04-236">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="15d04-237">Isso conclui a configuração do atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="15d04-237">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="15d04-238">Transferências de número de telefone externo – detalhes técnicos</span><span class="sxs-lookup"><span data-stu-id="15d04-238">External phone number transfers - technical details</span></span>

<span data-ttu-id="15d04-239">Consulte os [Pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) para permitir que os atenderes automáticos transfira chamadas externamente.</span><span class="sxs-lookup"><span data-stu-id="15d04-239">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="15d04-240">Além disso:</span><span class="sxs-lookup"><span data-stu-id="15d04-240">In addition:</span></span>

- <span data-ttu-id="15d04-241">Para uma conta [](calling-plans-for-office-365.md) de recurso com um número de Plano de Chamada, o número de telefone de transferência externa deve ser inserido no formato E.164 (+[código do país][código de área][número de telefone]).</span><span class="sxs-lookup"><span data-stu-id="15d04-241">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="15d04-242">Para uma conta de recurso com um número de Roteamento Direto, o formato de número de telefone de transferência externa depende das configurações do Controlador de Borda de Sessão [(SBC).](direct-routing-connect-the-sbc.md)</span><span class="sxs-lookup"><span data-stu-id="15d04-242">For a resource account with a Direct Routing number, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="15d04-243">O número de telefone de saída exibido é determinado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="15d04-243">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="15d04-244">Para números do Plano de Chamada, o número de telefone do chamador original é exibido.</span><span class="sxs-lookup"><span data-stu-id="15d04-244">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="15d04-245">Para números de Roteamento Direto, o número enviado baseia-se na configuração pai (identidade de P) no SBC, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="15d04-245">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="15d04-246">Se definido como Desabilitado, o número de telefone do chamador original será exibido.</span><span class="sxs-lookup"><span data-stu-id="15d04-246">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="15d04-247">Essa é a configuração padrão e recomendada.</span><span class="sxs-lookup"><span data-stu-id="15d04-247">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="15d04-248">Se definido como Habilitado, o número de telefone da conta de recurso será exibido.</span><span class="sxs-lookup"><span data-stu-id="15d04-248">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="15d04-249">Em um ambiente híbrido do Skype for Business, para transferir uma chamada de atendimento automático para o PSTN, crie um novo usuário local com o encaminhamento de chamadas definido para o número PSTN.</span><span class="sxs-lookup"><span data-stu-id="15d04-249">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="15d04-250">O usuário deve estar habilitado para o Enterprise Voice e ter uma política de voz atribuída.</span><span class="sxs-lookup"><span data-stu-id="15d04-250">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="15d04-251">Para saber mais, confira [a transferência de chamada do atendimento automático para pSTN.](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)</span><span class="sxs-lookup"><span data-stu-id="15d04-251">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="15d04-252">Criar um assistente automático com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="15d04-252">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="15d04-253">Você também pode usar o PowerShell para criar e configurar os participantes automáticos.</span><span class="sxs-lookup"><span data-stu-id="15d04-253">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="15d04-254">Aqui estão os cmdlets necessários para gerenciar um atendimento automático:</span><span class="sxs-lookup"><span data-stu-id="15d04-254">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="15d04-255">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="15d04-255">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="15d04-256">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="15d04-256">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="15d04-257">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="15d04-257">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="15d04-258">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="15d04-258">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="15d04-259">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="15d04-259">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="15d04-260">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="15d04-260">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="15d04-261">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="15d04-261">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="15d04-262">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="15d04-262">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="15d04-263">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="15d04-263">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="15d04-264">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="15d04-264">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="15d04-265">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="15d04-265">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="15d04-266">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="15d04-266">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="15d04-267">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="15d04-267">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="15d04-268">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="15d04-268">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="15d04-269">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="15d04-269">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="15d04-270">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="15d04-270">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="15d04-271">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="15d04-271">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="15d04-272">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="15d04-272">Related topics</span></span>

[<span data-ttu-id="15d04-273">Veja o que você obtém com o Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="15d04-273">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="15d04-274">Obter números de telefone de serviço</span><span class="sxs-lookup"><span data-stu-id="15d04-274">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="15d04-275">Disponibilidade de Audioconferência e Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="15d04-275">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="15d04-276">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="15d04-276">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
