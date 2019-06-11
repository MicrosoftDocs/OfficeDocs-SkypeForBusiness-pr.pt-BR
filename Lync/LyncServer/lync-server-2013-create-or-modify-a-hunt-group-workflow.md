---
title: 'Lync Server 2013: criar ou modificar um fluxo de trabalho de grupo coletivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c927b10107626c1d40c33290b30f331f660e45e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a>Criar ou modificar um fluxo de trabalho de grupo coletivo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-09-11_

Use um dos procedimentos a seguir para criar ou modificar um fluxo de trabalho de grupo coletivo.

<div>


> [!NOTE]  
> Você pode usar o Shell de gerenciamento do Lync Server ou a ferramenta de configuração de grupo de resposta para criar e modificar fluxos de trabalho de grupo de busca. Você pode acessar a ferramenta de configuração do grupo de resposta no painel de controle do Lync Server ou abrindo a página da Web diretamente de um navegador da Web, digitando a seguinte URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>Para usar a ferramenta de configuração de grupo de resposta para criar ou modificar um fluxo de trabalho de grupo coletivo

1.  Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.

4.  Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.

5.  No campo de pesquisa **Selecione um Serviço**, digite parte ou todo o nome do serviço do **ApplicationServer** que hospeda o fluxo de trabalho que você deseja alterar ou criar. Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > A ferramenta de configuração de grupo de resposta é aberta. Você também pode abrir a ferramenta de configuração de grupo de resposta diretamente de um navegador da Web digitando a seguinte URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.

    
    </div>

6.  Siga um destes procedimentos:
    
      - Em **Criar um Novo Fluxo de Trabalho**, próximo ao **Grupo de busca, clique em Criar**.
    
      - Em **Gerenciar um Fluxo de Trabalho Existente**, localize o fluxo de trabalho que você deseja alterar e, em **Ação**, clique em **Editar**.

7.  Se estiver pronto para que os usuários comecem a fazer chamadas para o fluxo de trabalho, selecione **Ativar o fluxo de trabalho**.
    
    <div>
    

    > [!NOTE]  
    > Se você estiver criando um fluxo de trabalho gerenciado, é necessário selecionar <STRONG>Ativar o fluxo de trabalho</STRONG>. Após salvar o fluxo de trabalho gerenciado ativo, é possível modificar e desativá-lo.

    
    </div>

8.  Para permitir que usuários federados façam chamadas para o grupo, selecione a opção **Habilitar para federação**. Você também deve ter uma política de acesso externo que se aplica ao aplicativo de grupo de resposta configurado para Federação.
    
    <div>
    

    > [!NOTE]  
    > A política de acesso externo global global aplica-se ao aplicativo de grupo de resposta. Você pode configurar a política global para a Federação de grupo de resposta usando o painel de controle do Lync Server ou usando o cmdlet <STRONG>set-CsExternalAccessPolicy</STRONG> para definir o parâmetro EnableOutsideAccess como true. Lembre-se que as configurações de política global se aplicam a todos os usuários, a não ser que eles sejam atribuídos com uma política de usuário ou de site. Portanto, antes de alterar esta configuração para grupos de resposta, certifique-se de que as configurações de federação cumpre os requisitos da sua organização. Para obter detalhes sobre como as políticas se aplicam aos usuários, consulte <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gerenciar a política de acesso externo no Lync Server 2013</A>. Para obter detalhes sobre a configuração de Federação, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">set-CsExternalAccessPolicy</A>.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Os usuários hospedados no Lync Online não podem fazer chamadas para grupos de resposta hospedados em uma implantação local. Isso é verdade nas implantações híbridas e nos casos em que uma implantação local é federada com uma implantação do Lync Online.

    
    </div>

9.  Para ocultar a identidade de operadores durante as chamadas, selecione a opção **Habilitar anonimato do operador**.
    
    <div>
    

    > [!NOTE]  
    > Chamadas anônimas não podem ter início com sistemas de mensagens instantâneas (IM) ou vídeo, embora o operador ou chamadas possam adicionar IM e vídeo depois que a chamada estiver estabelecida. Um operador anônimo também pode colocar chamadas em espera, transferir (transferências ocultas e de consulta), estacionar e recuperar chamadas. Chamadas anônimas não oferecem suporte a conferência, compartilhamento de aplicativos, transferência de arquivos, whiteboarding e colaboração de dados e gravação de chamadas. Agentes utilizando o Plugin Lync VDI podem atender chamadas em entrada anonimamente, mas não podem realizar chamadas em saída anonimamente.

    
    </div>

