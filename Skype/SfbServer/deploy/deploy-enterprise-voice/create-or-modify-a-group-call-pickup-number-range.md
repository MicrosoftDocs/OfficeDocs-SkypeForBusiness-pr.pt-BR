---
title: Criar ou modificar um intervalo de números de Retirada de Chamadas de Grupo no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Crie ou modifique um intervalo de números de Retirada de Chamadas de Grupo no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: e71915519014b1fa4cfffa3172327e9949ed73a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100417"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="16db9-103">Criar ou modificar um intervalo de números de Retirada de Chamadas de Grupo no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="16db9-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="16db9-104">Crie ou modifique um intervalo de números de Retirada de Chamadas de Grupo no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="16db9-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="16db9-105">A Retirada de Chamada de Grupo se baseia no aplicativo Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="16db9-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="16db9-106">Ao implantar a Coleta de Chamadas de Grupo, você deve configurar a tabela de órbita do estacionamento de chamadas com intervalos de números de telefone designados como números de grupo de retirada de chamadas.</span><span class="sxs-lookup"><span data-stu-id="16db9-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="16db9-107">Esses números de grupo são os números que os usuários discam para atender chamadas que estão tocando para outro usuário.</span><span class="sxs-lookup"><span data-stu-id="16db9-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="16db9-108">Assim como os números de órbita do estacionamento de chamada, os números do grupo de retirada de chamadas precisam ser extensões virtuais que não tenham usuário ou telefone atribuídos a eles.</span><span class="sxs-lookup"><span data-stu-id="16db9-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="16db9-109">Cada pool de Front-End onde você implanta a Coleta de Chamada de Grupo pode ter um ou mais intervalos de números de grupo de retirada de chamada.</span><span class="sxs-lookup"><span data-stu-id="16db9-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="16db9-110">Os intervalos de número de grupo devem ser globalmente exclusivos em sua implantação e devem ser atribuídos como o **tipo GroupPickup.**</span><span class="sxs-lookup"><span data-stu-id="16db9-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="16db9-111">Use o procedimento a seguir para criar ou modificar um intervalo de números de grupo de retirada de chamada na tabela de órbita do estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="16db9-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="16db9-112">Você deve usar o Shell de Gerenciamento do Skype for Business Server para criar, modificar, remover e exibir intervalos de números de Retirada de Chamadas de Grupo na tabela de órbita do estacionamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="16db9-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="16db9-113">Os intervalos de número de retirada de chamadas de grupo não estão disponíveis no Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="16db9-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="16db9-114">Os intervalos de número do grupo de retirada de chamada devem estar em conformidade com as seguintes regras:</span><span class="sxs-lookup"><span data-stu-id="16db9-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="16db9-115">O número inicial do intervalo deve ser menor ou igual ao número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="16db9-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="16db9-116">O valor do número inicial do intervalo deve ter a mesma extensão que o número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="16db9-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="16db9-117">O intervalo de números deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="16db9-117">The number range must be unique.</span></span> <span data-ttu-id="16db9-118">Esse intervalo não pode se sobrepor a nenhum outro intervalo.</span><span class="sxs-lookup"><span data-stu-id="16db9-118">This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="16db9-119">Se o intervalo de números começar com o caractere \* ou #, o intervalo deverá ser maior que 100.</span><span class="sxs-lookup"><span data-stu-id="16db9-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="16db9-120">Valores válidos: deve corresponder à cadeia de caracteres de expressão regular ([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="16db9-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="16db9-121">Isso significa que o valor deve ser uma cadeia de caracteres começando com o caractere ou # ou um \* número de 1 a 9 (o primeiro caractere não pode ser um zero).</span><span class="sxs-lookup"><span data-stu-id="16db9-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="16db9-122">Se o primeiro caractere for ou #, o caractere a seguir deverá ser um \* número de 1 a 9 (não pode ser um zero).</span><span class="sxs-lookup"><span data-stu-id="16db9-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="16db9-123">Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo, "#6000", " \* 92000", " \* 95551212" e "915551212").</span><span class="sxs-lookup"><span data-stu-id="16db9-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="16db9-124">Se o primeiro caractere não for ou #, o primeiro caractere deverá ser um número de 1 a 9 (não pode ser zero), seguido por até oito caracteres, cada um com um número de \* 0 a 9 (por exemplo, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="16db9-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="16db9-125">Para criar ou modificar um intervalo de grupo de retirada de chamada</span><span class="sxs-lookup"><span data-stu-id="16db9-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="16db9-126">Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários,** conforme descrito em Permissões de Instalação do Representante.</span><span class="sxs-lookup"><span data-stu-id="16db9-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="16db9-127">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="16db9-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="16db9-128">Use **New-CsCallParkOrbit** para criar um novo intervalo de números de grupo de retirada de chamadas.</span><span class="sxs-lookup"><span data-stu-id="16db9-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="16db9-129">Use **Set-CsCallParkOrbit** para modificar um intervalo existente de números de retirada de chamadas.</span><span class="sxs-lookup"><span data-stu-id="16db9-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="16db9-130">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="16db9-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="16db9-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="16db9-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="16db9-132">O exemplo a seguir mostra como alterar um intervalo de números de órbitas de estacionamento de chamada para grupos de retirada de chamada.</span><span class="sxs-lookup"><span data-stu-id="16db9-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="16db9-133">Use este cmdlet para alterar o tipo atribuído a intervalos de números somente se você especificou inicialmente o tipo incorreto e o intervalo de grupo ainda não está em uso.</span><span class="sxs-lookup"><span data-stu-id="16db9-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="16db9-134">Se você alterar o intervalo de números de CallPark para GroupPickup ou vice-versa e o intervalo de números já estiver em uso, o Estacionamento de Chamada ou a Retirada de Chamada de Grupo pararão de funcionar para esse intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="16db9-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="16db9-135">Por exemplo, se você alterar um intervalo de números de CallPark para GroupPick, o aplicativo Estacionamento de Chamadas não poderá mais usar esse intervalo de órbitas para estacionar chamadas.</span><span class="sxs-lookup"><span data-stu-id="16db9-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="16db9-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="16db9-136">See also</span></span>

[<span data-ttu-id="16db9-137">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="16db9-137">New-CsCallParkOrbit</span></span>](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="16db9-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="16db9-138">Set-CsCallParkOrbit</span></span>](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="16db9-139">Excluir um intervalo de órbita de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="16db9-139">Delete a Call Park Orbit Range</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)