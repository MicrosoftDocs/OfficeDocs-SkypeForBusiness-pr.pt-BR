---
title: Configurando intervalos de porta e uma política de qualidade de serviço para seus clientes
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este artigo descreve como configurar intervalos de portas para seus clientes e configurando políticas de qualidade de serviço do Skype para Business Server para clientes executando o Windows 10.
ms.openlocfilehash: 2e5328406634302a1b076eec8466e7f7b9245150
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881518"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="7b4a0-103">Configurando intervalos de porta e uma política de qualidade de serviço para os clientes do Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="7b4a0-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="7b4a0-104">Este artigo descreve como configurar intervalos de portas para seus clientes e configurando políticas de qualidade de serviço do Skype para Business Server para clientes executando o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="7b4a0-105">Configurar intervalos de porta</span><span class="sxs-lookup"><span data-stu-id="7b4a0-105">Configure port ranges</span></span>

<span data-ttu-id="7b4a0-106">Por padrão, Skype para aplicativos de cliente de negócios podem usar qualquer porta entre portas 1024 e 65535 quando estiver envolvido em uma sessão de comunicação; Isso ocorre porque os intervalos de porta específica não são automaticamente habilitados para clientes.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="7b4a0-107">Para usar a qualidade de serviço, no entanto, você precisará reatribuir os vários tipos de tráfego (áudio, vídeo, mídia, compartilhamento de aplicativos e transferência de arquivos) a uma série de intervalos de porta exclusivo.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="7b4a0-108">Isso pode ser feito usando o cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="7b4a0-109">Os usuários finais não pode fazer essas alterações em si.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="7b4a0-110">Alterações de porta só podem ser feitas por administradores usando o cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="7b4a0-111">Você pode determinar quais intervalos de porta são usados atualmente para sessões de comunicação executando o seguinte comando dentro do Skype do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="7b4a0-112">Supondo que não fazer qualquer alteração em suas configurações de conferência desde que instalou o Skype para Business Server, você deve obter informações que incluem estes valores de propriedade:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="7b4a0-113">Se você observe atentamente a saída anterior, você verá duas coisas de importância.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="7b4a0-114">Em primeiro lugar, a propriedade ClientMediaPortRangeEnabled é definida como False:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="7b4a0-115">Isso é importante porque, quando essa propriedade é definida como False, Skype para clientes corporativos irá usar qualquer porta disponível entre portas 1024 e 65535 quando estiver envolvido em uma sessão de comunicação; Isso é verdadeiro independentemente de qualquer outra configuração de porta (por exemplo, ClientMediaPort ou ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="7b4a0-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="7b4a0-116">Se você deseja restringir o uso de um conjunto especificado de portas (e isso é algo que você deseja fazer se você planeja implementar Quality of Service), em seguida, você deve primeiro habilitar intervalos de portas de mídia do cliente.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="7b4a0-117">Que pode ser feito usando o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="7b4a0-118">O comando anterior habilita os intervalos de portas de mídia do cliente para a coleção global de definições de configuração de conferência; No entanto, essas configurações também podem ser aplicadas ao escopo do site e/ou o escopo do serviço (apenas para o servidor de conferência serviço).</span><span class="sxs-lookup"><span data-stu-id="7b4a0-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="7b4a0-119">Intervalos para um site específico ou um servidor da porta de mídia do cliente para permitir que especifique a identidade do site ou o servidor ao chamar Set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="7b4a0-120">Como alternativa, você pode usar este comando para habilitar simultaneamente intervalos de portas para todas as suas definições de configuração de conferência:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="7b4a0-121">A segunda coisa importante que você observará é que o resultado de amostra mostrando que, por padrão, as portas de mídia intervalos definido para cada tipo de tráfego de rede é idênticos:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="7b4a0-122">Para implementar o QoS, cada um desses intervalos de portas precisará ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="7b4a0-123">Por exemplo, você pode configurar os intervalos de porta semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b4a0-124">Tipo de tráfego do cliente</span><span class="sxs-lookup"><span data-stu-id="7b4a0-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="7b4a0-125">Porta de início</span><span class="sxs-lookup"><span data-stu-id="7b4a0-125">Port Start</span></span></th>
<th><span data-ttu-id="7b4a0-126">Intervalo de portas</span><span class="sxs-lookup"><span data-stu-id="7b4a0-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b4a0-127">Áudio</span><span class="sxs-lookup"><span data-stu-id="7b4a0-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-128">50020</span><span class="sxs-lookup"><span data-stu-id="7b4a0-128">50020</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-129">20</span><span class="sxs-lookup"><span data-stu-id="7b4a0-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b4a0-130">Vídeo</span><span class="sxs-lookup"><span data-stu-id="7b4a0-130">Video</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-131">58000</span><span class="sxs-lookup"><span data-stu-id="7b4a0-131">58000</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-132">20</span><span class="sxs-lookup"><span data-stu-id="7b4a0-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b4a0-133">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="7b4a0-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-134">42000</span><span class="sxs-lookup"><span data-stu-id="7b4a0-134">42000</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-135">20</span><span class="sxs-lookup"><span data-stu-id="7b4a0-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b4a0-136">Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="7b4a0-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-137">42020</span><span class="sxs-lookup"><span data-stu-id="7b4a0-137">42020</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-138">20</span><span class="sxs-lookup"><span data-stu-id="7b4a0-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7b4a0-139">Na tabela anterior, os intervalos de porta do cliente representam um subconjunto dos intervalos de porta configurada para os seus servidores.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="7b4a0-140">Por exemplo, nos servidores, compartilhamento de aplicativos foi configurado para usar portas 40803 por meio de 49151; nos computadores cliente, compartilhamento de aplicativos é configurado para usar portas 42000 por meio de 42019.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="7b4a0-141">Isso, também, é feito principalmente para facilitar a administração de QoS: portas do cliente não precisa representam um subconjunto das portas usadas no servidor.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="7b4a0-142">(Por exemplo, nos computadores cliente você poderia configurar o compartilhamento de aplicativos para usar, digamos, portas 10000 através de 10019.) No entanto, é recomendável que você faça seu cliente de intervalos de porta um subconjunto dos intervalos de porta de servidor.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="7b4a0-143">Além disso, você pode ter percebido que 8348 portas foram postas para compartilhamento nos servidores de aplicativos, mas apenas 20 portas foram postas para os clientes de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="7b4a0-144">Isso, também, é recomendável, mas não for uma regra prontas.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="7b4a0-145">Em geral, você pode considerar cada porta disponível para representar uma sessão de comunicação único: se você tiver 100 portas disponíveis em um intervalo de porta, o que significa que o computador em questão pode participar, no máximo, 100 sessões de comunicação a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="7b4a0-146">Porque os servidores provavelmente serão participar de várias conversas mais que clientes, faz sentido para abrir muitas portas nos servidores que nos clientes.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="7b4a0-147">Configuração aside 20 portas compartilhamento de aplicativo em um cliente significa que um usuário pode participar de sessões de compartilhamento de aplicativo 20 no dispositivo especificado e todos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="7b4a0-148">Que deve comprovar suficiente para a maioria dos usuários.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="7b4a0-149">Para atribuir os intervalos de porta anteriores para seu conjunto global de definições de configuração de conferência, você pode usar a seguir Skype de comando do Shell de gerenciamento do servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="7b4a0-150">Ou, use este comando para atribuir estes mesmos intervalos de porta para todas as suas conferências definições de configuração:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="7b4a0-151">Usuários individuais devem fazer logoff do Skype para negócios e, em seguida, logon novamente antes que essas alterações realmente terem efeito.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="7b4a0-152">Você pode também habilitar intervalos de portas de mídia do cliente e, em seguida, atribuir esses intervalos de porta, usando um único comando.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="7b4a0-153">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="7b4a0-154">Configurar políticas de qualidade de serviço para clientes executando o Windows 10</span><span class="sxs-lookup"><span data-stu-id="7b4a0-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="7b4a0-155">Além de especificar intervalos de portas para uso pela sua Skype para clientes corporativos, você também deve criar diretivas de qualidade de serviço separadas que serão aplicadas aos computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="7b4a0-156">(As políticas de qualidade de serviço criadas para os servidores de mediação, aplicativo e conferência não devem ser aplicadas aos computadores cliente.) Essas informações só se aplica a computadores que executam o Skype para o cliente de negócios e Windows 10.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="7b4a0-157">O exemplo a seguir usa este conjunto de intervalos de portas para criar uma política de áudio e uma política de vídeo:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b4a0-158">Tipo de tráfego do cliente</span><span class="sxs-lookup"><span data-stu-id="7b4a0-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="7b4a0-159">Porta de início</span><span class="sxs-lookup"><span data-stu-id="7b4a0-159">Port Start</span></span></th>
<th><span data-ttu-id="7b4a0-160">Intervalo de portas</span><span class="sxs-lookup"><span data-stu-id="7b4a0-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b4a0-161">Áudio</span><span class="sxs-lookup"><span data-stu-id="7b4a0-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-162">50020</span><span class="sxs-lookup"><span data-stu-id="7b4a0-162">50020</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-163">20</span><span class="sxs-lookup"><span data-stu-id="7b4a0-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b4a0-164">Vídeo</span><span class="sxs-lookup"><span data-stu-id="7b4a0-164">Video</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-165">58000</span><span class="sxs-lookup"><span data-stu-id="7b4a0-165">58000</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-166">20</span><span class="sxs-lookup"><span data-stu-id="7b4a0-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b4a0-167">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="7b4a0-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-168">42000</span><span class="sxs-lookup"><span data-stu-id="7b4a0-168">42000</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-169">20</span><span class="sxs-lookup"><span data-stu-id="7b4a0-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b4a0-170">Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="7b4a0-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-171">42020</span><span class="sxs-lookup"><span data-stu-id="7b4a0-171">42020</span></span></p></td>
<td><p><span data-ttu-id="7b4a0-172">20</span><span class="sxs-lookup"><span data-stu-id="7b4a0-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7b4a0-173">Para criar uma política de áudio de qualidade de serviço para computadores Windows 10, primeiro faça logon em um computador no qual o gerenciamento de diretiva de grupo tenha sido instalado.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="7b4a0-174">Abra Gerenciamento de diretiva de grupo (clique em **Iniciar**, aponte para **Ferramentas administrativas**e clique em **Gerenciamento de diretiva de grupo**) e conclua o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="7b4a0-175">Em gerenciamento de diretiva de grupo, localize o contêiner onde a nova diretiva deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="7b4a0-176">Por exemplo, se todos os computadores cliente estão localizados em uma unidade Organizacional denominada clientes, a nova diretiva deve ser criada na unidade Organizacional cliente.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="7b4a0-177">Com o botão direito do contêiner apropriado e clique em **criar um GPO neste domínio e vinculá-lo aqui**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="7b4a0-178">Na caixa de diálogo **Novo GPO** , digite um nome para o novo objeto de diretiva de grupo na caixa **nome** e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="7b4a0-179">Com o botão direito na política recém criada e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="7b4a0-180">No Editor de gerenciamento de diretiva de grupo, expanda **Configuração do computador**, expanda **Configurações do Windows**, do mouse em **QoS baseada em política**e clique em **Criar nova política**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="7b4a0-181">Na caixa de diálogo **QoS baseada em política** , na página de abertura, digite um nome para a nova política na caixa **nome** .</span><span class="sxs-lookup"><span data-stu-id="7b4a0-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="7b4a0-182">Selecione **Especificar valor de DSCP** e defina o valor para **46**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="7b4a0-183">Deixe **Especificar taxa de aceleração saída** desmarcada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="7b4a0-184">Na próxima página, certifique-se de que **todos os aplicativos** está selecionada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-184">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="7b4a0-185">Essa configuração instrui a rede para procurar todos os pacotes com uma marcação de DSCP 46, não apenas de pacotes criados por um aplicativo específico.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-185">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

8.  <span data-ttu-id="7b4a0-186">Na terceira página, certifique-se de que **qualquer endereço IP de origem** e de **qualquer endereço IP de destino** estão marcada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="7b4a0-187">Estas duas configurações Certifique-se de que os pacotes serão gerenciados independentemente do computador (endereço IP) enviadas nesses pacotes e qual computador (endereço IP) receberá nesses pacotes.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="7b4a0-188">Na página quatro, selecione **TCP e UDP** na lista suspensa **, selecione o protocolo que essa política de QoS se aplica** .</span><span class="sxs-lookup"><span data-stu-id="7b4a0-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="7b4a0-189">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Skype para Business Server e seus aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="7b4a0-190">Sob o título, **Especifique o número da porta de origem**, selecione **este ou intervalo de porta de origem**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="7b4a0-191">Na caixa de texto que o acompanha, digite o intervalo de portas reservado para transmissões de áudio.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="7b4a0-192">Por exemplo, se você reservada portas 50020 através de portas 50039 para tráfego de áudio insira o intervalo de portas usando este formato: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="7b4a0-193">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-193">Click **Finish**.</span></span>

<span data-ttu-id="7b4a0-194">Depois que você criou a política de QoS para áudio, em seguida, crie uma segunda política para vídeo.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="7b4a0-195">Para criar uma política para vídeo, siga o mesmo procedimento básico que seguiu quando criar a política de áudio, tornando essas substituições:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="7b4a0-196">Use um nome de política diferente (e único).</span><span class="sxs-lookup"><span data-stu-id="7b4a0-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="7b4a0-197">Defina o valor DSCP para **34** , em vez de 46.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="7b4a0-198">(Conforme observado anteriormente, você não precisará usar o valor DSCP 34; você simplesmente deve atribuir um valor DSCP diferente daquela usada para áudio).</span><span class="sxs-lookup"><span data-stu-id="7b4a0-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="7b4a0-199">Use o intervalo de portas previamente configurados para o tráfego de vídeo.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="7b4a0-200">Por exemplo, se você tiver reservadas portas 58000 por meio de 58019 para vídeo, defina o intervalo de portas a esta: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="7b4a0-201">Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, faça essas substituições:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="7b4a0-202">Use um nome de política diferente (e único) (por exemplo, **Skype para compartilhamento de aplicativos do Business Server**).</span><span class="sxs-lookup"><span data-stu-id="7b4a0-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="7b4a0-203">Defina o valor DSCP para **24** em vez de 46.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="7b4a0-204">(Novamente, este valor não precisam ser 24; ele simplesmente deve ser diferente do que os valores DSCP usados para áudio e vídeo).</span><span class="sxs-lookup"><span data-stu-id="7b4a0-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="7b4a0-205">Use o intervalo de portas previamente configurados para o tráfego de vídeo.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="7b4a0-206">Por exemplo, se você tiver reservadas portas 42000 através do 42019 para compartilhamento de aplicativos, defina o intervalo de portas a esta: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="7b4a0-207">Para uma diretiva de transferência de arquivo:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="7b4a0-208">Use um nome de política diferente (e único) (por exemplo, **Skype para transferências de arquivos do servidor de negócios**).</span><span class="sxs-lookup"><span data-stu-id="7b4a0-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="7b4a0-209">Defina o valor DSCP para **14**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="7b4a0-210">(Novamente, este valor não precisam ser 14; ele simplesmente deve ser um código DSCP exclusivo).</span><span class="sxs-lookup"><span data-stu-id="7b4a0-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="7b4a0-211">Use o intervalo de portas previamente configurados para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="7b4a0-212">Por exemplo, se você tiver reservadas portas 42020 através do 42039 para compartilhamento de aplicativos, defina o intervalo de portas a esta: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="7b4a0-213">As novas políticas que você criou não terão efeito até que a diretiva de grupo tenha sido atualizada em seus computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="7b4a0-214">Embora a Política de Grupo seja periodicamente atualizada por si só, você pode forçar a atualização imediata executando o comando a seguir em cada computador em que a Política de Grupo deve ser atualizada:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="7b4a0-215">Esse comando pode ser executado em qualquer janela de comando executada com credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="7b4a0-216">Para executar uma janela de comando com credenciais de administrador, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="7b4a0-217">Tenha em mente que essas políticas devem ser voltadas para os seus computadores clientes.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="7b4a0-218">Não deve ser aplicadas aos servidores que executam o Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="7b4a0-219">Para ajudar a garantir que os pacotes de rede sejam marcados com o valor DSCP apropriado, você também deve criar uma nova entrada de registro em cada computador, Concluindo o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="7b4a0-220">Clique em  \*\*Iniciar \*\* e em  \*\*Executar \*\*.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="7b4a0-221">Na caixa de diálogo **Executar** , digite **regedit**e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="7b4a0-222">No Editor do registro, expanda **HKEY\_LOCAL\_máquina**, expanda **SYSTEM**, expanda **CurrentControlSet**, expanda **Serviços**e depois expanda **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="7b4a0-223">Clique com o botão **Tcpip**, aponte para **novo**e clique em **chave**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="7b4a0-224">Depois que a nova chave do registro é criada, digite **QoS**e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="7b4a0-225">Com o botão direito **QoS**, aponte para **novo**e clique em **Valor de cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="7b4a0-226">Depois que o novo valor do registro é criado, digite **não use NLA**e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="7b4a0-227">Clique duas vezes em **não use NLA**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="7b4a0-228">Na caixa de diálogo **Editar cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="7b4a0-229">Feche o Editor do registro e i:eboot seu computador.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="7b4a0-230">Configurar a qualidade de serviço em computadores com vários adaptadores de rede</span><span class="sxs-lookup"><span data-stu-id="7b4a0-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="7b4a0-231">Se você tiver um computador que tenha vários adaptadores de rede, você pode executar ocasionalmente problemas onde os valores DSCP são mostrados como 0x00 ao invés do valor configurado.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="7b4a0-232">Normalmente, isso ocorrerá nos computadores em que um ou mais dos adaptadores de rede não serão possível acessar o domínio do Active Directory (por exemplo, se esses adaptadores são usados para uma rede privada).</span><span class="sxs-lookup"><span data-stu-id="7b4a0-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="7b4a0-233">Em casos assim, os valores DSCP serão marcados para os adaptadores que podem acessar o domínio, mas não serão marcados para adaptadores que não é possível acessar o domínio.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="7b4a0-234">Se você gostaria de valores DSCP de marca para todos os adaptadores de rede em um computador, inclusive adaptadores que não têm acesso ao seu domínio, você precisará adicionar e configurar um valor no registro.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="7b4a0-235">Que pode ser feito, completando o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="7b4a0-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="7b4a0-236">Clique em  \*\*Iniciar \*\* e em  \*\*Executar \*\*.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="7b4a0-237">Na caixa de diálogo **Executar** , digite **regedit**e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="7b4a0-238">No Editor do registro, expanda **HKEY\_LOCAL\_máquina**, expanda **SYSTEM**, expanda **CurrentControlSet**, expanda **Serviços**e depois expanda **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="7b4a0-239">Se você não vir uma chave de registro rotulada **QoS** , em seguida, clique com o botão **Tcpip**, aponte para **novo**e clique em **chave**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="7b4a0-240">Depois que a nova chave é criada, digite **QoS**e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="7b4a0-241">Com o botão direito **QoS**, aponte para **novo**e clique em **Valor de cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="7b4a0-242">Depois que o novo valor do registro é criado, digite **não use NLA**e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="7b4a0-243">Clique duas vezes em **não use NLA**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="7b4a0-244">Na caixa de diálogo **Editar cadeia de caracteres** , digite **1** na caixa **dados do valor** e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="7b4a0-245">Após criar e configurar o novo valor do registro, você precisará reiniciar o computador para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="7b4a0-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b4a0-246">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7b4a0-246">See also</span></span>

[<span data-ttu-id="7b4a0-247">Criar um objeto de diretiva de grupo no Windows 10</span><span class="sxs-lookup"><span data-stu-id="7b4a0-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
