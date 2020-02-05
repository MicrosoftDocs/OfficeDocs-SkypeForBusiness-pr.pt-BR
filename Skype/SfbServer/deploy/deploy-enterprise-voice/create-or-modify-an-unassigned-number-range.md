---
title: Criar ou modificar um intervalo de números não atribuídos no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Criar, modificar ou excluir intervalos de números não atribuídos para o aplicativo de anúncio no Skype for Business Server Enterprise Voice. Isso afeta o modo como nas chamadas para números não atribuídos são administradas.
ms.openlocfilehash: d357a97bffda50d6d387ba40a12f62dacac5ce31
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767744"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a><span data-ttu-id="c9bda-104">Criar ou modificar um intervalo de números não atribuídos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c9bda-104">Create or modify an unassigned number range in Skype for Business Server</span></span>
 
<span data-ttu-id="c9bda-105">Criar, modificar ou excluir intervalos de números não atribuídos para o aplicativo de anúncio no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c9bda-105">Create, modify or delete unassigned number ranges for Announcement application in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="c9bda-106">Isso afeta o modo como nas chamadas para números não atribuídos são administradas.</span><span class="sxs-lookup"><span data-stu-id="c9bda-106">This affects how calls to unassigned numbers are handled.</span></span>
  
<span data-ttu-id="c9bda-107">O Skype for Business Server permite que você diga o que acontece com as chamadas recebidas para números de telefone válidos para sua organização, mas que não estão atribuídas a um usuário ou a um telefone.</span><span class="sxs-lookup"><span data-stu-id="c9bda-107">Skype for Business Server enables you to say what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="c9bda-108">Para lidar com essas chamadas, configure uma tabela de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="c9bda-108">To handle such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="c9bda-109">Você pode usar a tabela para direcionar as chamadas para um aplicativo de anúncio ou para um servidor de UM Exchange.</span><span class="sxs-lookup"><span data-stu-id="c9bda-109">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>
  
<span data-ttu-id="c9bda-p104">O modo como você configura a tabela de números não atribuída depende de como você deseja usá-la. É possível configurar a tabela com todas as extensões válidas para sua organização, com apenas extensões não atribuídas ou com uma combinação de ambos os tipos de números. A tabela de números não atribuída pode incluir números atribuídos e não atribuídos, mas é chamada somente quando um chamador disca um número que não está atribuído no momento. Se você incluir todas as extensões válidas na tabela de números não atribuída, você poderá especificar a ação que ocorre sempre que alguém deixa sua organização, sem a necessidade de reconfigurar a tabela. Se você incluir extensões não atribuídas na tabela, poderá personalizar a ação que ocorre para números específicos. Por exemplo, se você alterar a extensão para seu atendimento ao cliente, poderá incluir o número antigo de atendimento ao cliente na tabela, e atribuí-lo a um anúncio que fornece o novo número.</span><span class="sxs-lookup"><span data-stu-id="c9bda-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>
  
## <a name="configure-unassigned-phone-numbers"></a><span data-ttu-id="c9bda-116">Configurar números de telefone não atribuídos</span><span class="sxs-lookup"><span data-stu-id="c9bda-116">Configure unassigned phone numbers</span></span>

<span data-ttu-id="c9bda-117">Use um dos procedimentos a seguir para configurar intervalos de números não atribuídos para o aplicativo de anúncio.</span><span class="sxs-lookup"><span data-stu-id="c9bda-117">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c9bda-118">Antes de configurar a tabela numérica não atribuída, seu sistema já deve ter comunicados definidos ou uma configuração de atendedor automático de Unificação de mensagens do Exchange (um).</span><span class="sxs-lookup"><span data-stu-id="c9bda-118">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span> 
  
