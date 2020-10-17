---
title: Procedimentos de recuperação de desastre do grupo de resposta do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea967dc717f36b8ab5951fa758e7c78d6130dc0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511658"
---
# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Procedimentos de recuperação de desastre do grupo de resposta no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Durante a fase de failover ou de recuperação de desastres, o grupo de resposta reside em vários pools: no pool principal (que está indisponível) e no de backup. Os grupos de resposta em ambos os pools têm o mesmo nome e proprietário (o pool principal), mas têm pais diferentes. Durante esse tempo, os cmdlets do grupo de resposta funcionam de forma um pouco diferente. Certifique-se de usar parâmetros como especificado no seguinte procedimento. Para obter detalhes sobre como os cmdlets funcionam durante a fase de failover, consulte o artigo de blog NextHop "Lync Server 2013: Recuperando grupos de resposta durante a recuperação de desastres" em [https://go.microsoft.com/fwlink/p/?LinkId=263957](https://go.microsoft.com/fwlink/p/?linkid=263957) . Este artigo do blog também se aplica à versão lançada do Lync Server 2013.

Use as etapas do procedimento a seguir para preparar e executar a recuperação de desastres para o serviço de grupo de resposta do Lync Server.

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>Execução de failover e failback do grupo de resposta

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute backups de rotina. Na linha de comando, digite:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    Por exemplo:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  Durante uma falha, depois do failover do pool de backup, importe os grupos de resposta para o pool de backup. Na linha de comando, digite:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    Se deseja substituir as configuração de nível do aplicativo no pool de backup pelas configurações do pool principal, inclua o parâmetro –ReplaceExistingSettings. Por exemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > Se não substituir as configurações no pool de backup e não for possível recuperar o pool principal, então as configurações do pool principal serão perdidas. Para obter detalhes, consulte <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for Response Group Disaster Recovery in Lync Server 2013</A>.

    
    </div>

4.  Verifique se a importação ocorreu exibindo os grupos de resposta importados. Os grupos de resposta importados ainda são de propriedade do pool principal. Faça o seguinte:
    
      - Visualize todos os fluxos de trabalho no pool de backup que são de propriedade do pool principal e verifique se todos os fluxos de trabalho do pool principal estão incluídos. Na linha de comando, digite:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por exemplo:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - Visualize todas as filas no pool de backup que são de propriedade do pool principal e verifique se todas as filas do pool principal foram incluídas. Na linha de comando, digite:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por exemplo:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Visualize todos os grupos de agentes no pool de backup que são de propriedade do pool principal e verifique se todos os grupos de agentes do pool principal foram incluídos. Na linha de comando, digite:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por exemplo:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Visualize todos os horários comerciais no pool de backup que são de propriedade do pool principal e verifique se todas as horas comerciais do pool principal foram incluídas. Na linha de comando, digite:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por exemplo:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Visualize todos os conjuntos de feriados no pool de backup que são de propriedade do pool principal e verifique se todos os conjuntos de feriados do pool principal estão incluídos. Na linha de comando, digite:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por exemplo:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    Como alternativa, você pode exibir todos os grupos de resposta no pool de backup, incluindo os de propriedade do pool principal e os do pool de backup usando o parâmetro –ShowAll em vez de –Owner. Por exemplo:
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > Você deve usar o parâmetro –ShowAll ou –Owner. Se não usar nenhum deles, os grupos de resposta importados para o pool de backup não serão listado nos resultados retornados pelos cmdlets.

    
    </div>

5.  Verifique se a importação teve êxito fazendo uma chamada para um grupo de resposta importado e verificando se a chamada foi manipulada corretamente.

6.  Solicite que agentes membros de grupos de agentes formais se conectem a seus grupos de agentes no pool de backup.

7.  Gerencie e modifique os grupos de resposta importados normalmente.
    
    <div>
    

    > [!IMPORTANT]  
    > Enquanto os grupos de resposta estão no pool de backup, você precisa usar o Shell de gerenciamento do Lync Server para gerenciá-los. Você não pode usar o painel de controle do Lync Server para gerenciar os grupos de resposta importados para o pool de backup.

    
    </div>

8.  Depois que o pool principal é restaurado e o failback for concluído, exporte os grupos de resposta de pool principal que foram importados para o pool de backup. Na linha de comando, digite:
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  Importe os grupos de resposta para o pool principal. Na linha de comando, digite:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    Por exemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > Se reconstruir um pool durante a recuperação, com o mesmo nome de domínio qualificado (FQDN) ou um diferente, será necessário usar o parâmetro –OverwriteOwner. Como regra, você sempre pode usar o parâmetro –OverwriteOwner ao importar grupos de resposta para o pool primário.

    
    </div>
    
    Se você implantou um novo pool (como um FQDN igual ou diferente) para substituir o pool principal e deseja usar as configurações de nível de aplicativo do pool de backup para o novo pool, inclua o parâmetro –ReplaceExistingSettings. Na linha de comando, digite:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    Por exemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > Se não deseja substituir as configurações de nível de aplicativo e o arquivo de música de espera padrão do novo pool pelas configurações do pool de backup, então o novo pool usará as configurações de aplicativo padrão.

    
    </div>

10. Verifique se a importação para o pool principal teve êxito exibindo a configuração do grupo de resposta importado. Faça o seguinte:
    
      - Visualize todos os fluxos de trabalho no pool principal e verifique se todos os fluxos de trabalho importados foram incluídos. Na linha de comando, digite:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por exemplo:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - Visualize todas as filas no pool principal e verifique se todas as filas importadas foram incluídas. Na linha de comando, digite:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por exemplo:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Visualize todos os grupos de agentes no pool principal e verifique se todos os grupos de agentes importados foram incluídos. Na linha de comando, digite:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        Por exemplo:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Visualize todas as horas comerciais no pool principal e verifique se todas as horas comerciais importadas foram incluídas. Na linha de comando, digite:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por exemplo:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Visualize todos os conjuntos de feriados no pool principal e verifique se todos os conjuntos de feriados importados foram incluídos. Na linha de comando, digite:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por exemplo:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. Verifique se a importação teve êxito fazendo uma chamada para um grupo de resposta importado e verificando se a chamada foi manipulada corretamente.

12. Como opção, remova os grupos de resposta do pool principal do pool de backup. Na linha de comando, digite:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    Por exemplo:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > Esta etapa crie um novo arquivo com a configuração exportada e o remove do pool de backup.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

