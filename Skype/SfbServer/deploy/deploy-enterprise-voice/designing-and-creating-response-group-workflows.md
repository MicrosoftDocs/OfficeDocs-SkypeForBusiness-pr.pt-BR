---
title: Projetando e criando fluxos de trabalho de grupo de resposta no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: Projetar e criar fluxos de trabalho de grupo de resposta no Skype for Business Server Enterprise Voice. São abordados os fluxos de trabalho interativos e do grupo de busca.
ms.openlocfilehash: 5b48816a3eb528a1ff96097c135697d8f9cb22d8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002581"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a>Projetando e criando fluxos de trabalho de grupo de resposta no Skype for Business

Projetar e criar fluxos de trabalho de grupo de resposta no Skype for Business Server Enterprise Voice. São abordados os fluxos de trabalho interativos e do grupo de busca.

Um fluxo de trabalho define o comportamento de uma chamada desde a hora que o telefone toca até a hora que alguém atende essa chamada. O fluxo de trabalho especifica a fila que deve ser usada para colocar a chamada em espera, o método de roteamento a ser usado para fluxos de trabalho de grupos de busca ou as perguntas e respostas a serem usadas para fluxos de trabalho de grupos de respostas interativos.

Um fluxo de trabalho também define configurações, como a mensagem de boas-vindas, a música de espera, o horário comercial e os feriados.

> [!NOTE]
> Você deve criar grupos de agente e filas antes de criar um fluxo de trabalho que os utiliza.

## <a name="creating-or-modifying-a-hunt-group-workflow"></a>Criando ou modificando um fluxo de trabalho de grupo coletivo

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>Para usar a ferramenta de configuração de grupo de resposta para criar ou modificar um fluxo de trabalho de grupo coletivo

1. Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.

2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3. Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.

4. Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.

5. No campo de pesquisa **Selecione um Serviço**, digite parte ou todo o nome do serviço do **ApplicationServer** que hospeda o fluxo de trabalho que você deseja alterar ou criar. Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.

    > [!NOTE]
    > A ferramenta de configuração de grupo de resposta é aberta. Você também pode abrir a ferramenta de configuração de grupo de resposta diretamente de um navegador da Web digitando a\<seguinte\>URL: https://webPoolFqdn/RgsConfig.

6. Siga um destes procedimentos:

   - Em **criar um novo fluxo de trabalho**, ao lado de um **grupo coletivo**, clique em **criar**.

   - Em **Gerenciar um Fluxo de Trabalho Existente**, localize o fluxo de trabalho que você deseja alterar e, em **Ação**, clique em **Editar**.

7. Se estiver pronto para que os usuários comecem a fazer chamadas para o fluxo de trabalho, selecione **Ativar o fluxo de trabalho**.

    > [!NOTE]
    >  Se você estiver criando um fluxo de trabalho gerenciado, será necessário selecionar **ativar o fluxo de trabalho**. Após salvar o fluxo de trabalho gerenciado ativo, é possível modificar e desativá-lo.

8. Para permitir que usuários federados façam chamadas para o grupo, selecione a opção **Habilitar para federação**. Você também deve ter uma política de acesso externo que se aplica ao aplicativo de grupo de resposta configurado para Federação.

    > [!NOTE]
    > A política de acesso externo global global aplica-se ao aplicativo de grupo de resposta. Você pode configurar a política global para a reunião de grupo de resposta usando o painel de controle do Skype for Business Server ou usando o cmdlet **set-CsExternalAccessPolicy** para definir o parâmetro EnableOutsideAccess como true. Lembre-se que as configurações de política global se aplicam a todos os usuários, a não ser que eles sejam atribuídos com uma política de usuário ou de site. Portanto, antes de alterar esta configuração para grupos de resposta, certifique-se de que as configurações de federação cumpre os requisitos da sua organização. Para obter detalhes sobre como as políticas são aplicadas aos usuários, consulte [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx). Para obter detalhes sobre a configuração de Federação, consulte [set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps).

    > [!NOTE]
    > Os usuários hospedados no Skype for Business online não podem fazer chamadas para grupos de resposta hospedados em uma implantação local. Isso é verdade nas implantações híbridas e nos casos em que uma implantação local é federada com uma implantação do Skype for Business online.

9. Para ocultar a identidade de operadores durante as chamadas, selecione a opção **Habilitar anonimato do operador**.

    > [!NOTE]
    > Chamadas anônimas não podem ter início com sistemas de mensagens instantâneas (IM) ou vídeo, embora o operador ou chamadas possam adicionar IM e vídeo depois que a chamada estiver estabelecida. Um operador anônimo também pode colocar chamadas em espera, transferir (transferências ocultas e de consulta), estacionar e recuperar chamadas. Chamadas anônimas não oferecem suporte a conferência, compartilhamento de aplicativos, transferência de arquivos, whiteboarding e colaboração de dados e gravação de chamadas. Agentes utilizando o Plugin Lync VDI podem atender chamadas em entrada anonimamente, mas não podem realizar chamadas em saída anonimamente.

