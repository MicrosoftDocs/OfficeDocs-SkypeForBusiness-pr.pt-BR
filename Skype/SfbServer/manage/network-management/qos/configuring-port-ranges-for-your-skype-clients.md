---
title: Configurando intervalos de porta e uma política de qualidade de serviço para seus clientes
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Este artigo descreve como configurar intervalos de porta para seus clientes e configurar políticas de qualidade de serviço no Skype for Business Server para clientes em execução no Windows 10.
ms.openlocfilehash: 9a82a254ab5a01982e9f1d4bd3a994fd67c03615
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817420"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="9b687-103">Configurando intervalos de porta e uma política de qualidade de serviço para seus clientes no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9b687-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="9b687-104">Este artigo descreve como configurar intervalos de porta para seus clientes e configurar políticas de qualidade de serviço no Skype for Business Server para clientes em execução no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="9b687-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="9b687-105">Configurar intervalos de porta</span><span class="sxs-lookup"><span data-stu-id="9b687-105">Configure port ranges</span></span>

<span data-ttu-id="9b687-106">Por padrão, os aplicativos cliente do Skype for Business podem usar qualquer porta entre as portas 1024 e 65535 quando envolvidos em uma sessão de comunicação; Isso ocorre porque intervalos de porta específicos não são habilitados automaticamente para clientes.</span><span class="sxs-lookup"><span data-stu-id="9b687-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="9b687-107">No entanto, para usar a qualidade do serviço, você precisará reatribuir os vários tipos de tráfego (áudio, vídeo, mídia, compartilhamento de aplicativos e transferência de arquivos) a uma série de intervalos de porta exclusivos.</span><span class="sxs-lookup"><span data-stu-id="9b687-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="9b687-108">Isso pode ser feito usando o cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9b687-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="9b687-109">Os usuários finais não podem fazer essas alterações.</span><span class="sxs-lookup"><span data-stu-id="9b687-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="9b687-110">As alterações de porta só podem ser feitas por administradores usando o cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9b687-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="9b687-111">Você pode determinar quais intervalos de porta atualmente são usados para sessões de comunicação executando o seguinte comando no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="9b687-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="9b687-112">Pressupondo que você não fez nenhuma alteração nas configurações de conferência desde que instalou o Skype for Business Server, você deve obter informações que incluam estes valores de propriedade:</span><span class="sxs-lookup"><span data-stu-id="9b687-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="9b687-113">Se você olhar atentamente a saída anterior, verá duas coisas de importância.</span><span class="sxs-lookup"><span data-stu-id="9b687-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="9b687-114">Primeiro, a propriedade ClientMediaPortRangeEnabled é definida como false:</span><span class="sxs-lookup"><span data-stu-id="9b687-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="9b687-115">Isso é importante porque, quando essa propriedade é definida como falsa, os clientes do Skype for Business usarão qualquer porta disponível entre as portas 1024 e 65535 quando estiverem envolvidos em uma sessão de comunicação; Isso é verdadeiro independentemente de qualquer outra configuração de porta (por exemplo, ClientMediaPort ou ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="9b687-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="9b687-116">Se você quiser restringir o uso para um conjunto de portas especificado (e isso é algo que você deseja fazer se planeja implementar a qualidade de serviço), primeiro você deve habilitar os intervalos de porta de mídia do cliente.</span><span class="sxs-lookup"><span data-stu-id="9b687-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="9b687-117">Isso pode ser feito usando o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9b687-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="9b687-118">O comando anterior habilita os intervalos de porta de mídia do cliente para o conjunto global de definições de configuração de conferência; no entanto, essas configurações também podem ser aplicadas ao escopo do site e/ou ao escopo do serviço (somente para o serviço de servidor de conferência).</span><span class="sxs-lookup"><span data-stu-id="9b687-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="9b687-119">Para habilitar os intervalos de porta de mídia do cliente para um site ou servidor específico, especifique a identidade desse site ou servidor ao chamar Set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="9b687-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="9b687-120">Ou, se preferir, você pode usar esse comando para habilitar simultaneamente intervalos de porta para todas as suas definições de configuração de conferência:</span><span class="sxs-lookup"><span data-stu-id="9b687-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="9b687-121">O segundo motivo da importância que você observará é que a saída do exemplo mostra que, por padrão, os intervalos de porta de mídia definidos para cada tipo de tráfego de rede são idênticos:</span><span class="sxs-lookup"><span data-stu-id="9b687-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="9b687-122">Para implementar a QoS, cada um desses intervalos de portas precisará ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="9b687-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="9b687-123">Por exemplo, você pode configurar os intervalos de porta como este:</span><span class="sxs-lookup"><span data-stu-id="9b687-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b687-124">Tipo de tráfego do cliente</span><span class="sxs-lookup"><span data-stu-id="9b687-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="9b687-125">Início da porta</span><span class="sxs-lookup"><span data-stu-id="9b687-125">Port Start</span></span></th>
<th><span data-ttu-id="9b687-126">Intervalo de porta</span><span class="sxs-lookup"><span data-stu-id="9b687-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b687-127">Áudio</span><span class="sxs-lookup"><span data-stu-id="9b687-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="9b687-128">50020</span><span class="sxs-lookup"><span data-stu-id="9b687-128">50020</span></span></p></td>
<td><p><span data-ttu-id="9b687-129">cedido</span><span class="sxs-lookup"><span data-stu-id="9b687-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b687-130">Vídeo</span><span class="sxs-lookup"><span data-stu-id="9b687-130">Video</span></span></p></td>
<td><p><span data-ttu-id="9b687-131">58000</span><span class="sxs-lookup"><span data-stu-id="9b687-131">58000</span></span></p></td>
<td><p><span data-ttu-id="9b687-132">cedido</span><span class="sxs-lookup"><span data-stu-id="9b687-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b687-133">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="9b687-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="9b687-134">42000</span><span class="sxs-lookup"><span data-stu-id="9b687-134">42000</span></span></p></td>
<td><p><span data-ttu-id="9b687-135">cedido</span><span class="sxs-lookup"><span data-stu-id="9b687-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b687-136">Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="9b687-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="9b687-137">42020</span><span class="sxs-lookup"><span data-stu-id="9b687-137">42020</span></span></p></td>
<td><p><span data-ttu-id="9b687-138">cedido</span><span class="sxs-lookup"><span data-stu-id="9b687-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9b687-139">Na tabela anterior, intervalos de porta do cliente representam um subconjunto de intervalos de porta configurados para seus servidores.</span><span class="sxs-lookup"><span data-stu-id="9b687-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="9b687-140">Por exemplo, nos servidores, o compartilhamento de aplicativos foi configurado para usar as portas 40803 a 49151; nos computadores cliente, o compartilhamento de aplicativos é configurado para usar as portas 42000 a 42019.</span><span class="sxs-lookup"><span data-stu-id="9b687-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="9b687-141">Isso, também, é feito principalmente para facilitar a administração da QoS: as portas do cliente não precisam representar um subconjunto de portas usadas no servidor.</span><span class="sxs-lookup"><span data-stu-id="9b687-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="9b687-142">(Por exemplo, nos computadores cliente, você pode configurar o compartilhamento de aplicativos para usar, digamos, portas 10000 a 10019.) No entanto, é recomendável que os intervalos de porta do cliente sejam um subconjunto de intervalos de porta do servidor.</span><span class="sxs-lookup"><span data-stu-id="9b687-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="9b687-143">Além disso, você pode ter notado que 8348 portas foram reservadas para o compartilhamento de aplicativos nos servidores, mas apenas 20 portas foram reservadas para o compartilhamento de aplicativos nos clientes.</span><span class="sxs-lookup"><span data-stu-id="9b687-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="9b687-144">Isso também é recomendado, mas não é uma regra difícil e rápida.</span><span class="sxs-lookup"><span data-stu-id="9b687-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="9b687-145">Em geral, você pode considerar cada porta disponível para representar uma única sessão de comunicação: se você tiver portas 100 disponíveis em um intervalo de portabilidade, isso significa que o computador em questão pode participar, no máximo, 100 sessões de comunicação a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="9b687-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="9b687-146">Como os servidores provavelmente participarão de muitas mais conversas do que clientes, faz sentido abrir muito mais portas em servidores do que em clientes.</span><span class="sxs-lookup"><span data-stu-id="9b687-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="9b687-147">A configuração de mais de 20 portas para compartilhamento de aplicativos em um cliente significa que um usuário pode participar de 20 sessões de compartilhamento de aplicativos no dispositivo especificado e todos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="9b687-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="9b687-148">Isso deve provar suficiente para a grande maioria dos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="9b687-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="9b687-149">Para atribuir os intervalos de porta precedentes à sua coleção global de definições de configuração de conferência, você pode usar o seguinte comando do Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="9b687-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="9b687-150">Ou use este comando para atribuir esses mesmos intervalos de portas para todas as suas configurações de conferência:</span><span class="sxs-lookup"><span data-stu-id="9b687-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="9b687-151">Usuários individuais devem fazer logoff do Skype for Business e, em seguida, fazer logon novamente para que as alterações realmente entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="9b687-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="9b687-152">Você também pode habilitar os intervalos de porta de mídia do cliente e, em seguida, atribuir esses intervalos de porta usando um único comando.</span><span class="sxs-lookup"><span data-stu-id="9b687-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="9b687-153">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9b687-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="9b687-154">Configurar políticas de qualidade de serviço para clientes em execução no Windows 10</span><span class="sxs-lookup"><span data-stu-id="9b687-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="9b687-155">Além de especificar intervalos de porta para uso pelos clientes do Skype for Business, você também deve criar políticas de qualidade de serviço separadas que serão aplicadas aos computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="9b687-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="9b687-156">(As políticas de qualidade de serviço criadas para servidores de conferência, aplicativos e remediação não devem ser aplicadas a computadores cliente.) Essas informações se aplicam apenas a computadores que executam o cliente Skype for Business e o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="9b687-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="9b687-157">O exemplo a seguir usa esse conjunto de intervalos de porta para criar uma política de áudio e uma política de vídeo:</span><span class="sxs-lookup"><span data-stu-id="9b687-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b687-158">Tipo de tráfego do cliente</span><span class="sxs-lookup"><span data-stu-id="9b687-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="9b687-159">Início da porta</span><span class="sxs-lookup"><span data-stu-id="9b687-159">Port Start</span></span></th>
<th><span data-ttu-id="9b687-160">Intervalo de porta</span><span class="sxs-lookup"><span data-stu-id="9b687-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b687-161">Áudio</span><span class="sxs-lookup"><span data-stu-id="9b687-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="9b687-162">50020</span><span class="sxs-lookup"><span data-stu-id="9b687-162">50020</span></span></p></td>
<td><p><span data-ttu-id="9b687-163">cedido</span><span class="sxs-lookup"><span data-stu-id="9b687-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b687-164">Vídeo</span><span class="sxs-lookup"><span data-stu-id="9b687-164">Video</span></span></p></td>
<td><p><span data-ttu-id="9b687-165">58000</span><span class="sxs-lookup"><span data-stu-id="9b687-165">58000</span></span></p></td>
<td><p><span data-ttu-id="9b687-166">cedido</span><span class="sxs-lookup"><span data-stu-id="9b687-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b687-167">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="9b687-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="9b687-168">42000</span><span class="sxs-lookup"><span data-stu-id="9b687-168">42000</span></span></p></td>
<td><p><span data-ttu-id="9b687-169">cedido</span><span class="sxs-lookup"><span data-stu-id="9b687-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b687-170">Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="9b687-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="9b687-171">42020</span><span class="sxs-lookup"><span data-stu-id="9b687-171">42020</span></span></p></td>
<td><p><span data-ttu-id="9b687-172">cedido</span><span class="sxs-lookup"><span data-stu-id="9b687-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="9b687-173">Para criar uma política de qualidade de áudio de serviço para computadores com o Windows 10, primeiro faça logon em um computador onde o gerenciamento de política de grupo foi instalado.</span><span class="sxs-lookup"><span data-stu-id="9b687-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="9b687-174">Abra gerenciamento de política de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de política de grupo**) e, em seguida, conclua o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="9b687-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="9b687-175">No gerenciamento de política de grupo, localize o contêiner em que a nova política deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="9b687-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="9b687-176">Por exemplo, se todos os seus computadores cliente estiverem localizados em uma UO chamada clientes, a nova política deve ser criada na UO do cliente.</span><span class="sxs-lookup"><span data-stu-id="9b687-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="9b687-177">Clique com o botão direito do mouse no contêiner apropriado e, em seguida, clique em **criar um GPO neste domínio e vincule-o aqui**.</span><span class="sxs-lookup"><span data-stu-id="9b687-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="9b687-178">Na caixa de diálogo **novo GPO** , digite um nome para o novo objeto de política de grupo na caixa **nome** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b687-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="9b687-179">Clique com o botão direito do mouse na política recém-criada e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9b687-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="9b687-180">No editor de gerenciamento de política de grupo, expanda **configuração do computador**, expanda **configurações do Windows**, clique com o botão direito do mouse em **QoS baseado em política**e clique em **criar nova política**.</span><span class="sxs-lookup"><span data-stu-id="9b687-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="9b687-181">Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política na caixa **nome** .</span><span class="sxs-lookup"><span data-stu-id="9b687-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="9b687-182">Selecione **especificar valor DSCP** e defina o valor como **46**.</span><span class="sxs-lookup"><span data-stu-id="9b687-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="9b687-183">Deixe **especificar a taxa de aceleração de saída** desmarcada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9b687-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="9b687-184">Na próxima página, selecione **apenas aplicativos com esse nome executável**, digite **Lync. exe** como o nome e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9b687-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="9b687-185">Essa configuração instrui a política a priorizar somente o tráfego coincidente do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9b687-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="9b687-186">Na terceira página, verifique se **qualquer endereço IP de origem** e **qualquer endereço IP de destino** estão selecionados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9b687-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="9b687-187">Essas duas configurações garantem que os pacotes serão gerenciados independentemente de qual computador (endereço IP) enviou esses pacotes e qual computador (endereço IP) receberá esses pacotes.</span><span class="sxs-lookup"><span data-stu-id="9b687-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="9b687-188">Na página quatro, selecione **TCP e UDP** na lista **Selecione o protocolo que esta política de QoS se aplica à** lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="9b687-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="9b687-189">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Skype for Business Server e seus aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="9b687-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="9b687-190">Em título, **especifique o número da porta de origem**, selecione uma **destas portas de origem ou intervalo**.</span><span class="sxs-lookup"><span data-stu-id="9b687-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="9b687-191">Na caixa de texto acompanhada, digite o intervalo de porta reservado para transmissões de áudio.</span><span class="sxs-lookup"><span data-stu-id="9b687-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="9b687-192">Por exemplo, se você reservou portas 50020 pelas portas 50039 para tráfego de áudio, insira o intervalo de porta usando este formato: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="9b687-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="9b687-193">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="9b687-193">Click **Finish**.</span></span>

