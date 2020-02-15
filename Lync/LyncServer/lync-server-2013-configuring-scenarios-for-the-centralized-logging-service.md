---
title: 'Lync Server 2013: Configurando cenários para o serviço de registro em log centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring scenarios for the Centralized Logging Service
ms:assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688085(v=OCS.15)
ms:contentKeyID: 49733682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a39bcd23516970edf1c4694a8eff1ecb682eda1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-scenarios-for-the-centralized-logging-service-in-lync-server-2013"></a>Configurando cenários para o serviço de registro em log centralizado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-05_

Os cenários definem o escopo (ou seja, global, site, pool ou computador) e quais provedores usar no serviço de registro em log centralizado. Usando cenários, você habilita e desabilita o rastreamento nos provedores (por exemplo, S4, SIPStack, mensagens instantâneas e presença). Ao configurar um cenário, você pode agrupar todos os provedores de determinado conjunto lógico que tratam um problema específico. Se você achar que um cenário precisa ser modificado para atender às suas necessidades de solução de problemas e log, as ferramentas de depuração do Lync Server 2013 fornecem um módulo do Windows PowerShell chamado *ClsController. psm1* que contém uma função chamada *Edit-CsClsScenario*. A finalidade desse módulo é editar as propriedades do cenário nomeado. Neste tópico, serão fornecidos exemplos de como esse módulo funciona. As ferramentas de depuração do Lync Server 2013 são baixadas do seguinte link:[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)

<div>


> [!IMPORTANT]  
> Para qualquer dado escopo (global, site, pool ou computador), é possível executar no máximo dois cenários por vez. Para determinar quais cenários estão em execução no momento, use o Windows PowerShell e o <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsClsScenario">Get-CsClsScenario</A>. Usando o Windows PowerShell e o <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClsScenario">set-CsClsScenario</A>, você pode alterar dinamicamente quais cenários estão em execução. Você pode modificar quais cenários estão em execução durante uma sessão de registro em log para ajustar ou refinar os dados coletados e de quais provedores.



</div>

Para executar as funções de serviço de registro centralizado usando o Shell de gerenciamento do Lync Server, você deve ser membro dos grupos de segurança do controle de acesso baseado em função do CsAdministrator ou do CsServerAdministrator, ou uma função RBAC personalizada que contenha desses dois grupos. Para retornar uma lista de todas as funções RBAC às quais este cmdlet foi atribuído, incluindo qualquer função RBAC personalizada que você criou sozinho, execute o seguinte comando no Shell de gerenciamento do Lync Server ou no prompt do Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Por exemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

O restante deste tópico se concentra em como definir um cenário, modificar um cenário, recuperar quais cenários estão em execução, remover um cenário e especificar o que um cenário contém para otimizar a solução de problemas. Há duas maneiras de emitir comandos de serviço de registro centralizado. Você pode usar o CLSController. exe localizado, por padrão, no\\diretório C: Arquivos de programas\\comuns\\do Microsoft Lync Server 2013\\CLSAgent. Ou você pode usar o Shell de gerenciamento do Lync Server para emitir comandos do Windows PowerShell. A distinção importante é que, quando você usa o CLSController. exe na linha de comando, há uma seleção finita de cenários disponíveis. Ao usar o Windows PowerShell, você pode definir novos cenários para usar em suas sessões de registro em log.

