---
title: Mover os diretórios de conferência do Lync Server 2010 para o Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6712e22ffcdc2eaea9ae39be961bb50316beed5b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="e2302-102">Mover de diretórios de conferência</span><span class="sxs-lookup"><span data-stu-id="e2302-102">Move Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2302-103">_**Última modificação do tópico:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="e2302-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="e2302-104">Antes de encerrar um pool, você deve executar o procedimento a seguir para cada diretório de conferência no seu pool do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e2302-104">Before decommissioning a pool you must perform the following procedure for each conference directory in your Lync Server 2010 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="e2302-105">Para mover um diretório de conferência para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2302-105">To Move a Conference Directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="e2302-106">Abra o Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e2302-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="e2302-107">Para obter a identidade dos diretórios de conferência em sua organização, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e2302-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="e2302-108">O comando anterior retorna todos os diretórios de conferência em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e2302-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="e2302-109">Por isso, talvez você queira limitar os resultados ao pool que está sendo descomissionado.</span><span class="sxs-lookup"><span data-stu-id="e2302-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="e2302-110">Por exemplo, se você estiver encerrando o pool com o nome de domínio totalmente qualificado (FQDN) pool01.contoso.net, use este comando para limitar os dados retornados aos diretórios de conferência desse pool:</span><span class="sxs-lookup"><span data-stu-id="e2302-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="e2302-111">Esse comando retorna apenas os diretórios de conferência onde a propriedade ServiceId contém o FQDN pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="e2302-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="e2302-112">Para mover os diretórios de conferência, execute o seguinte comando para cada diretório de conferência no pool:</span><span class="sxs-lookup"><span data-stu-id="e2302-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="e2302-113">Por exemplo, para mover o diretório de conferências 3, use este comando, especificando um pool do Lync Server 2013 como o TargetPool:</span><span class="sxs-lookup"><span data-stu-id="e2302-113">For example, to move conference directory 3 use this command, specifying a Lync Server 2013 pool as the TargetPool:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    <span data-ttu-id="e2302-114">Se você deseja mover todos os diretórios de conferência em um pool, use um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="e2302-114">If you want to move all the conference directories on a pool then use a command similar to the following:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

<span data-ttu-id="e2302-115">Confira o documento "Desinstalando o Microsoft Lync Server 2010 e removendo funções de servidor" (que pode [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)ser baixado de) para obter instruções abrangentes e passo a passo sobre o encerramento de pools do Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="e2302-115">Please see the document "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (which can be downloaded from [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) for comprehensive, step-by-step instructions on decommissioning Lync 2010 pools.</span></span>

<span data-ttu-id="e2302-116">Ao mover os diretórios de conferência, você pode encontrar o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="e2302-116">When moving conference directories you might encounter the following error:</span></span>

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

<span data-ttu-id="e2302-117">Esse erro normalmente ocorre quando o Shell de gerenciamento do Lync Server requer um conjunto atualizado de permissões do Active Directory para concluir uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="e2302-117">This error typically occurs when the Lync Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="e2302-118">Para resolver o problema, feche a instância atual do Shell de gerenciamento, abra uma nova instância do Shell e execute novamente o comando para mover o diretório de conferência.</span><span class="sxs-lookup"><span data-stu-id="e2302-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command in order to move the conference directory.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

