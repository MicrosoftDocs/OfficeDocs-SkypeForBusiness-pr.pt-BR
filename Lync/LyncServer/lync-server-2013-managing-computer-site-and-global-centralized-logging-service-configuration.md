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

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="622b6-102">Gerenciando o computador, o site e a configuração de serviço de log centralizado global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="622b6-102">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="622b6-103">_**Tópico da última modificação:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="622b6-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="622b6-104">O serviço de log centralizado pode ser executado em um escopo que inclui um único computador, um pool de computadores, em um escopo de site (ou seja, um site definido, como o site Redmond que contém uma coleção de computador e pools em sua implantação) ou em um escopo global (ou seja, , todos os computadores e pools na sua implantação).</span><span class="sxs-lookup"><span data-stu-id="622b6-104">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="622b6-105">Para configurar o escopo do serviço de log centralizado usando o Shell de gerenciamento do Lync Server, você deve ser membro do grupo de segurança CsAdministrator ou do controle de acesso baseado em função do CsServerAdministrator (RBAC) ou uma função RBAC personalizada que contenha qualquer um desses dois grupos.</span><span class="sxs-lookup"><span data-stu-id="622b6-105">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="622b6-106">Para retornar uma lista de todas as funções RBAC às quais esse cmdlet foi atribuído (incluindo qualquer função RBAC personalizada que você criou), execute o seguinte comando no Shell de gerenciamento do Lync Server ou no prompt do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="622b6-106">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="622b6-107">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="622b6-107">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="622b6-108">O Windows PowerShell oferece mais opções e opções de configuração adicionais que não estão disponíveis usando CLSController. exe.</span><span class="sxs-lookup"><span data-stu-id="622b6-108">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="622b6-109">O CLSController oferece um método rápido e conciso para executar comandos, mas está limitado ao conjunto de comandos disponíveis para o CLSController.</span><span class="sxs-lookup"><span data-stu-id="622b6-109">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="622b6-110">O Windows PowerShell não está limitado apenas ao comando disponível para o processador de comando do CLSController e fornece um conjunto mais amplo de comandos e um conjunto mais rico de opções.</span><span class="sxs-lookup"><span data-stu-id="622b6-110">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="622b6-111">Por exemplo, CLSController. exe fornece uma opção de escopo para – computadores e – pools.</span><span class="sxs-lookup"><span data-stu-id="622b6-111">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="622b6-112">Com o Windows PowerShell, você pode indicar computadores ou pools na maioria dos comandos e, ao definir novos cenários (o CLSController tem um número finito de cenários que não podem ser modificados pelo usuário) você pode definir um site ou escopo global.</span><span class="sxs-lookup"><span data-stu-id="622b6-112">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="622b6-113">Esse recurso poderoso do Windows PowerShell permite definir um cenário para um site ou escopo global, mas limitar o registro em log para um computador ou pool.</span><span class="sxs-lookup"><span data-stu-id="622b6-113">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="622b6-114">Há diferenças fundamentais entre os comandos de linha de comando que você pode executar no Windows PowerShell ou no CLSController.</span><span class="sxs-lookup"><span data-stu-id="622b6-114">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="622b6-115">O Windows PowerShell fornece um método rico para configurar e definir cenários e reutilizá-los de forma significativa para seus cenários de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="622b6-115">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="622b6-116">Embora o CLSController forneça uma maneira rápida e eficiente para emitir comandos e obter resultados, o conjunto de comandos do CLSController está limitado aos comandos finitos que você tem disponível na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="622b6-116">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="622b6-117">Ao contrário dos cmdlets do Windows PowerShell, o CLSController não pode definir novos cenários, gerenciar o escopo em um nível global ou de site, além de muitas outras limitações de um conjunto de comandos finito que não pode ser configurado dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="622b6-117">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="622b6-118">Embora o CLSController forneça um meio de execução rápida, o Windows PowerShell fornece um meio de estender a funcionalidade do serviço de log centralizado além do que é possível com o CLSController.</span><span class="sxs-lookup"><span data-stu-id="622b6-118">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="622b6-p104">Um escopo de computador exclusivo pode ser definido durante a execução de um comando [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) e [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) usando o parâmetro –Computers. Esse parâmetro aceita uma lista separada por vírgulas de FQDNs (nomes de domínio totalmente qualificados) para o computador de destino.</span><span class="sxs-lookup"><span data-stu-id="622b6-p104">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/en-us/library/JJ619170(v=OCS.15)) command using the –Computers parameter. The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="622b6-121">Você pode também definir –Pools e uma lista de pools separada por vírgula na qual você deseja executar os comandos de log.</span><span class="sxs-lookup"><span data-stu-id="622b6-121">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="622b6-122">Os escopos do site e do global são definidos nos cmdlets do serviço de log **novo**, de **conjunto**e **de remoção** centralizado.</span><span class="sxs-lookup"><span data-stu-id="622b6-122">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="622b6-123">Os exemplos a seguir demonstram como definir o escopo global ou de um site.</span><span class="sxs-lookup"><span data-stu-id="622b6-123">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="622b6-124">Os comandos mostrados podem conter parâmetros e conceitos que são abordados em outras seções.</span><span class="sxs-lookup"><span data-stu-id="622b6-124">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="622b6-125">O exemplo de comandos tem a finalidade de demonstrar o uso do parâmetro <STRONG>–Identity</STRONG> para definir escopo e os outros parâmetros são incluídos para a integridade e para especificar o escopo.</span><span class="sxs-lookup"><span data-stu-id="622b6-125">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="622b6-126">Para obter detalhes sobre os cmdlets do <STRONG>Set-CsClsConfiguration</STRONG>, consulte <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="622b6-126">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="622b6-127">Para recuperar a configuração atual do serviço de log centralizado</span><span class="sxs-lookup"><span data-stu-id="622b6-127">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="622b6-128">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="622b6-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="622b6-129">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="622b6-129">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="622b6-130">Use os cmdlets **New-CsClsConfiguration** e **Set-CsClsConfiguration** para criar uma nova configuração ou para atualizar uma configuração existente.</span><span class="sxs-lookup"><span data-stu-id="622b6-130">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="622b6-131">Quando o **Get-CsClsConfiguration** é executado, ele exibe informações semelhantes à seguinte captura de tela, onde a implantação atualmente tem a configuração global, mas nenhuma configuração de site definida:</span><span class="sxs-lookup"><span data-stu-id="622b6-131">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="622b6-132">![Exemplo de saída do Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Exemplo de saída do Get-CsClsConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="622b6-132">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="622b6-133">Para recuperar a configuração atual do serviço de log centralizado no repositório local do computador</span><span class="sxs-lookup"><span data-stu-id="622b6-133">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="622b6-134">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="622b6-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="622b6-135">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="622b6-135">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="622b6-136">Quando você usa o primeiro exemplo em que **Get-CsClsConfiguration** não especifica nenhum parâmetro, o comando faz referência ao repositório central de gerenciamento dos dados.</span><span class="sxs-lookup"><span data-stu-id="622b6-136">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="622b6-137">Se você especificar o parâmetro – LocalStore, o comando referenciará o computador LocalStore em vez do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="622b6-137">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="622b6-138">Para recuperar uma lista de cenários definidos no momento</span><span class="sxs-lookup"><span data-stu-id="622b6-138">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="622b6-139">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="622b6-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="622b6-140">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="622b6-140">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="622b6-141">Por exemplo, para recuperar os cenários definidos no escopo global:</span><span class="sxs-lookup"><span data-stu-id="622b6-141">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="622b6-142">O cmdlet **Get-CsClsConfiguration** sempre exibe os cenários que fazem parte de uma dada configuração de escopo.</span><span class="sxs-lookup"><span data-stu-id="622b6-142">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="622b6-143">Na maioria dos casos, nem todos os cenários são exibidos e estão truncados.</span><span class="sxs-lookup"><span data-stu-id="622b6-143">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="622b6-144">O comando usado aqui lista todos os cenários e as informações parciais sobre quais provedores, configurações e sinalizadores são usados.</span><span class="sxs-lookup"><span data-stu-id="622b6-144">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="622b6-145">Para atualizar um escopo global para o serviço de log centralizado usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="622b6-145">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="622b6-146">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="622b6-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="622b6-147">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="622b6-147">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="622b6-148">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="622b6-148">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="622b6-p109">O comando diz ao CLSAgent em cada computador e pool na implantação para definir o tamanho do valor de sobreposição no arquivo de rastreamento para 40 megabytes. Os computadores e pools em todos os sites são afetados pelo comando, e definirão seu valor configurado de sobreposição de log de rastreamento para 40 megabytes.</span><span class="sxs-lookup"><span data-stu-id="622b6-p109">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="622b6-151">Para atualizar um escopo de site para o serviço de log centralizado usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="622b6-151">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="622b6-152">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="622b6-152">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="622b6-153">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="622b6-153">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="622b6-154">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="622b6-154">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="622b6-p110">Como observado no exemplo, o local padrão dos arquivos de log é %TEMP%\Tracing. No entanto, como é o CLSAgent que está gravando o arquivo, e o CSLAgent é executado no Serviço de Rede, a variável %TEMP% expande para %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span><span class="sxs-lookup"><span data-stu-id="622b6-p110">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="622b6-p111">O comando diz ao CLSAgent em cada computador e pool no site da Redmond para definir o tamanho do valor de sobreposição no arquivo de rastreamento para 40 megabytes. Os computadores e pools em outros sites não serão afetados pelo comando, e continuarão a usar o valor atualmente configurado de sobreposição de log de rastreamento definido pelo padrão (20 megabytes) ou durante o início da sessão de log.</span><span class="sxs-lookup"><span data-stu-id="622b6-p111">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="622b6-159">Para criar uma nova configuração de serviço de log centralizado</span><span class="sxs-lookup"><span data-stu-id="622b6-159">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="622b6-160">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="622b6-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="622b6-161">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="622b6-161">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="622b6-162">New-CsClsConfiguration fornece acesso a um grande número de definições de configuração adicionais.</span><span class="sxs-lookup"><span data-stu-id="622b6-162">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="622b6-163">Para obter detalhes sobre as opções de configuração, consulte <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> e <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">noções básicas sobre as configurações de serviço de log centralizado no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="622b6-163">For details about the configuration options, see <A href="https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="622b6-164">Por exemplo, para criar uma nova configuração que defina uma pasta de rede para arquivos de cache, o período de tempo de sobreposição dos arquivos de log e tamanho de sobreposição dos arquivos de log, você deverá digitar:</span><span class="sxs-lookup"><span data-stu-id="622b6-164">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="622b6-165">Você deve planejar cuidadosamente a criação de novas configurações e como definir novas propriedades para o serviço de log centralizado.</span><span class="sxs-lookup"><span data-stu-id="622b6-165">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="622b6-166">Você deve ter cuidado ao fazer alterações e ter certeza que compreende o impacto da sua capacidade de registrar cenários de problema corretamente.</span><span class="sxs-lookup"><span data-stu-id="622b6-166">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="622b6-167">Você deve fazer alterações na configuração que melhorarão sua capacidade de gerenciar logs para um tamanho e período de sobreposição que permita resolver problemas, quando surgirem.</span><span class="sxs-lookup"><span data-stu-id="622b6-167">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="622b6-168">Para remover uma configuração de serviço de log centralizado existente</span><span class="sxs-lookup"><span data-stu-id="622b6-168">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="622b6-169">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="622b6-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="622b6-170">Digite o seguinte no prompt de linha de comando:</span><span class="sxs-lookup"><span data-stu-id="622b6-170">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="622b6-171">Por exemplo, para remover uma configuração de serviço de log centralizada que você criou para aumentar o tempo de substituição do arquivo de log, aumente o tamanho do arquivo de log de substituição e defina o local do cache do arquivo de log para um compartilhamento de rede da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="622b6-171">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="622b6-172">Esta é a nova configuração que foi criada no procedimento "para criar uma nova configuração de serviço de log centralizado".</span><span class="sxs-lookup"><span data-stu-id="622b6-172">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="622b6-173">Se decidir remover a configuração no nível do site, o site usará as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="622b6-173">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="622b6-174">Confira também</span><span class="sxs-lookup"><span data-stu-id="622b6-174">See Also</span></span>


[<span data-ttu-id="622b6-175">Visão geral do serviço de log centralizado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="622b6-175">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="622b6-176">Gerenciar as configurações centralizadas de configuração do serviço de log no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="622b6-176">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="622b6-177">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="622b6-177">[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="622b6-178">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="622b6-178">[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="622b6-179">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="622b6-179">[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="622b6-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="622b6-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