Como apresentado na [visão geral do serviço de registro em log centralizado no Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md), os elementos de um cenário são:

  - **Provedores**   se você estiver familiarizado com o OCSLogger, os provedores são os componentes que você escolhe para informar ao OCSLogger de que o mecanismo de rastreamento deve coletar logs. Os provedores são os mesmos componentes e, em muitos casos, têm o mesmo nome que os componentes do OCSLogger. Se você não estiver familiarizado com o OCSLogger, os provedores são componentes específicos de função de servidor que o serviço de registro em log centralizado pode coletar logs. Para obter detalhes sobre a configuração de provedores, consulte [Configuring Providers for central Logging Service in Lync Server 2013](lync-server-2013-configuring-providers-for-centralized-logging-service.md).

  - **Identity**   o parâmetro – Identity define o escopo e o nome do cenário. Por exemplo, você pode definir um escopo "global" e identificar o cenário como “LyssServiceScenario”. Ao combinar os dois, você define a identidade (por exemplo, “global/LyssServiceScenario”).
    
    Opcionalmente, você pode usar os parâmetros –Name e –Parent. Você define o parâmetro Name para identificar exclusivamente o cenário. Se usá-lo, também deverá usar Parent para adicionar o cenário ao escopo global ou site.
    
    <div>
    

    > [!IMPORTANT]  
    > Se você usar os parâmetros Name e Parent, não poderá usar o parâmetro <STRONG>–Identity</STRONG>.

    
    </div>

<div>

## <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>Para criar um novo cenário com o cmdlet New-CsClsScenario

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Para criar um novo cenário para uma sessão de registro em log, use [New-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/New-CsClsProvider) e defina o nome do cenário (ou seja, como ele será identificado exclusivamente). Escolha um tipo de formato de registro em log entre WPP (ou seja, o pré-processador de rastreamento de software do Windows, que é o padrão), EventLog (ou seja, o formato de log de eventos do Windows) ou IISLog (ou seja, o arquivo de formato ASCII baseado no formato de arquivo de log do IIS). Em seguida, defina o nível (conforme definido em Níveis de registro em log neste tópico) e os sinalizadores (conforme definido em Sinalizadores neste tópico).
    
    Para este cenário de exemplo, usaremos LyssProvider como a variável de provedor de exemplo.
    
    Para criar um cenário usando as opções definidas, digite:
    
        New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
    
    Por exemplo:
    
        New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
    
    Formato alternativo usando –Name e –Parent:
    
        New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider

</div>

<div>

## <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>Para criar um novo cenário com vários provedores usando o cmdlet New-CsClsScenario

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Há um limite de dois cenários por escopo. No entanto, não há um limite quanto ao número de provedores. Neste exemplo, suponha que criamos três provedores e você deseja atribuir todos eles ao cenário que está definindo. Os nomes das variáveis dos provedores são LyssProvider, ABServerProvider e SIPStackProvider. Para definir e atribuir vários provedores a um cenário, digite o seguinte em um shell de gerenciamento do Lync Server ou prompt de comando do Windows PowerShell:
    
        New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
    
    <div>
    

    > [!NOTE]  
    > Como é conhecido no Windows PowerShell, a Convenção para criar uma tabela de hash de valores usando <CODE>@{&lt;variable&gt;=&lt;value1&gt;, &lt;value2&gt;, &lt;value&gt;...}</CODE> é conhecida como <EM>splatting</EM>. Para obter detalhes sobre o splatting no Windows PowerShell <A href="http://go.microsoft.com/fwlink/p/?linkid=267760">http://go.microsoft.com/fwlink/p/?LinkId=267760</A>, consulte.

    
    </div>

</div>

<div>

## <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>Para modificar um cenário existente com o cmdlet Set-CsClsScenario

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Há um limite de dois cenários por escopo. Você pode alterar quais cenários estão em execução a qualquer momento, mesmo quando uma sessão de coleta de log está em andamento. Se você redefinir os cenários em execução, a sessão de registro em log atual parará de usar o cenário que foi removido e começará a usar o novo cenário. No entanto, as informações de log que já foram coletadas com o cenário removido permanecerão nos logs coletados. Para definir um novo cenário, faça o seguinte (pressupondo a adição de um provedor já definido chamado “S4Provider”):
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
    
    Por exemplo:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
    
    Se você desejar substituir provedores, defina um único provedor ou uma lista separada por vírgulas de provedores para substituir o conjunto atual. Se você desejar substituir apenas um de vários provedores, adicione os provedores atuais junto com os novos provedores para criar um novo conjunto de provedores que contenha os provedores novos e existentes. Para substituir todos os provedores por um novo conjunto, digite o seguinte:
    
        Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
    
    Por exemplo, para substituir o conjunto atual de $LyssProvider, $ABServerProvider e $SIPStackProvider por $LyssServiceProvider:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
    
    Para substituir apenas o provedor $LyssProvider do conjunto atual de $LyssProvider, $ABServerProvider e $SIPStackProvider por $LyssServiceProvider, digite o seguinte:
    
        Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}

