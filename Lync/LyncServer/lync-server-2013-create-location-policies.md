---
title: 'Lync Server 2013: criar políticas de local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e09f63ab91071e979dbb0c90cf9bd31fcb60e62
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="86e31-102">Criar políticas de local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86e31-102">Create location policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86e31-103">_**Última modificação do tópico:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="86e31-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="86e31-104">O Lync Server usa uma política de local para habilitar os clientes do Lync para E9-1-1 durante o registro do cliente.</span><span class="sxs-lookup"><span data-stu-id="86e31-104">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="86e31-105">Uma política de localização contém as configurações que definem como o E9-1-1 será implementado.</span><span class="sxs-lookup"><span data-stu-id="86e31-105">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="86e31-p102">É possível editar a política de localização global e criar novas políticas de localização sinalizadas. Um cliente obtém uma política global quando não está localizado dentro de uma subrede com uma política de localização associada ou quando o cliente não foi atribuído diretamente com uma política de localização. As políticas sinalizadas são atribuídas à subredes ou usuários.</span><span class="sxs-lookup"><span data-stu-id="86e31-p102">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="86e31-109">Para criar uma política de localização, você deve usar uma conta membro do grupo RTCUniversalServerAdmins, membro da função administrativa CsVoiceAdministrator ou com direitos e permissões de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="86e31-109">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="86e31-110">Para obter uma descrição completa das políticas de local, consulte [definindo a política de local para o Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="86e31-110">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="86e31-111">Os cmdlets deste procedimento usam uma política de localização definida usando os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="86e31-111">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86e31-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="86e31-112">Element</span></span></th>
<th><span data-ttu-id="86e31-113">Valor</span><span class="sxs-lookup"><span data-stu-id="86e31-113">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86e31-114">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="86e31-114">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="86e31-115"><strong>Verdadeiro</strong></span><span class="sxs-lookup"><span data-stu-id="86e31-115"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86e31-116">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="86e31-116">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="86e31-117"><strong>Aviso de isenção de responsabilidade</strong></span><span class="sxs-lookup"><span data-stu-id="86e31-117"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86e31-118">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="86e31-118">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="86e31-p104">Sua empresa exige a definição de uma localização. Se você não a definir, os serviços de emergência não poderão localizá-lo em caso de emergência. Defina uma localização.</span><span class="sxs-lookup"><span data-stu-id="86e31-p104">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86e31-122">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="86e31-122">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="86e31-123"><strong>Falso</strong></span><span class="sxs-lookup"><span data-stu-id="86e31-123"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86e31-124">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="86e31-124">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="86e31-125"><strong>EmergencyUsage</strong></span><span class="sxs-lookup"><span data-stu-id="86e31-125"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86e31-126">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="86e31-126">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="86e31-127"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="86e31-127"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86e31-128">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="86e31-128">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="86e31-129"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="86e31-129"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86e31-130">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="86e31-130">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="86e31-131"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="86e31-131"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86e31-132">Conferenceui</span><span class="sxs-lookup"><span data-stu-id="86e31-132">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="86e31-133"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="86e31-133"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86e31-134">Conferencemode</span><span class="sxs-lookup"><span data-stu-id="86e31-134">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="86e31-135"><strong>TwoWay</strong></span><span class="sxs-lookup"><span data-stu-id="86e31-135"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86e31-136">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="86e31-136">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="86e31-137"><strong>duas</strong></span><span class="sxs-lookup"><span data-stu-id="86e31-137"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="86e31-138">Para obter detalhes sobre como trabalhar com políticas de local, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="86e31-138">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="86e31-139">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="86e31-139">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="86e31-140">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="86e31-140">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="86e31-141">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="86e31-141">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="86e31-142">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="86e31-142">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="86e31-143">Grant-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="86e31-143">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="86e31-144">Para criar políticas de localização</span><span class="sxs-lookup"><span data-stu-id="86e31-144">To create location policies</span></span>

1.  <span data-ttu-id="86e31-145">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="86e31-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="86e31-146">O CsLocationPolicy irá falhar se a configuração do <STRONG>PstnUsage</STRONG> ainda não estiver na lista Global de PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="86e31-146">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="86e31-147">Opcionalmente, execute o seguinte cmdlet para editar a política de localização global:</span><span class="sxs-lookup"><span data-stu-id="86e31-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="86e31-148">Execute o seguinte para criar uma política de localização sinalizada.</span><span class="sxs-lookup"><span data-stu-id="86e31-148">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="86e31-149">Execute o seguinte cmdlet para aplicar a política de localização sinalizada criada na etapa 3 em uma política de usuário.</span><span class="sxs-lookup"><span data-stu-id="86e31-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

