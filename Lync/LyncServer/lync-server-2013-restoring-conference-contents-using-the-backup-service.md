---
title: 'Lync Server 2013: restaurando o conteúdo da conferência usando o serviço de backup'
description: 'Lync Server 2013: restaurando o conteúdo da conferência usando o serviço de backup.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3a0037af711948c008e74c5444373ed995f0e6e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555177"
---
# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="7a9df-103">Restaurando o conteúdo da conferência usando o serviço de backup no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a9df-103">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a9df-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7a9df-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7a9df-p101">Se a informação de conferência armazenada no repositório de arquivo de um pool de Front Ends se tornar indisponível, você deverá restaurar essa informação para que os usuários hospedados no pool recuperem os dados de conferência. Caso o pool de Front End que perdeu os dados de conferência esteja pareado com outro pool de Front End, você pode utilizar o Serviço de Backup para restaurar os dados.</span><span class="sxs-lookup"><span data-stu-id="7a9df-p101">If the conference information stored in the file store of a Front End pool becomes unavailable. you must restore this information so that users homed on the pool retain their conference data. If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="7a9df-p102">Você também deve efetuar tal tarefa caso todo um pool falhe e você tenha que executar failover nos usuários para um pool de backup. Quando esses usuários retornarem para o pool original, você deve utilizar este procedimento para copiar o conteúdo de conferência de volta para o pool original.</span><span class="sxs-lookup"><span data-stu-id="7a9df-p102">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="7a9df-110">Presuma que o Pool1 está pareado com Pool2, e os dados de conferência de Pool1 foram perdidos.</span><span class="sxs-lookup"><span data-stu-id="7a9df-110">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="7a9df-111">Você pode usar o cmdlet a seguir para invocar o serviço de backup para restaurar o conteúdo:</span><span class="sxs-lookup"><span data-stu-id="7a9df-111">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="7a9df-p104">Restaurar o conteúdo pode levar algum tempo, dependendo do tamanho. Você pode utilizar o seguinte cmdlet para verificar o status do processo:</span><span class="sxs-lookup"><span data-stu-id="7a9df-p104">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="7a9df-114">O processo é concluído quando este cmdlet retorna um valor de Estado Estável para o módulo de conferência de dados.</span><span class="sxs-lookup"><span data-stu-id="7a9df-114">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