10. Sob **Insira o endereço do grupo que receberá as chamadas**, digite o endereço URI SIP primário do grupo que irá receber chamadas para o fluxo de trabalho.

    > [!NOTE]
    > O URI primário para um fluxo de trabalho é como o fluxo de trabalho é identificado e referenciado. O URI SIP que você insere é criado como um objeto de contato nos serviços de domínio Active Directory. Para criar o URI, o objeto deve ser exclusivo no Active Directory.

11. Em **nome para exibição**, digite o nome que você deseja exibir para o fluxo de trabalho (por exemplo, grupo de resposta de vendas).

    > [!NOTE]
    > Não inclua os caracteres "<" ou ">" no nome de exibição. Não use os nomes de exibição a seguir, pois são reservados: **Observador de Presença RG** ou **Serviço de Anúncio**.

12. Sob **Número de telefone**, digite o URI de linha para o grupo de resposta (por exemplo, +14255550165).

13. Em **Número de Exibição**, digite o número conforme deseja que apareça para o grupo de resposta (por exemplo, +1 (425) 555-0165).

14. Adicionais Em **Descrição**, digite uma descrição para o fluxo de trabalho como deseja que ele apareça no cartão de visita no Skype for Business.

15. Em **Tipo de fluxo de trabalho**, selecione **Gerenciado** se este fluxo de trabalho será gerenciado por um Gerente o Grupo de Resposta. Siga este procedimento para atribuir gerentes de grupo de resposta ao fluxo de trabalho:

    a. Digite o URI SIP de um gerente para este fluxo de trabalho e clique em **Adicionar**.

    b. Digite o URI SIP de gerentes adicionais para adicionar ao fluxo de trabalho e clique em **Adicionar**.

    > [!IMPORTANT]
    > Cada usuário que é designado como um gerente de um grupo de resposta deve ser atribuído à função CsResponseGroupManager. Se os usuários não sã atribuídos com esta função, eles não podem gerenciar grupos de resposta.

16. Sob **Etapa 2 Selecione um Idioma**, clique no idioma que deseja usar para reconhecimento de fala e conversão de texto em fala.

17. Se você deseja configurar uma mensagem de boas vindas, sob **Etapa 3 Configure uma Mensagem de Boas Vindas**, selecione a opção **Reproduzir uma mensagem de boas vindas** e execute um dos seguintes procedimentos:

    - Para inserir uma mensagem de boas vindas como texto convertido para fala para os chamadores, clique em **Usar conversão de texto em fala** e digite a mensagem de boas vindas na caixa de texto.

    > [!NOTE]
    > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

    - Para usar uma gravação de arquivo de áudio wave (.wav) ou (.wma) do Windows Media para a mensagem de boas vindas, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na janela do navegador, clique em **Procurar**, selecione o arquivo de áudio que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

    > [!NOTE]
    > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

18. Sob **Etapa 4 Especifique seu Horário Comercial**, em **Seu fuso horário**, clique no fuso horário para o fluxo de trabalho.

    > [!NOTE]
    > O fuso horário é onde os chamadores e operadores do fluxo de trabalho residem. Ele é usado para calcular os horários de abertura e encerramento. Por exemplo, se o fluxo de trabalho está configurado para usar o fuso horário da costa leste norte-americana e o fluxo de trabalho estiver agendado para abrir às 7:00 A.M e fechar às 11:00 P.M., os horários de abertura e fechamento são assumidos como sendo 7:00 horário da costa leste e 23:00 horário da costa leste, respectivamente (você deve inserir os horários na notação de 24 horas).

19. Selecione o tipo de agenda de horário comercial que deseja usar executando um dos seguintes procedimentos:

    - Para usar uma agenda pré-definida de horário comercial, clique em **Usar uma agenda predefinida** e selecione a agenda que deseja usar na lista suspensa.

      > [!NOTE]
      > Você deve ter definido no mínimo uma agenda predefinida anteriormente para selecionar esta opção. É possível definir agendamentos de predefinições usando o cmdlet **New-CSRgsHoursOfBusiness**. Para obter detalhes, consulte [(opcional) definir o horário comercial do grupo de resposta no Skype for Business](optional-define-response-group-business-hours.md).

      > [!NOTE]
      > Ao selecionar uma agenda predefinida, **Dia**, **Abertura** e **Fechamento** são automaticamente preenchidos com os dias e horas em que o grupo de resposta está disponível.

    - Para usar uma agenda personalizada que se aplique somente a este fluxo de trabalho, clique em **Usar uma agenda personalizada**.

20. Se estiver criando uma agenda personalizada para este fluxo de trabalho, clique nas opções para os dias da semana em que o grupo de resposta estará disponível.

