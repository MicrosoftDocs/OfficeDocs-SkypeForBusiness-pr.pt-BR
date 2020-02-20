---
title: 'Lync Server 2013: Configurando intervalos de portas para seus clientes Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f16fa3b16a992ce15f16e7413a59525e55ddba75
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a><span data-ttu-id="9e847-102">Configurando intervalos de portas para seus clientes Microsoft Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e847-102">Configuring port ranges for your Microsoft Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e847-103">_**Última modificação do tópico:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="9e847-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="9e847-104">Por padrão, os aplicativos cliente do Lync podem usar qualquer porta entre as portas 1024 e 65535 quando envolvido em uma sessão de comunicação; Isso ocorre porque intervalos de portas específicos não são automaticamente habilitados para clientes.</span><span class="sxs-lookup"><span data-stu-id="9e847-104">By default, Lync client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="9e847-105">Para poder usar a Qualidade do Serviço, no entanto, você precisará reatribuir os vários tipos de tráfego (áudio, vídeo, mídia, compartilhamento de aplicativos e transferência de arquivos) para uma série de intervalos de porta únicos.</span><span class="sxs-lookup"><span data-stu-id="9e847-105">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="9e847-106">Isto pode ser realizado usando o cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9e847-106">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e847-107">Os usuários finais não podem fazer essas alterações por conta própria.</span><span class="sxs-lookup"><span data-stu-id="9e847-107">End users cannot make these changes themselves.</span></span> <span data-ttu-id="9e847-108">As alterações de porta só podem ser feitas por administradores usando o cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9e847-108">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>



</div>

