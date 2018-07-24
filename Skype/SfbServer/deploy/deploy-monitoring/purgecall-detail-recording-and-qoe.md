---
title: Limpar manualmente o registro de detalhes da chamada e bancos de dados de qualidade da experiência no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Resumo: Saiba como limpar manualmente registros de bancos de dados QoE usados pelo Skype para Business Server e do CDR.'
ms.openlocfilehash: 14218bbc6af3d05cba3c9886da70ab7155d05159
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006079"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a><span data-ttu-id="1d967-103">Limpar manualmente o registro de detalhes da chamada e bancos de dados de qualidade da experiência no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="1d967-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>
 
<span data-ttu-id="1d967-104">**Resumo:** Saiba como limpar manualmente registros de bancos de dados QoE usados pelo Skype para Business Server e do CDR.</span><span class="sxs-lookup"><span data-stu-id="1d967-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server.</span></span>
  
<span data-ttu-id="1d967-p101">Os bancos de dados de CDR e QoE podem ser manual ou automaticamente eliminados dos registros. A limpeza dos registros pode ser importante de forma que os dados não se tornem obsoletos ou quando precisar redefinir os relatórios de uma linha de base inicial.</span><span class="sxs-lookup"><span data-stu-id="1d967-p101">The CDR and QoE databases can be manually or automatically purged of records. Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="1d967-107">Limpar os registros manualmente dos bancos de dados de CDR e QoE</span><span class="sxs-lookup"><span data-stu-id="1d967-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="1d967-p102">Os administradores podem configurar os bancos de dados de CDR (registro de detalhes das chamadas) e/ou QoE (qualidade da experiência) para que limpem automaticamente os registros antigos do banco de dados; isso ocorrerá se a limpeza for habilitada para o banco de dados especificado (CDR ou QoE) e se houver qualquer registro que esteja no banco de dados há mais tempo do que o período especificado. Por exemplo, os administradores podem configurar o sistema para que todos os dias, às 13:00, os registros de QoE com mais de 60 dias sejam excluídos do banco de dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="1d967-p102">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time. For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="1d967-110">Além das que automatic limpeza, dois novos cmdlets & #x 2014; Invoke-CsCdrDatabasePurge e CsQoEDatbasePurge invocar & #x 2014; foram adicionadas ao Skype para Business Server; Esses cmdlets permitem que administradores eliminação manualmente registros de dados de CDR e os bancos de dados de QoE a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="1d967-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="1d967-111">Por exemplo, para limpar manualmente todos os registros com mais de 10 dias do banco de dados de CDR, é possível usar um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="1d967-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="1d967-112">No comando anterior, os registros de detalhes das chamadas e os registros de dados de diagnósticos com mais de 10 dias eram excluídos do banco de dados de monitoramento em atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="1d967-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="1d967-113">(Os registros de detalhes das chamadas são relatórios de usuário/sessão.</span><span class="sxs-lookup"><span data-stu-id="1d967-113">(Call detail records are user/session reports.</span></span> <span data-ttu-id="1d967-114">Registros de dados de diagnóstico são carregados por aplicativos de cliente, como Skype para Business Server logs de diagnóstico.)</span><span class="sxs-lookup"><span data-stu-id="1d967-114">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server.)</span></span>
  
<span data-ttu-id="1d967-115">Como mostrado acima, quando o cmdlet Invoke-CsCdrDatabasePurge é executado, os parâmetros PurgeCallDetaiDataOlderThanDays e PurgeDiagnosticDataOlderThanDays devem ser incluídos.</span><span class="sxs-lookup"><span data-stu-id="1d967-115">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="1d967-116">No entanto, esses parâmetros não precisam ser definidos com o mesmo valor.</span><span class="sxs-lookup"><span data-stu-id="1d967-116">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="1d967-117">Por exemplo, é possível limpar registros de detalhes das chamadas com mais de 10 dias e, ao mesmo, tempo deixar todos os registros de dados de diagnósticos no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1d967-117">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="1d967-118">Para fazer isso, defina PurgeCallDetailDataOlderThanDays como 10 e PurgeDiagnosticDataOlderThanDays como 0.</span><span class="sxs-lookup"><span data-stu-id="1d967-118">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="1d967-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1d967-119">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="1d967-120">Por padrão, sempre que o Invoke-CsCdrDatabasePurge é executado, um aviso semelhante a esse é exibido para cada tabela de banco de dados que deve ser limpa:</span><span class="sxs-lookup"><span data-stu-id="1d967-120">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

<span data-ttu-id="1d967-p106">É preciso digitar S (Sim) ou T (Sim para Todos) para que a limpeza do banco de dados ocorra de fato. Se você preferir suprimir esse avisos de confirmação, adicione o seguinte parâmetro ao final de sua chamada para Invoke-CsCdrDatabasePurge:</span><span class="sxs-lookup"><span data-stu-id="1d967-p106">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```
-Confirm:$False
```

<span data-ttu-id="1d967-123">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1d967-123">For example:</span></span>
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="1d967-124">Se fizer isso, os avisos de confirmação não serão exibidos e a limpeza do banco de dados será realizada imediatamente.</span><span class="sxs-lookup"><span data-stu-id="1d967-124">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="1d967-125">Para limpar o banco de dados de QoE, use o cmdlet Invoke-CsQoEDatabasePurge e especifique a idade (em dias) dos registros a serem excluídos:</span><span class="sxs-lookup"><span data-stu-id="1d967-125">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


