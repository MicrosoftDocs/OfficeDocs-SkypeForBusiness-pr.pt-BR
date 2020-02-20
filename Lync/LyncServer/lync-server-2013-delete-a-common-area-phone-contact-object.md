---
title: 'Lync Server 2013: excluir um objeto de contato de telefone de área comum'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c77d9c220502abbd4275af337142927786be9be3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="95100-102">Excluir um objeto de contato de telefone de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95100-102">Delete a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95100-103">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="95100-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="95100-104">Você pode querer excluir o objeto de contato associado a um telefone de área comum.</span><span class="sxs-lookup"><span data-stu-id="95100-104">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="95100-105">Por exemplo, se você remover o telefone de um funcionário de descanso, não será necessário ter um objeto de contato associado a esse telefone.</span><span class="sxs-lookup"><span data-stu-id="95100-105">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="95100-106">O cmdlet **Remove-CsCommonAreaPhone** fornece uma maneira de excluir contas de telefone de área comum.</span><span class="sxs-lookup"><span data-stu-id="95100-106">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="95100-107">Quando você executa esse cmdlet, o telefone é excluído da lista de telefones de área comum retornados por **Get-CsCommonAreaPhone**.</span><span class="sxs-lookup"><span data-stu-id="95100-107">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="95100-108">Além disso, o objeto de contato associado a esse telefone é excluído dos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="95100-108">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="95100-109">Use **Remove-CsCommonAreaPhone** para remover um telefone de área comum ou todos os telefones de área comum que têm um elemento comum, como um nome de exibição ou código de área e de cidade.</span><span class="sxs-lookup"><span data-stu-id="95100-109">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="95100-110">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95100-110">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="95100-111">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="95100-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="95100-112">Removendo um telefone de área comum especificado</span><span class="sxs-lookup"><span data-stu-id="95100-112">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="95100-113">O comando a seguir remove o telefone de área comum com o endereço SIP sip:mainlobby@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="95100-113">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="95100-114">Removendo telefones de área comuns com base em seu nome de exibição</span><span class="sxs-lookup"><span data-stu-id="95100-114">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="95100-115">Este comando Remove todos os telefones de área comum onde o nome de exibição inclui o valor de cadeia de caracteres "Building 14":</span><span class="sxs-lookup"><span data-stu-id="95100-115">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="95100-116">Removendo telefones de área comum com base em seus códigos de área e país</span><span class="sxs-lookup"><span data-stu-id="95100-116">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="95100-117">Este comando Remove todos os telefones de área comum para os Estados Unidos (código do país 1) e o código de área 425:</span><span class="sxs-lookup"><span data-stu-id="95100-117">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="95100-118">Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="95100-118">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="95100-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="95100-119">See Also</span></span>


[<span data-ttu-id="95100-120">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="95100-120">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

