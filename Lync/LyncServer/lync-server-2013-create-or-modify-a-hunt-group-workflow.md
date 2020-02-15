---
title: 'Lync Server 2013: criar ou modificar um fluxo de trabalho de grupo de busca'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f56187645a48b4e2cdaebb8ce9091abcfadc065b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a>Criar ou modificar um fluxo de trabalho de grupo de busca no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-09-11_

Use um dos seguintes procedimentos para criar ou modificar um fluxo de trabalho de grupo de busca.

<div>


> [!NOTE]  
> Você pode usar o Shell de gerenciamento do Lync Server ou a ferramenta de configuração do grupo de resposta para criar e modificar fluxos de trabalho de grupo de busca. Você pode acessar a ferramenta de configuração do grupo de resposta no painel de controle do Lync Server ou abrindo a página da Web diretamente de um navegador da Web digitando a seguinte URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>Para usar a ferramenta de configuração de grupo de resposta para criar ou modificar um fluxo de trabalho de grupo de busca

1.  Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.

4.  Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.

5.  No campo de pesquisa **selecionar um serviço** , digite todo ou parte do nome do serviço **ApplicationServer** que hospeda o fluxo de trabalho que você deseja criar ou alterar. Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > A ferramenta de configuração do grupo de resposta é aberta. Você também pode abrir a ferramenta de configuração do grupo de resposta diretamente de um navegador da Web digitando a seguinte URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.

    
    </div>

6.  Siga um destes procedimentos:
    
      - Em **criar um novo fluxo de trabalho**, ao lado de **grupo de busca, clique em criar**.
    
      - Em **Gerenciar um Fluxo de Trabalho Existente**, localize o fluxo de trabalho que você deseja alterar e, em **Ação**, clique em **Editar**.

7.  Se você estiver pronto para os usuários começarem a chamar o fluxo de trabalho, selecione **ativar o fluxo de trabalho**.
    
    <div>
    

    > [!NOTE]  
    > Se estiver criando um fluxo de trabalho gerenciado, você precisa selecionar <STRONG>Ativar o fluxo de trabalho</STRONG>. Depois de salvar o fluxo de trabalho ativo e gerenciado, você pode modificá-lo e desativá-lo.

    
    </div>

8.  Para permitir que usuários federados façam chamadas para o grupo, selecione a opção **Habilitar para federação**. Você também deve ter uma política de acesso externo que se aplica ao aplicativo de grupo de resposta configurado para Federação.
    
    <div>
    

    > [!NOTE]  
    > A política de acesso externo global se aplica ao aplicativo grupo de resposta. Você pode configurar a política global para a Federação de grupo de resposta usando o painel de controle do Lync Server ou usando o cmdlet <STRONG>set-CsExternalAccessPolicy</STRONG> para definir o parâmetro EnableOutsideAccess como true. Lembre-se de que as configurações de política global se aplicam a todos os usuários a não ser que sejam atribuídos a um site ou uma política de usuário. Portanto, antes de alterar essa configuração para grupos de resposta, verifique se a configuração de federação atende aos requisitos da sua organização. Para obter detalhes sobre como as políticas se aplicam aos usuários, consulte <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gerenciar a política de acesso externo no Lync Server 2013</A>. Para obter detalhes sobre a configuração de Federação, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">set-CsExternalAccessPolicy</A>.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Os usuários hospedados no Lync Online não podem fazer chamadas para grupos de resposta hospedados em uma implantação local. Isso acontece em implantações híbridas e em casos em que uma implantação local é federada com uma implantação do Lync Online.

    
    </div>

9.  Para ocultar a identidade de operadores durante as chamadas, selecione a opção **Habilitar anonimato do operador**.
    
    <div>
    

    > [!NOTE]  
    > Chamadas anônimas não podem ter início com sistemas de mensagens instantâneas (IM) ou vídeo, embora o operador ou chamadas possam adicionar IM e vídeo depois que a chamada estiver estabelecida. Um operador anônimo também pode colocar chamadas em espera, transferir (transferências ocultas e de consulta), estacionar e recuperar chamadas. Chamadas anônimas não oferecem suporte a conferência, compartilhamento de aplicativos, transferência de arquivos, whiteboarding e colaboração de dados e gravação de chamadas. Os agentes que usam o plug-in do Lync VDI podem receber chamadas de entrada anonimamente, mas não podem fazer chamadas de saída anonimamente.

    
    </div>

10. Em **Inserir endereço do grupo que receberá as chamadas**, digite o endereço do identificador de recurso uniforme (URI) SIP primário do grupo que responderá chamadas do fluxo de trabalho.
    
    <div>
    

    > [!NOTE]  
    > O URI principal de um fluxo de trabalho é como o fluxo de trabalho é identificado e referenciado. O URI SIP que você insere é criado como um objeto de contato nos serviços de domínio do Active Directory. Para criar o URI, o objeto deve ser exclusivo no Active Directory.

    
    </div>