<span data-ttu-id="9e847-109">Você pode determinar quais intervalos de portas são usados atualmente para sessões de comunicação executando o seguinte comando no Shell de gerenciamento do Microsoft Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="9e847-109">You can determine which port ranges are currently used for communication sessions by running the following command from within the Microsoft Lync Server 2013 Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="9e847-110">Supondo que você não tenha feito nenhuma alteração nas configurações de conferência desde que você instalou o Lync Server 2013, você deve obter as informações que incluem estes valores de propriedade:</span><span class="sxs-lookup"><span data-stu-id="9e847-110">Assuming that you have not made any changes to your conferencing settings since you installed Lync Server 2013, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="9e847-111">Se você verificar o resultado anterior, você verá duas coisas de importância.</span><span class="sxs-lookup"><span data-stu-id="9e847-111">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="9e847-112">Primeiro, a propriedade ClientMediaPortRangeEnabled é definida para False:</span><span class="sxs-lookup"><span data-stu-id="9e847-112">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="9e847-113">Isso é importante porque, quando essa propriedade é definida como false, os clientes do Lync usarão qualquer porta disponível entre as portas 1024 e 65535 quando envolvidas em uma sessão de comunicação; Isso é verdadeiro independentemente de qualquer outra configuração de porta (por exemplo, ClientMediaPort ou ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="9e847-113">That's important because, when this property is set to False, Lync clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="9e847-114">Se você deseja restringir o uso para um conjunto de portas especificado (e isto é algo que você deseja fazer se planeja implementar a Qualidade do Serviço), você deve primeiro habilitar os intervalos de porta de mídia do cliente.</span><span class="sxs-lookup"><span data-stu-id="9e847-114">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service) then you must first enable client media port ranges.</span></span> <span data-ttu-id="9e847-115">Isso pode ser feito usando o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9e847-115">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="9e847-p105">O comando anterior habilita os intervalos de porta de mídia do cliente para o conjunto global de definições de configuração de conferência; no entanto, estas configurações também podem ser aplicadas para o escopo local e/ou de serviço (apenas para o serviço do Servidor de Conferência). Para habilitar os intervalos de porta de mídia do cliente para um site ou servidor específico, defina a Identidade deste site ou servidor ao chamar Set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="9e847-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="9e847-118">Em alternativa, é possível usar este comando para habilitar simultaneamente intervalos de portas para todas as suas definições de configuração de conferência:</span><span class="sxs-lookup"><span data-stu-id="9e847-118">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="9e847-119">A segunda coisa importante que você observará é o resultado de amostra mostrando que, por padrão, o conjunto de intervalos da porta de mídia para cada tipo de tráfego de rede são idênticos:</span><span class="sxs-lookup"><span data-stu-id="9e847-119">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="9e847-p106">Para poder implementar o QoS, cada um destes intervalos de porta precisarão ser exclusivos. Por exemplo, você pode configurar os intervalos de porta desta forma:</span><span class="sxs-lookup"><span data-stu-id="9e847-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e847-122">Tipo de Tráfego do Cliente</span><span class="sxs-lookup"><span data-stu-id="9e847-122">Client Traffic Type</span></span></th>
<th><span data-ttu-id="9e847-123">Início da Porta</span><span class="sxs-lookup"><span data-stu-id="9e847-123">Port Start</span></span></th>
<th><span data-ttu-id="9e847-124">Intervalo da Porta</span><span class="sxs-lookup"><span data-stu-id="9e847-124">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e847-125">Áudio</span><span class="sxs-lookup"><span data-stu-id="9e847-125">Audio</span></span></p></td>
<td><p><span data-ttu-id="9e847-126">50020</span><span class="sxs-lookup"><span data-stu-id="9e847-126">50020</span></span></p></td>
<td><p><span data-ttu-id="9e847-127">508</span><span class="sxs-lookup"><span data-stu-id="9e847-127">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e847-128">Vídeo</span><span class="sxs-lookup"><span data-stu-id="9e847-128">Video</span></span></p></td>
<td><p><span data-ttu-id="9e847-129">58000</span><span class="sxs-lookup"><span data-stu-id="9e847-129">58000</span></span></p></td>
<td><p><span data-ttu-id="9e847-130">508</span><span class="sxs-lookup"><span data-stu-id="9e847-130">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e847-131">Compartilhamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="9e847-131">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="9e847-132">42000</span><span class="sxs-lookup"><span data-stu-id="9e847-132">42000</span></span></p></td>
<td><p><span data-ttu-id="9e847-133">508</span><span class="sxs-lookup"><span data-stu-id="9e847-133">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e847-134">Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="9e847-134">File transfer</span></span></p></td>
<td><p><span data-ttu-id="9e847-135">42020</span><span class="sxs-lookup"><span data-stu-id="9e847-135">42020</span></span></p></td>
<td><p><span data-ttu-id="9e847-136">508</span><span class="sxs-lookup"><span data-stu-id="9e847-136">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9e847-p107">Na tabela anterior, os intervalos da porta do cliente representam um subconjunto dos intervalos de porta configurados para seus servidores. Por exemplo, nos servidores, o compartilhamento de aplicativos foi configurado para usar as portas 40803 a 49151; nos computadores clientes, o compartilhamento de aplicativos é configurado para usar as portas 42000 a 42019. Isto também é realizado principalmente para tornar a administração do QoS mais fácil: as portas do cliente não precisam representar um conjunto de portas usadas no servidor. (Por exemplo, em computadores clientes que você pode configurar o compartilhamento de aplicativos a usar, digamos, as portas 10000 a 10019.) No entanto, é recomendado que você torne seus intervalos da porta do cliente um subconjunto dos seus intervalos de porta do servidor.</span><span class="sxs-lookup"><span data-stu-id="9e847-p107">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers. For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019. This, too is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server. (For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="9e847-p108">Além disso, você pode observar que 8348 portas foram definidas para compartilhamento de aplicativos nos servidores, mas apenas 20 portas foram separadas para compartilhamento de aplicativos nos clientes. Isto também é recomendado, mas não é uma regra rígida. Em geral, você pode considerar cada porta disponível para representar uma única sessão de comunicação: se você possui 100 portas disponíveis em um intervalo de porta, significa que o computador em questão pode participar, no máximo, de 100 sessões de comunicação em um determinado momento. Como os servidores provavelmente terão parte em muito mais conversas do que os clientes, faz sentido abrir mais portas em servidores do que em clientes.Configurar outras 20 portas para compartilhamento de aplicativo em um cliente significa que um usuário pode participar de 20 sessões de compartilhamento de aplicativos no dispositivo especificado e tudo ao mesmo tempo. Isso deve ser suficiente para a grande maioria dos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="9e847-p108">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients. This, too is recommended, but is not a hard-and-fast rule. In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range that means that the computer in question could participate in, at most, 100 communication sessions at any given time. Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients. Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time. That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="9e847-147">Para atribuir os intervalos de portas precedentes à sua coleção global de definições de configuração de conferência, você pode usar o seguinte comando do Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="9e847-147">To assign the preceding port ranges to your global collection of conferencing configuration settings you can use the following Lync Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="9e847-148">Em alternativa, use este comando para atribuir estes mesmos intervalos de porta para todas suas definições de configuração de conferência:</span><span class="sxs-lookup"><span data-stu-id="9e847-148">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="9e847-149">Os usuários individuais devem fazer logoff do Lync e, em seguida, fazer logon novamente para que essas alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="9e847-149">Individual users must log off from Lync and then log back on before these changes will actually take effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e847-150">Também é possível habilitar intervalos de porta da mídia do cliente e atribuir estes intervalos de porta usando um único comando.</span><span class="sxs-lookup"><span data-stu-id="9e847-150">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="9e847-151">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9e847-151">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