10. Sob **Insira o endereço do grupo que receberá as chamadas**, digite o endereço URI SIP primário do grupo que irá receber chamadas para o fluxo de trabalho.
    
    <div>
    

    > [!NOTE]  
    > O URI primário para um fluxo de trabalho é como o fluxo de trabalho é identificado e referenciado. O URI SIP que você insere é criado como um objeto de contato nos serviços de domínio Active Directory. Para criar o URI, o objeto deve ser exclusivo no Active Directory.

    
    </div>

11. Em **nome para exibição**, digite o nome que você deseja exibir para o fluxo de trabalho (por exemplo, grupo de resposta de vendas).
    
    <div>
    

    > [!NOTE]  
    > Não inclua os caracteres "&lt;" ou "&gt;" no nome para exibição. Não use os nomes de exibição a seguir, pois são reservados: <STRONG>Observador de Presença RG</STRONG> ou <STRONG>Serviço de Anúncio</STRONG>.

    
    </div>

12. Sob **Número de telefone**, digite o URI de linha para o grupo de resposta (por exemplo, +14255550165).

13. Em **Número de Exibição**, digite o número conforme deseja que apareça para o grupo de resposta (por exemplo, +1 (425) 555-0165).

14. Adicionais Em **Descrição**, digite uma descrição para o fluxo de trabalho como deseja que ele apareça no cartão de visita do cliente do Lync.

15. Em **Tipo de fluxo de trabalho**, selecione **Gerenciado** se este fluxo de trabalho será gerenciado por um Gerente o Grupo de Resposta. Siga este procedimento para atribuir gerentes de grupo de resposta ao fluxo de trabalho:
    
    1.  Digite o URI SIP de um gerente para este fluxo de trabalho e clique em **Adicionar**.
    
    2.  Digite o URI SIP de gerentes adicionais para adicionar ao fluxo de trabalho e clique em **Adicionar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Cada usuário que é designado como um gerente de um grupo de resposta deve ser atribuído à função CsResponseGroupManager. Se os usuários não sã atribuídos com esta função, eles não podem gerenciar grupos de resposta.

    
    </div>

16. Sob **Etapa 2 Selecione um Idioma**, clique no idioma que deseja usar para reconhecimento de fala e conversão de texto em fala.

17. Se você deseja configurar uma mensagem de boas vindas, sob **Etapa 3 Configure uma Mensagem de Boas Vindas**, selecione a opção **Reproduzir uma mensagem de boas vindas** e execute um dos seguintes procedimentos:
    
      - Para inserir uma mensagem de boas vindas como texto convertido para fala para os chamadores, clique em **Usar conversão de texto em fala** e digite a mensagem de boas vindas na caixa de texto.
        
        <div>
        

        > [!NOTE]  
        > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

        
        </div>
    
      - Para usar uma gravação de arquivo de áudio wave (.wav) ou (.wma) do Windows Media para a mensagem de boas vindas, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na janela do navegador, clique em **Procurar**, selecione o arquivo de áudio que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.
        
        <div>
        

        > [!NOTE]  
        > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para obter detalhes sobre os formatos de arquivo com suporte, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para o grupo de resposta no Lync Server 2013</A>.

        
        </div>

18. Sob **Etapa 4 Especifique seu Horário Comercial**, em **Seu fuso horário**, clique no fuso horário para o fluxo de trabalho.
    
    <div>
    

    > [!NOTE]  
    > O fuso horário é onde os chamadores e operadores do fluxo de trabalho residem. Ele é usado para calcular os horários de abertura e encerramento. Por exemplo, se o fluxo de trabalho está configurado para usar o fuso horário da costa leste norte-americana e o fluxo de trabalho estiver agendado para abrir às 7:00 A.M e fechar às 11:00 P.M., os horários de abertura e fechamento são assumidos como sendo 7:00 horário da costa leste e 23:00 horário da costa leste, respectivamente (você deve inserir os horários na notação de 24 horas).

    
    </div>

