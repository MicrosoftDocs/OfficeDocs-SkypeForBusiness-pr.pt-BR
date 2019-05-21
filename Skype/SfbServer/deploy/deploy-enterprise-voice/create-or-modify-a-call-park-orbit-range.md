---
title: Criar ou modificar uma faixa de opções de estacionamento de chamada no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Crie ou modifique uma tabela de faixa de órbita de estacionamento de chamada no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 77be47597e5bbb674719ac2b3192efdf4217a3dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286260"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="d519f-103">Criar ou modificar uma faixa de opções de estacionamento de chamada no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d519f-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="d519f-104">Crie ou modifique uma tabela de faixa de órbita de estacionamento de chamada no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d519f-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="d519f-105">O parque de chamadas usa órbitas para chamadas de estacionamento.</span><span class="sxs-lookup"><span data-stu-id="d519f-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="d519f-106">Para que os usuários possam estacionar e recuperar chamadas, você deve configurar a tabela órbita do parque de chamadas.</span><span class="sxs-lookup"><span data-stu-id="d519f-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="d519f-107">Você precisa especificar os intervalos de números de ramal (órbitas) que a sua organização irá reservar para fazer chamadas de estacionamento e definir o roteamento para esses intervalos especificando qual o pool do estacionamento de chamadas manipula cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="d519f-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="d519f-108">Quando você define intervalos de órbita, a meta é ter órbitas suficientes para que qualquer uma das órbitas não seja reutilizada rapidamente, mas não muitas órbitas que você limite o número de extensões disponíveis para usuários ou outros serviços.</span><span class="sxs-lookup"><span data-stu-id="d519f-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="d519f-109">Você pode criar várias faixas órbitas do estacionamento de chamada para cada pool do Skype for Business Server onde o aplicativo de estacionamento de chamada é implantado.</span><span class="sxs-lookup"><span data-stu-id="d519f-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="d519f-110">Cada faixa de opções de estacionamento de chamadas deve ter um nome globalmente exclusivo e um conjunto exclusivo de extensões.</span><span class="sxs-lookup"><span data-stu-id="d519f-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d519f-p102">Normalmente, um intervalo de órbitas engloba 100 órbitas ou menos. Cada intervalo pode ser muito maior, contanto que seja menor do que o máximo de 10.000 órbitas por intervalo e tenha menos de 50.000 órbitas por pool. Se o intervalo for muito pequeno, as órbitas serão reutilizadas mais rapidamente.</span><span class="sxs-lookup"><span data-stu-id="d519f-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="d519f-114">Use blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído a elas) para intervalos de órbita.</span><span class="sxs-lookup"><span data-stu-id="d519f-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="d519f-115">Não há suporte para a atribuição de números do Direct Inward Dialing (DID) como números órbitas na tabela órbita do estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="d519f-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="d519f-116">Utilize um dos seguintes procedimentos para criar ou modificar um intervalo de órbitas de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="d519f-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="d519f-117">Para usar o painel de controle do Skype for Business Server para criar ou modificar um intervalo de números para chamadas de estacionamento</span><span class="sxs-lookup"><span data-stu-id="d519f-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="d519f-p103">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="d519f-p103">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="d519f-120">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d519f-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="d519f-121">Na barra de navegação esquerda, clique em **Recursos de Voz** e em **Estacionamento de Chamada(Call Park)**.</span><span class="sxs-lookup"><span data-stu-id="d519f-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="d519f-122">Na página **Estacionamento de Chamada**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="d519f-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="d519f-p104">Para criar um novo intervalo de órbitas, clique em **Novo**. Em **Nome**, digite um nome de identificação para esse intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="d519f-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="d519f-125">Após confirmar o intervalo de órbitas do banco de dados, não será possível alterar esse nome.</span><span class="sxs-lookup"><span data-stu-id="d519f-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="d519f-p105">Para modificar um intervalo de órbitas existente, digite todo ou parte do nome do intervalo de órbitas no campo de pesquisa. Na lista de resultados de órbitas, clique na órbita que desejar, clique em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="d519f-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="d519f-128">No primeiro campo do **Intervalo numérico**, digite o número inicial do intervalo de extensões desta órbita de estacionamento de chamada e, no segundo campo **Intervalo numérico**, digite o número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="d519f-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="d519f-129">Lembre-se:</span><span class="sxs-lookup"><span data-stu-id="d519f-129">Be aware:</span></span>

   - <span data-ttu-id="d519f-130">O número inicial do intervalo deve ser menor ou igual ao número final.</span><span class="sxs-lookup"><span data-stu-id="d519f-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="d519f-131">O valor do número inicial do intervalo deve ter o mesmo comprimento que o número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="d519f-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="d519f-p107">O intervalo de órbita deve ser exclusivo. Este intervalo não pode sobrepor outro intervalo.</span><span class="sxs-lookup"><span data-stu-id="d519f-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="d519f-134">Se o intervalo de órbita começar com o \* caractere ou #, o intervalo deve ser maior que 100.</span><span class="sxs-lookup"><span data-stu-id="d519f-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="d519f-135">Valores válidos: devem corresponder à cadeia de caracteres de expressão\\regular ([\* | #] ? [1-{0,7}9] \d) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="d519f-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="d519f-136">Isso significa que o valor deve ser uma cadeia de caracteres que comece \* com o caractere ou # ou um número de 1 a 9 (o primeiro caractere não pode ser zero).</span><span class="sxs-lookup"><span data-stu-id="d519f-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="d519f-137">Se o primeiro caractere for \* ou #, o seguinte caractere deve ser um número de 1 a 9 (não pode ser zero).</span><span class="sxs-lookup"><span data-stu-id="d519f-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="d519f-138">Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo, "#6000"\*, "92000"\*, "95551212" e "915551212").</span><span class="sxs-lookup"><span data-stu-id="d519f-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="d519f-139">Se o primeiro caractere não \* for ou #, o primeiro caractere deve ser um número de 1 a 9 (não pode ser zero), seguido por até oito caracteres, cada um dos números de 0 a 9 (por exemplo, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="d519f-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="d519f-p109">Você não deve ter mais do que um total de 50.000 órbitas por pool. Cada intervalo de órbita geralmente possui 100 ou menos órbitas, mas pode ser muito maior contanto que inclua menos do que 10.000 órbitas. Por exemplo, ao invés de especificar um número inicial de "7000000" e um número final de "8000000," considere especificar um número inicial de "7000000" e um número final de "7000100."</span><span class="sxs-lookup"><span data-stu-id="d519f-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="d519f-143">Em **FQDN do servidor de destino**, clique no nome de domínio totalmente qualificado (FQDN) ou ID de serviço do serviço de aplicativo que hospeda o aplicativo parque de chamadas.</span><span class="sxs-lookup"><span data-stu-id="d519f-143">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="d519f-144">Todas as chamadas estacionadas em números dentro do intervalo especificado pelo número inicial e número final do intervalo de órbita serão direcionadas para este servidor ou pool.</span><span class="sxs-lookup"><span data-stu-id="d519f-144">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="d519f-145">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d519f-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="d519f-146">Para usar o Shell de gerenciamento do Skype for Business Server para criar ou modificar um intervalo de números para chamadas de estacionamento</span><span class="sxs-lookup"><span data-stu-id="d519f-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="d519f-147">Faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **permissões de configuração do representante**.</span><span class="sxs-lookup"><span data-stu-id="d519f-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="d519f-148">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="d519f-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="d519f-149">Use o **New-CsCallParkOrbit** para criar um novo intervalo de números de órbitas.</span><span class="sxs-lookup"><span data-stu-id="d519f-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="d519f-150">Use o **Set-CsCallParkOrbit** para modificar um intervalo de números de órbitas de estacionamento de chamada existente.</span><span class="sxs-lookup"><span data-stu-id="d519f-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="d519f-151">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="d519f-151">At the command line, run:</span></span>

   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="d519f-152">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d519f-152">For example:</span></span>

   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="d519f-153">O seguinte exemplo mostra como modificar os números em intervalo de órbitas existente</span><span class="sxs-lookup"><span data-stu-id="d519f-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="d519f-154">Confira também</span><span class="sxs-lookup"><span data-stu-id="d519f-154">See also</span></span>

[<span data-ttu-id="d519f-155">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="d519f-155">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="d519f-156">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="d519f-156">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="d519f-157">Excluir uma faixa de opções de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="d519f-157">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
