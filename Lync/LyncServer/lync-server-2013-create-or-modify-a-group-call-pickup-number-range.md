---
title: 'Lync Server 2013: criar ou modificar um intervalo de números de recebimento de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd323e609a811a9735c966645c5176fb8784bb4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="d5244-102">Criar ou modificar um intervalo de números de recebimento de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5244-102">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5244-103">_**Última modificação do tópico:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="d5244-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="d5244-104">Use o procedimento a seguir para criar ou modificar um intervalo de números do grupo de recebimento de chamada na tabela de órbita de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="d5244-104">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5244-105">Você deve usar o Shell de gerenciamento do Lync Server para criar, modificar, remover e exibir intervalos de números de recebimento de chamadas em grupo na tabela de órbita de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="d5244-105">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="d5244-106">Os intervalos de números de recebimento de chamadas de grupo não estão disponíveis no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5244-106">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d5244-107">O intervalo de números do grupo de recebimento de chamadas deve ser atribuído a um tipo de GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="d5244-107">The call pickup group number range must be assigned a type of GroupPickup.</span></span> <span data-ttu-id="d5244-108">Os usuários são habilitados para o recebimento de chamadas em grupo somente se o número do grupo atribuído for o tipo GroupPickup.</span><span class="sxs-lookup"><span data-stu-id="d5244-108">Users are enabled for Group Call Pickup only if the group number that they are assigned is type GroupPickup.</span></span>



</div>

<span data-ttu-id="d5244-109">Os intervalos de números do grupo de recebimento de chamadas devem estar em conformidade com as seguintes regras:</span><span class="sxs-lookup"><span data-stu-id="d5244-109">The call pickup group number ranges must comply with the following rules:</span></span>

  - <span data-ttu-id="d5244-110">O número inicial do intervalo deve ser menor ou igual ao número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="d5244-110">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="d5244-111">O valor do número inicial do intervalo deve ter a mesma extensão que o número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="d5244-111">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="d5244-112">O intervalo de números deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="d5244-112">The number range must be unique.</span></span> <span data-ttu-id="d5244-113">Esse intervalo não pode se sobrepor a nenhum outro intervalo.</span><span class="sxs-lookup"><span data-stu-id="d5244-113">This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="d5244-114">Se o intervalo de números começar com o \* caractere \#ou, o intervalo deve ser maior que 100.</span><span class="sxs-lookup"><span data-stu-id="d5244-114">If the number range begins with the character \* or \#, the range must be greater than 100.</span></span>

  - <span data-ttu-id="d5244-115">Valores válidos: devem corresponder à cadeia de caracteres de\[\\\*|\#\]expressão\[ regular (? 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="d5244-115">Valid values: Must match the regular expression string (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}).</span></span> <span data-ttu-id="d5244-116">Isso significa que o valor deve ser uma cadeia de caracteres que comece \* com \# o caractere ou um número de 1 a 9 (o primeiro caractere não pode ser zero).</span><span class="sxs-lookup"><span data-stu-id="d5244-116">This means the value must be a string beginning with either the character \* or \# or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="d5244-117">Se o primeiro caractere for \* ou \#, o caractere seguinte deve ser um número de 1 a 9 (não pode ser zero).</span><span class="sxs-lookup"><span data-stu-id="d5244-117">If the first character is \* or \#, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="d5244-118">Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo\#, "6000"\*, "92000"\*, "95551212" e "915551212").</span><span class="sxs-lookup"><span data-stu-id="d5244-118">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "\#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="d5244-119">Se o primeiro caractere não \* for ou \#, o primeiro caractere deve ser um número de 1 a 9 (não pode ser zero), seguido por até oito caracteres, cada um com um número de 0 a 9 (por exemplo, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="d5244-119">If the first character is not \* or \#, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="d5244-120">Para criar ou modificar um intervalo de grupos de recebimento de chamadas</span><span class="sxs-lookup"><span data-stu-id="d5244-120">To create or modify a call pickup group range</span></span>

1.  <span data-ttu-id="d5244-121">Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d5244-121">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d5244-122">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d5244-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d5244-123">Use **New-CsCallParkOrbit** para criar um novo intervalo de números de grupo de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="d5244-123">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="d5244-124">Use **set-CsCallParkOrbit** para modificar um intervalo existente de números de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="d5244-124">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="d5244-125">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="d5244-125">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    <span data-ttu-id="d5244-126">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d5244-126">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    <span data-ttu-id="d5244-127">O exemplo a seguir mostra como alterar um intervalo de números de órbitas de estacionamento de chamada para chamar grupos de retirada.</span><span class="sxs-lookup"><span data-stu-id="d5244-127">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5244-128">Use este cmdlet para alterar o tipo atribuído a intervalos de números somente se você especificou inicialmente o tipo incorreto e o intervalo de grupo ainda não estiver em uso.</span><span class="sxs-lookup"><span data-stu-id="d5244-128">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="d5244-129">Se você alterar o intervalo de números de CallPark para GroupPickup ou vice-versa e o intervalo de números já estiver em uso, o estacionamento de chamadas ou o recebimento de chamadas de grupo deixará de funcionar para esse intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="d5244-129">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="d5244-130">Por exemplo, se você alterar um intervalo de números de CallPark para GroupPick, o aplicativo de estacionamento de chamadas não poderá mais usar esse intervalo de órbitas para estacionar chamadas.</span><span class="sxs-lookup"><span data-stu-id="d5244-130">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d5244-131">Confira Também</span><span class="sxs-lookup"><span data-stu-id="d5244-131">See Also</span></span>


[<span data-ttu-id="d5244-132">Excluir um intervalo de órbita de estacionamento de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5244-132">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="d5244-133">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="d5244-133">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="d5244-134">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="d5244-134">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

