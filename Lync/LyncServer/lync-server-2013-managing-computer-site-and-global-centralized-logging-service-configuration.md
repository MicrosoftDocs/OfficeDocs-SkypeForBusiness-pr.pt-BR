---
title: Gerenciando o computador, o site e a configuração global do serviço de registro centralizado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f714c82fdc4ade0fc70b0a977e32ef46b26914d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a>Gerenciando o computador, o site e a configuração de serviço de log centralizado global no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-04_

O serviço de log centralizado pode ser executado em um escopo que inclui um único computador, um pool de computadores, em um escopo de site (ou seja, um site definido, como o site Redmond que contém uma coleção de computador e pools em sua implantação) ou em um escopo global (ou seja, , todos os computadores e pools na sua implantação).

Para configurar o escopo do serviço de log centralizado usando o Shell de gerenciamento do Lync Server, você deve ser membro do grupo de segurança CsAdministrator ou do controle de acesso baseado em função do CsServerAdministrator (RBAC) ou uma função RBAC personalizada que contenha qualquer um desses dois grupos. Para retornar uma lista de todas as funções RBAC às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no Shell de gerenciamento do Lync Server ou no prompt do Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

Por exemplo:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> O Windows PowerShell oferece mais opções e opções de configuração adicionais que não estão disponíveis usando CLSController. exe. O CLSController oferece um método rápido e conciso para executar comandos, mas está limitado ao conjunto de comandos disponíveis para o CLSController. O Windows PowerShell não está limitado apenas ao comando disponível para o processador de comando do CLSController e fornece um conjunto mais amplo de comandos e um conjunto mais rico de opções. Por exemplo, CLSController. exe fornece uma opção de escopo para – computadores e – pools. Com o Windows PowerShell, você pode indicar computadores ou pools na maioria dos comandos e, ao definir novos cenários (o CLSController tem um número finito de cenários que não podem ser modificados pelo usuário) você pode definir um site ou escopo global. Esse recurso poderoso do Windows PowerShell permite definir um cenário para um site ou escopo global, mas limitar o registro em log para um computador ou pool.<BR>Há diferenças fundamentais entre os comandos de linha de comando que você pode executar no Windows PowerShell ou no CLSController. O Windows PowerShell fornece um método rico para configurar e definir cenários e reutilizá-los de forma significativa para seus cenários de solução de problemas. Embora o CLSController forneça uma maneira rápida e eficiente para emitir comandos e obter resultados, o conjunto de comandos do CLSController está limitado aos comandos finitos que você tem disponível na linha de comando. Ao contrário dos cmdlets do Windows PowerShell, o CLSController não pode definir novos cenários, gerenciar o escopo em um nível global ou de site, além de muitas outras limitações de um conjunto de comandos finito que não pode ser configurado dinamicamente. Embora o CLSController forneça um meio de execução rápida, o Windows PowerShell fornece um meio de estender a funcionalidade do serviço de log centralizado além do que é possível com o CLSController.



</div>

Um escopo de computador exclusivo pode ser definido durante a execução de um comando [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) e [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) usando o parâmetro –Computers. Esse parâmetro aceita uma lista separada por vírgulas de FQDNs (nomes de domínio totalmente qualificados) para o computador de destino.

<div>


> [!TIP]
> Você pode também definir –Pools e uma lista de pools separada por vírgula na qual você deseja executar os comandos de log.



</div>

Os escopos do site e do global são definidos nos cmdlets do serviço de log **novo**, de **conjunto**e **de remoção** centralizado. Os exemplos a seguir demonstram como definir o escopo global ou de um site.

<div>


> [!IMPORTANT]
> Os comandos mostrados podem conter parâmetros e conceitos que são abordados em outras seções. O exemplo de comandos tem a finalidade de demonstrar o uso do parâmetro <STRONG>–Identity</STRONG> para definir escopo e os outros parâmetros são incluídos para a integridade e para especificar o escopo. Para obter detalhes sobre os cmdlets do <STRONG>Set-CsClsConfiguration</STRONG>, consulte <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> na documentação Operações.



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a>Para recuperar a configuração atual do serviço de log centralizado

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Digite o seguinte no prompt de linha de comando:
    
        Get-CsClsConfiguration

Use os cmdlets **New-CsClsConfiguration** e **Set-CsClsConfiguration** para criar uma nova configuração ou para atualizar uma configuração existente.

