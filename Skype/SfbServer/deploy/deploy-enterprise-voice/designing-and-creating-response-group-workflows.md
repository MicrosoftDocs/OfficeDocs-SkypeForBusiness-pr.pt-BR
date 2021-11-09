---
title: Criando e criando fluxos de trabalho de grupo de resposta Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: Projete e crie fluxos de trabalho do Grupo de Resposta, Skype for Business Server Enterprise Voice. Tanto os fluxos de trabalho de grupo de busca quanto os fluxos de trabalho interativos são abordados.
ms.openlocfilehash: ec92a0dfa378746db98a6377b2ebd51df0e77813
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864378"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a>Criando e criando fluxos de trabalho de grupo de resposta Skype for Business

Projete e crie fluxos de trabalho do Grupo de Resposta, Skype for Business Server Enterprise Voice. Tanto os fluxos de trabalho de grupo de busca quanto os fluxos de trabalho interativos são abordados.

Um fluxo de trabalho define o comportamento de uma chamada desde a hora que o telefone toca até a hora que alguém atende essa chamada. O fluxo de trabalho especifica a fila a ser usada para a realização da chamada e especifica o método de roteamento a ser usado para a busca de fluxos de trabalho de grupo ou as perguntas e respostas a ser usadas para fluxos de trabalho de grupo de resposta interativos.

Um fluxo de trabalho também define configurações, como a mensagem de boas-vindas, a música de espera, o horário comercial e os feriados.

> [!NOTE]
> É necessário criar grupos de agentes e filas antes de criar um fluxo de trabalho que os use.

## <a name="creating-or-modifying-a-hunt-group-workflow"></a>Criando ou modificando um fluxo de trabalho de grupo de busca

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>Para usar a Ferramenta de Configuração de Grupo de Resposta para criar ou modificar um fluxo de trabalho de grupo de busca

1. Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinida que suportam o Grupo de Resposta.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.

4. Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.

5. No campo **Selecionar um serviço** de pesquisa, digite todo ou parte do nome do serviço **ApplicationServer** que hospeda o fluxo de trabalho que você deseja criar ou alterar. Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.

    > [!NOTE]
    > A Ferramenta de Configuração do Grupo de Resposta é aberta. Você também pode abrir a Ferramenta de Configuração de Grupo de Resposta diretamente de um navegador da Web digitando a seguinte URL: \<webPoolFqdn\> https:// /RgsConfig.

6. Faça um dos seguintes:

   - Em **Criar um Novo Fluxo de Trabalho,** ao lado de Grupo de **Busca,** clique em **Criar**.

   - Em **Gerenciar um Fluxo de Trabalho Existente**, localize o fluxo de trabalho que você deseja alterar e, em **Ação**, clique em **Editar**.

7. Se você estiver pronto para que os usuários comecem a chamar o fluxo de trabalho, selecione **Ativar o fluxo de trabalho**.

    > [!NOTE]
    >  Se você estiver criando um fluxo de trabalho gerenciado, será necessário selecionar **Ativar o fluxo de trabalho**. Depois de salvar o fluxo de trabalho ativo e gerenciado, você pode modificá-lo e desativá-lo.

8. Para permitir que usuários federados façam chamadas para o grupo, selecione a opção **Habilitar para federação**. Você também deve ter uma política de acesso externo que se aplique ao aplicativo do Grupo de Resposta configurado para federação.

    > [!NOTE]
    > A política de acesso externo global se aplica ao aplicativo grupo de resposta. Você pode configurar a política global para federação de grupo de resposta usando o Painel de Controle Skype for Business Server ou usando o cmdlet **Set-CsExternalAccessPolicy** para definir o parâmetro EnableOutsideAccess como True. Lembre-se de que as configurações de política global se aplicam a todos os usuários a não ser que sejam atribuídos a um site ou uma política de usuário. Portanto, antes de alterar essa configuração para grupos de resposta, verifique se a configuração de federação atende aos requisitos da sua organização. Para obter detalhes sobre como as políticas se aplicam aos usuários, consulte [Manage External Access Policy for Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-manage-external-access-policy-for-your-organization). Para obter detalhes sobre a configuração de federação, consulte [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps).

    > [!NOTE]
    > Os usuários hospedados no Skype for Business Online não podem fazer chamadas para grupos de resposta hospedados em uma implantação local. Isso é verdadeiro em implantações híbridas e em casos em que uma implantação local é federada com uma implantação Skype for Business Online.

