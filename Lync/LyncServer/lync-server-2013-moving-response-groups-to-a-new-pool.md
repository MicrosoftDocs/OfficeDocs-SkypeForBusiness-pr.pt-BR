---
title: 'Lync Server 2013: movendo grupos de resposta para um novo pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73138d5cbde1a835ab632fe98bf57ef58f11c0da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>Movendo grupos de resposta para um novo pool no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

O Lync Server 2013 introduz novo cmdlet support para mover grupos de resposta de um pool para outro pool, mesmo quando o FQDN (nome de domínio totalmente qualificado) for diferente.

Use as etapas no procedimento a seguir para mover grupos de resposta de um pool de front-ends para outro pool de front-ends com um FQDN diferente.

<div>


> [!NOTE]  
> Em um ambiente de coexistência, você pode mover grupos de resposta somente entre pools de front-ends do Lync Server 2013&nbsp;.



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>Para mover grupos de resposta para um pool com um FQDN diferente

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Exporte os grupos de resposta no pool de origem. Na linha de comando, digite:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    Por exemplo:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    Para remover os grupos de resposta de um pool de origem durante a exportação, inclua o parâmetro –RemoveExportedConfiguration. Por exemplo:
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  Importe os grupos de resposta para o pool de destino e atribua o pool de destino como o novo proprietário. Na linha de comando, digite:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    Se você também quiser copiar as configurações de nível de aplicativo do grupo de resposta do pool de origem para o pool de destino, inclua o parâmetro – ReplaceExistingRgsSettings. É possível definir apenas um conjunto de configurações a nível de aplicativo por pool. Se você copiar as configurações a nível de aplicativo do pool de origem para o pool de destino, as configurações do pool de origem substituem as configurações para o pool de destino. Se você não copiar as configurações a nível de aplicativo do pool de origem, as configurações existentes do pool de destino se aplicam aos grupos de resposta importados.
    
    Por exemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > As configurações a nível de aplicativo incluem a configuração de música em espera padrão, o arquivo de áudio de música em espera padrão, o período de espera do agente e a configuração de contexto da chamada. Para exibir estas definições de configuração, execute o cmdlet <STRONG>Get-CsRgsConfiguration</STRONG>. Para obter detalhes sobre esse cmdlet, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>.

    
    </div>

4.  Verifique se a importação teve êxito ao exibir a configuração do grupo de resposta importado fazendo o seguinte:
    
      - Verifique se todos os fluxos de trabalho foram importados. Na linha de comando, digite o seguinte:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Verifique se todas as filas foram importadas. Na linha de comando, digite o seguinte:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Verifique se todos os grupos de agente foram importados. Na linha de comando, digite o seguinte:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - Verifique se todas as horas comerciais foram importadas. Na linha de comando, digite o seguinte:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - Verifique se todos os conjuntos de feriados foram importados. Na linha de comando, digite o seguinte:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  Verifique se a importação teve êxito ao realizar uma chamada para um dos grupos de resposta e verificando se a chamada foi tratada corretamente.

6.  Agentes de solicitação membros de grupos de agente formais para se conectar em seus grupos de agentes no pool de destino.

7.  Se você não removeu anteriormente grupos de resposta do pool de origem, remova os grupos de resposta do pool de origem. Na linha de comando, digite:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    Por exemplo:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

