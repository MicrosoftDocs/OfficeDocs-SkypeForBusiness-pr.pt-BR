---
title: Noções básicas sobre definições de configuração do serviço de registro em log centralizado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1be1fcb159f3ad75688e63bb61de9afef9f5a8a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="7c789-102">Noções básicas sobre definições de configuração de serviço de registro em log centralizado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c789-102">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c789-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7c789-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7c789-104">O serviço de registro em log centralizado é configurado para definir o que o serviço de registro em log deve coletar, como ele coleta, onde coletará e quais serão as configurações de log.</span><span class="sxs-lookup"><span data-stu-id="7c789-104">The Centralized Logging Service is configured to define what the logging service is intended to collect, how it collects, where it will collect from, and what the log settings are.</span></span> <span data-ttu-id="7c789-105">Você define essas configurações globalmente (ou seja, para toda a implantação) ou para um site (ou seja, um site nomeado em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="7c789-105">You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment).</span></span> <span data-ttu-id="7c789-106">Qualquer log que você definir usará as configurações apropriadas para a identidade que você usa para os comandos Iniciar, parar, liberar e pesquisar logs.</span><span class="sxs-lookup"><span data-stu-id="7c789-106">Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.</span></span>

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="7c789-107">Para exibir a configuração atual do serviço de registro em log centralizado</span><span class="sxs-lookup"><span data-stu-id="7c789-107">To display the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="7c789-108">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7c789-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7c789-109">Digite o seguinte em uma linha de comando do promt:</span><span class="sxs-lookup"><span data-stu-id="7c789-109">Type the following at a command-line prompt:</span></span>
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > <span data-ttu-id="7c789-110">Você pode restringir ou expandir o escopo das definições de configuração que são retornadas definindo <CODE>-Identity</CODE> um escopo, como "site: Redmond", para retornar apenas o CsClsConfiguration para o site Redmond.</span><span class="sxs-lookup"><span data-stu-id="7c789-110">You can narrow or expand the scope of the configuration settings that are returned by defining <CODE>-Identity</CODE> and a scope, such as "Site:Redmond" to return only the CsClsConfiguration for the site Redmond.</span></span> <span data-ttu-id="7c789-111">Se quiser obter detalhes sobre uma determinada parte da configuração, você pode canalizar a saída para outro cmdlet do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7c789-111">If you want details about a given portion of the configuration, you can pipe the output into another Windows PowerShell cmdlet.</span></span> <span data-ttu-id="7c789-112">Por exemplo, para obter detalhes sobre os cenários definidos na configuração para o site "Redmond", digite:<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span><span class="sxs-lookup"><span data-stu-id="7c789-112">For example, to get details about the scenarios defined in the configuration for site "Redmond", type: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span></span>

    
    </div>
    
    <span data-ttu-id="7c789-113">![Exemplo de saída de Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Exemplo de saída de Get-CsClsConfiguration.")</span><span class="sxs-lookup"><span data-stu-id="7c789-113">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>
    
    <span data-ttu-id="7c789-114">O resultado do cmdlet exibe a configuração atual do serviço de registro em log centralizado.</span><span class="sxs-lookup"><span data-stu-id="7c789-114">The result from the cmdlet displays the current configuration of the Centralized Logging Service.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="7c789-115">Definição da Configuração</span><span class="sxs-lookup"><span data-stu-id="7c789-115">Configuration Setting</span></span></th>
    <th><span data-ttu-id="7c789-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="7c789-116">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="7c789-117"><strong>Identidade</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-117"><strong>Identity</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-p103">Identifica o escopo e o nome para esta configuração. Há apenas uma configuração global e uma configuração por local.</span><span class="sxs-lookup"><span data-stu-id="7c789-p103">Identifies the scope and name for this configuration. There is only one Global configuration, and one configuration per site.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7c789-120"><strong>Cenários</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-120"><strong>Scenarios</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-121">Lista de todos os cenários que são definidos para esta configuração.</span><span class="sxs-lookup"><span data-stu-id="7c789-121">Listing of all scenarios that are defined for this configuration.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7c789-122"><strong>SearchTerms</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-122"><strong>SearchTerms</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-123">Termos de busca definidos para a configuração.</span><span class="sxs-lookup"><span data-stu-id="7c789-123">Defined search terms for the configuration.</span></span> <span data-ttu-id="7c789-124">O Office 365, não implantações locais.</span><span class="sxs-lookup"><span data-stu-id="7c789-124">Office 365, not on-premises deployments.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7c789-125"><strong>SecurityGroups</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-125"><strong>SecurityGroups</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-126">Grupos de segurança definidos que controlam quem (isto é, membros dos grupos de segurança) podem ver computadores com base no local que estão.</span><span class="sxs-lookup"><span data-stu-id="7c789-126">Defined security groups that control who (that is, members of the security groups) can see computers based on the site they are located in.</span></span> <span data-ttu-id="7c789-127">O site, neste contexto, é o site, conforme definido no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="7c789-127">Site, in this context, is the site as defined in Topology Builder.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7c789-128"><strong>Regiões</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-128"><strong>Regions</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-129">Regiões definidas são utilizadas para coletar SecurityGroups em uma região, por exemplo EMEA.</span><span class="sxs-lookup"><span data-stu-id="7c789-129">Defined regions are used to collect SecurityGroups into a region, for example EMEA.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7c789-130"><strong>EtlFileFolder</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-130"><strong>EtlFileFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-p106">Caminho definido para a localização onde os arquivos de log são gravados nos computadores. O CLSAgent grava os arquivos de log e executa sob o contexto do Serviço de Rede. Neste caso, %TEMP% expande-se para %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span><span class="sxs-lookup"><span data-stu-id="7c789-p106">Defined path to the location where log files are written on computers. CLSAgent writes the log files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7c789-134"><strong>EtlFileRolloverSizeMB</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-134"><strong>EtlFileRolloverSizeMB</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-p107">O parâmetro indica o tamanho máximo do arquivo de log antes que um log de rastreio de evento (.etl) novo seja criado. Um novo arquivo de log é criado quando o tamanho definido é atingido, mesmo se o tempo máximo definido no EtlFileRolloverMinutes não tiver sido atingido ainda.</span><span class="sxs-lookup"><span data-stu-id="7c789-p107">The parameter indicates the maximum size of the log file before a new event trace log (.etl) file is created. A new log file is created when the defined size is reached even if the maximum time set in EtlFileRolloverMinutes has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7c789-137"><strong>EtlFileRolloverMinutes</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-137"><strong>EtlFileRolloverMinutes</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-p108">Quantidade de tempo máxima definida, em minutos, que um log pode decorrer antes de um novo arquivo .etl ser criado. Um novo arquivo de log é criado quando o cronômetro expira, mesmo que o tamanho máximo definido em EtlFileRolloverSizeMB não tenha sido atingido ainda.</span><span class="sxs-lookup"><span data-stu-id="7c789-p108">Defined maximum amount of time, in minutes, that a log can elapse before a new .etl file is created. A new log file is created when the timer expires even if the maximum size set in EtlFileRolloverSizeMB has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7c789-140"><strong>TmfFileSearchPath</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-140"><strong>TmfFileSearchPath</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-p109">Local para buscar por arquivos de formato de mensagens de rastreio. Os arquivos de formato de mensagem são utilizados para converter os arquivos binários em um formato humanamente legível.</span><span class="sxs-lookup"><span data-stu-id="7c789-p109">Location to search for the trace message format files. The trace message format files are used to convert the binary files into a human readable format.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7c789-143"><strong>CacheFileLocalFolders</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-143"><strong>CacheFileLocalFolders</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-p110">Caminho definido para o local onde os arquivos de cache são gravados nos computadores. O CLSAgent grava os arquivos de cache e executa sob o contexto do Serviço de Rede. Neste caso, %TEMP% expande-se para %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Por padrão, os arquivos de log e cache são gravados no mesmo diretório.</span><span class="sxs-lookup"><span data-stu-id="7c789-p110">Defined path to the location where cache files are written on computers. CLSAgent writes the cache files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. By default, cache files and log files are written to the same directory.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7c789-148"><strong>CacheFileNetworkFolder</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-148"><strong>CacheFileNetworkFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-149">Você pode definir um caminho de convenção de nomenclatura universal (UNC) para receber os arquivos de cache durante operações de log.</span><span class="sxs-lookup"><span data-stu-id="7c789-149">You can define a universal naming convention (UNC) path to receive the cache files during logging operations.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7c789-150"><strong>CacheFileLocalRetentionPeriod</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-150"><strong>CacheFileLocalRetentionPeriod</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-151">Definido como o tempo máximo em dias que os arquivos de cache são retidos.</span><span class="sxs-lookup"><span data-stu-id="7c789-151">Defined as the maximum time, in days, that cache files are retained.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7c789-152"><strong>CacheFileMaxDiskUsage</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-152"><strong>CacheFileMaxDiskUsage</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-153">Definido como a porcentagem de espaço em disco que pode ser utilizado pelos arquivos de cache.</span><span class="sxs-lookup"><span data-stu-id="7c789-153">Defined as the percentage of disk space that can be used by the cache files.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7c789-154"><strong>ComponentThrottleLimit</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-154"><strong>ComponentThrottleLimit</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-155">Definido como o número máximo de rastreios por segundo que um componente pode produzir antes de o limitador de aceleração automática é acionado.</span><span class="sxs-lookup"><span data-stu-id="7c789-155">Defined as the maximum number of traces per second that a component can produce before the automatic throttle limiter is triggered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="7c789-156"><strong>ComponentThrottleSample</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-156"><strong>ComponentThrottleSample</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-157">Número de vezes em 60 segundos em que o ComponentThrottleLimit pode ser excedido.</span><span class="sxs-lookup"><span data-stu-id="7c789-157">Number of times in 60 seconds that the ComponentThrottleLimit can be exceeded.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="7c789-158"><strong>MinimumClsAgentServiceVersion</strong></span><span class="sxs-lookup"><span data-stu-id="7c789-158"><strong>MinimumClsAgentServiceVersion</strong></span></span></p></td>
    <td><p><span data-ttu-id="7c789-159">A versão mínima do CLSAgent que pode ser executada.</span><span class="sxs-lookup"><span data-stu-id="7c789-159">The minimum version of the CLSAgent allowed to run.</span></span> <span data-ttu-id="7c789-160">Este elemento é destinado ao Office 365.</span><span class="sxs-lookup"><span data-stu-id="7c789-160">This element is intended for Office 365.</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7c789-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="7c789-161">See Also</span></span>


[<span data-ttu-id="7c789-162">Visão geral do serviço de registro em log centralizado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c789-162">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="7c789-163">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7c789-163">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="7c789-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7c789-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
<span data-ttu-id="7c789-165">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7c789-165">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="7c789-166">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7c789-166">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