9. Para ocultar a identidade de operadores durante as chamadas, selecione a opção **Habilitar anonimato do operador**.

    > [!NOTE]
    > Chamadas anônimas não podem ter início com sistemas de mensagens instantâneas (IM) ou vídeo, embora o operador ou chamadas possam adicionar IM e vídeo depois que a chamada estiver estabelecida. Um operador anônimo também pode colocar chamadas em espera, transferir (transferências ocultas e de consulta), estacionar e recuperar chamadas. Chamadas anônimas não oferecem suporte a conferência, compartilhamento de aplicativos, transferência de arquivos, whiteboarding e colaboração de dados e gravação de chamadas. Os agentes que usam o Plug-in do Lync VDI podem receber chamadas de entrada anonimamente, mas não podem fazer chamadas de saída anonimamente.

10. Em **Inserir endereço do grupo que receberá as chamadas**, digite o endereço do identificador de recurso uniforme (URI) SIP primário do grupo que responderá chamadas do fluxo de trabalho.

    > [!NOTE]
    > O URI principal de um fluxo de trabalho é como o fluxo de trabalho é identificado e referenciado. O URI SIP que você inserir é criado como um objeto de contato nos Serviços de Domínio do Active Directory. Para criar o URI, o objeto deve ser exclusivo no Active Directory.

11. Em **Nome de exibição,** digite o nome que você deseja exibir para o fluxo de trabalho (por exemplo, Grupo de Resposta de Vendas).

    > [!NOTE]
    > Não inclua os caracteres "<" ou ">" no nome de exibição. Não use os seguintes nomes de exibição porque eles são reservados: **RGS Presence Watcher** ou **Announcement Service**.

12. Em **Número de telefone**, digite o URI de linha para o grupo de resposta (por exemplo, +14255550165).

13. Em **Número de exibição**, digite o número como você deseja que seja exibido para o grupo de resposta (por exemplo, +1 (425) 555-0165).

14. (Opcional) Em **Descrição**, digite uma descrição para o fluxo de trabalho conforme você deseja que ele apareça no cartão de visita no Skype for Business.

15. Em **Tipo de fluxo de trabalho**, selecione **Gerenciado** se este fluxo de trabalho será gerenciado pelo Gerente do grupo de resposta. Faça o seguinte para atribuir Gerentes de Grupo de Resposta ao fluxo de trabalho:

    a. Digite o URI SIP de um gerente para esse fluxo de trabalho e clique em **Adicionar**.

    b. Digite o URI SIP de gerentes adicionais para adicionar ao fluxo de trabalho e clique em **Adicionar**.

    > [!IMPORTANT]
    > Todos os usuários designados como gerentes de um grupo de resposta devem ter uma função CsResponseGroupManager. Se os usuário não receberem essa função, não será possível gerenciar grupos de resposta.

16. Em **Etapa 2 Selecionar um idioma**, clique no idioma que você deseja usar para o reconhecimento de fala e conversão de texto em fala.

17. Se você deseja configurar uma mensagem de boas-vindas, em **Etapa 3 Configurar uma mensagem de boas-vindas**, marque a caixa de seleção **Reproduzir uma mensagem de boas-vindas** e faça um dos seguintes:

    - Para inserir uma mensagem de boas vindas como texto convertido para fala para os chamadores, clique em **Usar conversão de texto em fala** e digite a mensagem de boas vindas na caixa de texto.

    > [!NOTE]
    > Não inclua tags HTML no texto inserido. Se incluir tags HTML, você receberá uma mensagem de erro.

    - Para usar um arquivo wave (.wav) ou Windows Media audio (.wma) gravando a mensagem de boas-vindas, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo de áudio que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

    > [!NOTE]
    > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

