---
title: Limpar manualmente o registro de detalhes das chamadas e os bancos de dados de Qualidade da Experiência no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Resumo: Saiba como limpar manualmente registros do CDR e os bancos de dados do QoE usados pelo Skype para Business Server 2015.'
ms.openlocfilehash: 805bf72b3d4846bb00d3c3772b033242976cd7c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server-2015"></a>Limpar manualmente o registro de detalhes das chamadas e os bancos de dados de Qualidade da Experiência no Skype for Business Server 2015
 
**Resumo:** Saiba como limpar manualmente registros do CDR e os bancos de dados do QoE usados pelo Skype para Business Server 2015.
  
Os bancos de dados de CDR e QoE podem ser manual ou automaticamente eliminados dos registros. A limpeza dos registros pode ser importante de forma que os dados não se tornem obsoletos ou quando precisar redefinir os relatórios de uma linha de base inicial.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Limpar os registros manualmente dos bancos de dados de CDR e QoE

Os administradores podem configurar os bancos de dados de CDR (registro de detalhes das chamadas) e/ou QoE (qualidade da experiência) para que limpem automaticamente os registros antigos do banco de dados; isso ocorrerá se a limpeza for habilitada para o banco de dados especificado (CDR ou QoE) e se houver qualquer registro que esteja no banco de dados há mais tempo do que o período especificado. Por exemplo, os administradores podem configurar o sistema para que todos os dias, às 13:00, os registros de QoE com mais de 60 dias sejam excluídos do banco de dados de QoE.
  
Além das que automatic limpeza, dois novos cmdlets & #x 2014; Invoke-CsCdrDatabasePurge e CsQoEDatbasePurge invocar & #x 2014; foram adicionadas ao Skype para negócios 2015 do servidor; Esses cmdlets permitem que administradores eliminação manualmente registros de dados de CDR e os bancos de dados de QoE a qualquer momento. Por exemplo, para limpar manualmente todos os registros com mais de 10 dias do banco de dados de CDR, é possível usar um comando semelhante a este:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

No comando anterior ambos chamam de registros de detalhe e registros de dados de diagnóstico mais antigos do que 10 dias são excluídos do banco de dados de monitoramento no atl-sql-001. litwareinc.com. (Registros de detalhe de chamada são relatórios de sessão do usuário. Registros de dados de diagnóstico são carregados por aplicativos de cliente, como Skype para Business Server 2015 logs de diagnóstico.)
  
Como mostrado acima, quando o cmdlet Invoke-CsCdrDatabasePurge é executado, os parâmetros PurgeCallDetaiDataOlderThanDays e PurgeDiagnosticDataOlderThanDays devem ser incluídos. No entanto, esses parâmetros não precisam ser definidos com o mesmo valor. Por exemplo, é possível limpar registros de detalhes das chamadas com mais de 10 dias e, ao mesmo, tempo deixar todos os registros de dados de diagnósticos no banco de dados. Para fazer isso, defina PurgeCallDetailDataOlderThanDays como 10 e PurgeDiagnosticDataOlderThanDays como 0. Por exemplo:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

Por padrão, sempre que o Invoke-CsCdrDatabasePurge é executado, um aviso semelhante a esse é exibido para cada tabela de banco de dados que deve ser limpa:
  
```
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
```

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


