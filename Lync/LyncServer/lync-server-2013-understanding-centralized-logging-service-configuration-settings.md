---
title: Compreendendo as configurações centralizadas de configuração do serviço de log
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a4f9a6a2db8cb4726abc65553fc4482d349f38f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a>Compreendendo as configurações centralizadas de configuração do serviço de log no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

O serviço de log centralizado é configurado para definir o que o serviço de log destina-se a coletar, como ele coleta, de onde será coletado, e quais são as configurações de log. Você define essas configurações globalmente (ou seja, para toda a implantação) ou para um site (ou seja, um site nomeado na sua implantação). Qualquer log que você definir usará as configurações adequadas para a identidade usada para os comandos para iniciar, parar, liberar e pesquisar logs.

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a>Para exibir a configuração atual do serviço de log centralizado

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Digite o seguinte em uma linha de comando do prompt:
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > Você pode restringir ou expandir o escopo das configurações que são retornadas definindo <CODE>-Identity</CODE> -se um escopo, como "site: Redmond", para retornar apenas o CsClsConfiguration para o site Redmond. Se quiser obter detalhes sobre uma determinada parte da configuração, você pode canalizar a saída para outro cmdlet do Windows PowerShell. Por exemplo, para obter detalhes sobre os cenários definidos na configuração do site "Redmond", digite:<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE>

    
    </div>
    
    ![Exemplo de saída do Get-CsClsConfiguration.] (images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Exemplo de saída do Get-CsClsConfiguration.")
    
    O resultado do cmdlet exibe a configuração atual do serviço de log centralizado.
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Definição da Configuração</th>
    <th>Descrição</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Identidade</strong></p></td>
    <td><p>Identifica o escopo e o nome para esta configuração. Há apenas uma configuração global e uma configuração por local.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Cenários</strong></p></td>
    <td><p>Lista de todos os cenários que são definidos para esta configuração.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Termos de busca</strong></p></td>
    <td><p>Termos de busca definidos para a configuração. O Office 365, não implantações locais.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>SecurityGroups</strong></p></td>
    <td><p>Grupos de segurança definidos que controlam quem (isto é, membros dos grupos de segurança) podem ver computadores com base no local que estão. O site, nesse contexto, é o site definido no construtor de topologias.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Regiões</strong></p></td>
    <td><p>Regiões definidas são utilizadas para coletar SecurityGroups em uma região, por exemplo EMEA.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileFolder</strong></p></td>
    <td><p>Caminho definido para o local onde os arquivos de log são gravados em computadores. O CLSAgent grava os arquivos de log e é executado sob o contexto do serviço de rede. Nesse caso,% TEMP% se expande para%WINDIR%\ServiceProfiles\NetworkService\AppData\Local</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>EtlFileRolloverSizeMB</strong></p></td>
    <td><p>O parâmetro indica o tamanho máximo do arquivo de log antes que um log de rastreio de evento (.etl) novo seja criado. Um novo arquivo de log é criado quando o tamanho definido é atingido, mesmo se o tempo máximo definido no EtlFileRolloverMinutes não tiver sido atingido ainda.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EtlFileRolloverMinutes</strong></p></td>
    <td><p>Quantidade de tempo máxima definida, em minutos, que um log pode decorrer antes de um novo arquivo .etl ser criado. Um novo arquivo de log é criado quando o cronômetro expira, mesmo que o tamanho máximo definido em EtlFileRolloverSizeMB não tenha sido atingido ainda.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>TmfFileSearchPath</strong></p></td>
    <td><p>Local para buscar por arquivos de formato de mensagens de rastreio. Os arquivos de formato de mensagem de rastreamento são usados para converter os arquivos binários em um formato legível por pessoas.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalFolders</strong></p></td>
    <td><p>Caminho definido para o local onde os arquivos de cache são gravados nos computadores. O CLSAgent grava os arquivos de cache e executa sob o contexto do Serviço de Rede. Neste caso, %TEMP% expande-se para %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Por padrão, os arquivos de log e cache são gravados no mesmo diretório.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileNetworkFolder</strong></p></td>
    <td><p>Você pode definir um caminho de convenção de nomenclatura universal (UNC) para receber os arquivos de cache durante operações de log.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>CacheFileLocalRetentionPeriod</strong></p></td>
    <td><p>Definido como o tempo máximo em dias que os arquivos de cache são retidos.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>CacheFileMaxDiskUsage</strong></p></td>
    <td><p>Definido como a porcentagem de espaço em disco que pode ser utilizado pelos arquivos de cache.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ComponentThrottleLimit</strong></p></td>
    <td><p>Definido como o número máximo de rastreamentos por segundo que um componente pode produzir antes de o limitador de aceleração automática é acionado.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ComponentThrottleSample</strong></p></td>
    <td><p>Número de vezes que o ComponentThrottleLimit pode ser excedido em 60 segundos.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>MinimumClsAgentServiceVersion</strong></p></td>
    <td><p>A versão mínima do CLSAgent que pode ser executada. Esse elemento destina-se ao Office 365.</p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Visão geral do serviço de log centralizado no Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Set-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619182(v=OCS.15))  
[Remove-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619191(v=OCS.15))  
[New-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619177(v=OCS.15))  
[Get-CsClsConfiguration](https://technet.microsoft.com/en-us/library/JJ619179(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

