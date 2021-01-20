---
title: Configurar um atendedor automático para o Microsoft Teams-tutorial para empresas de pequeno porte
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
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
description: Saiba como configurar e testar atendedores automáticos do Microsoft 365 Business Voice.
ms.openlocfilehash: b3b291a91c96d75acdc8d4fe77f78790d2137914
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909599"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a><span data-ttu-id="ba395-103">Configurar um atendedor automático-tutorial para empresas de pequeno porte</span><span class="sxs-lookup"><span data-stu-id="ba395-103">Set up an auto attendant - small business tutorial</span></span>

<span data-ttu-id="ba395-104">Os atendedores automáticos permitem que as pessoas liguem para sua organização e naveguem em um sistema de menus para falar com o departamento certo, a fila de chamadas, a pessoa ou um operador.</span><span class="sxs-lookup"><span data-stu-id="ba395-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="ba395-105">Você pode criar atendedores automáticos para sua organização com o centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ba395-105">You can create auto attendants for your organization with the Microsoft Teams admin center.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="ba395-106">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="ba395-106">Before you begin</span></span>

<span data-ttu-id="ba395-107">Obtenha os números de serviço de que você precisa para os atendedores automáticos que você deseja que sejam acessíveis pela discagem direta de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="ba395-107">Get the service numbers that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="ba395-108">Isso pode incluir a [transferência de números de outro provedor](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou a [solicitação de novos números de serviço](../getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="ba395-108">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="ba395-109">Obter um [sistema telefônico-licença de usuário virtual](../teams-add-on-licensing/virtual-user.md) para cada atendedor automático que você planeja criar.</span><span class="sxs-lookup"><span data-stu-id="ba395-109">Get a [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md) for each auto attendant that you plan to create.</span></span> <span data-ttu-id="ba395-110">Essas licenças são gratuitas, portanto, sugerimos que você tenha alguns recursos adicionais para que você decida fazer alterações na sua configuração no futuro.</span><span class="sxs-lookup"><span data-stu-id="ba395-110">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="ba395-111">Se quiser que seu atendedor automático faça chamadas de forma diferente nos feriados, [crie os feriados que você deseja usar](../set-up-holidays-in-teams.md) antes de criar o atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="ba395-111">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="ba395-112">Siga estas etapas para configurar o atendedor automático</span><span class="sxs-lookup"><span data-stu-id="ba395-112">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="ba395-113">Número de telefone da etapa 1 <br></span><span class="sxs-lookup"><span data-stu-id="ba395-113">Step 1<br>Phone number</span></span>](#tab/phone-number)

<span data-ttu-id="ba395-114">Cada atendedor automático que você cria exige uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="ba395-114">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="ba395-115">Isso é semelhante a uma conta de usuário, exceto que a conta é associada a um atendedor automático ou fila de chamada em vez de uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="ba395-115">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="ba395-116">Nesta etapa, criaremos a conta, atribuímos a ela um *sistema telefônico Microsoft 365-licença de usuário virtual* e, em seguida, atribuímos um número de serviço.</span><span class="sxs-lookup"><span data-stu-id="ba395-116">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="ba395-117">Criar uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="ba395-117">Create a resource account</span></span>

<span data-ttu-id="ba395-118">Você pode criar uma conta de recurso no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ba395-118">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="ba395-119">No centro de administração do Teams, expanda **configurações de toda a organização** e clique em **contas de recursos**.</span><span class="sxs-lookup"><span data-stu-id="ba395-119">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="ba395-120">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ba395-120">Click **Add**.</span></span>

3. <span data-ttu-id="ba395-121">No painel **adicionar conta do recurso** , preencha o **nome para exibição**, o **nome de usuário** e escolha **atendedor automático** para o **tipo de conta de recurso**</span><span class="sxs-lookup"><span data-stu-id="ba395-121">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![Captura de tela da interface do usuário da conta adicionar recurso](../media/resource-account-add.png)

4. <span data-ttu-id="ba395-123">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ba395-123">Click **Save**.</span></span>

<span data-ttu-id="ba395-124">A nova conta será exibida na lista de contas.</span><span class="sxs-lookup"><span data-stu-id="ba395-124">The new account will appear in the list of accounts.</span></span>

![Captura de tela de uma lista de contas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="ba395-126">Atribuir uma licença</span><span class="sxs-lookup"><span data-stu-id="ba395-126">Assign a license</span></span>

<span data-ttu-id="ba395-127">Você deve atribuir um *sistema telefônico Microsoft 365-licença de usuário virtual* para a conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="ba395-127">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="ba395-128">No centro de administração do Microsoft 365, clique na conta de recurso à qual você deseja atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="ba395-128">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="ba395-129">Na guia **licenças e aplicativos** , em **licenças**, selecione **sistema telefônico Microsoft 365-usuário virtual**.</span><span class="sxs-lookup"><span data-stu-id="ba395-129">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="ba395-130">Clique em **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="ba395-130">Click **Save changes**.</span></span>

    ![Captura de tela da interface do usuário de atribuir licenças no centro de administração do Microsoft 365](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="ba395-132">Atribuir um número de serviço</span><span class="sxs-lookup"><span data-stu-id="ba395-132">Assign a service number</span></span>

<span data-ttu-id="ba395-133">Se você precisar que este atendedor automático seja alcançável por um número de telefone, atribua esse número à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="ba395-133">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="ba395-134">No centro de administração do Teams, na página **contas do recurso** , selecione a conta do recurso à qual você deseja atribuir um número de serviço e clique em **atribuir/Cancelar atribuição**.</span><span class="sxs-lookup"><span data-stu-id="ba395-134">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="ba395-135">Na lista suspensa **tipo de número de telefone** , escolha o tipo de número que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="ba395-135">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="ba395-136">Na caixa **número de telefone atribuído** , procure o número que deseja usar e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ba395-136">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![Captura de tela da interface de usuário atribuir número de serviço](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="ba395-138">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ba395-138">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ba395-139">Etapa 2-informações gerais sobre o atendedor automático ></span><span class="sxs-lookup"><span data-stu-id="ba395-139">Step 2 - Auto attendant general info ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="ba395-140"><br>Informações gerais do atendente da etapa 2</span><span class="sxs-lookup"><span data-stu-id="ba395-140">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="ba395-141">Para configurar um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="ba395-141">To set up an auto attendant</span></span>

1. <span data-ttu-id="ba395-142">No centro de administração do Teams, expanda **voz**, clique em **atendedores automáticos** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ba395-142">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="ba395-143">Digite um nome para o atendedor automático na caixa na parte superior.</span><span class="sxs-lookup"><span data-stu-id="ba395-143">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="ba395-144">Se você quiser designar um operador, especifique o destino para as chamadas para o operador.</span><span class="sxs-lookup"><span data-stu-id="ba395-144">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="ba395-145">Isso é opcional (mas recomendado).</span><span class="sxs-lookup"><span data-stu-id="ba395-145">This is optional (but recommended).</span></span> <span data-ttu-id="ba395-146">Você pode definir a opção de **operador** para permitir que os chamadores quebrem nos menus e falar com uma pessoa designada.</span><span class="sxs-lookup"><span data-stu-id="ba395-146">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="ba395-147">Especifique o fuso horário para este atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="ba395-147">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="ba395-148">O fuso horário é usado para calcular o horário comercial se você criar um fluxo de chamadas separado para o expediente.</span><span class="sxs-lookup"><span data-stu-id="ba395-148">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="ba395-149">Especifique um idioma para este atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="ba395-149">Specify a language for this auto attendant.</span></span> <span data-ttu-id="ba395-150">Esse é o idioma que será usado para solicitações de voz geradas pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="ba395-150">This the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="ba395-151">Escolha se deseja habilitar as entradas de voz.</span><span class="sxs-lookup"><span data-stu-id="ba395-151">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="ba395-152">Quando habilitado, o nome de cada opção de menu se torna uma palavra-chave de reconhecimento de fala.</span><span class="sxs-lookup"><span data-stu-id="ba395-152">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="ba395-153">Por exemplo, os chamadores podem dizer "um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "vendas" para selecionar a opção de menu chamada "vendas".</span><span class="sxs-lookup"><span data-stu-id="ba395-153">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![Captura de tela das configurações do atendedor automático para nome, operador, fuso horário, idioma e entradas de voz](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="ba395-155">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="ba395-155">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ba395-156">Etapa 3-fluxo de chamadas ></span><span class="sxs-lookup"><span data-stu-id="ba395-156">Step 3 - Call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="ba395-157">Fluxo de chamadas da etapa 3 <br></span><span class="sxs-lookup"><span data-stu-id="ba395-157">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="ba395-158">Escolha as opções de fluxo de chamadas</span><span class="sxs-lookup"><span data-stu-id="ba395-158">Choose your call flow options</span></span>

1. <span data-ttu-id="ba395-159">Escolha se deseja reproduzir uma saudação quando o atendedor automático atender a uma chamada.</span><span class="sxs-lookup"><span data-stu-id="ba395-159">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="ba395-160">Se você selecionar **executar um arquivo de áudio** , poderá usar o botão **carregar arquivo** para carregar uma mensagem de saudação gravada salva como áudio. WAV,. MP3 ou. Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="ba395-160">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="ba395-161">A gravação não pode ter mais de 5 MB.</span><span class="sxs-lookup"><span data-stu-id="ba395-161">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="ba395-162">Se você selecionar **digitar uma mensagem de saudação** , o sistema lerá o texto que você digitar (até 1000 caracteres) quando o atendedor automático atender a uma chamada.</span><span class="sxs-lookup"><span data-stu-id="ba395-162">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![Captura de tela das configurações da mensagem de saudação](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="ba395-164">Escolha como você deseja direcionar a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba395-164">Choose how you want to route the call.</span></span>

    <span data-ttu-id="ba395-165">Se você selecionar **Desconectar**, o atendedor automático irá desligar a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba395-165">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="ba395-166">Se você selecionar **redirecionar chamada**, poderá escolher um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="ba395-166">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="ba395-167">Se você selecionar **Opções do menu reproduzir**, poderá optar por **reproduzir um arquivo de áudio** ou **digitar uma mensagem de saudação** e escolher entre as opções do menu e a pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="ba395-167">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![Captura de tela das configurações de roteamento de chamadas](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="ba395-169">Se você quiser que os chamadores usem as teclas de discagem para navegar e, em seguida, em **definir opções do menu**, escolha o que você deseja que aconteça quando os chamadores pressionarem uma tecla de discagem.</span><span class="sxs-lookup"><span data-stu-id="ba395-169">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="ba395-170">(Se você estiver criando este atendedor automático como um diretório da empresa, deixe as opções da tecla de discagem em branco.)</span><span class="sxs-lookup"><span data-stu-id="ba395-170">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="ba395-171">Você pode definir qualquer uma das teclas de discagem para os seguintes destinos:</span><span class="sxs-lookup"><span data-stu-id="ba395-171">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="ba395-172">**Pessoa na organização** -uma pessoa em sua organização que pode receber chamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="ba395-172">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="ba395-173">**Aplicativo de voz** -outro atendedor automático ou uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="ba395-173">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="ba395-174">**Número de telefone externo** – qualquer número de telefone.</span><span class="sxs-lookup"><span data-stu-id="ba395-174">**External phone number** - any phone number.</span></span> <span data-ttu-id="ba395-175">Use este formato: + [código do país] [código de área] [número de telefone]</span><span class="sxs-lookup"><span data-stu-id="ba395-175">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="ba395-176">Correio **de voz-a** caixa de correio de voz associada a um grupo do Microsoft 365 que você especificar.</span><span class="sxs-lookup"><span data-stu-id="ba395-176">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="ba395-177">**Operator** – o operador definido para o atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="ba395-177">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="ba395-178">A definição de um operador é opcional.</span><span class="sxs-lookup"><span data-stu-id="ba395-178">Defining an operator is optional.</span></span> <span data-ttu-id="ba395-179">O operador pode ser definido como qualquer um dos outros destinos nesta lista.</span><span class="sxs-lookup"><span data-stu-id="ba395-179">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="ba395-180">Recomendamos configurar a tecla 0 para o operador.</span><span class="sxs-lookup"><span data-stu-id="ba395-180">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="ba395-181">Para cada opção de menu, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ba395-181">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="ba395-182">**Tecla de discagem** -a tecla no teclado do telefone para acessar esta opção.</span><span class="sxs-lookup"><span data-stu-id="ba395-182">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="ba395-183">**Comando de voz** -define o comando de voz que um chamador pode conceder para acessar essa opção, se as entradas de voz estiverem habilitadas.</span><span class="sxs-lookup"><span data-stu-id="ba395-183">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="ba395-184">Ele pode conter várias palavras como "atendimento ao cliente" ou "operações e aterramento".</span><span class="sxs-lookup"><span data-stu-id="ba395-184">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="ba395-185">**Redirecione para** -onde você deseja que a chamada se chame quando os chamadores escolherem esta opção.</span><span class="sxs-lookup"><span data-stu-id="ba395-185">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="ba395-186">Se você estiver redirecionando para um atendedor automático ou fila de chamadas, escolha a conta do recurso associada a ele.</span><span class="sxs-lookup"><span data-stu-id="ba395-186">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![Captura de tela das opções da tecla de discagem](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="ba395-188">Se você quiser usar esse atendedor automático como um diretório da empresa e, em **pesquisa de diretório**, selecione **discar por nome**.</span><span class="sxs-lookup"><span data-stu-id="ba395-188">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="ba395-189">Quando você habilita essa opção, os chamadores podem dizer o nome do usuário ou digitá-lo no teclado do telefone.</span><span class="sxs-lookup"><span data-stu-id="ba395-189">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="ba395-190">Qualquer usuário online com uma licença de sistema telefônico é um usuário elegível e pode ser encontrado com a discagem por nome.</span><span class="sxs-lookup"><span data-stu-id="ba395-190">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="ba395-191">(Você pode escolher a **extensão dial por**, no entanto, a extensão deve ser configurada no Azure Active Directory.)</span><span class="sxs-lookup"><span data-stu-id="ba395-191">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="ba395-192">Depois de selecionar uma opção de **pesquisa de diretório** , clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ba395-192">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ba395-193">Etapa 4-após horas de chamadas de fluxo de chamadas ></span><span class="sxs-lookup"><span data-stu-id="ba395-193">Step 4 - After hours call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="ba395-194">Etapa 4 <br> após horas</span><span class="sxs-lookup"><span data-stu-id="ba395-194">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="ba395-195">O horário comercial pode ser definido para cada atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="ba395-195">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="ba395-196">Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão.</span><span class="sxs-lookup"><span data-stu-id="ba395-196">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="ba395-197">O horário comercial pode ser definido com quebras de horário durante o dia, e todas as horas que não estão definidas como horário comercial são consideradas após o expediente.</span><span class="sxs-lookup"><span data-stu-id="ba395-197">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="ba395-198">Você pode definir diferentes opções de atendimento de chamadas e saudações por horas extras.</span><span class="sxs-lookup"><span data-stu-id="ba395-198">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="ba395-199">Dependendo de como você configurou seus atendedores automáticos e filas de chamadas, talvez você só precise especificar o roteamento de chamadas após a hora para atendedores automáticos com números de telefone diretos.</span><span class="sxs-lookup"><span data-stu-id="ba395-199">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="ba395-200">Se você quiser um encaminhamento de chamadas separado para chamadores após a hora e, em seguida, especifique o horário comercial para cada dia.</span><span class="sxs-lookup"><span data-stu-id="ba395-200">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="ba395-201">Clique em **Adicionar novo horário** para especificar vários conjuntos de horas para um determinado dia, por exemplo, para especificar um intervalo de almoço.</span><span class="sxs-lookup"><span data-stu-id="ba395-201">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![Captura de tela das configurações de horas e dia da hora](../media/auto-attendant-business-hours.png)

<span data-ttu-id="ba395-203">Depois de especificar o horário comercial, escolha as opções de roteamento de chamadas para o expediente.</span><span class="sxs-lookup"><span data-stu-id="ba395-203">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="ba395-204">As mesmas opções estão disponíveis para o encaminhamento de chamadas do horário comercial que você especificou na **etapa 3-fluxo de chamadas**.</span><span class="sxs-lookup"><span data-stu-id="ba395-204">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="ba395-205">Clique em **Avançar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="ba395-205">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ba395-206">Etapa 5->de fluxo de chamadas de feriados </span><span class="sxs-lookup"><span data-stu-id="ba395-206">Step 5 - Holiday call flow ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="ba395-207">Etapa 5 <br> feriados</span><span class="sxs-lookup"><span data-stu-id="ba395-207">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="ba395-208">Você pode fazer com que as chamadas para o atendedor automático sejam roteadas de forma diferente em feriados do que em outros dias.</span><span class="sxs-lookup"><span data-stu-id="ba395-208">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="ba395-209">(Se você não quiser ter um fluxo de chamadas diferente para feriados, pode ignorar esta etapa.)</span><span class="sxs-lookup"><span data-stu-id="ba395-209">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>



<span data-ttu-id="ba395-210">O atendedor automático pode ter um fluxo de chamadas para cada feriado que você configurou.</span><span class="sxs-lookup"><span data-stu-id="ba395-210">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="ba395-211">Você pode adicionar até 20 feriados agendados para cada atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="ba395-211">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="ba395-212">Na página de configurações de chamadas de Natal, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ba395-212">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="ba395-213">Digite um nome para esta configuração de feriado.</span><span class="sxs-lookup"><span data-stu-id="ba395-213">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="ba395-214">Na lista suspensa **feriado** , escolha o feriado que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="ba395-214">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="ba395-215">Escolha o tipo de saudação que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="ba395-215">Choose the type of greeting that you want to use.</span></span>

    ![Captura de tela das configurações de saudação de feriado e feriado](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="ba395-217">Escolha se deseja **Desconectar** ou **redirecionar** a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba395-217">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="ba395-218">Se você optou por redirecionar, escolha o destino de roteamento de chamadas para a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba395-218">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![Captura de tela das configurações de ação das chamadas de Natal](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="ba395-220">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ba395-220">Click **Save**.</span></span>

<span data-ttu-id="ba395-221">Repita o procedimento conforme necessário para cada feriado adicional.</span><span class="sxs-lookup"><span data-stu-id="ba395-221">Repeat the procedure as needed for each additional holiday.</span></span>

![Captura de tela das configurações de feriado com feriados listados](../media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="ba395-223">Depois de adicionar todos os seus feriados, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ba395-223">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ba395-224">Etapa 6-escolher quem está no diretório ></span><span class="sxs-lookup"><span data-stu-id="ba395-224">Step 6 - Choose who's in the directory ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="ba395-225">Etapa 6 <br> membros do diretório</span><span class="sxs-lookup"><span data-stu-id="ba395-225">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="ba395-226">O *escopo de discagem* define quais usuários estão disponíveis no diretório quando um chamador usa discar por nome ou discagem por extensão.</span><span class="sxs-lookup"><span data-stu-id="ba395-226">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="ba395-227">O padrão de **todos os usuários online** inclui todos os usuários de sua organização que são usuários online com uma licença de sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="ba395-227">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="ba395-228">Você pode incluir ou excluir usuários específicos selecionando **grupo de usuários personalizado** em **incluir** ou **excluir** e escolhendo um ou mais grupos do Microsoft 365, listas de distribuição ou grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="ba395-228">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="ba395-229">Por exemplo, talvez você queira excluir executivos de sua organização do diretório de discagem.</span><span class="sxs-lookup"><span data-stu-id="ba395-229">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="ba395-230">(Se um usuário estiver em ambas as listas, eles serão excluídos do diretório.)</span><span class="sxs-lookup"><span data-stu-id="ba395-230">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![Captura de tela das opções incluir e excluir do escopo de discagem](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="ba395-232">Pode levar até 36 horas para que um novo usuário tenha o nome listado no diretório.</span><span class="sxs-lookup"><span data-stu-id="ba395-232">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="ba395-233">Quando terminar de configurar o escopo de discagem, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ba395-233">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ba395-234">Etapa 7-atribuir uma conta de recurso ></span><span class="sxs-lookup"><span data-stu-id="ba395-234">Step 7 - Assign a resource account ></span></span>](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?branch=mikeplum-smb-voice&tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="ba395-235">Etapa 7 <br> contas de recursos</span><span class="sxs-lookup"><span data-stu-id="ba395-235">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="ba395-236">Todos os atendedores automáticos devem ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="ba395-236">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="ba395-237">Os atendedores automáticos de primeiro nível precisarão pelo menos uma conta de recurso que tenha um número de serviço associado.</span><span class="sxs-lookup"><span data-stu-id="ba395-237">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="ba395-238">Se quiser, você pode atribuir várias contas de recurso a um atendedor automático, cada uma com um número de serviço separado.</span><span class="sxs-lookup"><span data-stu-id="ba395-238">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="ba395-239">Para adicionar uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="ba395-239">To add a resource account</span></span>

1. <span data-ttu-id="ba395-240">Clique em **adicionar conta** e procure a conta que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="ba395-240">Click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="ba395-241">Clique em **Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ba395-241">Click **Add**, and then click **Add**.</span></span>

    ![Captura de tela da conta do recurso Adicionar painel de contas](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="ba395-243">Quando terminar de adicionar contas de serviço, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="ba395-243">When you have finished adding service accounts, click **Submit**.</span></span>

    ![Captura de tela da lista conta de recurso mostrando a conta do recurso com número de serviço atribuído](../media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="ba395-245">Isso conclui a configuração do atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="ba395-245">This completes the auto attendant configuration.</span></span>

---


