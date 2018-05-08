---
title: Conceber e criar fluxos de trabalho do Grupo de Resposta no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: Projetar e criar fluxos de trabalho do grupo de resposta, no Skype para Business Server Enterprise Voice. São abordados os fluxos de trabalho interativos e do grupo de busca.
ms.openlocfilehash: 71380d7dc048663eca9543a31d67462ead0321c3
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business-2015"></a>Conceber e criar fluxos de trabalho do Grupo de Resposta no Skype for Business 2015
 
Projetar e criar fluxos de trabalho do grupo de resposta, no Skype para Business Server Enterprise Voice. São abordados os fluxos de trabalho interativos e do grupo de busca.
  
Um fluxo de trabalho define o comportamento de uma chamada desde a hora que o telefone toca até a hora que alguém atende essa chamada. O fluxo de trabalho Especifica a fila a ser usada para manter a chamada e especifica o método de roteamento a ser usado para fluxos de trabalho de grupo de busca ou as perguntas e respostas a ser usado para fluxos de trabalho de grupo de resposta interativa. 
  
Um fluxo de trabalho também define configurações, como a mensagem de boas-vindas, a música de espera, o horário comercial e os feriados.
  
> [!NOTE]
> Você deve criar grupos de agente e filas antes de criar um fluxo de trabalho que os utiliza. 
  
## <a name="creating-or-modifying-a-hunt-group-workflow"></a>Criar ou modificar um fluxo de trabalho do grupo de busca

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>Usar a ferramenta de configuração de grupo de resposta para criar ou modificar um fluxo de trabalho do grupo de busca

1. Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.
    
4. Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.
    
5. No campo de pesquisa **Selecionar um serviço** , digite todo ou parte do nome do serviço **ApplicationServer** que hospeda o fluxo de trabalho que você deseja criar ou alterar. Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.
    
    > [!NOTE]
    > Abre a ferramenta de configuração de grupo de resposta. Você também pode abrir a ferramenta de configuração de grupo de resposta diretamente a partir de um navegador da web, digitando o seguinte URL: https:// _ \<webPoolFqdn\>_/RgsConfig. 
  
6. Siga um destes procedimentos:
    
   - Em **Criar um Novo Fluxo de Trabalho**, próximo ao **Grupo de busca, clique em Criar**.
    
   - Em **Gerenciar um Fluxo de Trabalho Existente**, localize o fluxo de trabalho que você deseja alterar e, em **Ação**, clique em **Editar**.
    
7. Se estiver pronto para que os usuários comecem a fazer chamadas para o fluxo de trabalho, selecione **Ativar o fluxo de trabalho**.
    
    > [!NOTE]
    >  Se você estiver criando um fluxo de trabalho gerenciado, é necessário selecionar **Ativar o fluxo de trabalho**. Após salvar o fluxo de trabalho gerenciado ativo, é possível modificar e desativá-lo. 
  
