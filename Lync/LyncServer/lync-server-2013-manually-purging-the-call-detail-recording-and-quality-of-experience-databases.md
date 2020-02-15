---
title: Limpando manualmente os bancos de dados de registro de detalhes das chamadas e qualidade da experiência
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
ms.openlocfilehash: f14485465e44b089e5002a04d3ed5e5a392ad4d8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41991856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a><span data-ttu-id="e790e-102">Limpar manualmente o registro de detalhes das chamadas e os bancos de dados de qualidade da experiência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e790e-102">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e790e-103">_**Última modificação do tópico:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="e790e-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="e790e-104">Os administradores podem configurar o CDR (registro de detalhes das chamadas) e/ou os bancos de dados de QoE (qualidade da experiência) para limpar automaticamente registros antigos do banco de dados; Isso ocorrerá se o descarte tiver sido habilitado para o banco de dados especificado (CDR ou QoE) e se houver algum registro no banco de dados maior do que o intervalo de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="e790e-104">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="e790e-105">Por exemplo, os administradores podem configurar o sistema para que  todos os dias, às 13:00, os registros de QoE com mais de 60 dias sejam excluídos do banco de dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="e790e-105">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>

<span data-ttu-id="e790e-106">Além desse descarte automático, dois novos cmdlets--Invoke-CsCdrDatabasePurge e Invoke-CsQoEDatbasePurge--foram adicionados ao Microsoft Lync Server 2013; Esses cmdlets permitem que os administradores limpem manualmente os registros dos bancos de dados CDR e QoE a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="e790e-106">In addition to that automatic purging, two new cmdlets -- Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge -- have been added to Microsoft Lync Server 2013; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="e790e-107">Por exemplo, para limpar manualmente todos os registros com mais de 10 dias do banco de dados de CDR, é possível usar um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="e790e-107">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

<span data-ttu-id="e790e-108">No comando anterior, os registros de detalhes da chamada e os registros de dados diagnósticos com mais de 10 dias eram excluídos do banco de dados de monitoramento em atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="e790e-108">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="e790e-109">(Os registros de detalhes da chamada são relatórios de usuário/sessão.</span><span class="sxs-lookup"><span data-stu-id="e790e-109">(Call detail records are user/session reports.</span></span> <span data-ttu-id="e790e-110">Os registros de dados de diagnóstico são logs de diagnóstico carregados por aplicativos cliente como o Lync 2013.)</span><span class="sxs-lookup"><span data-stu-id="e790e-110">Diagnostic data records are diagnostic logs uploaded by client applications such as Lync 2013.)</span></span>

<span data-ttu-id="e790e-111">Como mostrado acima, quando o cmdlet Invoke-CsCdrDatabasePurge é executado, os parâmetros PurgeCallDetaiDataOlderThanDays e PurgeDiagnosticDataOlderThanDays devem ser incluídos.</span><span class="sxs-lookup"><span data-stu-id="e790e-111">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="e790e-112">No entanto, esses parâmetros não precisam ser definidos com o mesmo valor.</span><span class="sxs-lookup"><span data-stu-id="e790e-112">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="e790e-113">Por exemplo, é possível limpar registros de detalhes da chamada com mais de 10 dias e ao mesmo tempo deixar todos os registros de dados diagnósticos no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e790e-113">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="e790e-114">Para fazer isso, defina PurgeCallDetailDataOlderThanDays como 10 e PurgeDiagnosticDataOlderThanDays como 0.</span><span class="sxs-lookup"><span data-stu-id="e790e-114">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="e790e-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e790e-115">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

<span data-ttu-id="e790e-116">Por padrão, sempre que o Invoke-CsCdrDatabasePurge é executado, um aviso semelhante a esse é exibido para cada tabela de banco de dados que deve ser limpo:</span><span class="sxs-lookup"><span data-stu-id="e790e-116">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

<span data-ttu-id="e790e-p105">É preciso digitar S (Sim) ou T (Sim para Todos) antes que a limpeza do banco de dados verdadeiramente ocorra. Se você preferir suprimir esse avisos de confirmação, adicione o seguinte parâmetro ao final de sua chamada como Invoke-CsCdrDatabasePurge:</span><span class="sxs-lookup"><span data-stu-id="e790e-p105">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>

    -Confirm:$False

<span data-ttu-id="e790e-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e790e-119">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

<span data-ttu-id="e790e-120">Se fizer isso, os avisos de confirmação não serão exibidos e a limpeza do banco de dados será realizada imediatamente.</span><span class="sxs-lookup"><span data-stu-id="e790e-120">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>

<span data-ttu-id="e790e-121">Para limpar o banco de dados de QoE, use o cmdlet Invoke-CsQoEDatabasePurge e especifique a idade (em dias) dos registros a serem excluídos:</span><span class="sxs-lookup"><span data-stu-id="e790e-121">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

