---
title: 'Lync Server 2013: excluir um objeto de contato de telefone de área comum'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17ab84f88417a6f5cb1c96c4cf7b6df45fa24b16
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="ab044-102">Excluir um objeto de contato de telefone de área comum no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab044-102">Delete a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab044-103">_**Tópico da última modificação:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ab044-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ab044-104">Talvez você queira excluir o objeto de contato associado a um telefone de área comum.</span><span class="sxs-lookup"><span data-stu-id="ab044-104">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="ab044-105">Por exemplo, se você remover o telefone de um funcionário de descanso, não será necessário ter um objeto de contato associado a esse telefone.</span><span class="sxs-lookup"><span data-stu-id="ab044-105">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="ab044-106">O cmdlet **Remove-CsCommonAreaPhone** fornece uma maneira de você excluir contas de telefone comuns de área.</span><span class="sxs-lookup"><span data-stu-id="ab044-106">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="ab044-107">Quando você executa esse cmdlet, o telefone é excluído da lista de telefones celulares comuns retornados por **Get-CsCommonAreaPhone**.</span><span class="sxs-lookup"><span data-stu-id="ab044-107">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="ab044-108">Além disso, o objeto de contato associado a esse telefone é excluído dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ab044-108">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="ab044-109">Use **Remove-CsCommonAreaPhone** para remover um telefone de área comum ou todos os celulares comuns que têm um elemento comum, como um nome de exibição ou um país e um código de área.</span><span class="sxs-lookup"><span data-stu-id="ab044-109">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="ab044-110">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ab044-110">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ab044-111">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="ab044-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="ab044-112">Como remover um telefone de área comum especificado</span><span class="sxs-lookup"><span data-stu-id="ab044-112">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="ab044-113">O comando a seguir remove o telefone de área comum com o endereço SIP sip:mainlobby@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="ab044-113">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="ab044-114">Removendo telefones celulares comuns com base em seu nome de exibição</span><span class="sxs-lookup"><span data-stu-id="ab044-114">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="ab044-115">Esse comando Remove todos os telefones celulares comuns onde o nome de exibição inclui o valor de cadeia de caracteres "Building 14":</span><span class="sxs-lookup"><span data-stu-id="ab044-115">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="ab044-116">Removendo telefones celulares comuns com base em seus códigos de país e área</span><span class="sxs-lookup"><span data-stu-id="ab044-116">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="ab044-117">Esse comando Remove todos os telefones fixos de área comuns para os Estados Unidos (código de país 1) e o código de área 425:</span><span class="sxs-lookup"><span data-stu-id="ab044-117">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="ab044-118">Para obter detalhes, consulte o tópico da ajuda para o cmdlet [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="ab044-118">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ab044-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="ab044-119">See Also</span></span>


[<span data-ttu-id="ab044-120">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="ab044-120">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