</div>

<div>

## <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>Para remover um cenário existente com o cmdlet Remove-CsClsScenario

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Se você desejar remover um cenário que foi definido anteriormente, digite o seguinte:
    
        Remove-CsClsScenario -Identity <name of scope and scenario>
    
    Por exemplo, para remover o cenário definido site:Redmond/LyssServiceScenario:
    
        Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"

O cmdlet **Remove-CsClsScenario** remove o cenário especificado, mas os rastreamentos que foram coletados ainda estarão disponíveis nos logs para pesquisa.

</div>

<div>

## <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clscontrollerpsm1-module"></a>Para carregar e descarregar o cmdlet Edit-CsClsScenario usando o módulo ClsController.psm1

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.
    
    <div>
    

    > [!IMPORTANT]  
    > O módulo ClsController.psm1 é fornecido como um download da Web separado. O módulo faz parte das ferramentas de depuração do Lync Server 2013. Por padrão, as ferramentas de depuração são instaladas no diretório C:\Program Files\Lync Server 2013\Debugging Tools.

    
    </div>

2.  No Windows PowerShell, digite:
    
        Import-Module "C:\Program Files\Lync Server 2013\Debugging Tools\ClsController.psm1"
    
    <div>
    

    > [!TIP]  
    > O carregamento bem-sucedido do módulo retorna ao prompt de comando do Windows PowerShell. Para confirmar que o módulo está carregado e que Edit-CsClsScenario está disponível, digite <CODE>Get-Help Edit-CsClsScenario</CODE>. Você deverá ver a sinopse básica da sintaxe de EditCsClsScenario.

    
    </div>

3.  Para descarregar os módulos, digite:
    
        Remove-Module ClsController
    
    <div>
    

    > [!TIP]  
    > O descarregamento bem-sucedido do módulo retorna ao prompt de comando do Windows PowerShell. Para confirmar que o módulo é descarregado, <CODE>Get-Help Edit-CsClsScenario</CODE>digite. O Windows PowerShell tentará localizar a ajuda para o cmdlet e falhará.

    
    </div>

</div>

<div>

## <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>Para remover um provedor existente de um cenário com o módulo Edit-ClsController

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Para remover um provedor do cenário AlwaysOn, digite:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
    
    Por exemplo:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
    
    Os parâmetros ScenarioName e ProviderName são posicionais (ou seja, devem ser definidos na posição esperada na linha de comando). O nome do parâmetro não precisa ser explicitamente definido se o nome do cenário estiver na segunda ou na terceira posição em relação ao nome do cmdlet na primeira posição. Usando essas informações, o comando anterior seria digitado como:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Remove
    
    A colocação posicional dos valores de parâmetro aplica-se somente a –Scenario e –Provider. Todos os outros parâmetros devem ser definidos explicitamente.

</div>

<div>

## <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>Para adicionar um provedor a um cenário com o cmdlet Edit-ClsController

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Para adicionar um provedor ao cenário AlwaysOn, digite:
    
        Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
    
    Por exemplo:
    
        Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
    
    \-LogLevel pode ser do tipo fatal, erro, aviso, info, Verbose, debug ou ALL. – Os sinalizadores podem ser qualquer um dos sinalizadores aos quais o provedor oferece suporte,\_como o componente\_TF, TF diag. –Flags também pode ter o valor ALL.
    
    O exemplo anterior também pode ser digitado com o uso do recurso posicional do cmdlet. Por exemplo, para adicionar o provedor ChatServer ao cenário AlwaysOn, digite:
    
        Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL

</div>

</div>

<span> </span>

</div>

</div>

</div>

