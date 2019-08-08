---
title: Limpar manualmente a gravação de detalhes da chamada e os bancos de dados de qualidade da experiência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Resumo: saiba como limpar registros manualmente dos bancos de dados CDR e QoE usados pelo Skype for Business Server.'
ms.openlocfilehash: ba87e05dd72e5da22cfe4e01cd68be1a9fac6242
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239872"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>Limpar manualmente a gravação de detalhes da chamada e os bancos de dados de qualidade da experiência no Skype for Business Server
 
**Resumo:** Saiba como limpar registros manualmente dos bancos de dados CDR e QoE usados pelo Skype for Business Server.
  
Os bancos de dados de CDR e QoE podem ser manual ou automaticamente eliminados dos registros. A limpeza dos registros pode ser importante de forma que os dados não se tornem obsoletos ou quando precisar redefinir os relatórios de uma linha de base inicial.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Limpar os registros manualmente dos bancos de dados de CDR e QoE

Os administradores podem configurar os bancos de dados de CDR (registro de detalhes das chamadas) e/ou QoE (qualidade da experiência) para que limpem automaticamente os registros antigos do banco de dados; isso ocorrerá se a limpeza for habilitada para o banco de dados especificado (CDR ou QoE) e se houver qualquer registro que esteja no banco de dados há mais tempo do que o período especificado. Por exemplo, os administradores podem configurar o sistema para que todos os dias, às 13:00, os registros de QoE com mais de 60 dias sejam excluídos do banco de dados de QoE.
  
Além da eliminação automática, dois cmdlets novos &#x2014; Invoke-CsCdrDatabasePurge e Invoke-CsQoEDatbasePurge &#x2014; foram adicionados ao Skype for Business Server; Esses cmdlets permitem aos administradores limpar manualmente registros dos bancos de dados CDR e QoE a qualquer momento. Por exemplo, para limpar manualmente todos os registros com mais de 10 dias do banco de dados de CDR, é possível usar um comando semelhante a este:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

No comando anterior, os registros de detalhes das chamadas e os registros de dados de diagnósticos com mais de 10 dias eram excluídos do banco de dados de monitoramento em atl-sql-001.litwareinc.com. (Os registros de detalhes das chamadas são relatórios de usuário/sessão. Registros de dados de diagnóstico são logs de diagnóstico carregados por aplicativos cliente, como o Skype for Business Server.)
  
Como mostrado acima, quando o cmdlet Invoke-CsCdrDatabasePurge é executado, os parâmetros PurgeCallDetaiDataOlderThanDays e PurgeDiagnosticDataOlderThanDays devem ser incluídos. No entanto, esses parâmetros não precisam ser definidos com o mesmo valor. Por exemplo, é possível limpar registros de detalhes das chamadas com mais de 10 dias e, ao mesmo, tempo deixar todos os registros de dados de diagnósticos no banco de dados. Para fazer isso, defina PurgeCallDetailDataOlderThanDays para 10 e PurgeDiagnosticDataOlderThanDays como 0. Por exemplo:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

Por padrão, sempre que o Invoke-CsCdrDatabasePurge é executado, um aviso semelhante a esse é exibido para cada tabela de banco de dados que deve ser limpa:
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

É preciso digitar S (Sim) ou T (Sim para Todos) para que a limpeza do banco de dados ocorra de fato. Se você preferir suprimir esse avisos de confirmação, adicione o seguinte parâmetro ao final de sua chamada para Invoke-CsCdrDatabasePurge:
  
```
-Confirm:$False
```

Por exemplo:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

Se fizer isso, os avisos de confirmação não serão exibidos e a limpeza do banco de dados será realizada imediatamente.
  
Para limpar o banco de dados de QoE, use o cmdlet Invoke-CsQoEDatabasePurge e especifique a idade (em dias) dos registros a serem excluídos:
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