11. Em **nome para exibição**, digite o nome que você deseja exibir para o fluxo de trabalho (por exemplo, grupo de resposta de vendas).
    
    <div>
    

    > [!NOTE]  
    > Não inclua os caracteres "&lt;" ou "&gt;" no nome de exibição. Não use os nomes de exibição a seguir, pois eles são reservados: Inspetor de presença ou <STRONG>serviço de anúncio</STRONG>do <STRONG>RGS</STRONG> .

    
    </div>

12. Em **Número de telefone**, digite o URI de linha para o grupo de resposta (por exemplo, +14255550165).

13. Em **Número de exibição**, digite o número como você deseja que seja exibido para o grupo de resposta (por exemplo, +1 (425) 555-0165).

14. Opcion Em **Descrição**, digite uma descrição para o fluxo de trabalho conforme você deseja que ele apareça no cartão de visita no cliente do Lync.

15. Em **Tipo de fluxo de trabalho**, selecione **Gerenciado** se este fluxo de trabalho será gerenciado pelo Gerente do grupo de resposta. Para atribuir os gerentes do grupo de resposta ao fluxo de trabalho, faça o seguinte:
    
    1.  Digite o URI SIP de um gerente para este fluxo de trabalho e clique em **Adicionar**.
    
    2.  Digite o URI SIP de gerentes adicionais para adicionar ao fluxo de trabalho e clique em **Adicionar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Todos os usuários designados como gerentes de um grupo de resposta devem ter uma função CsResponseGroupManager. Se os usuário não receberem essa função, não será possível gerenciar grupos de resposta.

    
    </div>

16. Em **Etapa 2 Selecionar um idioma**, clique no idioma que você deseja usar para o reconhecimento de fala e conversão de texto em fala.

17. Se você deseja configurar uma mensagem de boas-vindas, em **Etapa 3 Configurar uma mensagem de boas-vindas**, marque a caixa de seleção **Reproduzir uma mensagem de boas-vindas** e faça um dos seguintes:
    
      - Para inserir uma mensagem de boas vindas como texto convertido para fala para os chamadores, clique em **Usar conversão de texto em fala** e digite a mensagem de boas vindas na caixa de texto.
        
        <div>
        

        > [!NOTE]  
        > Não inclua tags HTML no texto inserido. Se incluir tags HTML, você receberá uma mensagem de erro.

        
        </div>
    
      - Para usar um arquivo wave (.wav) ou Windows Media audio (.wma) gravando a mensagem de boas-vindas, clique em **Selecionar uma gravação**. Se você deseja carregar um novo arquivo de áudio, clique no link **uma gravação**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo de áudio que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.
        
        <div>
        

        > [!NOTE]  
        > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para obter detalhes sobre os formatos de arquivo com suporte, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.

        
        </div>

18. Em **Etapa 4 Especificar seu horário comercial**, em **Seu fuso horário **, clique no fuso horário do fluxo de trabalho.
    
    <div>
    

    > [!NOTE]  
    > O fuso horário é o fuso onde os chamadores e agentes do fluxo de trabalho residem. É usado para calcular as horas abertas e fechadas. Por exemplo, se o fluxo de trabalho é configurado para usar o fuso horário Hora do Leste dos Estados Unidos e o fluxo de trabalho está programado para abrir às 7:00 e fechar as 23:00 horas, as horas abertas e fechadas devem ser 7:00 Horário do Leste e 23:00 Horário do Leste, respectivamente. (Você deve inserir as horas no formato de 24 horas.)

    
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

20. Se você está criando uma programação personalizada para este fluxo de trabalho, clique nas caixas de seleção para os dias da semana nos quais o grupo de resposta está disponível.

21. Se você está criando uma programação personalizada, digite a hora **Aberta** e **Fechado** para cada dia da semana que o grupo de resposta está disponível.
    
    <div>
    

    > [!NOTE]  
    > As horas <STRONG>Abrir</STRONG> e <STRONG>Fechar</STRONG> deve estar no formato 24 horas. Por exemplo, se seu escritório funciona de 9 as 17 horas e fecha ao meio dia para almoço, as horas comerciais são especificadas como <STRONG>Abrir</STRONG> 9:00, <STRONG>Fechar</STRONG> 12:00, <STRONG>Abrir</STRONG> 13:00 e <STRONG>Fechar</STRONG> 17:00.

    
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
        > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para obter detalhes sobre os formatos de arquivo de áudio suportados, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.

        
        </div>

23. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):
    
      - Para desconectar a chamada, clique em **Desconectar Chamada**.
    
      - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço de caixa postal é \<nome\>@\<de usuário nome_do_domínio\> (por exemplo, Bob@contoso.com).
    
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
        > Todos os arquivos de áudio fornecidos pelo usuário devem estar de acordo com determinados requisitos. Para obter detalhes sobre os formatos de arquivo de áudio suportados, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.

        
        </div>

26. Especifique como tratar chamadas após a reprodução da mensagem (se uma mensagem estiver configurada):
    
      - Para desconectar a chamada, clique em **Desconectar Chamada**.
    
      - Para encaminhar a chamada para a caixa postal, clique em **Encaminhar para caixa postal** e digite o endereço da caixa postal. O formato do endereço de caixa postal é \<nome\>@\<de usuário nome_do_domínio\> (por exemplo, Bob@contoso.com).
    
      - Para encaminhar a chamada para outro usuário, clique em **Encaminhar para URI do SIP** e digite um endereço de usuário. O formato do endereço de usuário é \<username\>@\<DomainName\>.
    
      - Para encaminhar a chamada para outro número de telefone, clique em **Encaminhar para número de telefone** e digite o número de telefone. O formato do número de telefone é \<número\>@\<DomainName\> (por exemplo, + 14255550121@contoso.com). O nome do domínio é usado para direcionar o chamador para o destino correto.

27. Em **Etapa 6 Configurar uma fila**, em **Selecionar a fila que irá receber as chamadas**, selecione a fila que deseja manter os chamadores até que um agente se tornar disponível.

28. Em **Etapa 7 Configurar música de espera**, escolha a música que você deseja que os chamadores ouçam enquanto aguardam por um agente, fazendo o seguinte:
    
      - Para usar a gravação padrão de música de espera, clique em **Usar padrão**.
    
      - Para usar uma gravação de arquivo de áudio para a música de espera, clique em **Selecionar um arquivo de música**. Se você deseja carregar um novo arquivo de áudio, clique no link **um arquivo de música**. Na nova janela do navegador, clique em **Procurar**, selecione o arquivo que deseja usar e clique em **Abrir**. Clique em **Carregar** para carregar o arquivo de áudio.
        
        <div>
        

        > [!NOTE]  
        > Todos os arquivos de áudio fornecidos pelo usuário devem cumprir determinados requisitos. Para obter detalhes sobre os formatos de arquivo de áudio suportados, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.

        
        </div>

29. Clique em **Implantar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a>Para usar o Windows PowerShell para criar ou modificar um fluxo de trabalho de grupo de busca

1.  Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Crie o prompt a ser tocado para a mensagem de boas-vindas e salve-o em uma variável. Na linha de comando, execute:
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Por exemplo:
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > Para usar um arquivo de áudio no prompt, use o cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>. Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

4.  Obtenha a identidade da fila ou pergunta onde as chamadas serão direcionadas. Na linha de comando, execute:
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    Para obter detalhes sobre como criar a fila, consulte [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).

5.  Defina a ação padrão a ser tomada quando um fluxo de trabalho for aberto durante o horário comercial e salve-o em uma variável. Na linha de comando, execute:
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > Para fluxos de trabalho de grupo de busca, a ação padrão deve direcionar a chamada para uma fila. Esse parâmetro é necessário para fluxos de trabalho ativos. Não é necessário para fluxos de trabalho inativos.

    
    </div>
    
    Por exemplo:
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  Se você deseja definir horários comerciais e feriados, precisa criá-los antes de criar ou modificar o fluxo de trabalho. Para obter detalhes, consulte [(opcional) definir o horário comercial do grupo de resposta no Lync server 2013](lync-server-2013-optional-define-response-group-business-hours.md) e [(opcional) definir os conjuntos de feriados do grupo de resposta no Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).

7.  Se você deseja ter solicitações para chamadas recebidas fora do horário comercial ou em feriados, use o cmdlet **New-CsRgsPrompt** para definir o prompt e use o **New-CsRgsCallAction** para definir a ação a ser tomada após o prompt. Para obter detalhes, consulte [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) e [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).

8.  Recupere o nome do serviço do serviço de grupo de resposta do Lync Server e atribua-o a uma variável. No comando, execute:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  Criar ou modificar o fluxo de trabalho. Para criar um fluxo de trabalho, use **New-CsRgsWorkflow**. Para modificar um fluxo de trabalho, use **set-CsRgsWorkflow**. Na linha de comando, digite:
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    Por exemplo:
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > Todos os usuários designados para os fluxos de trabalho devem ser atribuídos à função À csresponsegroupmanager.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Para obter detalhes sobre parâmetros opcionais adicionais, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> ou <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">set-CsRgsWorkflow</A>

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Opcion Definir os conjuntos de feriados do grupo de resposta no Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[Opcion Definir o horário comercial do grupo de resposta no Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)  


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

