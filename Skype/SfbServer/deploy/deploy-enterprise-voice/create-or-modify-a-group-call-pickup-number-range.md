---
title: Criar ou modificar um intervalo de números de atendimento de chamada do grupo no Skype para negócios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Criar ou modificar um intervalo de números de atendimento de chamada do grupo no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 569e1ed16e706e89ff2cf03c330f8161824e3bd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892934"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="b089b-103">Criar ou modificar um intervalo de números de atendimento de chamada do grupo no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="b089b-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="b089b-104">Criar ou modificar um intervalo de números de atendimento de chamada do grupo no Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b089b-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="b089b-105">Atendimento de chamada do grupo é baseado no aplicativo de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b089b-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="b089b-106">Quando você implanta o atendimento de chamada de grupo, você deve configurar a tabela de órbita de estacionamento de chamada com intervalos de números de telefone são designados como números de retirada de grupo de chamada.</span><span class="sxs-lookup"><span data-stu-id="b089b-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="b089b-107">Esses números do grupo são aqueles que os usuários discam para receber chamadas que estão tocando para outro usuário.</span><span class="sxs-lookup"><span data-stu-id="b089b-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="b089b-108">Como os números da órbita de estacionamento de chamada, os números do grupo de recebimento de chamada precisam ser extensões virtuais, sem nenhum usuário ou telefone atribuído.</span><span class="sxs-lookup"><span data-stu-id="b089b-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="b089b-109">Cada pool de Front-End, onde você implanta o atendimento de chamada do grupo pode ter um ou mais intervalos de números de retirada de grupo de chamada.</span><span class="sxs-lookup"><span data-stu-id="b089b-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="b089b-110">Os intervalos de números do grupo devem ser globalmente exclusivos em sua implantação e devem ser atribuídos como o tipo **GroupPickup**.</span><span class="sxs-lookup"><span data-stu-id="b089b-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="b089b-111">Utilize o procedimento a seguir para criar ou modificar o intervalo de números de um grupo de atendimento de chamadas na tabela de órbita de estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b089b-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="b089b-112">Você deve usar o Skype para Business Server Management Shell para criar, modificar, remover e exibir os intervalos de números de atendimento de chamada de grupo na tabela de órbita de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="b089b-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="b089b-113">Intervalos de números de atendimento de chamada de grupo não estão disponíveis no Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="b089b-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="b089b-114">Os intervalos de números de grupo de atendimento de chamadas precisam estar de acordo com as regras a seguir:</span><span class="sxs-lookup"><span data-stu-id="b089b-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="b089b-115">O número inicial do intervalo deve ser menor ou igual ao número final.</span><span class="sxs-lookup"><span data-stu-id="b089b-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="b089b-116">O valor do número inicial do intervalo deve ter o mesmo comprimento que o número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="b089b-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="b089b-p104">O intervalo de números precisa ser exclusivo. Esse intervalo não pode se sobrepor a nenhum outro intervalo.</span><span class="sxs-lookup"><span data-stu-id="b089b-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="b089b-119">Se o intervalo de números começa com o caractere \* ou #, o intervalo deve ser maior que 100.</span><span class="sxs-lookup"><span data-stu-id="b089b-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="b089b-120">Valores válidos: deve coincidir com a cadeia de caracteres de expressão regular ([\\* | #] ? [1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="b089b-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="b089b-121">Isso significa que o valor deve ser uma cadeia de caracteres iniciada com o caractere \* ou #, ou um número entre 1 e 9 (o primeiro caractere não pode ser um zero).</span><span class="sxs-lookup"><span data-stu-id="b089b-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="b089b-122">Se o primeiro caractere for \* ou #, o caractere seguinte deve ser um número entre 1 e 9 (ele não pode ser um zero).</span><span class="sxs-lookup"><span data-stu-id="b089b-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="b089b-123">Os caracteres subsequentes podem ser qualquer número entre 0 e 9 até sete caracteres adicionais (por exemplo, "#6000", "\*92000", "\*95551212" e "915551212").</span><span class="sxs-lookup"><span data-stu-id="b089b-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="b089b-124">Se o primeiro caractere não for \* ou #, o primeiro caractere deve ser um número entre 1 e 9 (ele não pode ser zero), seguido por até oito caracteres, cada um número entre 0 e 9 (por exemplo, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="b089b-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="b089b-125">Para criar ou modificar um intervalo de grupo de atendimento de chamadas</span><span class="sxs-lookup"><span data-stu-id="b089b-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="b089b-126">Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="b089b-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="b089b-127">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="b089b-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="b089b-128">Use o **New-CsCallParkOrbit** para criar um novo intervalo de números de grupo de atendimento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b089b-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="b089b-129">Use o **Set-CsCallParkOrbit** para modificar um intervalo existente de números de atendimento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b089b-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="b089b-130">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="b089b-130">At the command line, run:</span></span>

   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="b089b-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b089b-131">For example:</span></span>

   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="b089b-132">O exemplo a seguir mostra como trocar um intervalo de números de órbitas de estacionamento de chamadas para grupos de atendimento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b089b-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="b089b-133">Use esse cmdlet para mudar o tipo atribuído aos intervalos de números somente se você tiver especificado inicialmente o tipo incorreto e somente caso o intervalo de grupo ainda não esteja em uso.</span><span class="sxs-lookup"><span data-stu-id="b089b-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="b089b-134">Se você alterar o intervalo de números de CallPark para GroupPickup ou vice-versa e o intervalo de números já estiver em uso, o estacionamento de chamada ou o atendimento de chamada em grupo irá parar de funcionar para aquele intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="b089b-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="b089b-135">Por exemplo, se você alterar um intervalo de números de CallPark para GroupPick, o aplicativo de estacionamento de chamada não pode usar aquele intervalo de Órbitas para estacionar chamadas.</span><span class="sxs-lookup"><span data-stu-id="b089b-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="b089b-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="b089b-136">See also</span></span>

[<span data-ttu-id="b089b-137">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="b089b-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="b089b-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="b089b-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="b089b-139">Excluir um intervalo de órbita de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="b089b-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
