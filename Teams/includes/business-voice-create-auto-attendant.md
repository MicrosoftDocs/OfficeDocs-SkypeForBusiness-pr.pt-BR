#### <a name="video-demonstration"></a>Demonstração de vídeo

Este vídeo mostra um exemplo básico de como criar um assistente automático no Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

#### <a name="before-you-begin"></a>Antes de você começar

Obter os números de serviço (números de serviço são um tipo especial de número de telefone que são usados por atendentes automáticos) que você precisa para os atendimentos automáticos que você deseja que sejam acessíveis discando diretamente de fora da sua organização. Isso pode incluir [a transferência de números de outro provedor ou](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) a [solicitação de novos números de serviço.](../getting-service-phone-numbers.md)

Cada atendente automático precisa ter uma licença Sistema de Telefonia - Usuário Virtual. Quando você comprou Teams Telefone com o Plano de Chamada, também recebeu várias Sistema de Telefonia - Licenças de usuário virtual, portanto, provavelmente não é necessário solicitar mais. No entanto, se você precisar de mais no futuro, poderá obter seguindo as instruções em [Sistema de Telefonia - Licença de usuário virtual](../teams-add-on-licensing/virtual-user.md).

Se você quiser que sua rota de atendimento automático seja chamada de forma diferente nos [feriados,](../set-up-holidays-in-teams.md) crie os feriados que deseja usar antes de criar o atendimento automático.

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Siga estas etapas para configurar o seu assistente automático

# <a name="step-1brphone-number"></a>[Etapa 1 <br> Telefone número](#tab/phone-number)

