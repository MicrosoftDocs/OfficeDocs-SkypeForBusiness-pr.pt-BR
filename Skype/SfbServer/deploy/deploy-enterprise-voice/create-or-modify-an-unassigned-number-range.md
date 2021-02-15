---
title: Criar ou modificar um intervalo de números não atribuídos no Skype for Business Server
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
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Criar, modificar ou excluir intervalos de números não atribuídos para o aplicativo Comunicado no Skype for Business Server Enterprise Voice. Isso afeta como as chamadas para números não atribuídos são tratadas.
ms.openlocfilehash: 180db35a5ea7c2c55dcdbbdcb3be70f868149d88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837081"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a><span data-ttu-id="81b89-104">Criar ou modificar um intervalo de números não atribuídos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="81b89-104">Create or modify an unassigned number range in Skype for Business Server</span></span>
 
<span data-ttu-id="81b89-105">Criar, modificar ou excluir intervalos de números não atribuídos para o aplicativo Comunicado no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="81b89-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="81b89-106">Isso afeta como as chamadas para números não atribuídos são tratadas.</span><span class="sxs-lookup"><span data-stu-id="81b89-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="81b89-107">O Skype for Business Server permite que você diga o que acontece com as chamadas recebidas para números de telefone válidos para sua organização, mas que não estão atribuídos a um usuário ou telefone.</span><span class="sxs-lookup"><span data-stu-id="81b89-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="81b89-108">Para lidar com essas chamadas, você configura uma tabela de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="81b89-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="81b89-109">Você pode usar a tabela para rotear as chamadas para um aplicativo de Anúncio ou para um servidor UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="81b89-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="81b89-p104">O modo como você configura a tabela de números não atribuída depende de como você deseja usá-la. É possível configurar a tabela com todas as extensões válidas para sua organização, com apenas extensões não atribuídas ou com uma combinação de ambos os tipos de números. A tabela de números não atribuída pode incluir números atribuídos e não atribuídos, mas é chamada somente quando um chamador disca um número que não está atribuído no momento. Se você incluir todas as extensões válidas na tabela de números não atribuída, você poderá especificar a ação que ocorre sempre que alguém deixa sua organização, sem a necessidade de reconfigurar a tabela. Se você incluir extensões não atribuídas na tabela, poderá personalizar a ação que ocorre para números específicos. Por exemplo, se você alterar a extensão para seu atendimento ao cliente, poderá incluir o número antigo de atendimento ao cliente na tabela, e atribui-lo a um anúncio que fornece o novo número.</span><span class="sxs-lookup"><span data-stu-id="81b89-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="81b89-116">Configurar números de telefone não atribuídos</span><span class="sxs-lookup"><span data-stu-id="81b89-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="81b89-117">Use um dos seguintes procedimentos para configurar intervalos de números não atribuídos para o aplicativo Comunicado.</span><span class="sxs-lookup"><span data-stu-id="81b89-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="81b89-118">Antes de configurar a tabela de números não atribuídos, seu sistema já deve ter Comunicados definidos ou um Atendente Automático da Unificação de Mensagens (UM) do Exchange definido.</span><span class="sxs-lookup"><span data-stu-id="81b89-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="81b89-119">Quando alguém chama um número não atribuído, o Skype for Business Server pesquisa a tabela de números não atribuídos de cima para baixo e usa o primeiro intervalo correspondente.</span><span class="sxs-lookup"><span data-stu-id="81b89-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="81b89-120">Portanto, uma ação que você deseja executar como última alternativa deve ser especificada para o último intervalo na tabela.</span><span class="sxs-lookup"><span data-stu-id="81b89-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="81b89-121">Para usar o Painel de Controle do Skype for Business Server para configurar números de telefone não atribuídos</span><span class="sxs-lookup"><span data-stu-id="81b89-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="81b89-122">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="81b89-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="81b89-123">Para obter detalhes, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="81b89-123">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="81b89-124">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="81b89-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="81b89-125">Na barra de navegação esquerda, clique **em Recursos de** Voz e clique em Número Não **Atribuído.**</span><span class="sxs-lookup"><span data-stu-id="81b89-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="81b89-126">Na página **Número Não Atribuído,** faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="81b89-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="81b89-127">Para criar um novo intervalo de números, clique em **Novo.**</span><span class="sxs-lookup"><span data-stu-id="81b89-127">To create a new number range, click **New**.</span></span> <span data-ttu-id="81b89-128">Em **Nome**, digite um nome de identificação para esse intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="81b89-128">In **Name**, type an identifying name for this range of numbers.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="81b89-129">Depois de você comprometer o novo intervalo de números não atribuídos ao banco de dados, não será possível alterar esse nome.</span><span class="sxs-lookup"><span data-stu-id="81b89-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="81b89-130">Para modificar um intervalo de números existente, digite todo ou parte do nome do intervalo de números no campo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="81b89-130">To modify an existing number range, type all or part of the name of the number range in the search field.</span></span> <span data-ttu-id="81b89-131">Na lista resultante de intervalos de números, clique no nome que você deseja, clique em **Editar** e em **Mostrar detalhes.**</span><span class="sxs-lookup"><span data-stu-id="81b89-131">In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="81b89-132">No primeiro campo **Intervalo de números** digite o número inicial do intervalo, e no segundo campo **Intervalo de números** digite o número final.</span><span class="sxs-lookup"><span data-stu-id="81b89-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="81b89-133">O número inicial do intervalo deve ser menor ou igual ao número final.</span><span class="sxs-lookup"><span data-stu-id="81b89-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="81b89-134">Se o número inicial do intervalo ou o número final do intervalo incluir um número de extensão, os números inicial e final do intervalo precisarão incluir uma extensão e o número de extensão deverá ser o mesmo para os números inicial e final.</span><span class="sxs-lookup"><span data-stu-id="81b89-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="81b89-135">O número deve corresponder à expressão regular (tel:)?( \+ )? [1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?.</span><span class="sxs-lookup"><span data-stu-id="81b89-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="81b89-136">Isso significa que o número pode começar com a cadeia de caracteres tel: (se você não especificar essa cadeia de caracteres, ela será adicionada automaticamente para você), um sinal de mais (+) e um dígito de 1 a 9.</span><span class="sxs-lookup"><span data-stu-id="81b89-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="81b89-137">O número de telefone pode ter até 17 dígitos e pode ser seguido de um ramal no formato ;ext=, seguido do número do ramal.</span><span class="sxs-lookup"><span data-stu-id="81b89-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="81b89-138">Em **Serviço de anúncio**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="81b89-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="81b89-139">Clique em **Comunicado**.</span><span class="sxs-lookup"><span data-stu-id="81b89-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="81b89-140">Click **UM do Exchange**.</span><span class="sxs-lookup"><span data-stu-id="81b89-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="81b89-141">Se, na etapa prévia, você clicou em **Comunicado**, faça o seguinte</span><span class="sxs-lookup"><span data-stu-id="81b89-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="81b89-142">a.</span><span class="sxs-lookup"><span data-stu-id="81b89-142">a.</span></span> <span data-ttu-id="81b89-143">Em **FQDN do servidor de destino**, clique em **Selecionar**, clique no ID de serviço do serviço do Aplicativo que executa o aplicativo de Comunicado que manipulará as chamadas de entrada para esse intervalo de números não atribuídos e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="81b89-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="81b89-144">b.</span><span class="sxs-lookup"><span data-stu-id="81b89-144">b.</span></span> <span data-ttu-id="81b89-145">**Comunicado**, clique no comunicado que será reproduzido para esse intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="81b89-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="81b89-146">Se, na etapa prévia, você clicou em **UM do Exchange**, em **Número de telefone do Atendedor Automático**, clique em **Selecionar**, clique no número de telefone que será usado para esse intervalo de números não atribuídos e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="81b89-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="81b89-147">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="81b89-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="81b89-148">Na página **Número Não Atribuído,** certifique-se de que os intervalos de números não atribuídos sejam organizados na ordem que você deseja.</span><span class="sxs-lookup"><span data-stu-id="81b89-148">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want.</span></span> <span data-ttu-id="81b89-149">Para alterar a posição de um intervalo na tabela, clique em um ou mais nomes consecutivos na lista de intervalos e clique na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="81b89-149">To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="81b89-150">O Skype for Business Server pesquisa a tabela de números não atribuídos de cima para baixo e usa o primeiro intervalo que corresponde ao número não atribuído.</span><span class="sxs-lookup"><span data-stu-id="81b89-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="81b89-151">Se você tiver intervalos sobrepostos e um intervalo especificar uma ação de última instância, certifique-se de que o intervalo está na parte inferior da lista.</span><span class="sxs-lookup"><span data-stu-id="81b89-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="81b89-152">Quando você tiver os intervalos de números não atribuídos na ordem que deseja, clique em **Comprometer tudo.**</span><span class="sxs-lookup"><span data-stu-id="81b89-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="81b89-153">Para usar o Shell de Gerenciamento do Skype for Business Server para configurar números de telefone não atribuídos</span><span class="sxs-lookup"><span data-stu-id="81b89-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="81b89-154">Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários,** conforme descrito em Delegate Setup Permissions .</span><span class="sxs-lookup"><span data-stu-id="81b89-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="81b89-155">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="81b89-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="81b89-156">Use **New-CsUnassignedNumber** para criar um novo intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="81b89-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="81b89-157">Use **Set-CsUnassignedNumber** para modificar um intervalo de números não atribuídos existente.</span><span class="sxs-lookup"><span data-stu-id="81b89-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="81b89-158">Se você tiver intervalos sobrepostos e quiser que os intervalos sejam aplicados em uma ordem específica, inclua o parâmetro Priority.</span><span class="sxs-lookup"><span data-stu-id="81b89-158">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="81b89-159">O intervalo com a prioridade mais alta será aplicado à chamada.</span><span class="sxs-lookup"><span data-stu-id="81b89-159">The range with the highest priority will be applied to the call.</span></span> <span data-ttu-id="81b89-160">O valor 0 representa a prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="81b89-160">The value 0 represents the highest priority.</span></span>
  
    <span data-ttu-id="81b89-161">Na linha de comando, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="81b89-161">At the command line, do one of the following:</span></span>
    
   - <span data-ttu-id="81b89-162">Para criar um intervalo de números para um serviço de Comunicado, execute:</span><span class="sxs-lookup"><span data-stu-id="81b89-162">To create a number range for an Announcement service, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="81b89-163">Ou, para criar um intervalo de números para o Atendente Automático de UM do Exchange, execute:</span><span class="sxs-lookup"><span data-stu-id="81b89-163">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="81b89-164">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="81b89-164">For example:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="81b89-165">Ou</span><span class="sxs-lookup"><span data-stu-id="81b89-165">Or</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     <span data-ttu-id="81b89-166">O exemplo a seguir mostra como modificar os números em um intervalo de números não atribuídos existente:</span><span class="sxs-lookup"><span data-stu-id="81b89-166">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="81b89-167">Excluir um intervalo de números não assinados</span><span class="sxs-lookup"><span data-stu-id="81b89-167">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="81b89-168">Para usar o Painel de Controle do Skype for Business Server para excluir um intervalo de números não atribuídos</span><span class="sxs-lookup"><span data-stu-id="81b89-168">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="81b89-169">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="81b89-169">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="81b89-170">Para obter detalhes, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="81b89-170">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="81b89-171">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="81b89-171">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="81b89-172">Na barra de navegação à esquerda, clique em **Recursos de Voz** e em **Número Não Atribuído**.</span><span class="sxs-lookup"><span data-stu-id="81b89-172">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="81b89-173">Na página **Número Não Atribuído**, no campo de pesquisa, digite todo ou parte do nome do intervalo numérico não atribuído que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="81b89-173">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="81b89-174">Na lista de resultados de intervalos de número, clique no nome, clique em **Editar** e depois, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="81b89-174">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="81b89-175">Clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="81b89-175">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="81b89-176">Para usar o Shell de Gerenciamento do Skype for Business Server para excluir um intervalo de números não atribuídos</span><span class="sxs-lookup"><span data-stu-id="81b89-176">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="81b89-177">Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários,** conforme descrito em Delegate Setup Permissions .</span><span class="sxs-lookup"><span data-stu-id="81b89-177">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="81b89-178">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="81b89-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="81b89-179">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="81b89-179">At the command line, type:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="81b89-180">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="81b89-180">For example:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="81b89-181">Para obter detalhes sobre mais opções, [consulte Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="81b89-181">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="81b89-182">Confira também</span><span class="sxs-lookup"><span data-stu-id="81b89-182">See also</span></span>

[<span data-ttu-id="81b89-183">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="81b89-183">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="81b89-184">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="81b89-184">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="81b89-185">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="81b89-185">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
