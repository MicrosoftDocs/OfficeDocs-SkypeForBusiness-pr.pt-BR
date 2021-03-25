---
title: Criar ou modificar um intervalo de órbitas do Estacionamento de Chamadas no Skype for Business
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Crie ou modifique uma tabela de intervalo de órbitas do Estacionamento de Chamadas no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: eab1c3e6e53eaa878546b5fe4a9684147a00c583
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106317"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="6054a-103">Criar ou modificar um intervalo de órbitas do Estacionamento de Chamadas no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6054a-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="6054a-104">Crie ou modifique uma tabela de intervalo de órbitas do Estacionamento de Chamadas no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6054a-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="6054a-105">Call Park usa órbitas para chamadas de estacionamento.</span><span class="sxs-lookup"><span data-stu-id="6054a-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="6054a-106">Antes que os usuários possam estacionar e recuperar chamadas, você deve configurar a tabela de órbita do Estacionamento de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="6054a-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="6054a-107">Você precisa especificar os intervalos de números de extensão (órbitas) que sua organização reserva para chamadas de estacionamento e definir o roteamento para esses intervalos especificando qual pool de Estacionamento de Chamadas lida com cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="6054a-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="6054a-108">Quando você define intervalos de órbitas, o objetivo é ter órbitas suficientes para que qualquer órbita não seja reutilizada muito rapidamente, mas não tantas órbitas que você limite o número de extensões disponíveis para usuários ou outros serviços.</span><span class="sxs-lookup"><span data-stu-id="6054a-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="6054a-109">Você pode criar vários intervalos de órbita do Estacionamento de Chamadas para cada pool do Skype for Business Server onde o aplicativo Estacionamento de Chamadas é implantado.</span><span class="sxs-lookup"><span data-stu-id="6054a-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="6054a-110">Cada intervalo de órbitas do Estacionamento de Chamada deve ter um nome global exclusivo e um conjunto exclusivo de extensões.</span><span class="sxs-lookup"><span data-stu-id="6054a-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6054a-p102">Normalmente, um intervalo de órbitas engloba 100 órbitas ou menos. Cada intervalo pode ser muito maior, contanto que seja menor do que o máximo de 10.000 órbitas por intervalo e tenha menos de 50.000 órbitas por pool. Se o intervalo for muito pequeno, as órbitas serão reutilizadas mais rapidamente.</span><span class="sxs-lookup"><span data-stu-id="6054a-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="6054a-114">Use blocos de extensões virtuais (extensões sem um usuário ou telefone atribuído a elas) para intervalos de órbita.</span><span class="sxs-lookup"><span data-stu-id="6054a-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="6054a-115">Não há suporte para a atribuição de números DID (Discagem direta interna) como números de órbita na tabela de órbita do Estacionamento de Chamada.</span><span class="sxs-lookup"><span data-stu-id="6054a-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="6054a-116">Utilize um dos seguintes procedimentos para criar ou modificar um intervalo de órbitas de estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="6054a-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="6054a-117">Para usar o Painel de Controle do Skype for Business Server para criar ou modificar um intervalo de números para chamadas de estacionamento</span><span class="sxs-lookup"><span data-stu-id="6054a-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="6054a-118">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6054a-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="6054a-119">Para obter detalhes, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="6054a-119">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="6054a-120">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6054a-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="6054a-121">Na barra de navegação esquerda, clique em **Recursos de Voz** e em **Estacionamento de Chamada**.</span><span class="sxs-lookup"><span data-stu-id="6054a-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="6054a-122">Na página **Estacionamento de Chamada**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6054a-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="6054a-p104">Para criar um novo intervalo de órbitas, clique em **Novo**. Em **Nome**, digite um nome de identificação para esse intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="6054a-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="6054a-125">Após confirmar o intervalo de órbitas do banco de dados, não será possível alterar esse nome.</span><span class="sxs-lookup"><span data-stu-id="6054a-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="6054a-p105">Para modificar um intervalo de órbitas existente, digite todo ou parte do nome do intervalo de órbitas no campo de pesquisa. Na lista de resultados de órbitas, clique na órbita que desejar, clique em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="6054a-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="6054a-128">No primeiro campo do **Intervalo numérico**, digite o número inicial do intervalo de extensões desta órbita de estacionamento de chamada e, no segundo campo **Intervalo numérico**, digite o número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="6054a-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="6054a-129">Esteja ciente:</span><span class="sxs-lookup"><span data-stu-id="6054a-129">Be aware:</span></span>

   - <span data-ttu-id="6054a-130">O número inicial do intervalo deve ser menor ou igual ao número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="6054a-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="6054a-131">O valor do número inicial do intervalo deve ter a mesma extensão que o número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="6054a-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="6054a-p107">O intervalo da órbita deve ser único. Esse intervalo não pode se sobrepor a nenhum outro intervalo.</span><span class="sxs-lookup"><span data-stu-id="6054a-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="6054a-134">Se o intervalo de órbitas começar com o caractere \* ou #, o intervalo deve ser maior que 100.</span><span class="sxs-lookup"><span data-stu-id="6054a-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="6054a-135">Valores válidos: deve corresponder à cadeia de caracteres de expressão regular ([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="6054a-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="6054a-136">Isso significa que o valor deve ser uma cadeia de caracteres começando com o caractere ou # ou um \* número de 1 a 9 (o primeiro caractere não pode ser um zero).</span><span class="sxs-lookup"><span data-stu-id="6054a-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="6054a-137">Se o primeiro caractere for ou #, o caractere a seguir deverá ser um \* número de 1 a 9 (não pode ser um zero).</span><span class="sxs-lookup"><span data-stu-id="6054a-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="6054a-138">Os caracteres subsequentes podem ser qualquer número de 0 a 9 até sete caracteres adicionais (por exemplo, "#6000", " \* 92000", " \* 95551212" e "915551212").</span><span class="sxs-lookup"><span data-stu-id="6054a-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="6054a-139">Se o primeiro caractere não for ou #, o primeiro caractere deverá ser um número de 1 a 9 (não pode ser zero), seguido por até oito caracteres, cada um com um número de \* 0 a 9 (por exemplo, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="6054a-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="6054a-p109">Você não deve ter mais que um total de 50.000 órbitas por pool. Cada intervalo de órbita geralmente abrange 100 órbitas ou menos, mas pode ser muito maior, contanto que inclua menos que 10.000 órbitas. Por exemplo, em vez de especificar um número inicial em "7000000" e um número final em "8000000", considere especificar um número inicial em "7000000" e um número final em "7000100".</span><span class="sxs-lookup"><span data-stu-id="6054a-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="6054a-p110">No **FQDN do servidor de destino**, clique no FQDN ou na ID do serviço de aplicativo que hospeda o aplicativo de Estacionamento de Chamada. Todas as chamadas estacionadas em números entre o intervalo especificado pelo número inicial e o número final no intervalo da órbita será roteado para esse servidor ou pool.</span><span class="sxs-lookup"><span data-stu-id="6054a-p110">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application. All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="6054a-145">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="6054a-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="6054a-146">Para usar o Shell de Gerenciamento do Skype for Business Server para criar ou modificar um intervalo de números para chamadas de estacionamento</span><span class="sxs-lookup"><span data-stu-id="6054a-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="6054a-147">Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários,** conforme descrito em Permissões de Instalação do Representante.</span><span class="sxs-lookup"><span data-stu-id="6054a-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="6054a-148">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="6054a-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="6054a-149">Use o **New-CsCallParkOrbit** para criar um novo intervalo de números de órbitas.</span><span class="sxs-lookup"><span data-stu-id="6054a-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="6054a-150">Use o **Set-CsCallParkOrbit** para modificar um intervalo de números de órbitas de estacionamento de chamada existente.</span><span class="sxs-lookup"><span data-stu-id="6054a-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="6054a-151">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="6054a-151">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="6054a-152">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6054a-152">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="6054a-153">O seguinte exemplo mostra como modificar os números em intervalo de órbitas existente</span><span class="sxs-lookup"><span data-stu-id="6054a-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="6054a-154">Confira também</span><span class="sxs-lookup"><span data-stu-id="6054a-154">See also</span></span>

[<span data-ttu-id="6054a-155">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="6054a-155">New-CsCallParkOrbit</span></span>](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="6054a-156">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="6054a-156">Set-CsCallParkOrbit</span></span>](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="6054a-157">Excluir um intervalo de órbita de estacionamento de chamada</span><span class="sxs-lookup"><span data-stu-id="6054a-157">Delete a Call Park Orbit Range</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)