> [!NOTE]
> Se você estiver seguindo as etapas para configurar o Teams Telefone com o Plano de Chamadas pela primeira vez e estiver na Etapa **6:** Configurar um atendimento automático para o número de telefone principal da sua empresa, você já concluiu as etapas nesta guia. Vá para a próxima guia: [Informações](?tabs=general-info#steps)gerais do atendimento automático.

Cada atendimento automático criado requer uma conta de recurso. Isso é semelhante a uma conta de usuário, exceto que a conta está associada a um atendimento automático ou fila de chamada em vez de uma pessoa. Nesta etapa, criaremos a conta, atribuiremos uma Microsoft 365 Sistema de Telefonia *- licença* de usuário virtual e atribuiremos um número de serviço.

### <a name="create-a-resource-account"></a>Criar uma conta de recurso

Você pode criar uma conta de recurso no Teams de administração.

1. No centro Teams de administração, expanda **as** configurações de toda a organização e clique em **Contas de recursos.**

2. Clique em **Adicionar**.

3. No painel **Adicionar conta de** recurso, preencha **Nome** de exibição , Nome de **usuário** e escolha **Atendimento** automático para o tipo de conta **de recurso**

4. Clique em **Salvar**.

    A nova conta aparecerá na lista de contas.

### <a name="assign-a-license"></a>Atribuir uma licença

Você deve atribuir uma *Microsoft 365 Sistema de Telefonia - Licença de usuário virtual* à conta de recurso.

1. Na Centro de administração do Microsoft 365, clique na conta de recurso à qual deseja atribuir uma licença.

2. Na guia **Licenças e Aplicativos,** em **Licenças,** selecione **Microsoft 365 Sistema de Telefonia - Usuário Virtual**.

3. Clique em **Salvar alterações**.

### <a name="assign-a-service-number"></a>Atribuir um número de serviço

Se você precisar que esse atendimento automático seja acessível por um número de telefone, atribua esse número à conta de recurso.

1. No centro Teams de administração,  na página Contas de recursos, selecione a conta de recurso à qual você deseja atribuir um número de serviço e clique em **Atribuir/desatribuição.**

2. Na lista Telefone de tipo **de** número, escolha o tipo de número que você deseja usar.

3. Na caixa **Número de telefone atribuído,** pesquise o número que deseja usar e clique em **Adicionar**.

4. Clique em **Salvar**.

> [!div class="nextstepaction"]
> [Etapa 2 - Informações gerais do atendimento automático >](?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[Etapa 2 <br> Informações gerais do atendente](#tab/general-info)

Para configurar um atendimento automático

1. No centro Teams de administração, **expanda Voz,** clique em **Assistentes automáticos** e clique em **Adicionar**.

2. Digite um nome para o atendimento automático na caixa na parte superior.

3. Se você quiser designar um operador, especifique o destino das chamadas para o operador. Isso é opcional (mas recomendado). Você pode definir a **opção Operador** para permitir que os chamadores possam sair dos menus e falar com uma pessoa designada.

4. Especifique o fuso horário desse atendimento automático. O fuso horário é usado para calcular o horário comercial se você criar um fluxo de chamada separado para depois do horário.

5. [Especifique um idioma com suporte](../create-a-phone-system-auto-attendant-languages.md) para esse atendimento automático. Esse é o idioma que será usado para prompts de voz gerados pelo sistema.

6. Escolha se deseja habilitar entradas de voz. Quando habilitada, o nome de cada opção de menu se torna uma palavra-chave de reconhecimento de fala. Por exemplo, os chamadores podem dizer "Um" para selecionar a opção de menu mapeada para a tecla 1 ou podem dizer "Vendas" para selecionar a opção de menu chamada "Vendas".

7. Click **Next**.

> [!div class="nextstepaction"]
> [Etapa 3 - Fluxo de chamada >](?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[Etapa 3 <br> Fluxo de chamada](#tab/call-flow)

Escolha suas opções de fluxo de chamada

1. Escolha se deseja reproduzir uma saudação quando o atendente automático atender uma chamada.

    Se você selecionar **Reproduzir um arquivo de** áudio, poderá usar o botão de arquivo **Upload** para carregar uma mensagem de saudação gravada salva como áudio em . WAV, .MP3 ou . Formato WMA. A gravação não pode ser maior do que 5 MB.

    Se você selecionar **Digitar uma** mensagem de saudação, o sistema lerá o texto que você digitará (até 1000 caracteres) quando o atendemento automático atender a uma chamada.

2. Escolha como você deseja rotear a chamada.

    Se você selecionar **Desconectar,** o atendimento automático desligará a chamada.

    Se você selecionar **Redirecionar chamada,** poderá escolher um dos destinos de roteamento de chamadas.

    Se você selecionar Opções de menu  Reproduzir, poderá  optar por Reproduzir um arquivo de áudio ou Digitar uma mensagem de saudação e escolher entre opções de **menu** e pesquisa de diretório.

3. Se você quiser que os chamadores usem teclas de discagem para navegar, em Definir opções de **menu,** escolha o que você deseja que aconteça quando os chamadores pressionarem uma tecla de discagem. (Se você estiver criando esse atendimento automático como um diretório da empresa, deixe as opções da chave de discagem em branco.)

    Você pode definir qualquer uma das teclas de discagem para os seguintes destinos:

    - **Pessoa na organização** - uma pessoa em sua organização que é capaz de receber chamadas de voz.
    - **Aplicativo de voz** - outro atendimento automático ou uma fila de chamadas.
    - **Número de telefone externo** - qualquer número de telefone. Use este formato: +[código do país][código de área][número de telefone]
    - **Caixa** postal - a caixa de correio de voz associada a um grupo Microsoft 365 que você especificar. Você pode escolher se deseja transcrições de caixa postal e o "Por favor, deixe uma mensagem após o tom". prompt do sistema.
    - **Operador** - o operador definido para o atendimento automático. Definir um operador é opcional. O operador pode ser definido como qualquer um dos outros destinos nesta lista.

    Recomendamos a configuração de 0 tecla para o operador.

    Para cada opção de menu, especifique o seguinte:

    - **Tecla de** discagem - a chave no teclado do telefone para acessar essa opção.

    - **Comando de** voz - define o comando de voz que um chamador pode dar para acessar essa opção, se as entradas de voz estão habilitadas. Ele pode conter várias palavras como "Atendimento ao Cliente" ou "Operações e Motivos". 

    - **Redirecionar** para onde você deseja que a chamada vá quando os chamadores escolherem essa opção. Se você estiver redirecionando para um atendimento automático ou fila de chamada, escolha a conta de recurso associada a ela.

4. Se você quiser usar esse assistente automático como diretório da empresa, em **Pesquisa de** diretório, selecione **Discar por nome**. Quando você habilita essa opção, os chamadores podem dizer o nome do usuário ou digitá-lo no teclado do telefone. Qualquer usuário online com uma Sistema de Telefonia é um usuário qualificado e pode ser encontrado com Dial pelo nome.

    (Você pode escolher **Discar por extensão**, no entanto, a extensão deve ser configurada em Azure Active Directory.)

5. Depois de selecionar uma opção **de pesquisa de diretório,** clique em **Próximo**.

> [!div class="nextstepaction"]
> [Etapa 4 - Fluxo de chamada após o horário >](?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[Etapa 4 <br> Após horas](#tab/after-hours)

O horário comercial pode ser definido para cada atendimento automático. Se os horários comerciais não forem definidos, todos os dias e todas as horas do dia serão considerados horários comerciais, porque um cronograma 24/7 é definido por padrão. O horário comercial pode ser definido com pausas no tempo durante o dia e todas as horas que não estão definidas como horário comercial são consideradas após o horário. Você pode definir diferentes opções de tratamento de chamadas de entrada e saudações para o pós-horário.

Dependendo de como você configurou seus atendimentos automáticos e filas de chamadas, talvez seja necessário especificar apenas o roteamento de chamadas após o horário para os atendimentos automáticos com números de telefone diretos.

Se você quiser roteamento de chamadas separado para chamadores após o horário, especifique seu horário comercial para cada dia. Clique **em Adicionar novo horário** para especificar vários conjuntos de horas para um determinado dia, por exemplo, para especificar uma pausa de almoço.

Depois de especificar seu horário comercial, escolha suas opções de roteamento de chamadas para o horário de expediente. As mesmas opções estão disponíveis para o roteamento de chamadas de horário comercial especificado na **Etapa 3 - Fluxo de chamadas.**

Clique **em Próximo** quando terminar.

> [!div class="nextstepaction"]
> [Etapa 5 - Fluxo de chamada de feriado >](?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[Etapa 5 <br> Feriados](#tab/holidays)

Você pode ter chamadas para o seu atendimento automático roteados de forma diferente em feriados do que em outros dias. (Se você não quiser ter um fluxo de chamada diferente para feriados, ignore esta etapa.)

O seu atendente automático pode ter um fluxo de chamada para cada feriado que você definiu. Você pode adicionar até 20 feriados agendados para cada atendedor automático.

1. Na página Configurações de chamada de feriado, clique em **Adicionar**.

2. Digite um nome para essa configuração de feriado.

3. No menu **suspenso Feriado,** escolha o feriado que você deseja usar.

4. Escolha o tipo de saudação que você deseja usar.

5. Escolha se deseja **desconectar ou** **redirecionar** a chamada.

6. Se você optou por redirecionar, escolha o destino de roteamento de chamadas para a chamada.

7. Clique em **Salvar**.

    Repita o procedimento conforme necessário para cada feriado adicional.

    Quando você adicionou todos os feriados, clique em **Próximo**.

> [!div class="nextstepaction"]
> [Etapa 6 - Escolher quem está no diretório >](?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[Membros do Diretório etapa 6 <br>](#tab/dial-scope)

O *escopo de* discagem define quais usuários estão disponíveis no diretório quando um chamador usa discagem por nome ou discagem por extensão. O padrão de **Todos os usuários online** inclui todos os usuários em sua organização que são usuários online com uma Sistema de Telefonia de usuário.

Você pode incluir ou excluir  usuários específicos  selecionando Grupo de usuários personalizado em **Incluir** ou Excluir e escolher um ou mais grupos de Microsoft 365, listas de distribuição ou grupos de segurança. Por exemplo, talvez você queira excluir executivos em sua organização do diretório de discagem. (Se um usuário estiver em ambas as listas, ele será excluído do diretório.)

> [!NOTE]
> Pode levar até 36 horas para que um novo usuário tenha seu nome listado no diretório.

Quando terminar de definir o escopo de discagem, clique em **Próximo**.

> [!div class="nextstepaction"]
> [Etapa 7 - Atribuir uma conta de recurso >](?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[Etapa 7 <br> Contas de recursos](#tab/resource-accounts)

Todos os atendentes automáticos devem ter uma conta de recurso associada.  Os atendentes automáticos de primeiro nível precisarão de pelo menos uma conta de recurso que tenha um número de serviço associado. Se desejar, você pode atribuir várias contas de recurso a um atendimento automático, cada uma com um número de serviço separado.

Para adicionar uma conta de recurso

1. Clique **em Adicionar** e pesquisar a conta que você deseja adicionar. Clique **em Adicionar** e, em seguida, clique em **Adicionar**.

2. Quando terminar de adicionar contas de serviço, clique em **Enviar**.

    Isso conclui a configuração do atendimento automático.

---
