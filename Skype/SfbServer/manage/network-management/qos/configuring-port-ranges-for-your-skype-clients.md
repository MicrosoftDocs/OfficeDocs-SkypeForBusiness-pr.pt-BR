---
title: Configurando intervalos de portas e uma política de Qualidade de Serviço para seus clientes
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Este artigo descreve como configurar intervalos de porta para seus clientes e configurar políticas de Qualidade de Serviço no Skype for Business Server para clientes em execução no Windows 10.
ms.openlocfilehash: b2961193bef799742ac3b79a4f421a7aa50c5a03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814197"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="285cd-103">Configurando intervalos de portas e uma política de Qualidade de Serviço para seus clientes no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="285cd-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="285cd-104">Este artigo descreve como configurar intervalos de porta para seus clientes e configurar políticas de Qualidade de Serviço no Skype for Business Server para clientes em execução no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="285cd-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="285cd-105">Configurar intervalos de portas</span><span class="sxs-lookup"><span data-stu-id="285cd-105">Configure port ranges</span></span>

<span data-ttu-id="285cd-106">Por padrão, os aplicativos clientes do Skype for Business podem usar qualquer porta entre as portas 1024 e 65535 quando envolvidos em uma sessão de comunicação; isso acontece porque intervalos de portas específicos não são habilitados automaticamente para clientes.</span><span class="sxs-lookup"><span data-stu-id="285cd-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="285cd-107">Para poder usar a Qualidade do Serviço, no entanto, você precisará reatribuir os vários tipos de tráfego (áudio, vídeo, mídia, compartilhamento de aplicativos e transferência de arquivos) para uma série de intervalos de porta únicos.</span><span class="sxs-lookup"><span data-stu-id="285cd-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="285cd-108">Isto pode ser realizado usando o cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="285cd-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="285cd-109">Os usuários finais não podem fazer essas alterações por conta própria.</span><span class="sxs-lookup"><span data-stu-id="285cd-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="285cd-110">As alterações de porta só podem ser feitas por administradores usando o Set-CsConferencingConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="285cd-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="285cd-111">Você pode determinar quais intervalos de porta são usados atualmente para sessões de comunicação executando o seguinte comando no Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="285cd-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="285cd-112">Supondo que você não tenha feito alterações em suas configurações de conferência desde que instalou o Skype for Business Server, você deve obter informações que incluam estes valores de propriedade:</span><span class="sxs-lookup"><span data-stu-id="285cd-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="285cd-113">Se você verificar o resultado anterior, você verá duas coisas de importância.</span><span class="sxs-lookup"><span data-stu-id="285cd-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="285cd-114">Primeiro, a propriedade ClientMediaPortRangeEnabled é definida para False:</span><span class="sxs-lookup"><span data-stu-id="285cd-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="285cd-115">Isso é importante porque, quando essa propriedade é definida como False, os clientes do Skype for Business usarão qualquer porta disponível entre as portas 1024 e 65535 quando envolvidos em uma sessão de comunicação; isso é verdadeiro independentemente de qualquer outra configuração de porta (por exemplo, ClientMediaPort ou ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="285cd-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="285cd-116">Se você deseja restringir o uso a um conjunto especificado de portas (e isso é algo que você deseja fazer se planeja implementar a Qualidade de Serviço), você deve primeiro habilitar intervalos de porta de mídia do cliente.</span><span class="sxs-lookup"><span data-stu-id="285cd-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="285cd-117">Isso pode ser feito usando o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="285cd-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="285cd-p105">O comando anterior habilita os intervalos de porta de mídia do cliente para o conjunto global de definições de configuração de conferência; no entanto, estas configurações também podem ser aplicadas para o escopo local e/ou de serviço (apenas para o serviço do Servidor de Conferência). Para habilitar os intervalos de porta de mídia do cliente para um site ou servidor específico, defina a Identidade deste site ou servidor ao chamar Set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="285cd-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="285cd-120">Em alternativa, é possível usar este comando para habilitar simultaneamente intervalos de portas para todas as suas definições de configuração de conferência:</span><span class="sxs-lookup"><span data-stu-id="285cd-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="285cd-121">A segunda coisa importante que você observará é o resultado de amostra mostrando que, por padrão, o conjunto de intervalos da porta de mídia para cada tipo de tráfego de rede são idênticos:</span><span class="sxs-lookup"><span data-stu-id="285cd-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="285cd-p106">Para poder implementar o QoS, cada um destes intervalos de porta precisarão ser exclusivos. Por exemplo, você pode configurar os intervalos de porta desta forma:</span><span class="sxs-lookup"><span data-stu-id="285cd-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="285cd-124">Tipo de Tráfego do Cliente</span><span class="sxs-lookup"><span data-stu-id="285cd-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="285cd-125">Início da Porta</span><span class="sxs-lookup"><span data-stu-id="285cd-125">Port Start</span></span></th>
<th><span data-ttu-id="285cd-126">Intervalo da Porta</span><span class="sxs-lookup"><span data-stu-id="285cd-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="285cd-127">Áudio</span><span class="sxs-lookup"><span data-stu-id="285cd-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="285cd-128">50020</span><span class="sxs-lookup"><span data-stu-id="285cd-128">50020</span></span></p></td>
<td><p><span data-ttu-id="285cd-129">20</span><span class="sxs-lookup"><span data-stu-id="285cd-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="285cd-130">Vídeo</span><span class="sxs-lookup"><span data-stu-id="285cd-130">Video</span></span></p></td>
<td><p><span data-ttu-id="285cd-131">58000</span><span class="sxs-lookup"><span data-stu-id="285cd-131">58000</span></span></p></td>
<td><p><span data-ttu-id="285cd-132">20</span><span class="sxs-lookup"><span data-stu-id="285cd-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="285cd-133">Compartilhamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="285cd-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="285cd-134">42000</span><span class="sxs-lookup"><span data-stu-id="285cd-134">42000</span></span></p></td>
<td><p><span data-ttu-id="285cd-135">20</span><span class="sxs-lookup"><span data-stu-id="285cd-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="285cd-136">Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="285cd-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="285cd-137">42020</span><span class="sxs-lookup"><span data-stu-id="285cd-137">42020</span></span></p></td>
<td><p><span data-ttu-id="285cd-138">20</span><span class="sxs-lookup"><span data-stu-id="285cd-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="285cd-139">Na tabela anterior, os intervalos da porta do cliente representam um subconjunto dos intervalos de porta configurados para seus servidores.</span><span class="sxs-lookup"><span data-stu-id="285cd-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="285cd-140">Por exemplo, nos servidores, o compartilhamento de aplicativos foi configurado para usar as portas 40803 a 49151; nos computadores clientes, o compartilhamento de aplicativos é configurado para usar as portas 42000 a 42019.</span><span class="sxs-lookup"><span data-stu-id="285cd-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="285cd-141">Isso também é feito principalmente para facilitar a administração da QoS: as portas do cliente não têm que representar um subconjunto das portas usadas no servidor.</span><span class="sxs-lookup"><span data-stu-id="285cd-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="285cd-142">(Por exemplo, nos computadores cliente, você pode configurar o compartilhamento de aplicativos para usar, digamos, as portas 10000 a 10019.) No entanto, é recomendável que você faça dos intervalos de porta do cliente um subconjunto dos intervalos de porta do servidor.</span><span class="sxs-lookup"><span data-stu-id="285cd-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="285cd-143">Além disso, você deve ter notado que 8348 portas foram configuradas para compartilhamento de aplicativos nos servidores, mas apenas 20 portas foram configuradas para compartilhamento de aplicativos nos clientes.</span><span class="sxs-lookup"><span data-stu-id="285cd-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="285cd-144">Isso também é recomendado, mas não é uma regra rápida e difícil.</span><span class="sxs-lookup"><span data-stu-id="285cd-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="285cd-145">Em geral, você pode considerar cada porta disponível para representar uma única sessão de comunicação: se você tiver 100 portas disponíveis em um intervalo de portas, isso significa que o computador em questão pode participar, no máximo, de 100 sessões de comunicação a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="285cd-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="285cd-146">Como os servidores provavelmente participarão de muito mais conversas do que os clientes, faz sentido abrir muito mais portas em servidores do que em clientes.</span><span class="sxs-lookup"><span data-stu-id="285cd-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="285cd-147">Reservar 20 portas para o compartilhamento de aplicativos em um cliente significa que um usuário pode participar de 20 sessões de compartilhamento de aplicativos no dispositivo especificado e todas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="285cd-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="285cd-148">Isso deve ser suficiente para a grande maioria dos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="285cd-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="285cd-149">Para atribuir os intervalos de porta anteriores ao seu conjunto global de definições de configuração de conferências, você pode usar o seguinte comando do Shell de Gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="285cd-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="285cd-150">Em alternativa, use este comando para atribuir estes mesmos intervalos de porta para todas suas definições de configuração de conferência:</span><span class="sxs-lookup"><span data-stu-id="285cd-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="285cd-151">Os usuários individuais devem fazer logoff do Skype for Business e fazer logoff novamente antes que essas alterações realmente entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="285cd-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="285cd-152">Também é possível habilitar intervalos de porta da mídia do cliente e atribuir estes intervalos de porta usando um único comando.</span><span class="sxs-lookup"><span data-stu-id="285cd-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="285cd-153">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="285cd-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="285cd-154">Configurar políticas de Qualidade de Serviço para clientes em execução no Windows 10</span><span class="sxs-lookup"><span data-stu-id="285cd-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="285cd-155">Além de especificar intervalos de porta para uso pelos clientes do Skype for Business, você também deve criar políticas de Qualidade de Serviço separadas que serão aplicadas aos computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="285cd-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="285cd-156">(As políticas de Qualidade de Serviço criadas para servidores de Conferência, Aplicativo e Mediação não devem ser aplicadas a computadores cliente.) Essas informações se aplica somente a computadores que executam o cliente Skype for Business e o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="285cd-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="285cd-157">O exemplo a seguir usa esse conjunto de intervalos de porta para criar uma política de áudio e uma política de vídeo:</span><span class="sxs-lookup"><span data-stu-id="285cd-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="285cd-158">Tipo de Tráfego do Cliente</span><span class="sxs-lookup"><span data-stu-id="285cd-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="285cd-159">Início da Porta</span><span class="sxs-lookup"><span data-stu-id="285cd-159">Port Start</span></span></th>
<th><span data-ttu-id="285cd-160">Intervalo da Porta</span><span class="sxs-lookup"><span data-stu-id="285cd-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="285cd-161">Áudio</span><span class="sxs-lookup"><span data-stu-id="285cd-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="285cd-162">50020</span><span class="sxs-lookup"><span data-stu-id="285cd-162">50020</span></span></p></td>
<td><p><span data-ttu-id="285cd-163">20</span><span class="sxs-lookup"><span data-stu-id="285cd-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="285cd-164">Vídeo</span><span class="sxs-lookup"><span data-stu-id="285cd-164">Video</span></span></p></td>
<td><p><span data-ttu-id="285cd-165">58000</span><span class="sxs-lookup"><span data-stu-id="285cd-165">58000</span></span></p></td>
<td><p><span data-ttu-id="285cd-166">20</span><span class="sxs-lookup"><span data-stu-id="285cd-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="285cd-167">Compartilhamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="285cd-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="285cd-168">42000</span><span class="sxs-lookup"><span data-stu-id="285cd-168">42000</span></span></p></td>
<td><p><span data-ttu-id="285cd-169">20</span><span class="sxs-lookup"><span data-stu-id="285cd-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="285cd-170">Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="285cd-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="285cd-171">42020</span><span class="sxs-lookup"><span data-stu-id="285cd-171">42020</span></span></p></td>
<td><p><span data-ttu-id="285cd-172">20</span><span class="sxs-lookup"><span data-stu-id="285cd-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="285cd-173">Para criar uma política de áudio de Qualidade de Serviço para computadores Com Windows 10, primeiro faça logoff em um computador em que o Gerenciamento de Política de Grupo tenha sido instalado.</span><span class="sxs-lookup"><span data-stu-id="285cd-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="285cd-174">Abra o Gerenciamento de Política de Grupo (clique em **Iniciar,** aponte para Ferramentas Administrativas **e** clique em Gerenciamento de Política de **Grupo)** e conclua o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="285cd-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="285cd-175">No Gerenciamento de Política de Grupo, localize o contêiner em que a nova política deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="285cd-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="285cd-176">Por exemplo, se todos os seus computadores clientes estão localizados em uma UO chamada Clients, a nova política deve ser criada na UO Cliente.</span><span class="sxs-lookup"><span data-stu-id="285cd-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="285cd-177">Clique com o botão direito do mouse no contêiner apropriado e clique em **Criar um GPO neste domínio e vincule-o aqui.**</span><span class="sxs-lookup"><span data-stu-id="285cd-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="285cd-178">Na caixa **de diálogo Novo GPO,** digite um nome  para o novo objeto de Política de Grupo na caixa Nome e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="285cd-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="285cd-179">Clique com o botão direito do mouse na política recém-criada e clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="285cd-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="285cd-180">No Editor de Gerenciamento de Política de Grupo, **expanda** a Configuração do Computador, **expanda** As Configurações do Windows, clique com o botão direito do mouse em **QoS** baseada em política e clique em Criar **nova política.**</span><span class="sxs-lookup"><span data-stu-id="285cd-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="285cd-181">Na caixa **de diálogo QoS** baseada em política, na página de abertura, digite um nome para a nova política na **caixa** Nome.</span><span class="sxs-lookup"><span data-stu-id="285cd-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="285cd-182">Selecione **Especificar valor de DSCP** e defina o valor como **46**.</span><span class="sxs-lookup"><span data-stu-id="285cd-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="285cd-183">Deixe a opção **Especificar Taxa de Aceleração de Saída** desmarcada e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="285cd-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="285cd-184">Na próxima página, selecione **Somente aplicativos** com esse nome executável, insira **Lync.exe** como o nome e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="285cd-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="285cd-185">Essa configuração instrui a política a priorizar apenas o tráfego correspondente do cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="285cd-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="285cd-186">Na terceira página, certifique-se de que ambos os **endereços IP** de origem e Qualquer endereço **IP** de destino estão selecionados e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="285cd-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="285cd-187">Essas duas configurações garantem que os pacotes serão gerenciados independente de qual computador (endereço IP) tenha os enviado e de qual computador (endereço IP) os receberá.</span><span class="sxs-lookup"><span data-stu-id="285cd-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="285cd-188">Na página quatro, selecione **TCP e UDP** na lista suspensa **Selecione o protocolo ao qual esta política de QoS se aplica**.</span><span class="sxs-lookup"><span data-stu-id="285cd-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="285cd-189">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) são os dois protocolos de rede mais comumente usados pelo Skype for Business Server e seus aplicativos clientes.</span><span class="sxs-lookup"><span data-stu-id="285cd-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="285cd-190">No cabeçalho **Especifique o número da porta de origem**, selecione **Desta porta ou intervalo de origem**.</span><span class="sxs-lookup"><span data-stu-id="285cd-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="285cd-191">Na caixa de texto acompanhante, digite o intervalo de porta reservado para transmissões de áudio.</span><span class="sxs-lookup"><span data-stu-id="285cd-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="285cd-192">Por exemplo, se você reservou as portas 50020 até as portas 50039 para tráfego de áudio, insira o intervalo de portas usando este formato: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="285cd-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="285cd-193">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="285cd-193">Click **Finish**.</span></span>