> [!TIP]
> <span data-ttu-id="c9bda-119">Quando alguém chama um número não atribuído, o Skype for Business Server procura a tabela número não atribuído da parte superior para a inferior e usa o primeiro intervalo correspondente.</span><span class="sxs-lookup"><span data-stu-id="c9bda-119">When someone calls an unassigned number, Skype for Business Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="c9bda-120">Portanto, uma ação que você deseja executar como última alternativa deve ser especificada para o último intervalo na tabela.</span><span class="sxs-lookup"><span data-stu-id="c9bda-120">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="c9bda-121">Para usar o painel de controle do Skype for Business Server para configurar números de telefone não atribuídos</span><span class="sxs-lookup"><span data-stu-id="c9bda-121">To use Skype for Business Server Control Panel to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="c9bda-p106">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-p106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="c9bda-124">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9bda-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c9bda-125">Na barra de navegação à esquerda, clique em **Recursos de Voz** e depois, em **Número Não Atribuído**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-125">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="c9bda-126">Na página **Números não atribuídos**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="c9bda-126">On the **Unassigned Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="c9bda-p107">Para criar um novo intervalo de números, clique em **Novo**. Em **Nome**, digite o nome que identifica este intervalo de números.</span><span class="sxs-lookup"><span data-stu-id="c9bda-p107">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="c9bda-129">Depois de confirmar o novo intervalo de números não atribuídos para o banco de dados, não é possível alterar este nome.</span><span class="sxs-lookup"><span data-stu-id="c9bda-129">After you commit the new unassigned number range to the database, you cannot change this name.</span></span> 
  
   - <span data-ttu-id="c9bda-p108">Para modificar um intervalo de números existente, digite todo o nome do intervalo de órbita, ou parte dele, no campo de pesquisa. Na lista de resultados de intervalos de número, clique no nome desejado, clique em **Editar** e depois, clique em **Exibir Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-p108">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c9bda-132">No primeiro campo **Intervalo Numérico**, digite o número inicial do intervalo e no segundo campo **Intervalo Numérico** digite o número final do intervalo.</span><span class="sxs-lookup"><span data-stu-id="c9bda-132">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
   - <span data-ttu-id="c9bda-133">O número inicial do intervalo deve ser menor ou igual ao número final.</span><span class="sxs-lookup"><span data-stu-id="c9bda-133">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="c9bda-134">Se o número inicial ou o número final do intervalo incluir um número de ramal, ambos os números devem incluir um ramal, que deve ser o mesmo para ambos.</span><span class="sxs-lookup"><span data-stu-id="c9bda-134">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
   - <span data-ttu-id="c9bda-135">O número deve corresponder à expressão regular (Tel:)? ( \+)? [1-9] \d{0,17}(; Ext = [1-9] \d{0,9})?.</span><span class="sxs-lookup"><span data-stu-id="c9bda-135">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="c9bda-136">Isso significa que o número pode começar com a cadeia de caracteres Tel: (se você não especificar essa cadeia de caracteres, ela será adicionada automaticamente para você), um sinal de adição (+) e um dígito de 1 a 9.</span><span class="sxs-lookup"><span data-stu-id="c9bda-136">This means the number may begin with the string tel: (if you don't specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="c9bda-137">O número de telefone pode ter até 17 dígitos e pode ser seguido de um ramal no formato ;ext= seguido do número do ramal.</span><span class="sxs-lookup"><span data-stu-id="c9bda-137">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
6. <span data-ttu-id="c9bda-138">Em **Serviço de Comunicado**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="c9bda-138">In **Announcement service**, do one of the following:</span></span> 
    
   - <span data-ttu-id="c9bda-139">Clique em **Comunicado**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-139">Click **Announcement**.</span></span>
    
   - <span data-ttu-id="c9bda-140">Clique em **UM do Exchange**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-140">Click **Exchange UM**.</span></span>
    
7. <span data-ttu-id="c9bda-141">Se, na etapa anterior, você clicou em **Comunicado**, execute:</span><span class="sxs-lookup"><span data-stu-id="c9bda-141">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    <span data-ttu-id="c9bda-142">a.</span><span class="sxs-lookup"><span data-stu-id="c9bda-142">a.</span></span> <span data-ttu-id="c9bda-143">Em **FQDN do servidor de destino**, clique em **selecionar**, clique na ID de serviço do serviço de aplicativo que executa o aplicativo de anúncio que manipulará as chamadas de entrada para esse intervalo de números não atribuídos e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-143">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    <span data-ttu-id="c9bda-144">b.</span><span class="sxs-lookup"><span data-stu-id="c9bda-144">b.</span></span> <span data-ttu-id="c9bda-145">Em **Comunicado**, clique no comunicado a ser reproduzido para este intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="c9bda-145">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>
    
8. <span data-ttu-id="c9bda-146">Se, na etapa anterior, você clicou em **UM do Exchange**, sob **Número de telefone do Atendedor Automático**, clique em **Selecionar**, clique no número de telefone a ser usado para este intervalo de números não atribuídos e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-146">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>
    
9. <span data-ttu-id="c9bda-147">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-147">Click **OK**.</span></span>
    
10. <span data-ttu-id="c9bda-p112">Na página **Número Não Atribuído**, certifique-se de que os intervalos numéricos não atribuídos estejam organizados da ordem que você deseja. Para alterar a posição do intervalo na tabela, clique em um ou mais nomes consecutivos na lista de intervalos e clique na seta para cima ou para baixo.</span><span class="sxs-lookup"><span data-stu-id="c9bda-p112">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c9bda-150">O Skype for Business Server pesquisa na tabela de números não atribuídos do início ao fim e usa o primeiro intervalo que corresponde ao número não atribuído.</span><span class="sxs-lookup"><span data-stu-id="c9bda-150">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="c9bda-151">Se você tem intervalos sobrepostos e um intervalo que especifica uma última ação de reclassificação, certifique-se de que o intervalo esteja no final da lista.</span><span class="sxs-lookup"><span data-stu-id="c9bda-151">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
11. <span data-ttu-id="c9bda-152">Quando os intervalos numéricos não atribuídos estiverem na ordem desejada, clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-152">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="c9bda-153">Para usar o Shell de gerenciamento do Skype for Business Server para configurar números de telefone não atribuídos</span><span class="sxs-lookup"><span data-stu-id="c9bda-153">To use Skype for Business Server Management Shell to configure unassigned phone numbers</span></span>

1. <span data-ttu-id="c9bda-154">Faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **permissões de configuração do representante**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-154">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="c9bda-155">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-155">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c9bda-156">Use **New-CsUnassignedNumber** para criar um intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="c9bda-156">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="c9bda-157">Use **Set-CsUnassignedNumber** para modificar um intervalo de números não atribuídos existente.</span><span class="sxs-lookup"><span data-stu-id="c9bda-157">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c9bda-158">Se você tiver intervalos sobrepostos e desejar que os intervalos sejam aplicados em uma ordem específica, inclua o parâmetro Prioridade.</span><span class="sxs-lookup"><span data-stu-id="c9bda-158">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="c9bda-159">O intervalo com a maior prioridade será aplicado à chamada.</span><span class="sxs-lookup"><span data-stu-id="c9bda-159">The range with the highest priority will be applied to the call.</span></span> <span data-ttu-id="c9bda-160">O valor 0 representa a prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="c9bda-160">The value 0 represents the highest priority.</span></span>
  
    <span data-ttu-id="c9bda-161">No linha de comando, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="c9bda-161">At the command line, do one of the following:</span></span>
    
   - <span data-ttu-id="c9bda-162">Para criar um intervalo numérico para um serviço de Comunicado, execute:</span><span class="sxs-lookup"><span data-stu-id="c9bda-162">To create a number range for an Announcement service, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - <span data-ttu-id="c9bda-163">Ou para criar um intervalo numérico para Atendedor Automático do UM do Exchange, execute:</span><span class="sxs-lookup"><span data-stu-id="c9bda-163">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     <span data-ttu-id="c9bda-164">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9bda-164">For example:</span></span>
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     <span data-ttu-id="c9bda-165">Ou</span><span class="sxs-lookup"><span data-stu-id="c9bda-165">Or</span></span>
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     <span data-ttu-id="c9bda-166">O exemplo a seguir mostra como modificar os números em um intervalo numérico não atribuído existente.</span><span class="sxs-lookup"><span data-stu-id="c9bda-166">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a><span data-ttu-id="c9bda-167">Excluir um intervalo de números não atribuídos</span><span class="sxs-lookup"><span data-stu-id="c9bda-167">Delete an unnasigned number range</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a><span data-ttu-id="c9bda-168">Para usar o painel de controle do Skype for Business Server para excluir um intervalo numérico não atribuído</span><span class="sxs-lookup"><span data-stu-id="c9bda-168">To use Skype for Business Server Control Panel to delete an unassigned number range</span></span>

1.  <span data-ttu-id="c9bda-p116">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-p116">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="c9bda-171">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9bda-171">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c9bda-172">Na barra de navegação à esquerda, clique em **Recursos de Voz** e depois, em **Número Não Atribuído**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-172">In the left navigation bar, click **Voice Features** and then click **Unassigned Number**.</span></span>
    
4. <span data-ttu-id="c9bda-173">Na página **Número Não Atribuído**, no campo de pesquisa, digite todo ou parte do nome do intervalo numérico não atribuído que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="c9bda-173">On the **Unassigned Number** page, in the search field, type all or part of the name of the unassigned number range you want to delete.</span></span>
    
5. <span data-ttu-id="c9bda-174">Na lista de resultados de intervalos de número, clique no nome, clique em **Editar** e depois, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-174">In the resulting list of number ranges, click the name, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="c9bda-175">Clique em **Confirmar tudo**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-175">Click **Commit all**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a><span data-ttu-id="c9bda-176">Para usar o Shell de gerenciamento do Skype for Business Server para excluir um intervalo de números não atribuídos</span><span class="sxs-lookup"><span data-stu-id="c9bda-176">To use Skype for Business Server Management Shell to delete an unassigned number range</span></span>

1. <span data-ttu-id="c9bda-177">Faça logon no computador em que o Shell de gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **permissões de configuração do representante**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-177">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="c9bda-178">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="c9bda-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c9bda-179">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="c9bda-179">At the command line, type:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    <span data-ttu-id="c9bda-180">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9bda-180">For example:</span></span>
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > <span data-ttu-id="c9bda-181">Para obter detalhes sobre mais opções, consulte [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c9bda-181">For details about more options, see [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c9bda-182">Confira também</span><span class="sxs-lookup"><span data-stu-id="c9bda-182">See also</span></span>

[<span data-ttu-id="c9bda-183">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="c9bda-183">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="c9bda-184">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="c9bda-184">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[<span data-ttu-id="c9bda-185">Get-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="c9bda-185">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