18. Em **Etapa 4 Especificar seu horário comercial**, em **Seu fuso horário**, clique no fuso horário do fluxo de trabalho.

    > [!NOTE]
    > O fuso horário é o fuso onde os chamadores e agentes do fluxo de trabalho residem. É usado para calcular as horas abertas e fechadas. Por exemplo, se o fluxo de trabalho é configurado para usar o fuso horário Hora do Leste dos Estados Unidos e o fluxo de trabalho está programado para abrir às 7:00 e fechar as 23:00 horas, as horas abertas e fechadas devem ser 7:00 Horário do Leste e 23:00 Horário do Leste, respectivamente. (Você deve inserir as horas no formato de 24 horas.)

19. Selecione o tipo de agenda de horário comercial que deseja usar executando um dos seguintes procedimentos:

    - Para usar uma agenda pré-definida de horário comercial, clique em **Usar uma agenda predefinida** e selecione a agenda que deseja usar na lista suspensa.

      > [!NOTE]
      > Você deve ter definido no mínimo uma agenda predefinida anteriormente para selecionar esta opção. É possível definir agendamentos de predefinições usando o cmdlet **New-CSRgsHoursOfBusiness**. Para obter detalhes, consulte [(Opcional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md).

      > [!NOTE]
      > Ao selecionar uma agenda predefinida, **Dia**, **Abertura** e **Fechamento** são automaticamente preenchidos com os dias e horas em que o grupo de resposta está disponível.

    - Para usar uma agenda personalizada que se aplique somente a este fluxo de trabalho, clique em **Usar uma agenda personalizada**.

20. Se estiver criando uma agenda personalizada para este fluxo de trabalho, clique nas opções para os dias da semana em que o grupo de resposta estará disponível.

21. Se você estiver criando uma agenda  personalizada, digite o horário **de** Abertura e Fechamento para cada dia da semana em que o grupo de resposta está disponível.

    > [!NOTE]
    > As horas de **Abertura** e **Fechamento** devem estar na notação de 24 horas. Por exemplo, se seu escritório funciona em dias úteis das 9 às 5 e fecha ao meio dia para o almoço, o horário comercial é especificado como **Abertura** 9:00, **Fechamento** 12:00, **Abertura** 13:00 e **Fechamento** 17:00.

22. Se você desejar reproduzir uma mensagem quando o escritório não estiver aberto, selecione a opção **Reproduzir uma mensagem quando o grupo de resposta estiver fora do horário comercial** e especifique a mensagem a ser reproduzida executando um dos seguintes procedimentos:

    - Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.

      > [!NOTE]
      > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

    - Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

      > [!NOTE]
      > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivos de áudio com suporte, consulte [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

23. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):

    - Para desconectar a chamada, clique em **Desconectar Chamada**.

    - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço de caixa postal *\<username\>* @ *\<domainName\>* é (por exemplo, bob@contoso.com).

    - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço do usuário é _\<username\>_ @ _\<domainName\>_ .

    - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone *\<number\>* @ *\<domainName\>* é (por exemplo, +14255550121@contoso.com). O nome do domínio é usado para encaminhar o chamador ao destino correto.

24. Sob **Etapa 5 Especifique seus Feriados**, clique nas opções para um ou mais conjuntos de feriados que definem quando o grupo de resposta estará fechado para negócios.

    > [!NOTE]
    > É necessário definir feriados e conjuntos de feriados antes de configurar o fluxo de trabalho. Use os cmdlets **New-CsRgsHoliday** e **New-CsRgsHolidaySet** para definir feriados e conjuntos de feriados. Para obter detalhes, consulte [(Opcional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).

25. Se você deseja reproduzir uma mensagem nos feriados, selecione a opção **Reproduzir uma mensagem durante os feriados** e especifique a mensagem a ser executada realizado um dos seguintes procedimentos:

    - Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.

    > [!NOTE]
    > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

    - Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

      > [!NOTE]
      > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivos de áudio com suporte, consulte [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

26. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):

    - Para desconectar a chamada, clique em **Desconectar Chamada**.

    - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço de caixa postal *\<username\>* @ *\<domainName\>* é (por exemplo, bob@contoso.com).

    - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço do usuário é _\<username\>_ @ _\<domainName\>_ .

    - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone *\<number\>* @ *\<domainName\>* é (por exemplo, +14255550121@contoso.com). O nome do domínio é usado para direcionar o chamador para o destino correto.

27. Em **Etapa 6 Configurar uma fila**, em **Selecionar a fila que irá receber as chamadas**, selecione a fila que deseja manter os chamadores até que um agente se tornar disponível.

28. Em **Etapa 7 Configurar música de espera**, escolha a música que você deseja que os chamadores ouçam enquanto aguardam por um agente, fazendo o seguinte:

    - Para usar a gravação padrão de música de espera, clique em **Usar padrão**.

    - Para usar uma gravação de arquivo de áudio para a música de espera, clique em **Selecionar um arquivo de música**. Se você deseja carregar um novo arquivo de áudio, clique no link **um arquivo de música**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

      > [!NOTE]
      > Todos os arquivos de áudio fornecidos pelo usuário devem cumprir determinados requisitos. Para detalhes sobre formatos de arquivos de áudio com suporte, consulte [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

29. Clique em **Implantar**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a>Para usar Skype for Business Server Shell de Gerenciamento para criar ou modificar um fluxo de trabalho de grupo de busca

1. Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinida que suportam o Grupo de Resposta.

2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**

3. Crie o prompt a ser tocado para a mensagem de boas-vindas e salve-o em uma variável. Na linha de comando, execute:

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    Por exemplo:

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > Para usar um arquivo de áudio no prompt, use o cmdlet **Import-CsRgsAudioFile**. Para obter detalhes, [consulte Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).

4. Obter a identidade da fila ou pergunta para onde as chamadas serão direcionadas. Na linha de comando, execute:

   ```powershell
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    Para obter detalhes sobre como criar a fila, consulte [New-CsRgsQueue](/powershell/module/skype/new-csrgsqueue?view=skype-ps).

5. Defina a ação padrão a ser tomada quando um fluxo de trabalho for aberto durante o horário comercial e salve-o em uma variável. Na linha de comando, execute:

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > Para fluxos de trabalho de grupo de busca, a ação padrão deve direcionar a chamada para uma fila. Esse parâmetro é necessário para fluxos de trabalho ativos. Não é necessário para fluxos de trabalho inativos.

    Por exemplo:

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. Se você quiser definir horário comercial e feriados, você precisa crie-os antes de criar ou modificar o fluxo de trabalho. Para obter detalhes, consulte [(Opcional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).

7. Se você quiser ter prompts para chamadas recebidas fora do horário comercial ou em feriados, use o cmdlet **New-CsRgsPrompt** para definir o prompt e use **o New-CsRgsCallAction** para definir a ação a ser tomada após o prompt. Para obter detalhes, [consulte New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps) e [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps).

8. Recupere o nome do serviço para o serviço grupo de resposta do Lync Server e atribua-o a uma variável. No comando, execute:

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. Crie ou modifique o fluxo de trabalho. Para criar um fluxo de trabalho, use **New-CsRgsWorkflow**. Para modificar um fluxo de trabalho, use **Set-CsRgsWorkflow**. Na linha de comando, digite:

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    Por exemplo:

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > Todos os usuários designados para fluxos de trabalho devem ser atribuídos à função CsResponseGroupManager.

     > [!NOTE]
     > Para obter detalhes sobre parâmetros opcionais adicionais, consulte [New-CsRgsWorkflow](/powershell/module/skype/new-csrgsworkflow?view=skype-ps) ou [Set-CsRgsWorkflow](/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

## <a name="designing-an-interactive-workflow"></a>Projetando um fluxo de trabalho interativo

Você pode usar a ivr (resposta de voz interativa) para obter informações dos chamadores e direcionar a chamada para a fila apropriada. Os pares de perguntas e respostas determinam qual fila usar. Dependendo da resposta do chamador, o chamador ouvirá uma pergunta de acompanhamento ou será roteado para a fila apropriada. As perguntas ivr e as respostas do chamador são fornecidas ao agente que responde que aceita a chamada, fornecendo informações valiosas ao agente.

### <a name="overview-of-ivr-features"></a>Visão geral dos recursos do IVR

O aplicativo grupo de resposta oferece reconhecimento de fala e recursos de texto para fala em 26 idiomas. É possível inserir perguntas IVR usando a conversão texto em fala ou um arquivo wave (.wav) ou Windows Media audio (.wma). Os chamadores podem responder usando a voz ou multifrequência de dois tons (DTMF).

Os fluxos de trabalho interativos suportam até dois níveis de perguntas, com cada pergunta tendo até quatro respostas possíveis. A IVR faz uma pergunta ao chamador e, dependendo da resposta do chamador, encaminha o chamador para uma fila ou faz uma segunda pergunta. A segunda pergunta também pode ter quatro respostas possíveis. Dependendo da resposta à pergunta de segundo nível, o chamador é roteado para a fila adequada.

> [!NOTE]
> Ao projetar fluxos de chamada usando Skype for Business Server Shell de Gerenciamento, você pode definir qualquer número de níveis de perguntas IVR e qualquer número de respostas. No entanto, para melhor usabilidade do chamador, recomendamos que você não use mais de três níveis de perguntas, com não mais do que cinco respostas cada. Além disso, se você projetar um fluxo de chamada que tenha mais de dois níveis de perguntas com mais de quatro respostas cada, não será possível editar o fluxo de chamada usando o Painel de Controle Skype for Business Server.

As perguntas ivr e as respostas do chamador são fornecidas ao agente que responde que aceita a chamada.

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

A figura a seguir mostra o fluxo da chamada.

 **Fluxo de chamada interativa de um nível**

![Projetar fluxos de chamadas usando o Respo de Voz Interativa.](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

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

![Projetar fluxos de chamadas usando o Respo de Voz Interativa.](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a>Práticas recomendadas

A lista a seguir descreve algumas práticas recomendadas para projetar sua IVR:

- Permita que o chamador chegue à tarefa rapidamente. Evite oferecer muita informação ou mensagens de marketing longas em sua IVR.

- Se você deseja incluir uma mensagem longa, considere anexá-la à primeira pergunta ao invés da mensagem de boas-vindas. Os chamadores podem ignorar a mensagem se fizer parte da primeira pergunta respondendo à pergunta, mas não podem ignorar a mensagem de boas-vindas.

- Fale no idioma do chamador. Evite usar uma linguagem refinada. Fale naturalmente.

- Grave prompts eficazes e eficientes. Remova qualquer opção desnecessária. Estruturar as informações para que a resposta esperada do chamador seja no final da frase. Por exemplo, "Para falar com a equipe de vendas, pressione 1".

- Torne as respostas de voz fáceis. Por exemplo, se você especificar as respostas DTMF e voz, use algo como: "Para falar com a equipe de vendas, pressione 1 ou diga vendas."

- Teste a IVR em um grupo de usuários antes de implantar na sua organização.

## <a name="creating-or-modifying-an-interactive-workflow"></a>Criar ou modificar um fluxo de trabalho interativo

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>Para usar a Ferramenta de Configuração de Grupo de Resposta para criar ou modificar um fluxo de trabalho Interativo

1. Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinida que suportam o Grupo de Resposta.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.

4. Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.

5. No campo de pesquisa **Selecionar um serviço**, digite parte ou o nome inteiro do serviço **ApplicationServer** que hospeda o fluxo de trabalho que deseja criar ou modificar. Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.

    > [!NOTE]
    > A Ferramenta de Configuração do Grupo de Resposta é aberta. Você também pode abrir a Ferramenta de Configuração de Grupo de Resposta diretamente de um navegador da Web digitando a seguinte URL: \<webPoolFqdn\> https:// /RgsConfig.

6. Siga um destes procedimentos:

   - Em **Criar um Novo Fluxo de Trabalho**, ao lado de **Interativo**, clique em **Criar**.

   - Em **Gerenciar um Fluxo de Trabalho Existente**, localize o fluxo de trabalho que você deseja alterar e, em **Ação**, clique em **Editar**.

7. Se ainda não estiver tudo pronto para os usuários começarem a chamar o fluxo de trabalho, desmarque a caixa de seleção **Ativar o fluxo de trabalho**.

    > [!NOTE]
    >  Se você estiver criando um fluxo de trabalho gerenciado, será necessário selecionar **Ativar o fluxo de trabalho**. Depois de salvar o fluxo de trabalho ativo e gerenciado, você pode modificá-lo e desativá-lo.

8. Para permitir que usuários federados façam chamadas para o grupo, selecione a opção **Habilitar para federação**. Você também deve ter uma política de acesso externo que se aplique ao aplicativo do Grupo de Resposta configurado para federação.

    > [!NOTE]
    > A política de acesso externo global se aplica ao aplicativo grupo de resposta. Você pode configurar a política global para federação de grupo de resposta usando o Painel de Controle Skype for Business Server ou usando o cmdlet **Set-CsExternalAccessPolicy** para definir o parâmetro EnableOutsideAccess como True. Lembre-se de que as configurações de política global se aplicam a todos os usuários a não ser que sejam atribuídos a um site ou uma política de usuário. Portanto, antes de alterar essa configuração para grupos de resposta, verifique se a configuração de federação atende aos requisitos da sua organização. Para obter detalhes sobre como as políticas se aplicam aos usuários, consulte [Manage External Access Policy for Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-manage-external-access-policy-for-your-organization). Para obter detalhes sobre a configuração de federação, consulte **Set-CsExternalAccessPolicy** na documentação..

    > [!NOTE]
    > Os usuários hospedados no Skype for Business Online não podem fazer chamadas para grupos de resposta hospedados em uma implantação local. Isso é verdadeiro em implantações híbridas e em casos em que uma implantação local é federada com uma implantação Skype for Business Online.

9. Para ocultar a identidade de operadores durante as chamadas, selecione a opção **Habilitar anonimato do operador**.

    > [!NOTE]
    > Chamadas anônimas não podem ter início com sistemas de mensagens instantâneas (IM) ou vídeo, embora o operador ou chamadas possam adicionar IM e vídeo depois que a chamada estiver estabelecida. Um operador anônimo também pode colocar chamadas em espera, transferir (transferências ocultas e de consulta), estacionar e recuperar chamadas. Chamadas anônimas não oferecem suporte a conferência, compartilhamento de aplicativos, transferência de arquivos, whiteboarding e colaboração de dados e gravação de chamadas. Os agentes que usam o Plug-in do Lync VDI podem receber chamadas de entrada anonimamente, mas não podem fazer chamadas de saída anonimamente.

10. Em **Inserir endereço do grupo que receberá as chamadas**, digite o endereço do identificador de recurso uniforme (URI) SIP primário do grupo que responderá chamadas do fluxo de trabalho.

11. Em **Nome de exibição**, digite o nome que deseja exibir no fluxo de trabalho (por exemplo, Serviço de resposta IVR de vendas).

    > [!NOTE]
    > Não inclua os \<" or "\> caracteres " " no nome de exibição. Não use os seguintes nomes de exibição porque eles são reservados: **RGS Presence Watcher** ou **Announcement Service**.

12. Em **Número de telefone**, digite o URI de linha para o grupo de resposta (por exemplo, +14255550165).

13. Em **Número de Exibição**, digite o número conforme deseja que apareça para o grupo de resposta  (por exemplo, +1 (425) 555-0165).

14. (Opcional) Em **Descrição**, digite uma descrição do fluxo de trabalho que você deseja que apareça no cartão de visita Skype for Business.

15. Em **Tipo de fluxo de trabalho**, selecione **Gerenciado** se este fluxo de trabalho será gerenciado pelo Gerente do grupo de resposta. Faça o seguinte para atribuir Gerentes de Grupo de Resposta ao fluxo de trabalho:

    a. Digite o URI SIP de um gerente para esse fluxo de trabalho e clique em **Adicionar**.

    b. Digite o URI SIP de gerentes adicionais para adicionar ao fluxo de trabalho e clique em **Adicionar**.

    > [!IMPORTANT]
    > Todos os usuários designados como gerentes de um grupo de resposta devem ter uma função CsResponseGroupManager. Se os usuário não receberem essa função, não será possível gerenciar grupos de resposta.

16. Sob **Etapa 2 Selecione um Idioma**, clique no idioma a ser usado para o reconhecimento de fala e conversão de texto em fala.

17. Se você deseja configurar uma mensagem de boas vindas, sob **Etapa 3 Configure uma Mensagem de Boas Vindas**, selecione a opção **Reproduzir uma mensagem de boas vindas** e execute um dos seguintes procedimentos:

    - Para inserir uma mensagem de boas vindas como texto convertido para fala para os chamadores, clique em **Usar conversão de texto em fala** e digite a mensagem de boas vindas na caixa de texto.

    > [!NOTE]
    > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

    - Para usar uma gravação de arquivo Wave ou Windows Media Audio para a mensagem de boas vindas, clique em **Selecione uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na janela do navegador, clique em **Procurar**, selecione o arquivo de áudio que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

    > [!NOTE]
    > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

18. Sob **Etapa 4 Especifique seus Horários Comerciais**, na caixa **Seu fuso horário**, clique no fuso horário do fluxo de trabalho.

    > [!NOTE]
    > O fuso horário é onde os chamadores e operadores do fluxo de trabalho residem. Ele é usado para calcular os horários de abertura e encerramento. Por exemplo, se o fluxo de trabalho está configurado para usar o fuso horário da costa leste norte-americana e o fluxo de trabalho estiver agendado para abrir às 7:00 A.M e fechar às 11:00 P.M., os horários de abertura e fechamento são assumidos como sendo 7:00 horário da costa leste e 11:00:00 horário da costa leste, respectivamente (você deve inserir os horários na notação de 24 horas).

19. Selecione o tipo de agenda de horário comercial que deseja usar executando um dos seguintes procedimentos:

    - Para usar uma agenda pré-definida de horário comercial, clique em **Usar uma agenda predefinida** e selecione a agenda que deseja usar na lista suspensa.

      > [!NOTE]
      > Você deve ter definido no mínimo uma agenda predefinida anteriormente para selecionar esta opção. Você define cronogramas predefinidos usando o cmdlet **New-CsRgsHoursOfBusiness.** Para obter detalhes, consulte [(Opcional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md). Ao selecionar uma agenda predefinida, **Dia**, **Abertura** e **Fechamento** são automaticamente preenchidos com os dias e horas em que o grupo de resposta está disponível.

    - Para usar uma agenda personalizada que se aplique somente a este fluxo de trabalho, clique em **Usar uma agenda personalizada**.

20. Se estiver criando uma agenda personalizada para este fluxo de trabalho, clique nas opções para os dias da semana em que o grupo de resposta estará disponível.

21. Se você estiver criando uma agenda personalizada, digite o **horário de Abertura** e Fechamento quando o grupo de resposta estará disponível. 

     > [!NOTE]
     > As horas de **Abertura** e **Fechamento** devem estar na notação de 24 horas. Por exemplo, se seu escritório funciona em dias úteis das 9 às 5 e fecha ao meio dia para o almoço, o horário comercial é especificado como **Abertura** 9:00, **Fechamento** 12:00, **Abertura** 13:00 e **Fechamento** 17:00.

22. Se você desejar reproduzir uma mensagem quando o escritório não estiver aberto, selecione a opção **Reproduzir uma mensagem quando o grupo de resposta estiver fora do horário comercial** e especifique a mensagem a ser reproduzida executando um dos seguintes procedimentos:

    - Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.

      > [!NOTE]
      > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

    - Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

    > [!NOTE]
    > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

23. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):

    - Para desconectar a chamada, clique em **Desconectar Chamada**.

    - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço de caixa postal *\<username\>* @ *\<domainname\>* é (por exemplo, bob@contoso.com).

    - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço do usuário é _\<username\>_ @ _\<domainname\>_ .

    - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone *\<number\>* @ *\<domainname\>* é (por exemplo, +14255550121@contoso.com). O nome do domínio é usado para encaminhar o chamador ao destino correto.

24. Sob **Etapa 5 Especifique seus Feriados**, clique nas opções para um ou mais conjuntos de feriados que definem quando o grupo de resposta estará fechado para negócios.

    > [!NOTE]
    > É necessário definir feriados e conjuntos de feriados antes de configurar o fluxo de trabalho. Use os cmdlets **New-CsRgsHoliday** e **New-CsRgsHolidaySet** para definir feriados e conjuntos de feriados. Para obter detalhes, consulte [(Opcional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).

25. Se você deseja reproduzir uma mensagem nos feriados, selecione a opção **Reproduzir uma mensagem durante os feriados** e especifique a mensagem a ser executada realizado um dos seguintes procedimentos:

    - Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.

      > [!NOTE]
      > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

    - Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

      > [!NOTE]
      > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivos de áudio com suporte, consulte [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

26. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):

    - Para desconectar a chamada, clique em **Desconectar Chamada**.

    - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço de caixa postal *\<username\>* @ *\<domainname\>* é (por exemplo, bob@contoso.com).

    - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço do usuário é _\<username\>_ @ _\<domainname\>_ .

    - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone *\<number\>* @ *\<domainname\>* é (por exemplo, +14255550121@contoso.com). O nome do domínio é usado para encaminhar o chamador ao destino correto.

27. Sob **Etapa 6 Configure a Música de Espera**, escolha o que deseja que os chamadores ouçam enquanto esperam por um operador, executando um dos seguintes procedimentos:

    - Para usar a gravação padrão de música em espera, clique em **Usar padrão**.

    - Para usar uma gravação de arquivo de áudio como música de espera, clique em **Selecionar um arquivo de música**. Se você deseja carregar um novo arquivo de áudio, clique no link **um arquivo de música**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.

    > [!NOTE]
    > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

28. Sob **Etapa 7 Configure a Resposta Interativa de Voz**, sob o cabeçalho **O usuário ouvirá o seguinte texto ou mensagem gravada**, especifique a pergunta a ser feita aos chamadores da seguinte forma:

    - Para digitar uma pergunta em formato de texto, clique em **Usar conversão de texto em fala** e digite a pergunta na caixa de texto.

    > [!NOTE]
    > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

    > [!NOTE]
    > O símbolo "#" é traduzido pelo mecanismo de conversão de texto em fala como a palavra "número". Se for necessário fazer referência à tecla #, use o nome da tecla no prompt, em vez do símbolo. Por exemplo, "Para falar com vendas, pressione a tecla jogo da velha."

    - Para usar um arquivo de áudio pré-gravado que contenha a pergunta, clique em **Selecionar uma gravação** e clique no link **uma gravação** para carregar o arquivo. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo de áudio e clique em **Abrir**. Clique **Upload** carregar o arquivo e, opcionalmente, você pode digitar a pergunta na caixa de texto (isso permite que a pergunta e a resposta do chamador sejam encaminhadas para o agente que responde).

      > [!NOTE]
      > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para detalhes sobre formatos de arquivo com suporte, consulte [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).

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

31. Especifique até três mais respostas possíveis para a pergunta original, repetindo as etapas 28 e 29 para especificar as possíveis respostas e a ação para cada resposta. Para especificar uma terceira ou quarta resposta possível, clique na caixa de seleção **Resposta 3** ou **Resposta 4**.

32. Clique em **Implantar**.

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a>Para usar Skype for Business Server Shell de Gerenciamento para criar ou modificar um fluxo de trabalho Interativo

1.  Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinida que suportam o Grupo de Resposta.

2. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** clique em Todos os **Programas,** clique Skype for Business **2015** e clique **em Skype for Business Server Shell de Gerenciamento.**

3. Recupere o nome do serviço do serviço de Grupo de resposta e atribua-o a uma variável. Na linha de comando, execute:

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
     > Todos os usuários designados como gerentes de um grupo de resposta devem ser atribuídos à função CsResponseGroupManager. Se os usuário não têm essa função, não será possível gerenciar grupos de resposta.

## <a name="see-also"></a>Confira também

[(Opcional) Definir conjuntos de feriados do Grupo de Resposta Skype for Business](optional-define-response-group-holiday-sets.md)

[(Opcional) Definir o horário comercial do Grupo de Resposta em Skype for Business](optional-define-response-group-business-hours.md)

[New-CsRgsWorkflow](/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[Set-CsRgsWorkflow](/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)