21. Se você estiver criando um cronograma personalizado, digite as horas de **abertura** e de **fechamento** para cada dia da semana em que o grupo de resposta está disponível.

    > [!NOTE]
    > As horas de **Abertura** e **Fechamento** devem estar na notação de 24 horas. Por exemplo, se seu escritório funciona em dias úteis das 9 às 5 e fecha ao meio dia para o almoço, o horário comercial é especificado como **Abertura** 9:00, **Fechamento** 12:00, **Abertura** 13:00 e **Fechamento** 17:00.

22. Se você desejar reproduzir uma mensagem quando o escritório não estiver aberto, selecione a opção **Reproduzir uma mensagem quando o grupo de resposta estiver fora do horário comercial** e especifique a mensagem a ser reproduzida executando um dos seguintes procedimentos:

    - Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.

      > [!NOTE]
      > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

    - Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

      > [!NOTE]
      > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivos de áudio com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

23. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):

    - Para desconectar a chamada, clique em **Desconectar Chamada**.

    - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço de correio de voz * \<é\>username*@*\<DomainName\> * (por exemplo, Bob@contoso.com).

    - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço de usuário é _ \<username\>_@_\<DomainName\>_.

    - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone é * \<número\>*@*\<DomainName\> * (por exemplo, + 14255550121@contoso.com). O nome do domínio é usado para encaminhar o chamador ao destino correto.

24. Sob **Etapa 5 Especifique seus Feriados**, clique nas opções para um ou mais conjuntos de feriados que definem quando o grupo de resposta estará fechado para negócios.

    > [!NOTE]
    > É necessário definir feriados e conjuntos de feriados antes de configurar o fluxo de trabalho. Use os cmdlets **New-CsRgsHoliday** e **New-CsRgsHolidaySet** para definir feriados e conjuntos de feriados. Para obter detalhes, consulte [(opcional) definir os conjuntos de feriados do grupo de resposta no Skype for Business](optional-define-response-group-holiday-sets.md).

25. Se você deseja reproduzir uma mensagem nos feriados, selecione a opção **Reproduzir uma mensagem durante os feriados** e especifique a mensagem a ser executada realizado um dos seguintes procedimentos:

    - Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.

    > [!NOTE]
    > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

    - Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

      > [!NOTE]
      > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivos de áudio com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

26. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):

    - Para desconectar a chamada, clique em **Desconectar Chamada**.

    - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço de correio de voz * \<é\>username*@*\<DomainName\> * (por exemplo, Bob@contoso.com).

    - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço de usuário é _ \<username\>_@_\<DomainName\>_.

    - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone é * \<número\>*@*\<DomainName\> * (por exemplo, + 14255550121@contoso.com). O nome do domínio é usado para encaminhar o chamador ao destino correto.

27. Sob **Etapa 6 Configure uma Fila**, em **Selecione a fila que receberá as chamadas**, selecione a fila que você deseja que segure as chamadas até que um operador torne-se disponível.

28. Sob **Etapa 7 Configure Música de Espera**, escolha a música que deseja que os chamadores ouçam enquanto esperam que um operador, executando um dos seguintes procedimentos:

    - Para usar a gravação padrão de música de espera, clique em **Usar padrão**.

    - Para usar uma gravação de arquivo de áudio para a música de espera, clique em **Selecionar um arquivo de música**. Se você deseja carregar um novo arquivo de áudio, clique no link **um arquivo de música**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

      > [!NOTE]
      > Todos os arquivos de áudio fornecidos pelo usuário devem atender determinados requisitos. Para detalhes sobre formatos de arquivos de áudio com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

29. Clique em **Implantar**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a>Para usar o Shell de gerenciamento do Skype for Business Server para criar ou modificar um fluxo de trabalho de grupo coletivo

1. Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.

2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

3. Crie o prompt a ser reproduzido na mensagem de boas-vindas e salve-o como uma variável. Na linha de comando, execute:

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    Por exemplo:

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > Para usar um arquivo de áudio no prompt, use o cmdlet **Import-CsRgsAudioFile**. Para obter detalhes, consulte [importar-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).

