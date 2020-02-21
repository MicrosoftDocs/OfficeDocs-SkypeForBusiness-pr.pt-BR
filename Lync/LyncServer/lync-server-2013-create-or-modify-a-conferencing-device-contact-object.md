---
title: 'Lync Server 2013: criar ou modificar um objeto de contato do dispositivo de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74808a2deae4f7fa52e1a48fcbd415205eca93cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a><span data-ttu-id="22a95-102">Criar ou modificar um objeto de contato de dispositivo de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22a95-102">Create or modify a conferencing device Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22a95-103">_**Última modificação do tópico:** 2013-10-02_</span><span class="sxs-lookup"><span data-stu-id="22a95-103">_**Topic Last Modified:** 2013-10-02_</span></span>

<span data-ttu-id="22a95-104">Para criar um objeto de sala de conferência, primeiro crie uma conta de usuário do Active Directory para representar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22a95-104">To create a conferencing room object, first create an Active Directory user account to represent the device.</span></span> <span data-ttu-id="22a95-105">Em seguida, use o cmdlet **Enable-CsMeetingRoom** para permitir que essa conta funcione como um dispositivo de conferência.</span><span class="sxs-lookup"><span data-stu-id="22a95-105">Then, use the **Enable-CsMeetingRoom** cmdlet to enable that account to function as a conferencing device.</span></span> <span data-ttu-id="22a95-106">Se você precisar alterar as propriedades de um dispositivo de conferência existente, use o cmdlet **set-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="22a95-106">If you need to change the properties of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span>

<span data-ttu-id="22a95-107">Esses cmdlets podem ser executados a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22a95-107">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="22a95-108">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="22a95-108">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a><span data-ttu-id="22a95-109">Criando um dispositivo de conferência</span><span class="sxs-lookup"><span data-stu-id="22a95-109">Creating a Conferencing Device</span></span>

  - <span data-ttu-id="22a95-110">Depois de criar a conta de usuário do Active Directory que representa o novo dispositivo de conferência, habilite-o usando o cmdlet **Enable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="22a95-110">After you create the Active Directory user account that represents the new conferencing device, enable it by using the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="22a95-111">Certifique-se de incluir uma, a identidade do dispositivo de conferência, b) o pool de registradores onde a conta da sala será hospedada e c) o endereço SIP a ser atribuído a essa conta.</span><span class="sxs-lookup"><span data-stu-id="22a95-111">Be sure to include a) the conferencing device identity, b) the registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span> <span data-ttu-id="22a95-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="22a95-112">For example:</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a><span data-ttu-id="22a95-113">Modificando um dispositivo de conferência</span><span class="sxs-lookup"><span data-stu-id="22a95-113">Modifying a Conferencing Device</span></span>

  - <span data-ttu-id="22a95-114">Para modificar os valores de propriedade de um dispositivo de conferência existente, use o cmdlet **set-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="22a95-114">To modify the property values of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="22a95-115">Por exemplo, o seguinte comando atualiza o número de telefone (LineUri) associado a um dispositivo de conferência:</span><span class="sxs-lookup"><span data-stu-id="22a95-115">For example, the following command updates the phone number (LineUri) associated with a conferencing device:</span></span>
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

<span data-ttu-id="22a95-116">Para obter detalhes, consulte os tópicos de ajuda para o cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) e o cmdlet [set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="22a95-116">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

