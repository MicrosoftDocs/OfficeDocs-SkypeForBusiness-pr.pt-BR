---
title: Limpando manualmente os bancos de dados de registro de detalhes das chamadas e qualidade da experiência
description: Limpar manualmente o registro de detalhes das chamadas e os bancos de dados de qualidade da experiência.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manually purging the call detail recording and Quality of Experience databases
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48183859
ms.date: 07/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c7903431d28bf1a829991ce35c2ee7351168b4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556557"
---
# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a>Limpar manualmente o registro de detalhes das chamadas e os bancos de dados de qualidade da experiência no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-07-07_

Os administradores podem configurar o CDR (registro de detalhes das chamadas) e/ou os bancos de dados de QoE (qualidade da experiência) para limpar automaticamente registros antigos do banco de dados; Isso ocorrerá se o descarte tiver sido habilitado para o banco de dados especificado (CDR ou QoE) e se houver algum registro no banco de dados maior do que o intervalo de tempo especificado. Por exemplo, os administradores podem configurar o sistema para que  todos os dias, às 13:00, os registros de QoE com mais de 60 dias sejam excluídos do banco de dados de QoE.

Além desse descarte automático, dois novos cmdlets--Invoke-CsCdrDatabasePurge e Invoke-CsQoEDatbasePurge--foram adicionados ao Microsoft Lync Server 2013; Esses cmdlets permitem que os administradores limpem manualmente os registros dos bancos de dados CDR e QoE a qualquer momento. Por exemplo, para limpar manualmente todos os registros com mais de 10 dias do banco de dados de CDR, é possível usar um comando semelhante a este:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

No comando anterior, os registros de detalhes da chamada e os registros de dados diagnósticos com mais de 10 dias eram excluídos do banco de dados de monitoramento em atl-sql-001.litwareinc.com. (Os registros de detalhes da chamada são relatórios de usuário/sessão. Os registros de dados de diagnóstico são logs de diagnóstico carregados por aplicativos cliente como o Lync 2013.)

Como mostrado acima, quando o cmdlet Invoke-CsCdrDatabasePurge é executado, os parâmetros PurgeCallDetaiDataOlderThanDays e PurgeDiagnosticDataOlderThanDays devem ser incluídos. No entanto, esses parâmetros não precisam ser definidos com o mesmo valor. Por exemplo, é possível limpar registros de detalhes da chamada com mais de 10 dias e ao mesmo tempo deixar todos os registros de dados diagnósticos no banco de dados. Para fazer isso, defina PurgeCallDetailDataOlderThanDays como 10 e PurgeDiagnosticDataOlderThanDays como 0. Por exemplo:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

Por padrão, sempre que o Invoke-CsCdrDatabasePurge é executado, um aviso semelhante a esse é exibido para cada tabela de banco de dados que deve ser limpo:

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

É preciso digitar S (Sim) ou T (Sim para Todos) antes que a limpeza do banco de dados verdadeiramente ocorra. Se você preferir suprimir esse avisos de confirmação, adicione o seguinte parâmetro ao final de sua chamada como Invoke-CsCdrDatabasePurge:

    -Confirm:$False

Por exemplo:

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

Se fizer isso, os avisos de confirmação não serão exibidos e a limpeza do banco de dados será realizada imediatamente.

Para limpar o banco de dados de QoE, use o cmdlet Invoke-CsQoEDatabasePurge e especifique a idade (em dias) dos registros a serem excluídos:

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

