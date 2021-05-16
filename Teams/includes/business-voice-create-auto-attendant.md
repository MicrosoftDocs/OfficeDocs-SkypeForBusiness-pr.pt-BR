#### <a name="video-demonstration"></a><span data-ttu-id="60032-101">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="60032-101">Video demonstration</span></span>

<span data-ttu-id="60032-102">Este vídeo mostra um exemplo básico de como criar um assistente automático no Teams.</span><span class="sxs-lookup"><span data-stu-id="60032-102">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="60032-103">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="60032-103">Before you begin</span></span>

<span data-ttu-id="60032-104">Obter os números de serviço (números de serviço são um tipo especial de número de telefone que são usados por atendentes automáticos) que você precisa para os atendimentos automáticos que você deseja que sejam acessíveis discando diretamente de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="60032-104">Get the service numbers (service numbers are a special type of phone number that are used by auto attendants) that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="60032-105">Isso pode incluir [a transferência de números de outro provedor ou](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) a [solicitação de novos números de serviço.](../getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="60032-105">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="60032-106">Cada atendente automático precisa ter uma licença Sistema de Telefonia - Usuário Virtual.</span><span class="sxs-lookup"><span data-stu-id="60032-106">Each auto attendant needs to be assigned a Phone System - Virtual User license.</span></span> <span data-ttu-id="60032-107">Ao comprar o Business Voice, você também recebeu várias Sistema de Telefonia - Licenças de usuário virtual, portanto, provavelmente não é necessário solicitar mais.</span><span class="sxs-lookup"><span data-stu-id="60032-107">When you purchased Business Voice, you also received a number of Phone System - Virtual User licenses, so you probably don't need to request more.</span></span> <span data-ttu-id="60032-108">No entanto, se você precisar de mais no futuro, poderá obter seguindo as instruções em [Sistema de Telefonia - Licença de usuário virtual](../teams-add-on-licensing/virtual-user.md).</span><span class="sxs-lookup"><span data-stu-id="60032-108">However, if you need more in the future, you can get them by following the instructions in [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="60032-109">Se você quiser que sua rota de atendimento automático seja chamada de forma diferente nos [feriados,](../set-up-holidays-in-teams.md) crie os feriados que deseja usar antes de criar o atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="60032-109">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="60032-110">Siga estas etapas para configurar o seu assistente automático</span><span class="sxs-lookup"><span data-stu-id="60032-110">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="60032-111">Etapa 1 <br> Telefone número</span><span class="sxs-lookup"><span data-stu-id="60032-111">Step 1<br>Phone number</span></span>](#tab/phone-number)

> [!NOTE]
> <span data-ttu-id="60032-112">Se você estiver seguindo as etapas para configurar o Business Voice pela primeira vez e estiver na Etapa **6:** Configurar um atendente automático para o número de telefone principal da sua empresa, você já concluiu as etapas nesta guia. Vá para a próxima guia: [Informações gerais do atendimento automático.](?tabs=general-info#steps)</span><span class="sxs-lookup"><span data-stu-id="60032-112">If you're following the steps to set up Business Voice for the first time and you're on **Step 6: Set up an auto attendant for your company's main phone number**, you've already finished the steps on this tab. Move to the next tab: [Auto attendant general info](?tabs=general-info#steps).</span></span>

<span data-ttu-id="60032-113">Cada atendimento automático criado requer uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="60032-113">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="60032-114">Isso é semelhante a uma conta de usuário, exceto que a conta está associada a um atendimento automático ou fila de chamada em vez de uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="60032-114">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="60032-115">Nesta etapa, criaremos a conta, atribuiremos uma Microsoft 365 Sistema de Telefonia *- licença* de usuário virtual e atribuiremos um número de serviço.</span><span class="sxs-lookup"><span data-stu-id="60032-115">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="60032-116">Criar uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="60032-116">Create a resource account</span></span>

<span data-ttu-id="60032-117">Você pode criar uma conta de recurso no Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="60032-117">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="60032-118">No centro Teams de administração, expanda **as** configurações de toda a organização e clique em **Contas de recursos.**</span><span class="sxs-lookup"><span data-stu-id="60032-118">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="60032-119">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="60032-119">Click **Add**.</span></span>

3. <span data-ttu-id="60032-120">No painel **Adicionar conta de** recurso, preencha **Nome** de exibição , Nome de **usuário** e escolha **Atendimento** automático para o tipo de conta **de recurso**</span><span class="sxs-lookup"><span data-stu-id="60032-120">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![Captura de tela da interface do usuário adicionar conta de recurso](../media/resource-account-add.png)

4. <span data-ttu-id="60032-122">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="60032-122">Click **Save**.</span></span>

    <span data-ttu-id="60032-123">A nova conta aparecerá na lista de contas.</span><span class="sxs-lookup"><span data-stu-id="60032-123">The new account will appear in the list of accounts.</span></span>

    ![Captura de tela de uma lista de contas de recursos](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="60032-125">Atribuir uma licença</span><span class="sxs-lookup"><span data-stu-id="60032-125">Assign a license</span></span>

<span data-ttu-id="60032-126">Você deve atribuir uma *Microsoft 365 Sistema de Telefonia - Licença de usuário virtual* à conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="60032-126">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="60032-127">No centro Microsoft 365 de administração, clique na conta de recurso à qual você deseja atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="60032-127">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="60032-128">Na guia **Licenças e Aplicativos,** em **Licenças,** selecione **Microsoft 365 Sistema de Telefonia - Usuário Virtual**.</span><span class="sxs-lookup"><span data-stu-id="60032-128">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="60032-129">Clique **em Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="60032-129">Click **Save changes**.</span></span>

    ![Captura de tela da interface do usuário atribuir licenças no Microsoft 365 de administração](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="60032-131">Atribuir um número de serviço</span><span class="sxs-lookup"><span data-stu-id="60032-131">Assign a service number</span></span>

<span data-ttu-id="60032-132">Se você precisar que esse atendimento automático seja acessível por um número de telefone, atribua esse número à conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="60032-132">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="60032-133">No centro Teams de administração,  na página Contas de recursos, selecione a conta de recurso à qual você deseja atribuir um número de serviço e clique em **Atribuir/desatribuição.**</span><span class="sxs-lookup"><span data-stu-id="60032-133">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="60032-134">Na lista Telefone de tipo **de** número, escolha o tipo de número que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="60032-134">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="60032-135">Na caixa **Número de telefone atribuído,** pesquise o número que deseja usar e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="60032-135">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![Captura de tela da interface do usuário atribuir número de serviço](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="60032-137">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="60032-137">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="60032-138">Etapa 2 - Informações gerais do atendimento automático ></span><span class="sxs-lookup"><span data-stu-id="60032-138">Step 2 - Auto attendant general info ></span></span>](?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="60032-139">Etapa 2 <br> Informações gerais do atendente</span><span class="sxs-lookup"><span data-stu-id="60032-139">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="60032-140">Para configurar um atendimento automático</span><span class="sxs-lookup"><span data-stu-id="60032-140">To set up an auto attendant</span></span>

1. <span data-ttu-id="60032-141">No centro Teams de administração, **expanda Voz,** clique em **Assistentes automáticos** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="60032-141">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="60032-142">Digite um nome para o atendimento automático na caixa na parte superior.</span><span class="sxs-lookup"><span data-stu-id="60032-142">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="60032-143">Se você quiser designar um operador, especifique o destino das chamadas para o operador.</span><span class="sxs-lookup"><span data-stu-id="60032-143">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="60032-144">Isso é opcional (mas recomendado).</span><span class="sxs-lookup"><span data-stu-id="60032-144">This is optional (but recommended).</span></span> <span data-ttu-id="60032-145">Você pode definir a **opção Operador** para permitir que os chamadores possam sair dos menus e falar com uma pessoa designada.</span><span class="sxs-lookup"><span data-stu-id="60032-145">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="60032-146">Especifique o fuso horário desse atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="60032-146">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="60032-147">O fuso horário é usado para calcular o horário comercial se você criar um fluxo de chamada separado para depois do horário.</span><span class="sxs-lookup"><span data-stu-id="60032-147">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="60032-148">Especifique um idioma para esse atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="60032-148">Specify a language for this auto attendant.</span></span> <span data-ttu-id="60032-149">Esse é o idioma que será usado para prompts de voz gerados pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="60032-149">This is the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="60032-150">Escolha se deseja habilitar entradas de voz.</span><span class="sxs-lookup"><span data-stu-id="60032-150">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="60032-151">Quando habilitada, o nome de cada opção de menu se torna uma palavra-chave de reconhecimento de fala.</span><span class="sxs-lookup"><span data-stu-id="60032-151">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="60032-152">Por exemplo, os chamadores podem dizer "Um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "Vendas" para selecionar a opção de menu chamada "Vendas".</span><span class="sxs-lookup"><span data-stu-id="60032-152">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![Captura de tela das configurações de atendimento automático para nome, operador, fuso horário, idioma e entradas de voz](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="60032-154">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="60032-154">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="60032-155">Etapa 3 - Fluxo de chamada ></span><span class="sxs-lookup"><span data-stu-id="60032-155">Step 3 - Call flow ></span></span>](?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="60032-156">Etapa 3 <br> Fluxo de chamada</span><span class="sxs-lookup"><span data-stu-id="60032-156">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="60032-157">Escolha suas opções de fluxo de chamada</span><span class="sxs-lookup"><span data-stu-id="60032-157">Choose your call flow options</span></span>

1. <span data-ttu-id="60032-158">Escolha se deseja reproduzir uma saudação quando o atendente automático atender uma chamada.</span><span class="sxs-lookup"><span data-stu-id="60032-158">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="60032-159">Se você selecionar **Reproduzir um arquivo de** áudio, poderá usar o botão de arquivo **Upload** para carregar uma mensagem de saudação gravada salva como áudio em . WAV, .MP3 ou . Formato WMA.</span><span class="sxs-lookup"><span data-stu-id="60032-159">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="60032-160">A gravação não pode ser maior do que 5 MB.</span><span class="sxs-lookup"><span data-stu-id="60032-160">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="60032-161">Se você selecionar **Digitar uma** mensagem de saudação, o sistema lerá o texto que você digitará (até 1000 caracteres) quando o atendemento automático atender a uma chamada.</span><span class="sxs-lookup"><span data-stu-id="60032-161">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![Captura de tela das configurações da mensagem de saudação](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="60032-163">Escolha como você deseja rotear a chamada.</span><span class="sxs-lookup"><span data-stu-id="60032-163">Choose how you want to route the call.</span></span>

    <span data-ttu-id="60032-164">Se você selecionar **Desconectar,** o atendimento automático desligará a chamada.</span><span class="sxs-lookup"><span data-stu-id="60032-164">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="60032-165">Se você selecionar **Redirecionar chamada,** poderá escolher um dos destinos de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="60032-165">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="60032-166">Se você selecionar Opções de menu  Reproduzir, poderá  optar por Reproduzir um arquivo de áudio ou Digitar uma mensagem de saudação e escolher entre opções de **menu** e pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="60032-166">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![Captura de tela das configurações de roteamento de chamadas](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="60032-168">Se você quiser que os chamadores usem teclas de discagem para navegar, em Definir opções de **menu,** escolha o que você deseja que aconteça quando os chamadores pressionarem uma tecla de discagem.</span><span class="sxs-lookup"><span data-stu-id="60032-168">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="60032-169">(Se você estiver criando esse atendimento automático como um diretório da empresa, deixe as opções da chave de discagem em branco.)</span><span class="sxs-lookup"><span data-stu-id="60032-169">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="60032-170">Você pode definir qualquer uma das teclas de discagem para os seguintes destinos:</span><span class="sxs-lookup"><span data-stu-id="60032-170">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="60032-171">**Pessoa na organização** - uma pessoa em sua organização que é capaz de receber chamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="60032-171">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="60032-172">**Aplicativo de voz** - outro atendimento automático ou uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="60032-172">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="60032-173">**Número de telefone externo** - qualquer número de telefone.</span><span class="sxs-lookup"><span data-stu-id="60032-173">**External phone number** - any phone number.</span></span> <span data-ttu-id="60032-174">Use este formato: +[código do país][código de área][número de telefone]</span><span class="sxs-lookup"><span data-stu-id="60032-174">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="60032-175">**Caixa** postal - a caixa de correio de voz associada a um grupo Microsoft 365 que você especificar.</span><span class="sxs-lookup"><span data-stu-id="60032-175">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="60032-176">**Operador** - o operador definido para o atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="60032-176">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="60032-177">Definir um operador é opcional.</span><span class="sxs-lookup"><span data-stu-id="60032-177">Defining an operator is optional.</span></span> <span data-ttu-id="60032-178">O operador pode ser definido como qualquer um dos outros destinos nesta lista.</span><span class="sxs-lookup"><span data-stu-id="60032-178">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="60032-179">Recomendamos a configuração de 0 tecla para o operador.</span><span class="sxs-lookup"><span data-stu-id="60032-179">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="60032-180">Para cada opção de menu, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="60032-180">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="60032-181">**Tecla de** discagem - a chave no teclado do telefone para acessar essa opção.</span><span class="sxs-lookup"><span data-stu-id="60032-181">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="60032-182">**Comando de** voz - define o comando de voz que um chamador pode dar para acessar essa opção, se as entradas de voz estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="60032-182">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="60032-183">Ele pode conter várias palavras como "Atendimento ao Cliente" ou "Operações e Motivos".</span><span class="sxs-lookup"><span data-stu-id="60032-183">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="60032-184">**Redirecionar** para onde você deseja que a chamada vá quando os chamadores escolherem essa opção.</span><span class="sxs-lookup"><span data-stu-id="60032-184">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="60032-185">Se você estiver redirecionando para um atendimento automático ou fila de chamada, escolha a conta de recurso associada a ela.</span><span class="sxs-lookup"><span data-stu-id="60032-185">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![Captura de tela das opções de teclas de discagem](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="60032-187">Se você quiser usar esse assistente automático como diretório da empresa, em **Pesquisa de** diretório, selecione **Discar por nome**.</span><span class="sxs-lookup"><span data-stu-id="60032-187">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="60032-188">Quando você habilita essa opção, os chamadores podem dizer o nome do usuário ou digitá-lo no teclado do telefone.</span><span class="sxs-lookup"><span data-stu-id="60032-188">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="60032-189">Qualquer usuário online com uma Sistema de Telefonia é um usuário qualificado e pode ser encontrado com Dial pelo nome.</span><span class="sxs-lookup"><span data-stu-id="60032-189">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="60032-190">(Você pode escolher **Discar por extensão**, no entanto, a extensão deve ser configurada em Azure Active Directory.)</span><span class="sxs-lookup"><span data-stu-id="60032-190">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="60032-191">Depois de selecionar uma opção **de pesquisa de diretório,** clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="60032-191">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="60032-192">Etapa 4 - Fluxo de chamada após o horário ></span><span class="sxs-lookup"><span data-stu-id="60032-192">Step 4 - After hours call flow ></span></span>](?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="60032-193">Etapa 4 <br> Após horas</span><span class="sxs-lookup"><span data-stu-id="60032-193">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="60032-194">O horário comercial pode ser definido para cada atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="60032-194">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="60032-195">Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão.</span><span class="sxs-lookup"><span data-stu-id="60032-195">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="60032-196">O horário comercial pode ser definido com pausas no tempo durante o dia e todas as horas que não estão definidas como horário comercial são consideradas após o horário.</span><span class="sxs-lookup"><span data-stu-id="60032-196">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="60032-197">Você pode definir diferentes opções de tratamento de chamadas de entrada e saudações para o pós-horário.</span><span class="sxs-lookup"><span data-stu-id="60032-197">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="60032-198">Dependendo de como você configurou seus atendimentos automáticos e filas de chamadas, talvez seja necessário especificar apenas o roteamento de chamadas após o horário para os atendimentos automáticos com números de telefone diretos.</span><span class="sxs-lookup"><span data-stu-id="60032-198">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="60032-199">Se você quiser roteamento de chamadas separado para chamadores após o horário, especifique seu horário comercial para cada dia.</span><span class="sxs-lookup"><span data-stu-id="60032-199">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="60032-200">Clique **em Adicionar novo horário** para especificar vários conjuntos de horas para um determinado dia, por exemplo, para especificar uma pausa de almoço.</span><span class="sxs-lookup"><span data-stu-id="60032-200">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![Captura de tela das configurações de dia e hora após o expediente](../media/auto-attendant-business-hours.png)

<span data-ttu-id="60032-202">Depois de especificar seu horário comercial, escolha suas opções de roteamento de chamadas para o horário de expediente.</span><span class="sxs-lookup"><span data-stu-id="60032-202">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="60032-203">As mesmas opções estão disponíveis para o roteamento de chamadas de horário comercial especificado na **Etapa 3 - Fluxo de chamadas.**</span><span class="sxs-lookup"><span data-stu-id="60032-203">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="60032-204">Clique **em Próximo** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="60032-204">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="60032-205">Etapa 5 - Fluxo de chamada de feriado ></span><span class="sxs-lookup"><span data-stu-id="60032-205">Step 5 - Holiday call flow ></span></span>](?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="60032-206">Etapa 5 <br> Feriados</span><span class="sxs-lookup"><span data-stu-id="60032-206">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="60032-207">Você pode ter chamadas para o seu atendimento automático roteados de forma diferente em feriados do que em outros dias.</span><span class="sxs-lookup"><span data-stu-id="60032-207">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="60032-208">(Se você não quiser ter um fluxo de chamada diferente para feriados, ignore esta etapa.)</span><span class="sxs-lookup"><span data-stu-id="60032-208">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>

<span data-ttu-id="60032-209">O seu atendente automático pode ter um fluxo de chamada para cada feriado que você definiu.</span><span class="sxs-lookup"><span data-stu-id="60032-209">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="60032-210">Você pode adicionar até 20 feriados agendados para cada atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="60032-210">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="60032-211">Na página Configurações de chamada de feriado, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="60032-211">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="60032-212">Digite um nome para essa configuração de feriado.</span><span class="sxs-lookup"><span data-stu-id="60032-212">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="60032-213">No menu **suspenso Feriado,** escolha o feriado que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="60032-213">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="60032-214">Escolha o tipo de saudação que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="60032-214">Choose the type of greeting that you want to use.</span></span>

    ![Captura de tela das configurações de saudação de feriados e feriados](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="60032-216">Escolha se deseja **desconectar ou** **redirecionar** a chamada.</span><span class="sxs-lookup"><span data-stu-id="60032-216">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="60032-217">Se você optou por redirecionar, escolha o destino de roteamento de chamadas para a chamada.</span><span class="sxs-lookup"><span data-stu-id="60032-217">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![Captura de tela das configurações de ação de chamada de feriado](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="60032-219">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="60032-219">Click **Save**.</span></span>

    <span data-ttu-id="60032-220">Repita o procedimento conforme necessário para cada feriado adicional.</span><span class="sxs-lookup"><span data-stu-id="60032-220">Repeat the procedure as needed for each additional holiday.</span></span>

    ![Captura de tela das configurações de feriados com feriados listados](../media/auto-attendant-holiday-call-settings.png)

    <span data-ttu-id="60032-222">Quando você adicionou todos os feriados, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="60032-222">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="60032-223">Etapa 6 - Escolher quem está no diretório ></span><span class="sxs-lookup"><span data-stu-id="60032-223">Step 6 - Choose who's in the directory ></span></span>](?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="60032-224">Membros do Diretório etapa 6 <br></span><span class="sxs-lookup"><span data-stu-id="60032-224">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="60032-225">O *escopo de* discagem define quais usuários estão disponíveis no diretório quando um chamador usa discagem por nome ou discagem por extensão.</span><span class="sxs-lookup"><span data-stu-id="60032-225">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="60032-226">O padrão de **Todos os usuários online** inclui todos os usuários em sua organização que são usuários online com uma Sistema de Telefonia de usuário.</span><span class="sxs-lookup"><span data-stu-id="60032-226">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="60032-227">Você pode incluir ou excluir  usuários específicos  selecionando Grupo de usuários personalizado em **Incluir** ou Excluir e escolher um ou mais grupos de Microsoft 365, listas de distribuição ou grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="60032-227">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="60032-228">Por exemplo, talvez você queira excluir executivos em sua organização do diretório de discagem.</span><span class="sxs-lookup"><span data-stu-id="60032-228">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="60032-229">(Se um usuário estiver em ambas as listas, ele será excluído do diretório.)</span><span class="sxs-lookup"><span data-stu-id="60032-229">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![Captura de tela do escopo de discagem incluem e excluem opções](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="60032-231">Pode levar até 36 horas para que um novo usuário tenha seu nome listado no diretório.</span><span class="sxs-lookup"><span data-stu-id="60032-231">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="60032-232">Quando terminar de definir o escopo de discagem, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="60032-232">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="60032-233">Etapa 7 - Atribuir uma conta de recurso ></span><span class="sxs-lookup"><span data-stu-id="60032-233">Step 7 - Assign a resource account ></span></span>](?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="60032-234">Etapa 7 <br> Contas de recursos</span><span class="sxs-lookup"><span data-stu-id="60032-234">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="60032-235">Todos os atendentes automáticos devem ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="60032-235">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="60032-236">Os atendentes automáticos de primeiro nível precisarão de pelo menos uma conta de recurso que tenha um número de serviço associado.</span><span class="sxs-lookup"><span data-stu-id="60032-236">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="60032-237">Se desejar, você pode atribuir várias contas de recurso a um atendimento automático, cada uma com um número de serviço separado.</span><span class="sxs-lookup"><span data-stu-id="60032-237">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="60032-238">Para adicionar uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="60032-238">To add a resource account</span></span>

1. <span data-ttu-id="60032-239">Clique **em Adicionar** e pesquisar a conta que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="60032-239">Click **Add** and search for the account that you want to add.</span></span> <span data-ttu-id="60032-240">Clique **em Adicionar** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="60032-240">Click **Add**, and then click **Add**.</span></span>

    ![Captura de tela do painel adicionar contas de conta de recurso](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="60032-242">Quando terminar de adicionar contas de serviço, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="60032-242">When you have finished adding service accounts, click **Submit**.</span></span>

    ![Captura de tela da lista de contas de recursos mostrando a conta de recurso com o número de serviço atribuído](../media/auto-attendant-resource-account-assigned.png)

    <span data-ttu-id="60032-244">Isso conclui a configuração do atendimento automático.</span><span class="sxs-lookup"><span data-stu-id="60032-244">This completes the auto attendant configuration.</span></span>

---
