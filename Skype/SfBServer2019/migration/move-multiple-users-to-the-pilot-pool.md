---
title: Mover vários usuários para o pool piloto
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode mover vários usuários do seu pool herdado para seu Skype para pool de piloto Business Server 2019 usando Skype para painel de controle do Business Server 2019 ou Skype para Business Server 2019 Management Shell.
ms.openlocfilehash: 3b01613e16e41ed2ee7aac7bc6c443e19db933c2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372506"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="e3b01-103">Mover vários usuários para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="e3b01-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="e3b01-104">Você pode mover vários usuários do seu pool herdado para seu Skype para pool de piloto Business Server 2019 usando Skype para painel de controle do Business Server 2019 ou Skype para Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e3b01-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="e3b01-105">**Neste artigo**</span><span class="sxs-lookup"><span data-stu-id="e3b01-105">**In this article**</span></span>
  
[<span data-ttu-id="e3b01-106">Para mover vários usuários usando o Skype para o painel de controle do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e3b01-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="e3b01-107">Para mover vários usuários usando o Skype para o Shell de gerenciamento do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e3b01-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="e3b01-108">Para mover todos os usuários ao mesmo tempo usando o Skype para o Shell de gerenciamento do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e3b01-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="e3b01-109">Para mover vários usuários usando o Skype para o painel de controle do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e3b01-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="e3b01-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="e3b01-110"></span></span>

1. <span data-ttu-id="e3b01-111">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="e3b01-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="e3b01-112">Clique em **usuários**, clique em **Pesquisar**e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="e3b01-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="e3b01-113">Selecione os dois usuários que você deseja mover para o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="e3b01-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="e3b01-114">Neste exemplo, podemos moverá usuários Chen Yang e Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="e3b01-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Mover usuários para o pool de registrador específico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="e3b01-116">No menu **ação** , selecione **mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="e3b01-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="e3b01-117">Na lista suspensa, selecione o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="e3b01-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="e3b01-118">Clique em **ação**e, em seguida, clique em **mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="e3b01-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="e3b01-119">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3b01-119">Click **OK**.</span></span>
    
     ![Mover usuários, caixa de diálogo de pool de registradores de destino](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="e3b01-121">Verifique se a coluna **pool de registrador** para os usuários agora contém o Skype para Business Server 2019 pool, que indica se os usuários foram movidos com êxito.</span><span class="sxs-lookup"><span data-stu-id="e3b01-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="e3b01-122">Para mover vários usuários usando o Skype para o Shell de gerenciamento do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e3b01-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="e3b01-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="e3b01-123"></span></span>

1. <span data-ttu-id="e3b01-124">Abra o Skype do Shell de gerenciamento do servidor 2019 de negócios.</span><span class="sxs-lookup"><span data-stu-id="e3b01-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="e3b01-125">Na linha de comando, digite o seguinte e substitua **User1** e **User2** nomes de usuário específicos que você deseja mover e substitua **pool_FQDN** pelo nome do pool de destino.</span><span class="sxs-lookup"><span data-stu-id="e3b01-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="e3b01-126">Neste exemplo, podemos moverá usuários Hao Chen e Katie Jordânia.</span><span class="sxs-lookup"><span data-stu-id="e3b01-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Exemplo do cmdlet Get-CsUser do PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="e3b01-128">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e3b01-128">At the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="e3b01-129">A identidade do **Pool de registrador** agora deve apontar para o pool que você especificou como **pool_FQDN** na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="e3b01-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="e3b01-130">A presença dessa identidade confirma que o usuário foi movido com êxito.</span><span class="sxs-lookup"><span data-stu-id="e3b01-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="e3b01-131">Repita as etapas para verificar se o **Usuário2** foram movidos.</span><span class="sxs-lookup"><span data-stu-id="e3b01-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Saída do PowerShell Get-UsUser-Identity cmdlet](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="e3b01-133">Para mover todos os usuários ao mesmo tempo usando o Skype para o Shell de gerenciamento do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="e3b01-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="e3b01-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="e3b01-134"></span></span>

<span data-ttu-id="e3b01-135">Neste exemplo, todos os usuários foram retornados ao pool herdado (pool01. contoso.NET).</span><span class="sxs-lookup"><span data-stu-id="e3b01-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="e3b01-136">Usando o Skype para o Shell de gerenciamento do Business Server 2019, podemos moverá todos os usuários ao mesmo tempo para o Skype para Business Server 2019 pool (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="e3b01-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="e3b01-137">Abra o Skype do Shell de gerenciamento do servidor 2019 de negócios.</span><span class="sxs-lookup"><span data-stu-id="e3b01-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="e3b01-138">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e3b01-138">At the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet do PowerShell e resultados no Shell de gerenciamento](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="e3b01-140">Execute **Get-CsUser** para um dos usuários piloto.</span><span class="sxs-lookup"><span data-stu-id="e3b01-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="e3b01-141">A identidade do **Pool de registrador** para cada usuário agora aponta para o pool que você especificou como **pool_FQDN** na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="e3b01-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="e3b01-142">A presença dessa identidade confirma que o usuário foi movido com êxito.</span><span class="sxs-lookup"><span data-stu-id="e3b01-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="e3b01-143">Além disso, podemos exibir a lista de usuários no Skype para painel de controle do Business Server 2019 e verificar que o valor de Pool de registradores aponta agora para o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="e3b01-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Skype para a lista de usuários do painel de controle do Business Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

