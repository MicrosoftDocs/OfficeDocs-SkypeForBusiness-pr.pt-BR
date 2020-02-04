---
title: 'Lync Server 2013: Procedimento de recuperação de desastre do grupo de resposta'
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
ms.openlocfilehash: 5325f84ff5bf5a0f8d9d1a856110e0ac18b37d93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a>Procedimento de recuperação de desastre do grupo de resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Durante a fase de failover da recuperação de desastres, os grupos de resposta residem em vários pools: no pool primário (que não está disponível) e no pool de backup. Os grupos de resposta em ambos os pools têm o mesmo nome e o mesmo proprietário (o pool primário), mas têm pais diferentes. Durante esse tempo, os cmdlets do grupo de resposta funcionam de maneira um pouco diferente. Certifique-se de usar parâmetros conforme especificado no procedimento a seguir. Para obter detalhes sobre como os cmdlets funcionam durante a fase de failover, consulte artigo do blog NextHop "Lync Server 2013: Recuperando grupos de respostas durante [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)a recuperação de desastres" em. Este artigo de blog também se aplica à versão de lançamento do Lync Server 2013.

Use as etapas do procedimento a seguir para se preparar e executar a recuperação de desastres para o serviço do grupo de resposta do Lync Server.

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a>Para fazer failover e failback do grupo de resposta

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Fazer backups rotineiramente. Na linha de comando, digite:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    Por exemplo:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  Durante uma interrupção, após o failover do pool de backup, importe os grupos de resposta para o pool de backup. Na linha de comando, digite:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    Se você quiser substituir as configurações no nível do aplicativo no pool de backup pelas configurações do pool primário, inclua o parâmetro – ReplaceExistingSettings. Por exemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > Se você não substituir as configurações no pool de backup e o pool primário não puder ser recuperado, as configurações do pool primário serão perdidas. Para obter detalhes, consulte <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">planejando a recuperação de desastres do grupo de resposta no Lync Server 2013</A>.

    
    </div>

4.  Verifique se a importação foi bem-sucedida exibindo os grupos de resposta importados. Os grupos de resposta importados ainda são pertencentes ao pool primário. Do the following:
    
      - Exiba todos os fluxos de trabalho do pool de backup que pertencem ao pool primário e verifique se todos os fluxos de trabalho do pool primário estão incluídos. Na linha de comando, digite:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por exemplo:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - Exiba todas as filas do pool de backup que são Propriedade do pool primário e verifique se todas as filas do pool primário estão incluídas. Na linha de comando, digite:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por exemplo:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Exiba todos os grupos de agente no pool de backup que pertencem ao pool primário e verifique se todos os grupos de agente de pool primário estão incluídos. Na linha de comando, digite:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por exemplo:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Exiba todas as horas de negócios no pool de backup que são Propriedade do pool primário e verifique se todas as horas de trabalho do pool primário estão incluídas. Na linha de comando, digite:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por exemplo:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - Exiba todos os conjuntos de feriados no pool de backup que pertencem ao pool primário e verifique se todos os conjuntos de feriados do pool primário estão incluídos. Na linha de comando, digite:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        Por exemplo:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    Como alternativa, você pode exibir todos os grupos de resposta no pool de backup, incluindo aqueles pertencentes ao pool primário e àqueles pertencentes ao pool de backup usando o parâmetro – ShowAll em vez do parâmetro – Owner. Por exemplo:
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > Você deve usar o parâmetro – ShowAll ou o parâmetro – Owner. Se você não usar nenhum desses parâmetros, os grupos de resposta que você importou para o pool de backup não serão listados nos resultados retornados pelos cmdlets.

    
    </div>

5.  Verifique se a importação foi bem-sucedida fazendo uma chamada para um grupo de resposta importada e verificando se a chamada foi manipulada corretamente.

6.  Solicite aos agentes que são membros de grupos de agentes formais para entrar em seus grupos de agente no pool de backup.

7.  Gerencie e modifique os grupos de resposta importados normalmente.
    
    <div>
    

    > [!IMPORTANT]  
    > Enquanto os grupos de resposta estiverem no pool de backup, você precisará usar o Shell de gerenciamento do Lync Server para gerenciá-los. Você não pode usar o painel de controle do Lync Server para gerenciar os grupos de resposta importados para o pool de backup.

    
    </div>

8.  Depois que o pool primário for restaurado e o failback estiver concluído, exporte os grupos de resposta de pool primário que foram importados para o pool de backup. Na linha de comando, digite:
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  Importe os grupos de resposta de volta para o pool primário. Na linha de comando, digite:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    Por exemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > Se você recriar um pool durante a recuperação, seja com o mesmo ou um nome de domínio totalmente qualificado (FQDN) diferente, será necessário usar o parâmetro – OverwriteOwner. Como regra geral, você sempre pode usar o parâmetro – OverwriteOwner ao importar grupos de resposta de volta para o pool primário.

    
    </div>
    
    Se você implantou um novo pool (com o mesmo ou um FQDN diferente) para substituir o pool primário e deseja usar as configurações no nível do aplicativo a partir do pool de backup para o novo pool, inclua o parâmetro – ReplaceExistingSettings. Na linha de comando, digite:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    Por exemplo:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > Se você não quiser substituir as configurações no nível do aplicativo e o arquivo de áudio de música em espera padrão para o novo pool com as configurações do pool de backup, o novo pool usará as configurações padrão do aplicativo no nível do aplicativo.

    
    </div>

10. Verifique se a importação de volta para o pool primário foi bem-sucedida exibindo a configuração do grupo de resposta importado. Do the following:
    
      - Exiba todos os fluxos de trabalho no pool primário e verifique se todos os fluxos de trabalho importados estão incluídos. Na linha de comando, digite:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por exemplo:
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - Exiba todas as filas no pool primário e verifique se todas as filas importadas estão incluídas. Na linha de comando, digite:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por exemplo:
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Exiba todos os grupos de agente no pool primário e verifique se todos os grupos de agentes importados estão incluídos. Na linha de comando, digite:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        Por exemplo:
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Exiba todas as horas de negócios no pool principal e verifique se todas as horas de trabalho importadas estão incluídas. Na linha de comando, digite:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por exemplo:
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - Exiba todos os conjuntos de feriados no pool primário e verifique se todos os conjuntos de feriados importados estão incluídos. Na linha de comando, digite:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        Por exemplo:
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. Verifique se a importação foi bem-sucedida fazendo uma chamada para um grupo de resposta importada e verificando se a chamada foi manipulada corretamente.

12. Opcionalmente, remova os grupos de resposta pertencentes ao pool principal do pool de backup. Na linha de comando, digite:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    Por exemplo:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > Esta etapa cria um novo arquivo com a configuração exportada e, em seguida, remove-o do pool de backup.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