Quando o **Get-CsClsConfiguration** é executado, ele exibe informações semelhantes à seguinte captura de tela, onde a implantação atualmente tem a configuração global, mas nenhuma configuração de site definida:

![Exemplo de saída do Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Exemplo de saída do Get-CsClsConfiguration.")

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a>Para recuperar a configuração atual do serviço de log centralizado no repositório local do computador

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Digite o seguinte no prompt de linha de comando:
    
        Get-CsClsConfiguration -LocalStore

Quando você usa o primeiro exemplo em que **Get-CsClsConfiguration** não especifica nenhum parâmetro, o comando faz referência ao repositório central de gerenciamento dos dados. Se você especificar o parâmetro – LocalStore, o comando referenciará o computador LocalStore em vez do repositório de gerenciamento central.

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a>Para recuperar uma lista de cenários definidos no momento

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Digite o seguinte no prompt de linha de comando:
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    Por exemplo, para recuperar os cenários definidos no escopo global:
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

O cmdlet **Get-CsClsConfiguration** sempre exibe os cenários que fazem parte de uma dada configuração de escopo. Na maioria dos casos, nem todos os cenários são exibidos e estão truncados. O comando usado aqui lista todos os cenários e as informações parciais sobre quais provedores, configurações e sinalizadores são usados.

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para atualizar um escopo global para o serviço de log centralizado usando o Windows PowerShell

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Digite o seguinte no prompt de linha de comando:
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    Por exemplo:
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

O comando diz ao CLSAgent em cada computador e pool na implantação para definir o tamanho do valor de sobreposição no arquivo de rastreamento para 40 megabytes. Os computadores e pools em todos os sites são afetados pelo comando, e definirão seu valor configurado de sobreposição de log de rastreamento para 40 megabytes.

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a>Para atualizar um escopo de site para o serviço de log centralizado usando o Windows PowerShell

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Digite o seguinte no prompt de linha de comando:
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    Por exemplo:
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > Como observado no exemplo, o local padrão dos arquivos de log é %TEMP%\Tracing. No entanto, como é o CLSAgent que está gravando o arquivo, e o CSLAgent é executado no Serviço de Rede, a variável %TEMP% expande para %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.

    
    </div>

O comando diz ao CLSAgent em cada computador e pool no site da Redmond para definir o tamanho do valor de sobreposição no arquivo de rastreamento para 40 megabytes. Os computadores e pools em outros sites não serão afetados pelo comando, e continuarão a usar o valor atualmente configurado de sobreposição de log de rastreamento definido pelo padrão (20 megabytes) ou durante o início da sessão de log.

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a>Para criar uma nova configuração de serviço de log centralizado

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Digite o seguinte no prompt de linha de comando:
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > New-CsClsConfiguration fornece acesso a um grande número de definições de configuração adicionais. Para obter detalhes sobre as opções de configuração, consulte <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> e <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">noções básicas sobre as configurações de serviço de log centralizado no Lync Server 2013</A>.

    
    </div>
    
    Por exemplo, para criar uma nova configuração que defina uma pasta de rede para arquivos de cache, o período de tempo de sobreposição dos arquivos de log e tamanho de sobreposição dos arquivos de log, você deverá digitar:
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

Você deve planejar cuidadosamente a criação de novas configurações e como definir novas propriedades para o serviço de log centralizado. Você deve ter cuidado ao fazer alterações e ter certeza que compreende o impacto da sua capacidade de registrar cenários de problema corretamente. Você deve fazer alterações na configuração que melhorarão sua capacidade de gerenciar logs para um tamanho e período de sobreposição que permita resolver problemas, quando surgirem.

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a>Para remover uma configuração de serviço de log centralizado existente

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Digite o seguinte no prompt de linha de comando:
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    Por exemplo, para remover uma configuração de serviço de log centralizada que você criou para aumentar o tempo de substituição do arquivo de log, aumente o tamanho do arquivo de log de substituição e defina o local do cache do arquivo de log para um compartilhamento de rede da seguinte maneira:
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > Esta é a nova configuração que foi criada no procedimento "para criar uma nova configuração de serviço de log centralizado".

    
    </div>

Se decidir remover a configuração no nível do site, o site usará as configurações globais.

</div>

<div>

## <a name="see-also"></a>Confira também


[Visão geral do serviço de log centralizado no Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Gerenciar as configurações centralizadas de configuração do serviço de log no Lync Server 2013](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

