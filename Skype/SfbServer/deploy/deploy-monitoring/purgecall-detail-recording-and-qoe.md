---
title: Limpar manualmente o registro de detalhes de chamada e os bancos de dados de Qualidade da Experiência no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Resumo: saiba como limpar manualmente os registros da CDR e dos bancos de dados QoE usados por Skype for Business Server.'
ms.openlocfilehash: edaeb5d34fefe1ea8f50da4d7bb4bb31c94c62b5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851595"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>Limpar manualmente o registro de detalhes de chamada e os bancos de dados de Qualidade da Experiência no Skype for Business Server
 
**Resumo:** Saiba como limpar manualmente os registros da CDR e dos bancos de dados QoE usados por Skype for Business Server.
  
Os bancos de dados CDR e QoE podem ser limpos manualmente ou automaticamente dos registros. A repuração de registros pode ser importante para que os dados não se tornem antigos ou quando for necessário redefinir relatórios de uma linha de base inicial.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Limpar manualmente registros de bancos de dados CDR e QoE

Os administradores podem configurar o CDR (Registro de Detalhes de Chamada) e/ou os bancos de dados de Qualidade da Experiência (QoE) para limpar automaticamente registros antigos do banco de dados; isso ocorrerá se a purgação tiver sido habilitada para o banco de dados especificado (CDR ou QoE) e se houver quaisquer registros que tenham estado no banco de dados por mais tempo do que o tempo especificado. Por exemplo, os administradores podem configurar o sistema para que  todos os dias, às 13:00, os registros de QoE com mais de 60 dias sejam excluídos do banco de dados de QoE.
  
Além dessa purga automática, dois novos cmdlets &#x2014; Invoke-CsCdrDatabasePurge e Invoke-CsQoEDatbasePurge &#x2014; foram adicionados ao Skype for Business Server; esses cmdlets permitem que os administradores limpem manualmente registros da CDR e dos bancos de dados QoE a qualquer momento. Por exemplo, para limpar manualmente todos os registros com mais de 10 dias do banco de dados de CDR, é possível usar um comando semelhante a este:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

No comando anterior, os registros de detalhes da chamada e os registros de dados diagnósticos com mais de 10 dias eram excluídos do banco de dados de monitoramento em atl-sql-001.litwareinc.com. (Os registros de detalhes da chamada são relatórios de usuário/sessão. Os registros de dados de diagnóstico são logs de diagnóstico carregados por aplicativos cliente, como Skype for Business Server.)
  
Como mostrado acima, quando o cmdlet Invoke-CsCdrDatabasePurge é executado, os parâmetros PurgeCallDetaiDataOlderThanDays e PurgeDiagnosticDataOlderThanDays devem ser incluídos. No entanto, esses parâmetros não precisam ser definidos com o mesmo valor. Por exemplo, é possível limpar registros de detalhes da chamada com mais de 10 dias e ao mesmo tempo deixar todos os registros de dados diagnósticos no banco de dados. Para fazer isso, desmarque PurgeCallDetailDataOlderThanDays como 10 e PurgeDiagnosticDataOlderThanDays como 0. Por exemplo:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

Por padrão, sempre que o Invoke-CsCdrDatabasePurge é executado, um aviso semelhante a esse é exibido para cada tabela de banco de dados que deve ser limpo:
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

É preciso digitar S (Sim) ou T (Sim para Todos) antes que a limpeza do banco de dados verdadeiramente ocorra. Se você preferir suprimir esse avisos de confirmação, adicione o seguinte parâmetro ao final de sua chamada como Invoke-CsCdrDatabasePurge:
  
```powershell
-Confirm:$False
```

Por exemplo:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

Se fizer isso, os avisos de confirmação não serão exibidos e a limpeza do banco de dados será realizada imediatamente.
  
Para limpar o banco de dados de QoE, use o cmdlet Invoke-CsQoEDatabasePurge e especifique a idade (em dias) dos registros a serem excluídos:
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


