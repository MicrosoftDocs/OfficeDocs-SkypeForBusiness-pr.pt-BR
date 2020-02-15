---
title: 'Lync Server 2013: criar ou modificar uma fila'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1db2211f174c18c160262c1f62c55a178b2cda4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a>Criar ou modificar uma fila no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Use um dos seguintes procedimentos para criar ou modificar uma fila.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a>Para usar o painel de controle do Lync Server para criar ou modificar uma fila

1.  Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.
    
    <div>
    

    > [!NOTE]  
    > Se você for um dos Gerentes de grupo de resposta delegados para um fluxo de trabalho gerenciado, é possível criar ou modificar filas de grupo de resposta e atribuí-las aos fluxos de trabalho gerenciados.

    
    </div>

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Grupos de Resposta** e clique em **Fila**.

4.  Na página **Fila**, siga um destes procedimentos:
    
      - Para criar uma nova fila, clique em **Nova**. Em **Selecionar um serviço**, digite uma parte ou o nome inteiro do serviço do **ApplicationServer** onde deseja adicionar a fila no campo de pesquisa. Na lista resultante de serviços, clique no serviço que você deseja e clique em **OK**.
    
      - Para modificar uma fila existente, digite uma parte ou o nome inteiro da fila no campo de pesquisa. Na lista resultante de filas, clique na fila que você deseja, em **Editar** e em **Mostrar detalhes**.

5.  Em **Nome**, digite um nome identificador para a fila.

6.  Em **Descrição**, digite uma descrição para a fila.

7.  Em **Grupos**, especifique os grupos que você deseja atribuir à fila. Siga um destes procedimentos:
    
      - Para adicionar um grupo à fila, clique em **Selecionar**. No campo de pesquisa **Selecionar grupos**, digite o parte ou o nome inteiro do grupo de agentes que você deseja atribuir à fila, clique no grupo de agentes desejado e em **OK**.
    
      - Para remover um grupo da fila, na lista de grupos de agentes, clique no grupo que você deseja remover e em **Remover**.
    
      - Para alterar a ordem em que os agentes são pesquisados, na lista de grupos de agentes, clique em um grupo e na seta para cima ou para baixo.
        
        <div>
        

        > [!NOTE]  
        > Quando o servidor pesquisa por um agente disponível para a fila, ele usa a ordem do grupo. Ou seja, o primeiro grupo da lista é pesquisado primeiro, seguido pelo segundo e assim sucessivamente.

        
        </div>

8.  Para especificar um período máximo de tempo para um chamador aguardar em espera antes que um agente responda à chamada, marque a caixa de seleção **Habilitar o tempo limite da fila** e, em seguida, faça o seguinte:
    
    1.  Em **Período de tempo limite (segundos)**, especifique o número máximo de segundos que um chamador aguarda antes de um agente responder à chamada.
    
    2.  Em **Ação de Chamada**, selecione a ação que ocorre quando o tempo limite de uma chamada se esgota da seguinte maneira:
    
    <!-- end list -->
    
      - Para desconectar a chamada após o tempo limite, clique em **Desconectar**.
    
      - Para encaminhar a chamada para caixa postal, clique em **encaminhar para caixa postal**e, em seguida, no campo **endereço SIP** , digite um endereço de caixa postal\<no\>@\<formato SIP:\> username DomainName (por exemplo, SIP:Bob@contoso.com).
    
      - Para encaminhar a chamada para outro número de telefone, clique em **encaminhar para número de telefone**e, no campo **endereço SIP** , digite o número de telefone no\<formato\>@\<SIP: Number\> DomainName (por exemplo, SIP:+14255550121@contoso.com).
    
      - Para encaminhar a chamada para outro usuário, clique em **encaminhar para endereço SIP**e, no campo **endereço SIP** , digite o URI para o usuário no formato SIP:\<username\>@\<DomainName\>.
    
      - Para encaminhar a chamada para outra fila de espera, clique em **Encaminhar para outra fila** e, em seguida, procure na fila a ser usada.

9.  Para especificar um número máximo de chamadas que a fila de espera poderá conter, marque a caixa de seleção **Habilitar o estouro da fila** e faça o seguinte:
    
    1.  Em **Número máximo de chamadas**, selecione o número máximo de chamadas que a fila de espera conterá.
    
    2.  Em **Encaminhar a chamada**, selecione qual chamada será encaminhada quando a fila estiver cheia: **Chamada Mais Recente** ou **Chamada Mais Antiga**.
    
    3.  Em **Ação de chamada**, selecione a ação que ocorre quando o limite de excedente é atingido da seguinte forma:
    
    <!-- end list -->
    
      - Para desconectar a chamada após o tempo limite, clique em **Desconectar**.
    
      - Para encaminhar a chamada para caixa postal, clique em **encaminhar para caixa postal**e, em seguida, no campo **endereço SIP** , digite um endereço de caixa postal\<no\>@\<formato SIP:\> username DomainName (por exemplo, SIP:Bob@contoso.com).
    
      - Para encaminhar a chamada para outro número de telefone, clique em **encaminhar para número de telefone**e, no campo **endereço SIP** , digite o número de telefone no\<formato\>@\<SIP: Number\> DomainName (por exemplo, SIP:+14255550121@contoso.com).
    
      - Para encaminhar a chamada para outro usuário, clique em **encaminhar para endereço SIP**e, no campo **endereço SIP** , digite o URI para o usuário no formato SIP:\<username\>@\<DomainName\>.
    
      - Para encaminhar a chamada para outra fila de espera, clique em **Encaminhar para outra fila** e, em seguida, procure na fila a ser usada.

10. Clique em **Confirmar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a>Para usar o Windows PowerShell para criar ou modificar uma fila

1.  Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.
    
    <div>
    

    > [!NOTE]  
    > Se você for um dos Gerentes do grupo de resposta designado para um fluxo de trabalho gerenciado, será possível criar grupos de agentes e filas, bem como atribuir grupos de agentes a filas.

    
    </div>

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Crie o prompt para que seja reproduzido quando o limite de tempo da fila é atingido e salve-o em um variável. Na linha de comando, execute:
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Por exemplo:
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > Para usar um arquivo de áudio no prompt, use o cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>. Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

4.  Defina a ação que será executada quando o limite de tempo da fila for atingido e salve-o em um variável. Na linha de comando, execute:
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > Para obter detalhes sobre as ações possíveis e sua sintaxe, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.

    
    </div>
    
    Por exemplo:
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  Crie o prompt que será reproduzido quando o limite de excedente da fila for atingido e salve-o em uma variável. Na linha de comando, execute:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Por exemplo:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > Para usar um arquivo de áudio no prompt, use o cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>. Para obter detalhes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

6.  Defina a ação que será executada quando o limite de excedente da fila for atingido e salve-o em uma variável. Na linha de comando, execute:
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > Para obter detalhes sobre as ações possíveis e sua sintaxe, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.

    
    </div>
    
    Por exemplo:
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  Recupere o nome do serviço do serviço de Grupo de resposta e atribua-o a uma variável. Na linha de comando, execute:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  Obtenha a identidade do grupo de agente que será atribuído à fila. Na linha de comando, execute:
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > Para obter detalhes sobre como criar o grupo de agentes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A>

    
    </div>

9.  Crie a fila. Na linha de comando, execute:
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    Por exemplo:
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. Confirme se a fila foi criada. Execute:
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>Confira também


[New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[Remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