4. Obtenha a identidade da fila ou pergunta onde as chamadas serão direcionadas. Na linha de comando, execute:

   ```powershell
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    Para obter detalhes sobre como criar a fila, consulte [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps).

5. Defina a ação padrão a ser realizada quando um fluxo de trabalho é aberto durante o horário comercial e salve-o em uma variável. Na linha de comando, execute:

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > Para fluxos de trabalho do grupo de busca, a ação padrão deve direcionar a chamada para uma fila. Esse parâmetro é obrigatório para fluxos de trabalho ativos. Não é necessário para fluxos de trabalho inativos.

    Por exemplo:

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. Se você deseja definir o horário comercial e feriados, é necessário criá-los antes de criar ou modificar o fluxo de trabalho. Para obter detalhes, consulte [(opcional) definir o horário comercial do grupo de resposta no Skype for Business](optional-define-response-group-business-hours.md) e [(opcional) definir os conjuntos de feriados do grupo de resposta no Skype for Business](optional-define-response-group-holiday-sets.md).

7. Se você deseja ter prompts para chamadas recebidas fora do horário comercial ou em feriados, use o cmdlet **New-CsRgsPrompt** para definir o prompt e use o **New-CsRgsCallAction** para definir a ação a ser realizada após o prompt. Para obter detalhes, consulte [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).

8. Recupere o nome do serviço do serviço de grupo de resposta do Lync Server e atribua-o a uma variável. No comando, execute:

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. Crie ou modifique o fluxo de trabalho. Para criar um fluxo de trabalho, use **New-CsRgsWorkflow**. Para modificar um fluxo de trabalho, use **set-CsRgsWorkflow**. Na linha de comando, digite:

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    Por exemplo:

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > Todos os usuários que são gerentes para fluxos de trabalho devem ser atribuídos à função CsResponseGroupManager.

     > [!NOTE]
     > Para obter detalhes sobre parâmetros opcionais adicionais, consulte [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) ou [set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

## <a name="designing-an-interactive-workflow"></a>Projetando um fluxo de trabalho interativo

Você pode usar a IVR (resposta de voz interativa) para obter informações de chamadores e direcionar a chamada para a fila apropriada. Os pares de perguntas e respostas determinam qual fila usar. Dependendo da resposta do chamador, o chamador ouve uma pergunta de acompanhamento ou é encaminhado para a fila apropriada. As perguntas do IVR e as respostas do chamador são fornecidas ao agente de resposta que aceita a chamada, fornecendo informações valiosas ao agente.

### <a name="overview-of-ivr-features"></a>Visão geral dos recursos do IVR

O aplicativo grupo de resposta oferece recursos de reconhecimento de fala e conversão de texto em fala em 26 idiomas. É possível inserir perguntas IVR usando a conversão texto em fala ou um arquivo wave (.wav) ou Windows Media audio (.wma). Os chamadores podem responder usando a voz ou multifrequência de dois tons (DTMF).

Os fluxos de trabalho interativos suportam até dois níveis de perguntas, com cada pergunta tendo até quatro respostas possíveis. O IVR faz uma pergunta ao autor e, dependendo da resposta do chamador, roteia o usuário para uma fila ou faz uma segunda pergunta. A segunda pergunta também pode ter quatro respostas possíveis. Dependendo da resposta à pergunta de segundo nível, o chamador é roteado para a fila adequada.

> [!NOTE]
> Ao projetar fluxos de chamadas usando o Shell de gerenciamento do Skype for Business Server, você pode definir qualquer número de níveis de perguntas do IVR e qualquer número de respostas. No entanto, para melhor usabilidade do chamador, recomendamos que você não use mais de três níveis de perguntas, com não mais do que cinco respostas cada. Além disso, se você criar um fluxo de chamadas com mais de dois níveis de perguntas com mais de quatro respostas, não poderá editar o fluxo de chamadas usando o painel de controle do Skype for Business Server.

As perguntas do IVR e as respostas do chamador são fornecidas ao agente de resposta que aceita a chamada.

### <a name="working-with-speech-technologies"></a>Trabalhando com tecnologias de fala

Tecnologias de fala, como o reconhecimento de fala e conversão de texto em fala, podem aprimorar a experiência do cliente e permitir que as pessoas acessem informações de forma mais natural e eficaz. No entanto, pode haver casos em que o texto especificado ou a resposta de voz do usuário não é reconhecido corretamente pelo mecanismo de fala. Por exemplo, o símbolo "#" é traduzido pelo mecanismo de conversão de texto em fala como a palavra "número". Este problema pode ser reduzido pelo seguinte:

- O mecanismo de fala fornece ao chamador cinco tentativas de responder a pergunta. Se o chamador responder incorretamente (isto é, a resposta não é uma das respostas especificadas) ou não oferecer uma resposta, ele ou ela tem outra chance de responder. O chamador tem cinco tentativas de responder a pergunta antes de ser desconectado. É possível configurar a IVR para reproduzir uma mensagem personalizada após cada erro do chamador. A pergunta é repetida todas as vezes.

- Para minimizar que o potencial ruído ambiente seja interpretado pelo mecanismo de fala como uma resposta, use respostas mais longas. Por exemplo, as respostas devem ter mais de uma sílaba e devem soar diferente uma da outra.

- Se suas perguntas possuem respostas de fala e DTMF, configure as respostas de fala com palavras que representam um conceito ao invés da resposta DTMF. Por exemplo, ao invés de usar "Pressione ou fale 1", use "Pressione 1 ou fale faturamento."

- Após projetar sua IVR, ligue par ao fluxo de trabalho, ouça às solicitações, responda cada uma delas usando a voz e verifique se a IVR soa e se comporta conforme esperado. É possível modificar a IVR para corrigir qualquer problema de interpretação. No exemplo a seguir, se você precisa consultar a tecla #, é possível regravar sua solicitação IVR para usar o nome da tecla ao invés do símbolo #. Por exemplo, "Para falar com vendas, pressione a tecla jogo da velha."

### <a name="ivr-design-examples"></a>Exemplos de design de IVR

As seções a seguir contêm exemplos de diferentes cenários de IVR e pares de perguntas e respostas.

#### <a name="ivr-with-one-level-of-questions"></a>IVR com um nível de perguntas

O exemplo a seguir mostra uma IVR que usa um nível de perguntas. Ele usa o reconhecimento de fala para detectar a resposta do chamador.

 **Pergunta:** "Obrigado por ligar para os Recursos Humanos. Se você deseja falar com a folha de pagamentos, diga folha de pagamentos. Caso contrário, diga RH."

- **A opção 1 é selecionada:** O chamador é roteado para a equipe de folha de pagamentos.

- **A opção 2 é selecionada:** O chamador é roteado para a equipe de recursos humanos.

A figura a seguir mostra o fluxo de chamadas.

 **Fluxo de chamada interativa de um nível**

![Criar fluxos de chamadas usando o respo de voz interativo](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a>IVR com dois níveis de perguntas

O exemplo a seguir mostra uma IVR que usa dois níveis de perguntas. Permite aos chamadores responder usando fala ou entrada do teclado DTMF.

 **Pergunta:** "Obrigado por ligar para o Help Desk de TI. Se você está com um problema de acesso à rede, pressione 1 ou diga rede. Se você está com um problema de software, pressione 2 ou diga software. Se você está com um problema de hardware, pressione 3 ou diga hardware."

- **A opção 1 é selecionada:** O chamador é roteado para a equipe de suporte de rede.

- **A opção 2 é selecionada:** É realizada uma pergunta de acompanhamento ao chamador:

    **Pergunta:** "Se é um problema do sistema operacional, pressione 1 ou diga sistema operacional. Se é um problema com um aplicativo interno, pressione 2 ou diga aplicativo interno. Caso contrário, pressione 3 ou diga outro."

  - **A opção 1 é selecionada:** O chamador é roteado para a equipe de suporte ao sistema operacional.

  - **A opção 2 é selecionada:** O chamador é roteado para a equipe de suporte a aplicativos internos.

  - **A opção 3 é selecionada:** O chamador é roteado para a equipe de suporte de software.

- **A opção 3 é selecionada:** É realizada uma pergunta de acompanhamento ao chamador:

    **Pergunta:** "Se é um problema de impressora, pressione 1. Caso contrário, pressione 2."

  - **A opção 1 é selecionada:** O chamador é roteado para a equipe de suporte a impressoras.

  - **A opção 2 é selecionada:** O chamador é roteado para a equipe de suporte ao hardware.

A figura a seguir mostra o fluxo de chamadas.

 **Fluxo de chamada interativa de dois níveis**

![Criar fluxos de chamadas usando o respo de voz interativo](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a>Práticas recomendadas

A lista a seguir descreve algumas práticas recomendadas para projetar sua IVR:

- Permita que o chamador chegue à tarefa rapidamente. Evite oferecer muita informação ou mensagens de marketing longas em sua IVR.

- Se você deseja incluir uma mensagem longa, considere anexá-la à primeira pergunta ao invés da mensagem de boas-vindas. Os chamadores podem ignorar a mensagem se fizer parte da primeira pergunta respondendo à pergunta, mas não podem ignorar a mensagem de boas-vindas.

- Fale no idioma do chamador. Evite usar uma linguagem refinada. Fale naturalmente.

- Grave prompts eficazes e eficientes. Remova qualquer opção desnecessária. Estruture as informações para que a resposta esperada do chamador esteja no final da sentença. Por exemplo, "para falar com a equipe de vendas, pressione 1."

- Torne as respostas de voz fáceis. Por exemplo, se você especificar as respostas DTMF e voz, use algo como: "Para falar com a equipe de vendas, pressione 1 ou diga vendas."

- Teste a IVR em um grupo de usuários antes de implantar na sua organização.

## <a name="creating-or-modifying-an-interactive-workflow"></a>Criando ou modificando um fluxo de trabalho interativo

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>Para usar a ferramenta de configuração de grupo de resposta para criar ou modificar um fluxo de trabalho interativo

1. Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.

2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3. Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.

4. Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.

5. No campo de pesquisa **Selecionar um serviço**, digite parte ou o nome inteiro do serviço **ApplicationServer** que hospeda o fluxo de trabalho que deseja criar ou modificar. Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.

    > [!NOTE]
    > A ferramenta de configuração de grupo de resposta é aberta. Você também pode abrir a ferramenta de configuração de grupo de resposta diretamente de um navegador da Web digitando a\<seguinte\>URL: https://webPoolFqdn/RgsConfig.

6. Siga um destes procedimentos:

   - Em **Criar um Novo Fluxo de Trabalho**, ao lado de **Interativo**, clique em **Criar**.

   - Em **Gerenciar um Fluxo de Trabalho Existente**, localize o fluxo de trabalho que você deseja alterar e, em **Ação**, clique em **Editar**.

7. Se ainda não estiver tudo pronto para os usuários começarem a chamar o fluxo de trabalho, desmarque a caixa de seleção **Ativar o fluxo de trabalho**.

    > [!NOTE]
    >  Se você estiver criando um fluxo de trabalho gerenciado, será necessário selecionar **ativar o fluxo de trabalho**. Após salvar o fluxo de trabalho gerenciado ativo, é possível modificar e desativá-lo.

8. Para permitir que usuários federados façam chamadas para o grupo, selecione a opção **Habilitar para federação**. Você também deve ter uma política de acesso externo que se aplica ao aplicativo de grupo de resposta configurado para Federação.

    > [!NOTE]
    > A política de acesso externo global global aplica-se ao aplicativo de grupo de resposta. Você pode configurar a política global para a reunião de grupo de resposta usando o painel de controle do Skype for Business Server ou usando o cmdlet **set-CsExternalAccessPolicy** para definir o parâmetro EnableOutsideAccess como true. Lembre-se que as configurações de política global se aplicam a todos os usuários, a não ser que eles sejam atribuídos com uma política de usuário ou de site. Portanto, antes de alterar esta configuração para grupos de resposta, certifique-se de que as configurações de federação cumpre os requisitos da sua organização. Para obter detalhes sobre como as políticas são aplicadas aos usuários, consulte [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx). Para obter detalhes sobre a configuração de Federação, consulte **set-CsExternalAccessPolicy** in Documentation..

    > [!NOTE]
    > Os usuários hospedados no Skype for Business online não podem fazer chamadas para grupos de resposta hospedados em uma implantação local. Isso é verdade nas implantações híbridas e nos casos em que uma implantação local é federada com uma implantação do Skype for Business online.

9. Para ocultar a identidade de operadores durante as chamadas, selecione a opção **Habilitar anonimato do operador**.

    > [!NOTE]
    > Chamadas anônimas não podem ter início com sistemas de mensagens instantâneas (IM) ou vídeo, embora o operador ou chamadas possam adicionar IM e vídeo depois que a chamada estiver estabelecida. Um operador anônimo também pode colocar chamadas em espera, transferir (transferências ocultas e de consulta), estacionar e recuperar chamadas. Chamadas anônimas não oferecem suporte a conferência, compartilhamento de aplicativos, transferência de arquivos, whiteboarding e colaboração de dados e gravação de chamadas. Agentes utilizando o Plugin Lync VDI podem atender chamadas em entrada anonimamente, mas não podem realizar chamadas em saída anonimamente.

10. Sob **Insira o endereço do grupo que receberá as chamadas**, digite o endereço URI SIP primário do grupo que irá receber chamadas para o fluxo de trabalho.

11. Em **Nome de exibição**, digite o nome que deseja exibir no fluxo de trabalho (por exemplo, Serviço de resposta IVR de vendas).

    > [!NOTE]
    > Não inclua os caracteres "\<" ou "\>" no nome para exibição. Não use os nomes de exibição a seguir, pois são reservados: **Observador de Presença RG** ou **Serviço de Anúncio**.

12. Em **Número de telefone**, digite o URI de linha para o grupo de resposta (por exemplo, +14255550165).

13. Em **Número de Exibição**, digite o número conforme deseja que apareça para o grupo de resposta (por exemplo, +1 (425) 555-0165).

14. Adicionais Em **Descrição**, digite uma descrição para o fluxo de trabalho que você deseja que apareça no cartão de visita no Skype for Business.

15. Em **Tipo de fluxo de trabalho**, selecione **Gerenciado** se este fluxo de trabalho será gerenciado por um Gerente o Grupo de Resposta. Siga este procedimento para atribuir gerentes de grupo de resposta ao fluxo de trabalho:

    a. Digite o URI SIP de um gerente para este fluxo de trabalho e clique em **Adicionar**.

    b. Digite o URI SIP de gerentes adicionais para adicionar ao fluxo de trabalho e clique em **Adicionar**.

    > [!IMPORTANT]
    > Cada usuário que é designado como um gerente de um grupo de resposta deve ser atribuído à função CsResponseGroupManager. Se os usuários não sã atribuídos com esta função, eles não podem gerenciar grupos de resposta.

16. Sob **Etapa 2 Selecione um Idioma**, clique no idioma a ser usado para o reconhecimento de fala e conversão de texto em fala.

17. Se você deseja configurar uma mensagem de boas vindas, sob **Etapa 3 Configure uma Mensagem de Boas Vindas**, selecione a opção **Reproduzir uma mensagem de boas vindas** e execute um dos seguintes procedimentos:

    - Para inserir uma mensagem de boas vindas como texto convertido para fala para os chamadores, clique em **Usar conversão de texto em fala** e digite a mensagem de boas vindas na caixa de texto.

    > [!NOTE]
    > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

    - Para usar uma gravação de arquivo Wave ou Windows Media Audio para a mensagem de boas vindas, clique em **Selecione uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na janela do navegador, clique em **Procurar**, selecione o arquivo de áudio que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

    > [!NOTE]
    > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

18. Sob **Etapa 4 Especifique seus Horários Comerciais**, na caixa **Seu fuso horário**, clique no fuso horário do fluxo de trabalho.

    > [!NOTE]
    > O fuso horário é onde os chamadores e operadores do fluxo de trabalho residem. Ele é usado para calcular os horários de abertura e encerramento. Por exemplo, se o fluxo de trabalho está configurado para usar o fuso horário da costa leste norte-americana e o fluxo de trabalho estiver agendado para abrir às 7:00 A.M e fechar às 11:00 P.M., os horários de abertura e fechamento são assumidos como sendo 7:00 horário da costa leste e 11:00 horário da costa leste, respectivamente (você deve inserir os horários na notação de 24 horas).

19. Selecione o tipo de agenda de horário comercial que deseja usar executando um dos seguintes procedimentos:

    - Para usar uma agenda pré-definida de horário comercial, clique em **Usar uma agenda predefinida** e selecione a agenda que deseja usar na lista suspensa.

      > [!NOTE]
      > Você deve ter definido no mínimo uma agenda predefinida anteriormente para selecionar esta opção. Você define cronogramas predefinidos usando o cmdlet **New-CsRgsHoursOfBusiness** . Para obter detalhes, consulte [(opcional) definir o horário comercial do grupo de resposta no Skype for Business](optional-define-response-group-business-hours.md). Ao selecionar uma agenda predefinida, **Dia**, **Abertura** e **Fechamento** são automaticamente preenchidos com os dias e horas em que o grupo de resposta está disponível.

    - Para usar uma agenda personalizada que se aplique somente a este fluxo de trabalho, clique em **Usar uma agenda personalizada**.

20. Se estiver criando uma agenda personalizada para este fluxo de trabalho, clique nas opções para os dias da semana em que o grupo de resposta estará disponível.

21. Se você estiver criando um cronograma personalizado, digite as horas de **abertura** e de **fechamento** quando o grupo de resposta estiver disponível.

     > [!NOTE]
     > As horas de **Abertura** e **Fechamento** devem estar na notação de 24 horas. Por exemplo, se seu escritório funciona em dias úteis das 9 às 5 e fecha ao meio dia para o almoço, o horário comercial é especificado como **Abertura** 9:00, **Fechamento** 12:00, **Abertura** 13:00 e **Fechamento** 17:00.

22. Se você desejar reproduzir uma mensagem quando o escritório não estiver aberto, selecione a opção **Reproduzir uma mensagem quando o grupo de resposta estiver fora do horário comercial** e especifique a mensagem a ser reproduzida executando um dos seguintes procedimentos:

    - Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.

      > [!NOTE]
      > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

    - Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

    > [!NOTE]
    > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

23. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):

    - Para desconectar a chamada, clique em **Desconectar Chamada**.

    - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço de correio de voz * \<é\>username*@*\<DomainName\> * (por exemplo, Bob@contoso.com).

    - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço de usuário é _ \<username\>_@_\<DomainName\>_.

    - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone é * \<número\>*@*\<DomainName\> * (por exemplo, + 14255550121@contoso.com). O nome do domínio é usado para encaminhar o chamador ao destino correto.

24. Sob **Etapa 5 Especifique seus Feriados**, clique nas opções para um ou mais conjuntos de feriados que definem quando o grupo de resposta estará fechado para negócios.

    > [!NOTE]
    > É necessário definir feriados e conjuntos de feriados antes de configurar o fluxo de trabalho. Use os cmdlets **New-CsRgsHoliday** e **New-CsRgsHolidaySet** para definir feriados e conjuntos de feriados. Para obter detalhes, consulte [(opcional) definir os conjuntos de feriados do grupo de resposta no Skype for Business](optional-define-response-group-holiday-sets.md).

25. Se você deseja reproduzir uma mensagem nos feriados, selecione a opção **Reproduzir uma mensagem durante os feriados** e especifique a mensagem a ser executada realizado um dos seguintes procedimentos:

    - Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.

      > [!NOTE]
      > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

    - Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

      > [!NOTE]
      > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivos de áudio com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

26. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):

    - Para desconectar a chamada, clique em **Desconectar Chamada**.

    - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço de correio de voz * \<é\>username*@*\<DomainName\> * (por exemplo, Bob@contoso.com).

    - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço de usuário é _ \<username\>_@_\<DomainName\>_.

    - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone é * \<número\>*@*\<DomainName\> * (por exemplo, + 14255550121@contoso.com). O nome do domínio é usado para encaminhar o chamador ao destino correto.

27. Sob **Etapa 6 Configure a Música de Espera**, escolha o que deseja que os chamadores ouçam enquanto esperam por um operador, executando um dos seguintes procedimentos:

    - Para usar a gravação padrão de música em espera, clique em **Usar padrão**.

    - Para usar uma gravação de arquivo de áudio como música de espera, clique em **Selecionar um arquivo de música**. Se você deseja carregar um novo arquivo de áudio, clique no link **um arquivo de música**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

    > [!NOTE]
    > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

28. Sob **Etapa 7 Configure a Resposta Interativa de Voz**, sob o cabeçalho **O usuário ouvirá o seguinte texto ou mensagem gravada**, especifique a pergunta a ser feita aos chamadores da seguinte forma:

    - Para digitar uma pergunta em formato de texto, clique em **Usar conversão de texto em fala** e digite a pergunta na caixa de texto.

    > [!NOTE]
    > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

    > [!NOTE]
    > O símbolo "#" é traduzido pelo mecanismo de conversão de texto em fala como a palavra "número". Se for necessário fazer referência à tecla #, use o nome da tecla no prompt, em vez do símbolo. Por exemplo, "Para falar com vendas, pressione a tecla jogo da velha."

    - Para usar um arquivo de áudio pré-gravado que contenha a pergunta, clique em **Selecionar uma gravação** e clique no link **uma gravação** para carregar o arquivo. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo de áudio e clique em **Abrir**. Clique em **carregar** para carregar o arquivo e, em seguida, opcionalmente, você pode digitar a pergunta na caixa de texto (isso permite que a pergunta e a resposta do chamador sejam encaminhadas para o agente de resposta).

      > [!NOTE]
      > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).

29. Em **Resposta 1**, especifique a primeira resposta possível para a pergunta executando um dos seguintes procedimentos:

    > [!IMPORTANT]
    > Não use aspas (") em qualquer resposta de voz. Aspas podem provocar falhas no IVR.

    > [!NOTE]
    > Você pode optar por permitir que os chamadores respondam usando a fala, entradas do teclado alfanumérico ou ambos.

    - Se desejar permitir que o chamador responda usando a fala, insira a resposta em **Insira uma resposta de voz**.

    - Se você desejar permitir que o chamador responda pressionando uma tecla no teclado, em **Dígito**, clique no dígito do teclado.

30. Especifique se o chamador será encaminhado para uma fila ou se será feita outra pergunta, da seguinte maneira:

    - Para rotear o chamador para uma fila, clique em **Enviar para uma fila** e, em **Selecione uma fila**, clique na fila que deseja usar.

    - Para fazer outra pergunta, clique em **Fazer outra pergunta**, clique em **Use conversão de texto em fala** e digite a pergunta ou clique em **Selecione uma gravação**. Use os agrupamentos de resposta nesta seção para especificar até quatro possíveis respostas para a pergunta adicional e a fila a ser usada para cada resposta. Para especificar uma terceira ou quarta resposta possível, clique na opção **Resposta 3** ou **Resposta 4**.

31. Especifique até mais três respostas possíveis para a pergunta original, repetindo as etapas 28 e 29 para especificar as possíveis respostas e a ação para cada resposta. Para especificar uma terceira ou quarta resposta possível, clique na caixa de seleção **Resposta 3** ou **Resposta 4**.

32. Clique em **Implantar**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a>Para usar o Shell de gerenciamento do Skype for Business Server para criar ou modificar um fluxo de trabalho interativo

1.  Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.

2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.

3. Recupere o nome do serviço do Grupo de Resposta e o atribua a uma variável. Na linha de comando, execute:

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. Um fluxo de trabalho interativo requer duas ou mais filas e dois ou mais grupos de agentes. Primeiro, crie os grupos de agentes. Execute:

   ```powershell
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. Crie as filas. Execute:

   ```powershell
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. Crie o primeiro prompt de grupo de resposta. Execute:

   ```powershell
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. Em seguida, crie a ação que será executada depois do prompt. Execute:

   ```powershell
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. Crie a primeira resposta do grupo de resposta. Execute:

   ```powershell
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. Agora crie o segundo prompt, a ação da chamada e a resposta. Primeiro crie o prompt. Execute:

   ```powershell
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. Crie a segunda ação de chamada. Execute:

    ```powershell
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. Crie a segunda resposta do grupo de resposta. Execute:

    ```powershell
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. Crie o prompt do nível superior. Execute:

    ```powershell
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. Crie a pergunta do nível superior. Execute:

    ```powershell
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. Agora crie o fluxo de trabalho. Execute:

    ```powershell
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > Todos os usuários que foram designados como gerentes de um grupo de resposta devem receber a função CsResponseGroupManager. Se os usuário não têm essa função, não será possível gerenciar grupos de resposta.

## <a name="see-also"></a>Confira também

[Adicionais Definir conjuntos de feriados do grupo de resposta no Skype for Business](optional-define-response-group-holiday-sets.md)

[Adicionais Definir o horário comercial do grupo de resposta no Skype for Business](optional-define-response-group-business-hours.md)

[New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)