19. Selecione o tipo de agenda de horário comercial que deseja usar executando um dos seguintes procedimentos:
    
      - Para usar uma agenda pré-definida de horário comercial, clique em **Usar uma agenda predefinida** e selecione a agenda que deseja usar na lista suspensa.
        
        <div>
        

        > [!NOTE]  
        > Você deve ter definido no mínimo uma agenda predefinida anteriormente para selecionar esta opção. É possível definir agendamentos de predefinições usando o cmdlet <STRONG>New-CSRgsHoursOfBusiness</STRONG>. Para obter detalhes, consulte <A href="lync-server-2013-optional-define-response-group-business-hours.md">(opcional) definir o horário comercial do grupo de resposta no Lync Server 2013</A>.

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > Ao selecionar uma agenda predefinida, <STRONG>Dia</STRONG>, <STRONG>Abertura</STRONG> e <STRONG>Fechamento</STRONG> são automaticamente preenchidos com os dias e horas em que o grupo de resposta está disponível.

        
        </div>
    
      - Para usar uma agenda personalizada que se aplique somente a este fluxo de trabalho, clique em **Usar uma agenda personalizada**.

20. Se estiver criando uma agenda personalizada para este fluxo de trabalho, clique nas opções para os dias da semana em que o grupo de resposta estará disponível.

21. Se estiver criando uma agenda personalizada, digite as horas de **Abertura** e **Fechamento** para cada dia da semana em que o grupo de resposta estará disponível.
    
    <div>
    

    > [!NOTE]  
    > As horas de <STRONG>Abertura</STRONG> e <STRONG>Fechamento</STRONG> devem estar na notação de 24 horas. Por exemplo, se seu escritório funciona em dias úteis das 9 às 5 e fecha ao meio dia para o almoço, o horário comercial é especificado como <STRONG>Abertura</STRONG> 9:00, <STRONG>Fechamento</STRONG> 12:00, <STRONG>Abertura</STRONG> 13:00 e <STRONG>Fechamento</STRONG> 17:00.

    
    </div>

22. Se você desejar reproduzir uma mensagem quando o escritório não estiver aberto, selecione a opção **Reproduzir uma mensagem quando o grupo de resposta estiver fora do horário comercial** e especifique a mensagem a ser reproduzida executando um dos seguintes procedimentos:
    
      - Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.
        
        <div>
        

        > [!NOTE]  
        > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

        
        </div>
    
      - Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.
        
        <div>
        

        > [!NOTE]  
        > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para obter detalhes sobre os formatos de arquivo de áudio com suporte, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para o grupo de resposta no Lync Server 2013</A>.

        
        </div>

23. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):
    
      - Para desconectar a chamada, clique em **Desconectar Chamada**.
    
      - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço de correio de voz \<é\>@\<username DomainName\> (por exemplo, Bob@contoso.com).
    
      - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço de usuário é \<username\>@\<DomainName\>.
    
      - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone é \<número\>@\<DomainName\> (por exemplo, + 14255550121@contoso.com). O nome do domínio é usado para encaminhar o chamador ao destino correto.

24. Sob **Etapa 5 Especifique seus Feriados**, clique nas opções para um ou mais conjuntos de feriados que definem quando o grupo de resposta estará fechado para negócios.
    
    <div>
    

    > [!NOTE]  
    > É necessário definir feriados e conjuntos de feriados antes de configurar o fluxo de trabalho. Use os cmdlets <STRONG>New-CsRgsHoliday</STRONG> e <STRONG>New-CsRgsHolidaySet</STRONG> para definir feriados e conjuntos de feriados. Para obter detalhes, consulte <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(opcional) definir os conjuntos de feriados do grupo de resposta no Lync Server 2013</A>.

    
    </div>

25. Se você deseja reproduzir uma mensagem nos feriados, selecione a opção **Reproduzir uma mensagem durante os feriados** e especifique a mensagem a ser executada realizado um dos seguintes procedimentos:
    
      - Para inserir as mensagem como um texto a ser convertido para fala para o chamador, clique em **Usar conversão de texto para fala** e digite a mensagem na caixa de texto.
        
        <div>
        

        > [!NOTE]  
        > Não inclua tags HTML no texto digitado. Se você incluir tags HTML, receberá uma mensagem de erro.

        
        </div>
    
      - Para usar uma gravação de arquivo de áudio para a mensagem, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.
        
        <div>
        

        > [!NOTE]  
        > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para obter detalhes sobre os formatos de arquivo de áudio com suporte, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para o grupo de resposta no Lync Server 2013</A>.

        
        </div>

26. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):
    
      - Para desconectar a chamada, clique em **Desconectar Chamada**.
    
      - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço de correio de voz \<é\>@\<username DomainName\> (por exemplo, Bob@contoso.com).
    
      - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço de usuário é \<username\>@\<DomainName\>.
    
      - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone é \<número\>@\<DomainName\> (por exemplo, + 14255550121@contoso.com). O nome do domínio é usado para encaminhar o chamador ao destino correto.

27. Sob **Etapa 6 Configure uma Fila**, em **Selecione a fila que receberá as chamadas**, selecione a fila que você deseja que segure as chamadas até que um operador torne-se disponível.

28. Sob **Etapa 7 Configure Música de Espera**, escolha a música que deseja que os chamadores ouçam enquanto esperam que um operador, executando um dos seguintes procedimentos:
    
      - Para usar a gravação padrão de música de espera, clique em **Usar padrão**.
    
      - Para usar uma gravação de arquivo de áudio para a música de espera, clique em **Selecionar um arquivo de música**. Se você deseja carregar um novo arquivo de áudio, clique no link **um arquivo de música**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.
        
        <div>
        

        > [!NOTE]  
        > Todos os arquivos de áudio fornecidos pelo usuário devem atender determinados requisitos. Para obter detalhes sobre os formatos de arquivo de áudio com suporte, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para o grupo de resposta no Lync Server 2013</A>.

        
        </div>

29. Clique em **Implantar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a>Para usar o Windows PowerShell para criar ou modificar um fluxo de trabalho de grupo coletivo

1.  Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Crie o prompt a ser reproduzido na mensagem de boas-vindas e salve-o como uma variável. Na linha de comando, execute:
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Por exemplo:
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > Para usar um arquivo de áudio no prompt, use o cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>. Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">importar-CsRgsAudioFile</A>.

    
    </div>

4.  Obtenha a identidade da fila ou pergunta onde as chamadas serão direcionadas. Na linha de comando, execute:
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    Para obter detalhes sobre como criar a fila, consulte [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).

5.  Defina a ação padrão a ser realizada quando um fluxo de trabalho é aberto durante o horário comercial e salve-o em uma variável. Na linha de comando, execute:
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > Para fluxos de trabalho do grupo de busca, a ação padrão deve direcionar a chamada para uma fila. Este parâmetro é necessário para fluxos de trabalho ativos. Não é necessário para fluxos de trabalho inativos.

    
    </div>
    
    Por exemplo:
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  Se você deseja definir o horário comercial e feriados, é necessário criá-los antes de criar ou modificar o fluxo de trabalho. Para obter detalhes, consulte [(opcional) definir o grupo de resposta horário comercial no Lync server 2013](lync-server-2013-optional-define-response-group-business-hours.md) e [(opcional) definir os conjuntos de feriados do grupo de resposta no Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).

7.  Se você deseja ter prompts para chamadas recebidas fora do horário comercial ou em feriados, use o cmdlet **New-CsRgsPrompt** para definir o prompt e use o **New-CsRgsCallAction** para definir a ação a ser realizada após o prompt. Para obter detalhes, consulte [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).

8.  Recupere o nome do serviço do serviço de grupo de resposta do Lync Server e atribua-o a uma variável. No comando, execute:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  Crie ou modifique o fluxo de trabalho. Para criar um fluxo de trabalho, use **New-CsRgsWorkflow**. Para modificar um fluxo de trabalho, use **set-CsRgsWorkflow**. Na linha de comando, digite:
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    Por exemplo:
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > Todos os usuários que são gerentes para fluxos de trabalho devem ser atribuídos à função CsResponseGroupManager.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Para obter detalhes sobre parâmetros opcionais adicionais, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> ou <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">set-CsRgsWorkflow</A>

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Adicionais Definir conjuntos de feriados do grupo de resposta no Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[Adicionais Definir o horário comercial do grupo de resposta no Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)  


[New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