8. Para permitir que usuários federados façam chamadas para o grupo, selecione a opção **Habilitar para federação**. Você também deve ter uma política de acesso externo que se aplica ao aplicativo grupo de resposta configurado para federação.
    
    > [!NOTE]
    > A política de acesso externo global aplica-se ao aplicativo grupo de resposta. Você pode configurar a política global para federação de grupo de resposta usando Skype para o painel de controle do Business Server ou usando o cmdlet **Set-CsExternalAccessPolicy** para definir o parâmetro EnableOutsideAccess como True. Lembre-se que as configurações de política global se aplicam a todos os usuários, a não ser que eles sejam atribuídos com uma política de usuário ou de site. Portanto, antes de alterar esta configuração para grupos de resposta, certifique-se de que as configurações de federação cumpre os requisitos da sua organização. Para obter detalhes sobre como as políticas se aplicam aos usuários, consulte [Gerenciar política de acesso externo para sua organização](http://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx). Para obter detalhes sobre a configuração de federação, consulte [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps). 
  
    > [!NOTE]
    > Usuários hospedados no Skype para Business Online não podem fazer chamadas para os grupos de resposta hospedadas em uma implantação no local. Isso é verdadeiro em ambas as implantações híbridas e, em casos onde uma implantação no local é federada com um Skype para implantação Business Online. 
  
9. Para ocultar a identidade de operadores durante as chamadas, selecione a opção **Habilitar anonimato do operador**.
    
    > [!NOTE]
    > Chamadas anônimas não podem ter início com sistemas de mensagens instantâneas (IM) ou vídeo, embora o operador ou chamadas possam adicionar IM e vídeo depois que a chamada estiver estabelecida. Um operador anônimo também pode colocar chamadas em espera, transferir (transferências ocultas e de consulta), estacionar e recuperar chamadas. Chamadas anônimas não oferecem suporte a conferência, compartilhamento de aplicativos, transferência de arquivos, whiteboarding e colaboração de dados e gravação de chamadas. Agentes utilizando o Plugin Lync VDI podem atender chamadas em entrada anonimamente, mas não podem realizar chamadas em saída anonimamente. 
  
10. Sob **Insira o endereço do grupo que receberá as chamadas**, digite o endereço URI SIP primário do grupo que irá receber chamadas para o fluxo de trabalho.
    
    > [!NOTE]
    > O URI primário para um fluxo de trabalho é como o fluxo de trabalho é identificado e referenciado. O URI do SIP inserido é criado como um objeto de contato nos serviços de domínio Active Directory. Para criar o URI, o objeto deve ser exclusivo no Active Directory. 
  
11. Em **nome para exibição**, digite o nome que você deseja exibir no fluxo de trabalho (por exemplo, grupo de resposta de vendas).
    
    > [!NOTE]
    > Não inclua os caracteres "<" ou ">" no nome de exibição. Não use os nomes de exibição a seguir, pois são reservados: **Observador de Presença RG** ou **Serviço de Anúncio**. 
  
12. Sob **Número de telefone**, digite o URI de linha para o grupo de resposta (por exemplo, +14255550165).
    
13. Em **Número de Exibição**, digite o número conforme deseja que apareça para o grupo de resposta (por exemplo, +1 (425) 555-0165).
    
14. (Opcional) Em **Descrição**, digite uma descrição para o fluxo de trabalho como você deseja que ele apareça no cartão de visita, do Skype para negócios.
    
15. Em **Tipo de fluxo de trabalho**, selecione **Gerenciado** se este fluxo de trabalho será gerenciado por um Gerente o Grupo de Resposta. Faça o seguinte para atribuir gerentes do grupo de resposta ao fluxo de trabalho:
    
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
    > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para obter detalhes sobre os formatos de arquivo com suporte, consulte [Requisitos técnicos para grupos de resposta](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
18. Sob **Etapa 4 Especifique seu Horário Comercial**, em **Seu fuso horário**, clique no fuso horário para o fluxo de trabalho.
    
    > [!NOTE]
    > O fuso horário é onde os chamadores e operadores do fluxo de trabalho residem. Ele é usado para calcular os horários de abertura e encerramento. Por exemplo, se o fluxo de trabalho está configurado para usar o fuso horário da costa leste norte-americana e o fluxo de trabalho estiver agendado para abrir às 7:00 A.M e fechar às 11:00 P.M., os horários de abertura e fechamento são assumidos como sendo 7:00 horário da costa leste e 23:00 horário da costa leste, respectivamente (você deve inserir os horários na notação de 24 horas). 
  
19. Selecione o tipo de agenda de horário comercial que deseja usar executando um dos seguintes procedimentos:
    
   - Para usar uma agenda pré-definida de horário comercial, clique em **Usar uma agenda predefinida** e selecione a agenda que deseja usar na lista suspensa.
    
     > [!NOTE]
     > Você deve ter definido no mínimo uma agenda predefinida anteriormente para selecionar esta opção. É possível definir agendamentos de predefinições usando o cmdlet **New-CSRgsHoursOfBusiness**. Para obter detalhes, consulte [horário comercial de grupo de resposta (opcional) definir no Skype para negócios 2015](optional-define-response-group-business-hours.md). 
  
     > [!NOTE]
     > Ao selecionar uma agenda predefinida, **Dia**, **Abertura** e **Fechamento** são automaticamente preenchidos com os dias e horas em que o grupo de resposta está disponível.
  
   - Para usar uma agenda personalizada que se aplique somente a este fluxo de trabalho, clique em **Usar uma agenda personalizada**.
    
20. Se estiver criando uma agenda personalizada para este fluxo de trabalho, clique nas opções para os dias da semana em que o grupo de resposta estará disponível.
    
21. Se estiver criando uma agenda personalizada, digite as horas de **Abertura** e **Fechamento** para cada dia da semana em que o grupo de resposta estará disponível.
    
    > [!NOTE]
    > As horas de **Abertura** e **Fechamento** devem estar na notação de 24 horas. Por exemplo, se seu escritório funciona em dias úteis das 9 às 5 e fecha ao meio dia para o almoço, o horário comercial é especificado como **Abertura** 9:00, **Fechamento** 12:00, **Abertura** 13:00 e **Fechamento** 17:00.
  
22. Se você desejar reproduzir uma mensagem quando o escritório não estiver aberto, selecione a opção **Reproduzir uma mensagem quando o grupo de resposta estiver fora do horário comercial** e especifique a mensagem a ser reproduzida executando um dos seguintes procedimentos:
    
   - Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.
    
     > [!NOTE]
     > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro. 
  
   - Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.
    
     > [!NOTE]
     > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para obter detalhes sobre os formatos de arquivo de áudio com suporte, consulte [Requisitos técnicos para grupos de resposta](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
23. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):
    
   - Para desconectar a chamada, clique em **Desconectar Chamada**.
    
   - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço da caixa postal é _ \<username\>_@ _\<domainName\> _ (por exemplo, bob@contoso.com).
    
   - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço do usuário é _ \<username\>_@ _\<domainName\>_.
    
   - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone é _ \<número\>_@ _\<domainName\> _ (por exemplo, +14255550121@contoso.com). O nome do domínio é usado para encaminhar o chamador ao destino correto.
    
24. Sob **Etapa 5 Especifique seus Feriados**, clique nas opções para um ou mais conjuntos de feriados que definem quando o grupo de resposta estará fechado para negócios.
    
    > [!NOTE]
    > É necessário definir feriados e conjuntos de feriados antes de configurar o fluxo de trabalho. Use os cmdlets **New-CsRgsHoliday** e **New-CsRgsHolidaySet** para definir feriados e conjuntos de feriados. Para obter detalhes, consulte [os conjuntos de feriados do grupo de resposta (opcional) definir no Skype para negócios 2015](optional-define-response-group-holiday-sets.md). 
  
25. Se você deseja reproduzir uma mensagem nos feriados, selecione a opção **Reproduzir uma mensagem durante os feriados** e especifique a mensagem a ser executada realizado um dos seguintes procedimentos:
    
  - Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.
    
    > [!NOTE]
    > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro. 
  
   - Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.
    
     > [!NOTE]
     > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para obter detalhes sobre os formatos de arquivo de áudio com suporte, consulte [Requisitos técnicos para grupos de resposta](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
26. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):
    
   - Para desconectar a chamada, clique em **Desconectar Chamada**.
    
   - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço da caixa postal é _ \<username\>_@ _\<domainName\> _ (por exemplo, bob@contoso.com).
    
   - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço do usuário é _ \<username\>_@ _\<domainName\>_.
    
   - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone é _ \<número\>_@ _\<domainName\> _ (por exemplo, +14255550121@contoso.com). O nome do domínio é usado para encaminhar o chamador ao destino correto.
    
27. Sob **Etapa 6 Configure uma Fila**, em **Selecione a fila que receberá as chamadas**, selecione a fila que você deseja que segure as chamadas até que um operador torne-se disponível.
    
28. Sob **Etapa 7 Configure Música de Espera**, escolha a música que deseja que os chamadores ouçam enquanto esperam que um operador, executando um dos seguintes procedimentos:
    
   - Para usar a gravação padrão de música de espera, clique em **Usar padrão**.
    
   - Para usar uma gravação de arquivo de áudio para a música de espera, clique em **Selecionar um arquivo de música**. Se você deseja carregar um novo arquivo de áudio, clique no link **um arquivo de música**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.
    
     > [!NOTE]
     > Todos os arquivos de áudio fornecidos pelo usuário devem atender determinados requisitos. Para obter detalhes sobre os formatos de arquivo de áudio com suporte, consulte [Requisitos técnicos para grupos de resposta](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
29. Clique em **Implantar**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a>Usar Skype para Business Server Management Shell para criar ou modificar um fluxo de trabalho do grupo de busca

1. Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Crie o prompt a ser reproduzido na mensagem de boas-vindas e salve-o como uma variável. Na linha de comando, execute:
    
   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    Por exemplo:
    
   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > Para usar um arquivo de áudio para o prompt, use o cmdlet **Import-CsRgsAudioFile** . Para obter detalhes, consulte [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
4. Obtenha a identidade da fila ou pergunta onde as chamadas serão direcionadas. Na linha de comando, execute:
    
   ```
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    Para obter detalhes sobre como criar filas, consulte [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps).
    
5. Defina a ação padrão a ser realizada quando um fluxo de trabalho é aberto durante o horário comercial e salve-o em uma variável. Na linha de comando, execute:
    
   ```
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > Para fluxos de trabalho do grupo de busca, a ação padrão deve direcionar a chamada para uma fila. Este parâmetro é necessário para fluxos de trabalho ativos. Não é necessário para fluxos de trabalho inativos. 
  
    Por exemplo:
    
   ```
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. Se você deseja definir o horário comercial e feriados, é necessário criá-los antes de criar ou modificar o fluxo de trabalho. Para obter detalhes, consulte [horário comercial de grupo de resposta (opcional) definir no Skype para negócios 2015](optional-define-response-group-business-hours.md) e [conjuntos de feriados do grupo de resposta (opcional) definir no Skype para negócios 2015](optional-define-response-group-holiday-sets.md).
    
7. Se você quiser prompts de chamadas recebidas fora do horário comercial ou em feriados, use o cmdlet **New-CsRgsPrompt** para definir o prompt e use o **New-CsRgsCallAction** para definir a ação a ser executada após o aviso. Para obter detalhes, consulte [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) e [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).
    
8. Recuperar o nome de serviço para o serviço de grupo de resposta do Lync Server e atribuí-la a uma variável. No comando, execute:
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. Criar ou modificar o fluxo de trabalho. Para criar um fluxo de trabalho, use **New-CsRgsWorkflow**. Para modificar um fluxo de trabalho, utilize **Set-CsRgsWorkflow**. Na linha de comando, digite:
    
   ```
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    Por exemplo:
    
   ```
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > Todos os usuários que são gerentes para fluxos de trabalho devem ser atribuídos à função CsResponseGroupManager. 
  
     > [!NOTE]
     > Para obter detalhes sobre parâmetros opcionais adicionais, consulte [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) ou [Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)
  
## <a name="designing-an-interactive-workflow"></a>Projetando um fluxo de trabalho interativo

Você pode usar uma resposta de voz interativa (IVR) para obter informações dos chamadores e direcionar a chamada para a fila apropriada. Os pares de perguntas e respostas determinam qual fila a ser usada. Dependendo da resposta do chamador, o chamador ouve uma pergunta de acompanhamento tanto é roteado para a fila apropriada. As perguntas IVR e as respostas do chamador são fornecidas ao operador que a aceitar a chamada, fornecendo informações valiosas ao operador.
  
### <a name="overview-of-ivr-features"></a>Visão geral dos recursos do IVR

O aplicativo de grupo de resposta oferece reconhecimento de fala e recursos de texto em fala em 26 idiomas. É possível inserir perguntas IVR usando a conversão texto em fala ou um arquivo wave (.wav) ou Windows Media audio (.wma). Os chamadores podem responder usando a voz ou multifrequência de dois tons (DTMF).
  
Os fluxos de trabalho interativos suportam até dois níveis de perguntas, com cada pergunta tendo até quatro respostas possíveis. IVR faz o chamador uma pergunta e dependendo da resposta do chamador, encaminha o chamador para uma fila ou solicita uma segunda pergunta. A segunda pergunta também pode ter quatro respostas possíveis. Dependendo da resposta à pergunta de segundo nível, o chamador é roteado para a fila adequada.
  
> [!NOTE]
> Ao criar fluxos de chamada usando Skype do Shell de gerenciamento do servidor de negócios, você pode definir qualquer números níveis de perguntas IVR e qualquer número de respostas. No entanto, para melhor usabilidade do chamador, recomendamos que você não use mais de três níveis de perguntas, com não mais do que cinco respostas cada. Além disso, se você estiver desenvolvendo um fluxo de chamadas que tem mais de dois níveis de perguntas com mais de quatro respostas, você não pode editar o fluxo de chamadas usando Skype para o painel de controle do servidor de negócios. 
  
As perguntas IVR e as respostas do chamador são fornecidas ao operador que aceita a chamada.
  
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
  
![Projetar fluxos de chamada usando a resposta de voz interativa](../../media/Ops_OCS_RGS_IVRLevel1.jpg)
  
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
  
![Projetar fluxos de chamada usando a resposta de voz interativa](../../media/Ops_OCS_RGS_IVRLevel2.jpg)
  
### <a name="best-practices"></a>Práticas recomendadas

A lista a seguir descreve algumas práticas recomendadas para projetar sua IVR:
  
- Permita que o chamador chegue à tarefa rapidamente. Evite oferecer muita informação ou mensagens de marketing longas em sua IVR.
    
- Se você deseja incluir uma mensagem longa, considere anexá-la à primeira pergunta ao invés da mensagem de boas-vindas. Os chamadores podem ignorar a mensagem se fizer parte da primeira pergunta respondendo à pergunta, mas não podem ignorar a mensagem de boas-vindas.
    
- Fale no idioma do chamador. Evite usar uma linguagem refinada. Fale naturalmente.
    
- Grave prompts eficazes e eficientes. Remova qualquer opção desnecessária. Estruture as informações de modo que a resposta esperada do chamador está no final da frase. Por exemplo, "Para falar com a equipe de venda, pressione 1".
    
- Torne as respostas de voz fáceis. Por exemplo, se você especificar as respostas DTMF e voz, use algo como: "Para falar com a equipe de vendas, pressione 1 ou diga vendas."
    
- Teste a IVR em um grupo de usuários antes de implantar na sua organização.
    
## <a name="creating-or-modifying-an-interactive-workflow"></a>Criando ou modificando um fluxo de trabalho interativo

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>Usar a ferramenta de configuração de grupo de resposta para criar ou modificar um fluxo de trabalho interativo

1. Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.
    
4. Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.
    
5. No campo de pesquisa **Selecionar um serviço** , digite todo ou parte do nome do serviço **ApplicationServer** que hospeda o fluxo de trabalho que você deseja criar ou modificar. Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.
    
    > [!NOTE]
    > Abre a ferramenta de configuração de grupo de resposta. Você também pode abrir a ferramenta de configuração de grupo de resposta diretamente a partir de um navegador da web, digitando o seguinte URL: https:// _ \<webPoolFqdn\>_/RgsConfig. 
  
6. Siga um destes procedimentos:
    
   - Em **Criar um Novo Fluxo de Trabalho**, ao lado de **Interativo**, clique em **Criar**.
    
   - Em **Gerenciar um Fluxo de Trabalho Existente**, localize o fluxo de trabalho que você deseja alterar e, em **Ação**, clique em **Editar**.
    
7. Se ainda não estiver tudo pronto para os usuários começarem a chamar o fluxo de trabalho, desmarque a caixa de seleção **Ativar o fluxo de trabalho**.
    
    > [!NOTE]
    >  Se você estiver criando um fluxo de trabalho gerenciado, é necessário selecionar **Ativar o fluxo de trabalho**. Após salvar o fluxo de trabalho gerenciado ativo, é possível modificar e desativá-lo. 
  
8. Para permitir que usuários federados façam chamadas para o grupo, selecione a opção **Habilitar para federação**. Você também deve ter uma política de acesso externo que se aplica ao aplicativo grupo de resposta configurado para federação.
    
    > [!NOTE]
    > A política de acesso externo global aplica-se ao aplicativo grupo de resposta. Você pode configurar a política global para federação de grupo de resposta usando Skype para o painel de controle do Business Server ou usando o cmdlet **Set-CsExternalAccessPolicy** para definir o parâmetro EnableOutsideAccess como True. Lembre-se que as configurações de política global se aplicam a todos os usuários, a não ser que eles sejam atribuídos com uma política de usuário ou de site. Portanto, antes de alterar esta configuração para grupos de resposta, certifique-se de que as configurações de federação cumpre os requisitos da sua organização. Para obter detalhes sobre como as políticas se aplicam aos usuários, consulte [Gerenciar política de acesso externo para sua organização](http://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx). Para obter detalhes sobre a configuração de federação, consulte **Set-CsExternalAccessPolicy** na documentação..
  
    > [!NOTE]
    > Usuários hospedados no Skype para Business Online não podem fazer chamadas para os grupos de resposta hospedadas em uma implantação no local. Isso é verdadeiro em ambas as implantações híbridas e, em casos onde uma implantação no local é federada com um Skype para implantação Business Online. 
  
9. Para ocultar a identidade de operadores durante as chamadas, selecione a opção **Habilitar anonimato do operador**.
    
    > [!NOTE]
    > Chamadas anônimas não podem ter início com sistemas de mensagens instantâneas (IM) ou vídeo, embora o operador ou chamadas possam adicionar IM e vídeo depois que a chamada estiver estabelecida. Um operador anônimo também pode colocar chamadas em espera, transferir (transferências ocultas e de consulta), estacionar e recuperar chamadas. Chamadas anônimas não oferecem suporte a conferência, compartilhamento de aplicativos, transferência de arquivos, whiteboarding e colaboração de dados e gravação de chamadas. Agentes utilizando o Plugin Lync VDI podem atender chamadas em entrada anonimamente, mas não podem realizar chamadas em saída anonimamente. 
  
10. Sob **Insira o endereço do grupo que receberá as chamadas**, digite o endereço URI SIP primário do grupo que irá receber chamadas para o fluxo de trabalho.
    
11. Em **Nome de exibição**, digite o nome que deseja exibir no fluxo de trabalho (por exemplo, Serviço de resposta IVR de vendas).
    
    > [!NOTE]
    > Não inclua o "\<"ou"\>" caracteres no nome de exibição. Não use os nomes de exibição a seguir, pois são reservados: Observador de Presença RG ou Serviço de Anúncio. 
  
12. Em **Número de telefone**, digite o URI de linha para o grupo de resposta (por exemplo, +14255550165).
    
13. Em **Número de Exibição**, digite o número conforme deseja que apareça para o grupo de resposta (por exemplo, +1 (425) 555-0165).
    
14. (Opcional) Em **Descrição**, digite uma descrição para o fluxo de trabalho que você deseja que apareça no cartão de visita, do Skype para negócios. 
    
15. Em **Tipo de fluxo de trabalho**, selecione **Gerenciado** se este fluxo de trabalho será gerenciado por um Gerente o Grupo de Resposta. Faça o seguinte para atribuir gerentes do grupo de resposta ao fluxo de trabalho:
    
    a. Digite o URI SIP de um gerente deste fluxo de trabalho e clique em **Adicionar**.
    
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
    > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para obter detalhes sobre os formatos de arquivo com suporte, consulte [Requisitos técnicos para grupos de resposta](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
18. Sob **Etapa 4 Especifique seus Horários Comerciais**, na caixa **Seu fuso horário**, clique no fuso horário do fluxo de trabalho.
    
    > [!NOTE]
    > O fuso horário é onde os chamadores e operadores do fluxo de trabalho residem. Ele é usado para calcular os horários de abertura e encerramento. Por exemplo, se o fluxo de trabalho está configurado para usar o fuso horário da costa leste norte-americana e o fluxo de trabalho estiver agendado para abrir às 7:00 A.M e fechar às 11:00 P.M., os horários de abertura e fechamento são assumidos como sendo 7:00 horário da costa leste e 11:00 horário da costa leste, respectivamente (você deve inserir os horários na notação de 24 horas). 
  
19. Selecione o tipo de agenda de horário comercial que deseja usar executando um dos seguintes procedimentos:
    
   - Para usar uma agenda pré-definida de horário comercial, clique em **Usar uma agenda predefinida** e selecione a agenda que deseja usar na lista suspensa.
    
     > [!NOTE]
     > Você deve ter definido no mínimo uma agenda predefinida anteriormente para selecionar esta opção. É possível definir agendamentos de predefinições usando o cmdlet **New-CSRgsHoursOfBusiness**. Para obter detalhes, consulte [horário comercial de grupo de resposta (opcional) definir no Skype para negócios 2015](optional-define-response-group-business-hours.md). Ao selecionar uma agenda predefinida, **Dia**, **Abertura** e **Fechamento** são automaticamente preenchidos com os dias e horas em que o grupo de resposta está disponível.
  
   - Para usar uma agenda personalizada que se aplique somente a este fluxo de trabalho, clique em **Usar uma agenda personalizada**.
    
20. Se estiver criando uma agenda personalizada para este fluxo de trabalho, clique nas opções para os dias da semana em que o grupo de resposta estará disponível.
    
21. Se estiver criando uma agenda personalizada, digite as horas de **Abertura** e **Fechamento** em que o grupo de resposta estará disponível.
    
     > [!NOTE]
     > As horas de **Abertura** e **Fechamento** devem estar na notação de 24 horas. Por exemplo, se seu escritório funciona em dias úteis das 9 às 5 e fecha ao meio dia para o almoço, o horário comercial é especificado como **Abertura** 9:00, **Fechamento** 12:00, **Abertura** 13:00 e **Fechamento** 17:00.
  
22. Se você desejar reproduzir uma mensagem quando o escritório não estiver aberto, selecione a opção **Reproduzir uma mensagem quando o grupo de resposta estiver fora do horário comercial** e especifique a mensagem a ser reproduzida executando um dos seguintes procedimentos:
    
    - Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.
    
     > [!NOTE]
     > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro. 
  
    - Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.
    
    > [!NOTE]
    > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para obter detalhes sobre os formatos de arquivo com suporte, consulte [Requisitos técnicos para grupos de resposta](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
23. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):
    
     - Para desconectar a chamada, clique em **Desconectar Chamada**.
    
     - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço da caixa postal é _ \<username\>_@ _\<domainname\> _ (por exemplo, bob@contoso.com).
    
     - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço do usuário é _ \<username\>_@ _\<domainname\>_.
    
     - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone é _ \<número\>_@ _\<domainname\> _ (por exemplo, +14255550121@contoso.com). O nome do domínio é usado para encaminhar o chamador ao destino correto.
    
24. Sob **Etapa 5 Especifique seus Feriados**, clique nas opções para um ou mais conjuntos de feriados que definem quando o grupo de resposta estará fechado para negócios.
    
    > [!NOTE]
    > É necessário definir feriados e conjuntos de feriados antes de configurar o fluxo de trabalho. Use os cmdlets **New-CsRgsHoliday** e **New-CsRgsHolidaySet** para definir feriados e conjuntos de feriados. Para obter detalhes, consulte [os conjuntos de feriados do grupo de resposta (opcional) definir no Skype para negócios 2015](optional-define-response-group-holiday-sets.md). 
  
25. Se você deseja reproduzir uma mensagem nos feriados, selecione a opção **Reproduzir uma mensagem durante os feriados** e especifique a mensagem a ser executada realizado um dos seguintes procedimentos:
    
   - Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.
    
     > [!NOTE]
     > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro. 
  
   - Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.
    
     > [!NOTE]
     > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para obter detalhes sobre os formatos de arquivo de áudio com suporte, consulte [Requisitos técnicos para grupos de resposta](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
26. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):
    
    - Para desconectar a chamada, clique em **Desconectar Chamada**.
    
    - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço da caixa postal é _ \<username\>_@ _\<domainname\> _ (por exemplo, bob@contoso.com).
    
    - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço do usuário é _ \<username\>_@ _\<domainname\>_.
    
    - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone é _ \<número\>_@ _\<domainname\> _ (por exemplo, +14255550121@contoso.com). O nome do domínio é usado para encaminhar o chamador ao destino correto.
    
27. Sob **Etapa 6 Configure a Música de Espera**, escolha o que deseja que os chamadores ouçam enquanto esperam por um operador, executando um dos seguintes procedimentos:
    
    - Para usar a gravação padrão de música em espera, clique em **Usar padrão**.
    
    - Para usar uma gravação de arquivo de áudio como música de espera, clique em **Selecionar um arquivo de música**. Se você deseja carregar um novo arquivo de áudio, clique no link **um arquivo de música**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.
    
    > [!NOTE]
    > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para obter detalhes sobre os formatos de arquivo com suporte, consulte [Requisitos técnicos para grupos de resposta](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
28. Sob **Etapa 7 Configure a Resposta Interativa de Voz**, sob o cabeçalho **O usuário ouvirá o seguinte texto ou mensagem gravada**, especifique a pergunta a ser feita aos chamadores da seguinte forma:
    
    - Para digitar uma pergunta em formato de texto, clique em **Usar conversão de texto em fala** e digite a pergunta na caixa de texto.
    
    > [!NOTE]
    > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro. 
  
    > [!NOTE]
    > O símbolo "#" é traduzido pelo mecanismo de conversão de texto em fala como a palavra "número". Se for necessário fazer referência à tecla #, use o nome da tecla no prompt, em vez do símbolo. Por exemplo, "Para falar com vendas, pressione a tecla jogo da velha." 
  
   - Para usar um arquivo de áudio pré-gravado que contenha a pergunta, clique em **Selecionar uma gravação** e clique no link **uma gravação** para carregar o arquivo. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo de áudio e clique em **Abrir**. Clique em **carregar** para carregar o arquivo e, em seguida, opcionalmente, você pode digitar a pergunta na caixa de texto (Isso habilitará a pergunta e resposta do chamador para serem encaminhadas ao operador).
    
     > [!NOTE]
     > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para obter detalhes sobre os formatos de arquivo com suporte, consulte [Requisitos técnicos para grupos de resposta](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
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
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a>Usar Skype para Business Server Management Shell para criar ou modificar um fluxo de trabalho interativo

1.  Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Recupere o nome do serviço do Grupo de Resposta e o atribua a uma variável. Na linha de comando, execute:
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}) .ServiceId;
   ```

4. Um fluxo de trabalho interativo requer duas ou mais filas e dois ou mais grupos de agentes. Primeiro, crie os grupos de agentes. Execute:
    
   ```
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. Crie as filas. Execute:
    
   ```
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. Crie o primeiro prompt de grupo de resposta. Execute:
    
   ```
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. Em seguida, crie a ação que será executada depois do prompt. Execute:
    
   ```
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. Crie a primeira resposta do grupo de resposta. Execute:
    
   ```
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. Agora crie o segundo prompt, a ação da chamada e a resposta. Primeiro crie o prompt. Execute:
    
   ```
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. Crie a segunda ação de chamada. Execute:
    
    ```
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. Crie a segunda resposta do grupo de resposta. Execute:
    
    ```
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. Crie o prompt do nível superior. Execute:
    
    ```
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. Crie a pergunta do nível superior. Execute:
    
    ```
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. Agora crie o fluxo de trabalho. Execute:
    
    ```
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > Todos os usuários que foram designados como gerentes de um grupo de resposta devem ter uma função CsResponseGroupManager. Se os usuário não têm essa função, não será possível gerenciar grupos de resposta. 
  
## <a name="see-also"></a>Consulte também

#### 

[(Opcional) Conjuntos de feriados do grupo de resposta definir Skype para negócios 2015](optional-define-response-group-holiday-sets.md)
#### 

[(Opcional) Grupo de resposta definir expediente no Skype para negócios 2015](optional-define-response-group-business-hours.md)
#### 

[New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)
  
[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)
  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)

