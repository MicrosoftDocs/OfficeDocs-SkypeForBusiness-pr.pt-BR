---
title: Configurar um atendedor automático para o Microsoft Teams
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
description: Saiba como configurar e testar atendedores automáticos do Microsoft Teams.
ms.openlocfilehash: 203a05e19ffce4154c123cbb700ca59e0b75a63a
ms.sourcegitcommit: 660d0d65892408d0bb4ac1a870c88b11a7c6841e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49530584"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="21aeb-103">Configurar um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="21aeb-103">Set up an auto attendant</span></span>

<span data-ttu-id="21aeb-104">Os atendedores automáticos permitem que as pessoas liguem para sua organização e naveguem em um sistema de menus para falar com o departamento certo, a fila de chamadas, a pessoa ou um operador.</span><span class="sxs-lookup"><span data-stu-id="21aeb-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="21aeb-105">Você pode criar atendedores automáticos para sua organização com o centro de administração do Microsoft Teams ou com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21aeb-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="21aeb-106">Verifique se você leu o [plano de atendedores automáticos e filas de chamadas do teams](plan-auto-attendant-call-queue.md) e seguiu as [etapas de introdução](plan-auto-attendant-call-queue.md#getting-started) antes de seguir os procedimentos deste artigo.</span><span class="sxs-lookup"><span data-stu-id="21aeb-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="21aeb-107">Os atendedores automáticos podem direcionar chamadas com base nas entradas dos chamadores para um dos seguintes destinos: <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="21aeb-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="21aeb-108">**Pessoa na organização** -uma pessoa em sua organização que pode receber chamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="21aeb-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="21aeb-109">Pode ser um usuário online ou um usuário hospedado no local usando o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="21aeb-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="21aeb-110">**Aplicativo de voz** -outro atendedor automático ou uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="21aeb-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="21aeb-111">(Escolha a conta de recurso associada ao atendedor automático ou à fila de chamadas ao escolher este destino.)</span><span class="sxs-lookup"><span data-stu-id="21aeb-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="21aeb-112">**Número de telefone externo** – qualquer número de telefone.</span><span class="sxs-lookup"><span data-stu-id="21aeb-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="21aeb-113">(Veja [detalhes técnicos da transferência externa](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span><span class="sxs-lookup"><span data-stu-id="21aeb-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="21aeb-114">Correio **de voz-a** caixa de correio de voz associada a um grupo do Microsoft 365 que você especificar.</span><span class="sxs-lookup"><span data-stu-id="21aeb-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="21aeb-115">**Operator** – o operador definido para o atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="21aeb-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="21aeb-116">A definição de um operador é opcional.</span><span class="sxs-lookup"><span data-stu-id="21aeb-116">Defining an operator is optional.</span></span> <span data-ttu-id="21aeb-117">O operador pode ser definido como qualquer um dos outros destinos nesta lista.</span><span class="sxs-lookup"><span data-stu-id="21aeb-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="21aeb-118">Você será solicitado a escolher uma dessas opções em diversos estágios à medida que configurar um atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="21aeb-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="21aeb-119">Para configurar um atendedor automático, no centro de administração do Teams, expanda **voz**, clique em **atendedores automáticos** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="21aeb-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="21aeb-120">Informações gerais</span><span class="sxs-lookup"><span data-stu-id="21aeb-120">General info</span></span>

![Captura de tela das configurações do atendedor automático para nome, operador, fuso horário, idioma e entradas de voz](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="21aeb-122">Digite um nome para o atendedor automático na caixa na parte superior.</span><span class="sxs-lookup"><span data-stu-id="21aeb-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="21aeb-123">Se você quiser designar um operador, especifique o destino para as chamadas para o operador.</span><span class="sxs-lookup"><span data-stu-id="21aeb-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="21aeb-124">Isso é opcional (mas recomendado).</span><span class="sxs-lookup"><span data-stu-id="21aeb-124">This is optional (but recommended).</span></span> <span data-ttu-id="21aeb-125">Você pode definir a opção de **operador** para permitir que os chamadores quebrem nos menus e falar com uma pessoa designada.</span><span class="sxs-lookup"><span data-stu-id="21aeb-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="21aeb-126">Especifique o fuso horário para este atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="21aeb-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="21aeb-127">O fuso horário é usado para calcular o horário comercial se você [criar um fluxo de chamadas separado para o expediente](#call-flow-for-after-hours).</span><span class="sxs-lookup"><span data-stu-id="21aeb-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="21aeb-128">Especifique um idioma para este atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="21aeb-128">Specify a language for this auto attendant.</span></span> <span data-ttu-id="21aeb-129">Esse é o idioma que será usado para solicitações de voz geradas pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="21aeb-129">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="21aeb-130">Escolha se deseja habilitar as entradas de voz.</span><span class="sxs-lookup"><span data-stu-id="21aeb-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="21aeb-131">Quando habilitado, o nome de cada opção de menu se torna uma palavra-chave de reconhecimento de fala.</span><span class="sxs-lookup"><span data-stu-id="21aeb-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="21aeb-132">Por exemplo, os chamadores podem dizer "um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "vendas" para selecionar a opção de menu chamada "vendas".</span><span class="sxs-lookup"><span data-stu-id="21aeb-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="21aeb-133">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="21aeb-133">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="21aeb-134">Fluxo de chamadas</span><span class="sxs-lookup"><span data-stu-id="21aeb-134">Call flow</span></span>

![Captura de tela das configurações da mensagem de saudação](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="21aeb-136">Escolha se deseja reproduzir uma saudação quando o atendedor automático atender a uma chamada.</span><span class="sxs-lookup"><span data-stu-id="21aeb-136">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="21aeb-137">Se você selecionar **executar um arquivo de áudio** , poderá usar o botão **carregar arquivo** para carregar uma mensagem de saudação gravada salva como áudio. WAV,. MP3 ou. Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="21aeb-137">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="21aeb-138">A gravação não pode ter mais de 5 MB.</span><span class="sxs-lookup"><span data-stu-id="21aeb-138">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="21aeb-139">Se você selecionar **digitar uma mensagem de saudação** , o sistema lerá o texto que você digitar (até 1000 caracteres) quando o atendedor automático atender a uma chamada.</span><span class="sxs-lookup"><span data-stu-id="21aeb-139">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![Captura de tela das configurações de roteamento de chamadas](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="21aeb-141">Escolha como você deseja direcionar a chamada.</span><span class="sxs-lookup"><span data-stu-id="21aeb-141">Choose how you want to route the call.</span></span>

<span data-ttu-id="21aeb-142">Se você selecionar **Desconectar**, o atendedor automático irá desligar a chamada.</span><span class="sxs-lookup"><span data-stu-id="21aeb-142">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="21aeb-143">Se você selecionar **redirecionar chamada**, poderá escolher um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="21aeb-143">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="21aeb-144">Se você selecionar **Opções do menu reproduzir**, poderá optar por **reproduzir um arquivo de áudio** ou **digitar uma mensagem de saudação** e escolher entre as opções do menu e a pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="21aeb-144">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="21aeb-145">Opções do menu</span><span class="sxs-lookup"><span data-stu-id="21aeb-145">Menu options</span></span>

![Captura de tela das opções da tecla de discagem](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="21aeb-147">Para opções de discagem, você pode atribuir as chaves 0-9 no teclado de telefone a um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="21aeb-147">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="21aeb-148">(As teclas \* (Repetir) e \# (verso) são reservados pelo sistema e não podem ser reatribuídos.)</span><span class="sxs-lookup"><span data-stu-id="21aeb-148">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="21aeb-149">Os mapeamentos de chave não precisam ser contínuos.</span><span class="sxs-lookup"><span data-stu-id="21aeb-149">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="21aeb-150">É possível, por exemplo, criar um menu com as teclas 0, 1 e 3 mapeadas para as opções, enquanto que a 2 chave não seja usada.</span><span class="sxs-lookup"><span data-stu-id="21aeb-150">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="21aeb-151">Recomendamos mapear a chave 0 para a operadora se você tiver configurado uma.</span><span class="sxs-lookup"><span data-stu-id="21aeb-151">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="21aeb-152">Se o operador não estiver definido como qualquer chave, o comando de voz "operador" também será desabilitado.</span><span class="sxs-lookup"><span data-stu-id="21aeb-152">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="21aeb-153">Para cada opção de menu, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="21aeb-153">For each menu option, specify the following:</span></span>

- <span data-ttu-id="21aeb-154">**Tecla de discagem** -a tecla no teclado do telefone para acessar esta opção.</span><span class="sxs-lookup"><span data-stu-id="21aeb-154">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="21aeb-155">Se as entradas de voz estiverem disponíveis, os chamadores também poderão dizer esse número para acessar a opção.</span><span class="sxs-lookup"><span data-stu-id="21aeb-155">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="21aeb-156">**Comando de voz** -define o comando de voz que um chamador pode conceder para acessar essa opção, se as entradas de voz estiverem habilitadas.</span><span class="sxs-lookup"><span data-stu-id="21aeb-156">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="21aeb-157">Ele pode conter várias palavras como "atendimento ao cliente" ou "operações e aterramento".</span><span class="sxs-lookup"><span data-stu-id="21aeb-157">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="21aeb-158">Por exemplo, o chamador pode pressionar 2, dizer "dois", ou dizer "vendas" para selecionar a opção mapeada para a chave 2.</span><span class="sxs-lookup"><span data-stu-id="21aeb-158">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="21aeb-159">Esse texto também é renderizado por texto em fala para o prompt de confirmação do serviço, que pode ser algo parecido com "Transferindo sua chamada para vendas".</span><span class="sxs-lookup"><span data-stu-id="21aeb-159">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="21aeb-160">**Redirecionar para** -o destino de roteamento de chamadas usado quando os chamadores escolhem essa opção.</span><span class="sxs-lookup"><span data-stu-id="21aeb-160">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="21aeb-161">Se você estiver redirecionando para um atendedor automático ou fila de chamadas, escolha a conta do recurso associada a ele.</span><span class="sxs-lookup"><span data-stu-id="21aeb-161">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="21aeb-162">Pesquisa de diretório</span><span class="sxs-lookup"><span data-stu-id="21aeb-162">Directory search</span></span>

<span data-ttu-id="21aeb-163">Se você atribuir chaves de discagem aos destinos, recomendamos que você escolha **nenhuma** para **pesquisa de diretório**.</span><span class="sxs-lookup"><span data-stu-id="21aeb-163">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="21aeb-164">Se um usuário tentar discar um nome ou uma extensão usando chaves atribuídas a destinos específicos, eles podem ser roteados inesperadamente para um destino antes de terminarem de digitar o nome ou a extensão.</span><span class="sxs-lookup"><span data-stu-id="21aeb-164">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="21aeb-165">Recomendamos que você crie um atendedor automático separado para a pesquisa de diretório e tenha o link principal do atendedor automático por meio de uma tecla de discagem.</span><span class="sxs-lookup"><span data-stu-id="21aeb-165">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="21aeb-166">Se você não atribuiu teclas de discagem, selecione uma opção para **pesquisa de diretório**.</span><span class="sxs-lookup"><span data-stu-id="21aeb-166">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="21aeb-167">**Discar por nome** -se você habilitar essa opção, os chamadores poderão dizer o nome do usuário ou digitá-lo no teclado do telefone.</span><span class="sxs-lookup"><span data-stu-id="21aeb-167">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="21aeb-168">Qualquer usuário online com uma licença de sistema telefônico ou qualquer usuário hospedado no local usando o Skype for Business Server é um usuário elegível e pode ser encontrado com o nome discado.</span><span class="sxs-lookup"><span data-stu-id="21aeb-168">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="21aeb-169">(Você pode definir quem é e não está incluído no diretório na página de [escopo de discagem](#dial-scope) ).</span><span class="sxs-lookup"><span data-stu-id="21aeb-169">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="21aeb-170">**Discar por extensão** -se você habilitar essa opção, os chamadores poderão se conectar aos usuários na sua organização discando a extensão do telefone.</span><span class="sxs-lookup"><span data-stu-id="21aeb-170">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="21aeb-171">Qualquer usuário online com uma licença do sistema telefônico ou qualquer usuário hospedado no local usando o Skype for Business Server é um usuário elegível e pode ser encontrado com a **extensão dial**-to.</span><span class="sxs-lookup"><span data-stu-id="21aeb-171">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="21aeb-172">(Você pode definir quem é e não está incluído no diretório na página de [escopo de discagem](#dial-scope) ).</span><span class="sxs-lookup"><span data-stu-id="21aeb-172">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="21aeb-173">Os usuários que você deseja disponibilizar por ramal devem ter uma extensão especificada como parte de um dos seguintes atributos de telefone definidos no Active Directory ou Active Directory do Azure (consulte [Adicionar usuários individualmente ou em massa](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) para obter mais informações.)</span><span class="sxs-lookup"><span data-stu-id="21aeb-173">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="21aeb-174">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="21aeb-174">OfficePhone</span></span>
- <span data-ttu-id="21aeb-175">HomePhone</span><span class="sxs-lookup"><span data-stu-id="21aeb-175">HomePhone</span></span>
- <span data-ttu-id="21aeb-176">Celular/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="21aeb-176">Mobile/MobilePhone</span></span>
- <span data-ttu-id="21aeb-177">TelephoneNumber/intervalo</span><span class="sxs-lookup"><span data-stu-id="21aeb-177">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="21aeb-178">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="21aeb-178">OtherTelephone</span></span>

<span data-ttu-id="21aeb-179">O formato obrigatório para inserir a extensão no campo de número de telefone do usuário é *+ \<phone number> : ext \<extension> =* ou *+ \<phone number> ; \<extension> x*.</span><span class="sxs-lookup"><span data-stu-id="21aeb-179">The required format to enter the extension in the user phone number field is either *+\<phone number>;ext=\<extension>* or *+\<phone number>;x\<extension>*.</span></span>
<span data-ttu-id="21aeb-180">Exemplo: Set-MsolUser-UserPrincipalName usern@domain.com-intervalo "+ 15555555678; ext = 5678".</span><span class="sxs-lookup"><span data-stu-id="21aeb-180">Example: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678".</span></span>

<span data-ttu-id="21aeb-181">Você pode definir a extensão no [centro de administração do Microsoft 365](https://admin.microsoft.com/) ou no [centro de administração do Azure Active Directory](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="21aeb-181">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="21aeb-182">Pode levar até 12 horas antes que as alterações sejam disponibilizadas para atendedores automáticos e filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="21aeb-182">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="21aeb-183">Se você quiser usar os recursos **discar por nome** e **discar pelos** recursos de extensão, poderá atribuir uma tecla de discagem em seu atendedor principal para acessar um atendedor automático habilitado para **discar por nome**.</span><span class="sxs-lookup"><span data-stu-id="21aeb-183">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="21aeb-184">Nesse atendedor automático, você pode atribuir uma tecla 1 (que não tem letras associadas a ela) para alcançar o atendedor automático de **discagem por extensão** .</span><span class="sxs-lookup"><span data-stu-id="21aeb-184">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="21aeb-185">Depois de selecionar uma opção de **pesquisa de diretório** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="21aeb-185">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="21aeb-186">Fluxo de chamadas por horas extras</span><span class="sxs-lookup"><span data-stu-id="21aeb-186">Call flow for after hours</span></span>

![Captura de tela das configurações de horas e dia da hora](media/auto-attendant-business-hours.png)

<span data-ttu-id="21aeb-188">O horário comercial pode ser definido para cada atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="21aeb-188">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="21aeb-189">Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão.</span><span class="sxs-lookup"><span data-stu-id="21aeb-189">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="21aeb-190">O horário comercial pode ser definido com quebras de horário durante o dia, e todas as horas que não estão definidas como horário comercial são consideradas após o expediente.</span><span class="sxs-lookup"><span data-stu-id="21aeb-190">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="21aeb-191">Você pode definir diferentes opções de atendimento de chamadas e saudações por horas extras.</span><span class="sxs-lookup"><span data-stu-id="21aeb-191">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="21aeb-192">Dependendo de como você configurou seus atendedores automáticos e filas de chamadas, talvez você só precise especificar o roteamento de chamadas após a hora para atendedores automáticos com números de telefone diretos.</span><span class="sxs-lookup"><span data-stu-id="21aeb-192">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="21aeb-193">Se você quiser um encaminhamento de chamadas separado para chamadores após a hora e, em seguida, especifique o horário comercial para cada dia.</span><span class="sxs-lookup"><span data-stu-id="21aeb-193">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="21aeb-194">Clique em **Adicionar novo horário** para especificar vários conjuntos de horas para um determinado dia, por exemplo, para especificar um intervalo de almoço.</span><span class="sxs-lookup"><span data-stu-id="21aeb-194">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="21aeb-195">Depois de especificar o horário comercial, escolha as opções de roteamento de chamadas para o expediente.</span><span class="sxs-lookup"><span data-stu-id="21aeb-195">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="21aeb-196">As mesmas opções estão disponíveis para o encaminhamento de chamadas do horário comercial que você especificou acima.</span><span class="sxs-lookup"><span data-stu-id="21aeb-196">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="21aeb-197">Clique em **Avançar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="21aeb-197">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="21aeb-198">Fluxos de chamadas durante feriados</span><span class="sxs-lookup"><span data-stu-id="21aeb-198">Call flows during holidays</span></span>

![Captura de tela das configurações de saudação de feriado e feriado](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="21aeb-200">O atendedor automático pode ter um fluxo de chamadas para cada [feriado que você configurou](set-up-holidays-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="21aeb-200">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="21aeb-201">Você pode adicionar até 20 feriados agendados para cada atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="21aeb-201">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="21aeb-202">Na página de configurações de chamadas de Natal, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="21aeb-202">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="21aeb-203">Digite um nome para esta configuração de feriado.</span><span class="sxs-lookup"><span data-stu-id="21aeb-203">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="21aeb-204">Na lista suspensa **feriado** , escolha o feriado que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="21aeb-204">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="21aeb-205">Escolha o tipo de saudação que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="21aeb-205">Choose the type of greeting that you want to use.</span></span>

    ![Captura de tela das configurações de ação das chamadas de Natal](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="21aeb-207">Escolha se deseja **Desconectar** ou **redirecionar** a chamada.</span><span class="sxs-lookup"><span data-stu-id="21aeb-207">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="21aeb-208">Se você optou por redirecionar, escolha o destino de roteamento de chamadas para a chamada.</span><span class="sxs-lookup"><span data-stu-id="21aeb-208">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="21aeb-209">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="21aeb-209">Click **Save**.</span></span>

![Captura de tela das configurações de feriado com feriados listados](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="21aeb-211">Repita o procedimento conforme necessário para cada feriado adicional.</span><span class="sxs-lookup"><span data-stu-id="21aeb-211">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="21aeb-212">Depois de adicionar todos os seus feriados, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="21aeb-212">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="21aeb-213">Escopo de discagem</span><span class="sxs-lookup"><span data-stu-id="21aeb-213">Dial scope</span></span>

![Captura de tela das opções incluir e excluir do escopo de discagem](media/auto-attendant-dial-scope.png)

<span data-ttu-id="21aeb-215">O *escopo de discagem* define quais usuários estão disponíveis no diretório quando um chamador usa discar por nome ou discagem por extensão.</span><span class="sxs-lookup"><span data-stu-id="21aeb-215">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="21aeb-216">O padrão de **todos os usuários online** inclui todos os usuários em sua organização que são usuários online com uma licença do sistema telefônico ou hospedada no local usando o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="21aeb-216">The default of **All online users** includes all users in your organization that are Online users with a Phone System license or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="21aeb-217">Você pode incluir ou excluir usuários específicos selecionando **grupo de usuários personalizado** em **incluir** ou **excluir** e escolhendo um ou mais grupos do Microsoft 365, listas de distribuição ou grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="21aeb-217">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="21aeb-218">Por exemplo, talvez você queira excluir executivos de sua organização do diretório de discagem.</span><span class="sxs-lookup"><span data-stu-id="21aeb-218">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="21aeb-219">(Se um usuário estiver em ambas as listas, eles serão excluídos do diretório.)</span><span class="sxs-lookup"><span data-stu-id="21aeb-219">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="21aeb-220">Pode levar até 36 horas para que um novo usuário tenha o nome listado no diretório.</span><span class="sxs-lookup"><span data-stu-id="21aeb-220">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="21aeb-221">Quando terminar de configurar o escopo de discagem, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="21aeb-221">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="21aeb-222">Contas de recursos</span><span class="sxs-lookup"><span data-stu-id="21aeb-222">Resource accounts</span></span>

<span data-ttu-id="21aeb-223">Todos os atendedores automáticos devem ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="21aeb-223">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="21aeb-224">Os atendedores automáticos de primeiro nível precisarão pelo menos uma conta de recurso que tenha um número de serviço associado.</span><span class="sxs-lookup"><span data-stu-id="21aeb-224">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="21aeb-225">Se quiser, você pode atribuir várias contas de recurso a um atendedor automático, cada uma com um número de serviço separado.</span><span class="sxs-lookup"><span data-stu-id="21aeb-225">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![Captura de tela da conta do recurso Adicionar painel de contas](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="21aeb-227">Para adicionar uma conta de recurso, clique em **adicionar conta** e procure a conta que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="21aeb-227">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="21aeb-228">Clique em **Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="21aeb-228">Click **Add**, and then click **Add**.</span></span>

![Captura de tela da lista conta de recurso mostrando a conta do recurso com número de serviço atribuído](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="21aeb-230">Quando terminar de adicionar contas de serviço, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="21aeb-230">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="21aeb-231">Isso conclui a configuração do atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="21aeb-231">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="21aeb-232">Transferências de número de telefone externo-detalhes técnicos</span><span class="sxs-lookup"><span data-stu-id="21aeb-232">External phone number transfers - technical details</span></span>

<span data-ttu-id="21aeb-233">Para permitir que atendedores automáticos Transfira chamadas externamente, consulte os [pré-requisitos](plan-auto-attendant-call-queue.md#prerequisites) para permitir que atendedores automáticos transfiram chamadas externamente.</span><span class="sxs-lookup"><span data-stu-id="21aeb-233">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="21aeb-234">Além disso:</span><span class="sxs-lookup"><span data-stu-id="21aeb-234">In addition:</span></span>

- <span data-ttu-id="21aeb-235">Para uma conta de recurso com um número de [plano de chamada](calling-plans-for-office-365.md) , o número de telefone de transferência externa deve ser inserido no formato E. 164 (+ [código do país] [código de área] [número de telefone]).</span><span class="sxs-lookup"><span data-stu-id="21aeb-235">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="21aeb-236">Para uma conta de recurso com um número de roteamento direto, o formato de número de telefone de transferência externa depende das configurações de [SBC (controlador de borda de sessão)](direct-routing-connect-the-sbc.md) .</span><span class="sxs-lookup"><span data-stu-id="21aeb-236">For a resource account with a Direct Routing number, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="21aeb-237">O número de telefone de saída exibido é determinado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="21aeb-237">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="21aeb-238">Para números de plano de chamada, o número de telefone do chamador original é exibido.</span><span class="sxs-lookup"><span data-stu-id="21aeb-238">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="21aeb-239">Para números de roteamento direto, o número enviado é baseado na configuração P-Assertd-Identity (PAI) no SBC, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="21aeb-239">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="21aeb-240">Se definido como Disabled, o número de telefone do chamador original será exibido.</span><span class="sxs-lookup"><span data-stu-id="21aeb-240">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="21aeb-241">Esta é a configuração padrão e recomendada.</span><span class="sxs-lookup"><span data-stu-id="21aeb-241">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="21aeb-242">Se definido como habilitado, o número de telefone da conta do recurso será exibido.</span><span class="sxs-lookup"><span data-stu-id="21aeb-242">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="21aeb-243">Em um ambiente híbrido do Skype for Business, para transferir uma chamada de atendedor automático para a PSTN, crie um novo usuário local com encaminhamento de chamadas definido para o número PSTN.</span><span class="sxs-lookup"><span data-stu-id="21aeb-243">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="21aeb-244">O usuário deve estar habilitado para o Enterprise Voice e ter uma política de voz atribuída.</span><span class="sxs-lookup"><span data-stu-id="21aeb-244">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="21aeb-245">Para saber mais, consulte [transferência de chamadas de atendedor automático para PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span><span class="sxs-lookup"><span data-stu-id="21aeb-245">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="21aeb-246">Criar um atendedor automático com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="21aeb-246">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="21aeb-247">Você também pode usar o PowerShell para criar e configurar atendedores automáticos.</span><span class="sxs-lookup"><span data-stu-id="21aeb-247">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="21aeb-248">Estes são os cmdlets necessários para gerenciar um atendedor automático:</span><span class="sxs-lookup"><span data-stu-id="21aeb-248">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="21aeb-249">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="21aeb-249">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="21aeb-250">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="21aeb-250">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="21aeb-251">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="21aeb-251">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="21aeb-252">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="21aeb-252">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="21aeb-253">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="21aeb-253">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="21aeb-254">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="21aeb-254">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="21aeb-255">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="21aeb-255">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="21aeb-256">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="21aeb-256">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="21aeb-257">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="21aeb-257">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="21aeb-258">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="21aeb-258">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="21aeb-259">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="21aeb-259">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="21aeb-260">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="21aeb-260">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="21aeb-261">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="21aeb-261">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="21aeb-262">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="21aeb-262">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="21aeb-263">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="21aeb-263">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="21aeb-264">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="21aeb-264">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="21aeb-265">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="21aeb-265">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="21aeb-266">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="21aeb-266">Related topics</span></span>

[<span data-ttu-id="21aeb-267">Veja o que você obtém com o Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="21aeb-267">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="21aeb-268">Obter números de telefone de serviço</span><span class="sxs-lookup"><span data-stu-id="21aeb-268">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="21aeb-269">Disponibilidade de audioconferência e Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="21aeb-269">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="21aeb-270">Exemplo de pequena empresa – configurar um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="21aeb-270">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

[<span data-ttu-id="21aeb-271">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="21aeb-271">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