<span data-ttu-id="285cd-194">Depois de criar a política de QoS para áudio, você deve criar uma segunda política para vídeo.</span><span class="sxs-lookup"><span data-stu-id="285cd-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="285cd-195">Para criar uma política para vídeo, siga o mesmo procedimento básico da criação da política de áudio, fazendo as seguintes substituições:</span><span class="sxs-lookup"><span data-stu-id="285cd-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="285cd-196">Use um nome de política diferente (e exclusivo).</span><span class="sxs-lookup"><span data-stu-id="285cd-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="285cd-197">Defina o valor DSCP para **34** em vez de 46.</span><span class="sxs-lookup"><span data-stu-id="285cd-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="285cd-198">(Conforme mencionado anteriormente, você não precisa usar o valor 34 do DSCP; basta atribuir um valor DSCP diferente do usado para áudio.)</span><span class="sxs-lookup"><span data-stu-id="285cd-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="285cd-199">Use o intervalo de portas configurado anteriormente para o tráfego de vídeo.</span><span class="sxs-lookup"><span data-stu-id="285cd-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="285cd-200">Por exemplo, se você reservou as portas 58000 a 58019 para vídeo, de acordo com o intervalo de portas: **58000:58019.**</span><span class="sxs-lookup"><span data-stu-id="285cd-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="285cd-201">Se você decidir criar uma política para gerenciar o tráfego de compartilhamento de aplicativos, faça estas substituições:</span><span class="sxs-lookup"><span data-stu-id="285cd-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="285cd-202">Use um nome de política diferente (e exclusivo) (por exemplo, **compartilhamento de aplicativos do Skype for Business Server).**</span><span class="sxs-lookup"><span data-stu-id="285cd-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="285cd-203">Defina o valor DSCP para **24** em vez de 46.</span><span class="sxs-lookup"><span data-stu-id="285cd-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="285cd-204">(Novamente, esse valor não precisa ser 24; ele simplesmente deve ser diferente dos valores DSCP usados para áudio e vídeo.)</span><span class="sxs-lookup"><span data-stu-id="285cd-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="285cd-205">Use o intervalo de portas configurado anteriormente para o tráfego de vídeo.</span><span class="sxs-lookup"><span data-stu-id="285cd-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="285cd-206">Por exemplo, se você reservou as portas 42000 a 42019 para compartilhamento de aplicativos, de definir o intervalo de portas como: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="285cd-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="285cd-207">Para uma política de transferência de arquivos:</span><span class="sxs-lookup"><span data-stu-id="285cd-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="285cd-208">Use um nome de política diferente (e exclusivo) (por exemplo, Transferências de Arquivos do **Skype for Business Server).**</span><span class="sxs-lookup"><span data-stu-id="285cd-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="285cd-209">De definir o valor de DSCP **como 14**.</span><span class="sxs-lookup"><span data-stu-id="285cd-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="285cd-210">(Novamente, esse valor não precisa ser 14; ele simplesmente deve ser um código DSCP exclusivo.)</span><span class="sxs-lookup"><span data-stu-id="285cd-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="285cd-211">Use o intervalo de portas configurado anteriormente para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="285cd-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="285cd-212">Por exemplo, se você reservou as portas 42020 a 42039 para compartilhamento de aplicativos, de acordo com o intervalo de portas: **42020:42039.**</span><span class="sxs-lookup"><span data-stu-id="285cd-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="285cd-213">As novas políticas criadas não terão efeito até que a Política de Grupo seja atualizada nos computadores cliente.</span><span class="sxs-lookup"><span data-stu-id="285cd-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="285cd-214">Embora a Política de Grupo seja atualizada periodicamente sozinha, você pode forçar uma atualização imediata executando o comando a seguir em cada computador em que for necessário atualizar a Política de Grupo:</span><span class="sxs-lookup"><span data-stu-id="285cd-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="285cd-215">Esse comando pode ser executado em qualquer janela de comando que está sendo executado sob credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="285cd-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="285cd-216">Para executar uma janela de comando sob credenciais de administrador, clique em **Iniciar**, clique com o botão direito em **Prompt de Comando** e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="285cd-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="285cd-217">Lembre-se de que essas políticas devem ser direcionadas para seus computadores clientes.</span><span class="sxs-lookup"><span data-stu-id="285cd-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="285cd-218">Eles não devem ser aplicados a servidores que executam o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="285cd-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="285cd-219">Para ajudar a garantir que os pacotes de rede sejam marcados com o valore DSCP correto, você também deve criar uma nova entrada de registro em cada computador, concluindo o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="285cd-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="285cd-220">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="285cd-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="285cd-221">Na caixa **de** diálogo Executar, digite **regedit** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="285cd-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="285cd-222">No Editor do Registro, **expanda HKEY \_ LOCAL \_ MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="285cd-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="285cd-223">Clique com o botão direito em **Tcpip**, aponte para **Novo** e clique em **Chave**.</span><span class="sxs-lookup"><span data-stu-id="285cd-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="285cd-224">Depois que a nova chave do Registro for criada, digite **QoS** e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="285cd-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="285cd-225">Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**.</span><span class="sxs-lookup"><span data-stu-id="285cd-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="285cd-226">Depois que o novo valor do Registro for criado, digite **Não usar NLA** e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="285cd-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="285cd-227">Clique duas vezes **em Não usar NLA.**</span><span class="sxs-lookup"><span data-stu-id="285cd-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="285cd-228">Na caixa **de diálogo Editar Cadeia** de Caracteres, digite **1** na caixa **de** dados Valor e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="285cd-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="285cd-229">Feche o Editor do Registro e eboote seu computador.</span><span class="sxs-lookup"><span data-stu-id="285cd-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="285cd-230">Configurar a Qualidade de Serviço em computadores com vários adaptadores de rede</span><span class="sxs-lookup"><span data-stu-id="285cd-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="285cd-231">Se você tiver um computador com vários adaptadores de rede, poderá ocasionalmente ter problemas em que os valores DSCP são mostrados como 0x00 em vez do valor configurado.</span><span class="sxs-lookup"><span data-stu-id="285cd-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="285cd-232">Isso normalmente ocorrerá em computadores em que um ou mais adaptadores de rede não conseguem acessar seu domínio do Active Directory (por exemplo, se esses adaptadores são usados para uma rede privada).</span><span class="sxs-lookup"><span data-stu-id="285cd-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="285cd-233">Nesses casos, os valores DSCP serão marcados para os adaptadores que podem acessar o domínio, mas não serão marcados para adaptadores que não possam acessar o domínio.</span><span class="sxs-lookup"><span data-stu-id="285cd-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="285cd-234">Se você quiser marcar valores DSCP para todos os adaptadores de rede em um computador, incluindo adaptadores que não têm acesso ao seu domínio, será necessário adicionar e configurar um valor para o Registro.</span><span class="sxs-lookup"><span data-stu-id="285cd-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="285cd-235">Isso pode ser feito realizando o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="285cd-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="285cd-236">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="285cd-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="285cd-237">Na caixa **de** diálogo Executar, digite **regedit** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="285cd-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="285cd-238">No Editor do Registro, **expanda HKEY \_ LOCAL \_ MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="285cd-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="285cd-239">Se você não vir uma chave do Registro rotulada **como QoS,** clique com o botão direito do mouse em **Tcpip**, aponte para Novo e clique em **Chave.** </span><span class="sxs-lookup"><span data-stu-id="285cd-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="285cd-240">Depois que a nova chave for criada, digite **QoS** e pressione ENTER para renomear a chave.</span><span class="sxs-lookup"><span data-stu-id="285cd-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="285cd-241">Clique com o botão direito em **QoS**, aponte para **Novo** e clique em **Valor da Sequência**.</span><span class="sxs-lookup"><span data-stu-id="285cd-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="285cd-242">Depois que o novo valor do Registro for criado, digite **Não usar NLA** e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="285cd-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="285cd-243">Clique duas vezes **em Não usar NLA.**</span><span class="sxs-lookup"><span data-stu-id="285cd-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="285cd-244">Na caixa **de diálogo Editar Cadeia** de Caracteres, digite **1** na caixa **de** dados Valor e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="285cd-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="285cd-245">Depois de criar e configurar o novo valor do Registro, você precisará reiniciar o computador para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="285cd-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="285cd-246">Confira também</span><span class="sxs-lookup"><span data-stu-id="285cd-246">See also</span></span>

[<span data-ttu-id="285cd-247">Criar um objeto de política de grupo no Windows 10</span><span class="sxs-lookup"><span data-stu-id="285cd-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