<span data-ttu-id="9b687-194">Depois de criar a política de QoS para o áudio, você deve criar uma segunda política para vídeo.</span><span class="sxs-lookup"><span data-stu-id="9b687-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="9b687-195">Para criar uma política de vídeo, siga o mesmo procedimento básico que você seguiu ao criar a política de áudio, como fazer essas substituições:</span><span class="sxs-lookup"><span data-stu-id="9b687-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="9b687-196">Use um nome de política diferente (e exclusivo).</span><span class="sxs-lookup"><span data-stu-id="9b687-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="9b687-197">Defina o valor de DSCP para **34** em vez de 46.</span><span class="sxs-lookup"><span data-stu-id="9b687-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="9b687-198">(Conforme observado anteriormente, você não precisa usar o valor de DSCP 34; basta atribuir um valor de DSCP diferente do usado para áudio.)</span><span class="sxs-lookup"><span data-stu-id="9b687-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="9b687-199">Use o intervalo de porta configurado anteriormente para o tráfego de vídeo.</span><span class="sxs-lookup"><span data-stu-id="9b687-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="9b687-200">Por exemplo, se você reservou portas de 58000 a 58019 para vídeo, defina o intervalo de porta para isso: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="9b687-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="9b687-201">Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, faça essas substituições:</span><span class="sxs-lookup"><span data-stu-id="9b687-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="9b687-202">Use um nome de política diferente (e exclusivo) (por exemplo, **compartilhamento de aplicativos do Skype for Business Server**).</span><span class="sxs-lookup"><span data-stu-id="9b687-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="9b687-203">Defina o valor de DSCP para **24** em vez de 46.</span><span class="sxs-lookup"><span data-stu-id="9b687-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="9b687-204">(Novamente, esse valor não precisa ser 24; ele simplesmente deve ser diferente dos valores de DSCP usados para áudio e vídeo.)</span><span class="sxs-lookup"><span data-stu-id="9b687-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="9b687-205">Use o intervalo de porta configurado anteriormente para o tráfego de vídeo.</span><span class="sxs-lookup"><span data-stu-id="9b687-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="9b687-206">Por exemplo, se você reservou portas de 42000 a 42019 para compartilhamento de aplicativos, defina o intervalo de porta como: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="9b687-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="9b687-207">Para uma política de transferência de arquivos:</span><span class="sxs-lookup"><span data-stu-id="9b687-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="9b687-208">Use um nome de política diferente (e exclusivo) (por exemplo, **transferências de arquivo do Skype for Business Server**).</span><span class="sxs-lookup"><span data-stu-id="9b687-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="9b687-209">Defina o valor de DSCP para **14**.</span><span class="sxs-lookup"><span data-stu-id="9b687-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="9b687-210">(Novamente, esse valor não precisa ser 14; ele simplesmente deve ser um código DSCP exclusivo.)</span><span class="sxs-lookup"><span data-stu-id="9b687-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="9b687-211">Use o intervalo de portas configurado anteriormente para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9b687-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="9b687-212">Por exemplo, se você reservou portas de 42020 a 42039 para compartilhamento de aplicativos, defina o intervalo de porta como: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="9b687-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="9b687-213">As novas políticas que você criou não entrarão em vigor até que a política de grupo seja atualizada em seus computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="9b687-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="9b687-214">Embora a Política de Grupo seja periodicamente atualizada por si só, você pode forçar a atualização imediata executando o comando a seguir em cada computador em que a Política de Grupo deve ser atualizada:</span><span class="sxs-lookup"><span data-stu-id="9b687-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="9b687-215">Esse comando pode ser executado em qualquer janela de comando executada com credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="9b687-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="9b687-216">Para executar uma janela de comando com credenciais de administrador, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="9b687-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="9b687-217">Lembre-se de que essas políticas devem ser direcionadas para seus computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="9b687-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="9b687-218">Elas não devem ser aplicadas a servidores que executam o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9b687-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="9b687-219">Para ajudar a garantir que os pacotes de rede sejam marcados com o valor DSCP apropriado, você também deve criar uma nova entrada de registro em cada computador completando o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="9b687-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="9b687-220">Clique em  \*\*Iniciar \*\* e em  \*\*Executar \*\*.</span><span class="sxs-lookup"><span data-stu-id="9b687-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="9b687-221">Na caixa de diálogo **executar** , digite **regedit**e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="9b687-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="9b687-222">No editor do registro, expanda **\_hKey\_local Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="9b687-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="9b687-223">Clique com o botão direito do mouse em **tcpip**, aponte para **novo**e, em seguida, clique em **tecla**.</span><span class="sxs-lookup"><span data-stu-id="9b687-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="9b687-224">Após a criação da nova chave do registro, digite **QoS**e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="9b687-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="9b687-225">Clique com o botão direito do mouse em **QoS**, aponte para **novo**e clique em **valor da cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="9b687-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="9b687-226">Depois que o novo valor do registro for criado, digite não **use NLA**e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="9b687-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="9b687-227">Clique duas vezes em **não usar NLA**.</span><span class="sxs-lookup"><span data-stu-id="9b687-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="9b687-228">Na caixa de diálogo **Editar Cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b687-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="9b687-229">Feche o editor do registro e eboot seu computador.</span><span class="sxs-lookup"><span data-stu-id="9b687-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="9b687-230">Configurar a qualidade do serviço em computadores com vários adaptadores de rede</span><span class="sxs-lookup"><span data-stu-id="9b687-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="9b687-231">Se você tiver um computador com vários adaptadores de rede, você pode ocasionalmente executar em problemas nos quais valores de DSCP são mostrados como 0x00, em vez do valor configurado.</span><span class="sxs-lookup"><span data-stu-id="9b687-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="9b687-232">Isso normalmente ocorrerá em computadores em que um ou mais adaptadores de rede não conseguem acessar o domínio do Active Directory (por exemplo, se esses adaptadores forem usados para uma rede privada).</span><span class="sxs-lookup"><span data-stu-id="9b687-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="9b687-233">Em casos como esse, os valores de DSCP serão marcados para os adaptadores que podem acessar o domínio, mas não serão marcados para adaptadores que não podem acessar o domínio.</span><span class="sxs-lookup"><span data-stu-id="9b687-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="9b687-234">Se você quiser marcar valores DSCP para todos os adaptadores de rede em um computador, incluindo adaptadores que não têm acesso ao seu domínio, será necessário adicionar e configurar um valor para o registro.</span><span class="sxs-lookup"><span data-stu-id="9b687-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="9b687-235">Isso pode ser feito completando o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="9b687-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="9b687-236">Clique em  \*\*Iniciar \*\* e em  \*\*Executar \*\*.</span><span class="sxs-lookup"><span data-stu-id="9b687-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="9b687-237">Na caixa de diálogo **executar** , digite **regedit**e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="9b687-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="9b687-238">No editor do registro, expanda **\_hKey\_local Machine**, expanda **System**, expanda **CurrentControlSet**, expanda **Services**e, em seguida, expanda **tcpip**.</span><span class="sxs-lookup"><span data-stu-id="9b687-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="9b687-239">Se você não vir uma chave do registro rotulada como **QoS** , clique com o botão direito do mouse em **tcpip**, aponte para **novo**e clique em **tecla**.</span><span class="sxs-lookup"><span data-stu-id="9b687-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="9b687-240">Após a criação da nova chave, digite **QoS**e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="9b687-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="9b687-241">Clique com o botão direito do mouse em **QoS**, aponte para **novo**e clique em **valor da cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="9b687-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="9b687-242">Depois que o novo valor do registro for criado, digite não **use NLA**e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="9b687-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="9b687-243">Clique duas vezes em **não usar NLA**.</span><span class="sxs-lookup"><span data-stu-id="9b687-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="9b687-244">Na caixa de diálogo **Editar Cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b687-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="9b687-245">Depois de criar e configurar o novo valor do registro, será necessário reinicializar o computador para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="9b687-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b687-246">Confira também</span><span class="sxs-lookup"><span data-stu-id="9b687-246">See also</span></span>

[<span data-ttu-id="9b687-247">Criar um objeto de política de grupo no Windows 10</span><span class="sxs-lookup"><span data-stu-id="9b687-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
