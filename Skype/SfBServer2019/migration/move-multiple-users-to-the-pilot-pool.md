---
title: Mover vários usuários para o pool piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você pode mover vários usuários do seu pool herdado para seu pool piloto do Skype for Business Server 2019 usando o Painel de Controle do Skype for Business Server 2019 ou o Shell de Gerenciamento do Skype for Business Server 2019.
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753423"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="a5c1a-103">Mover vários usuários para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="a5c1a-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="a5c1a-104">Você pode mover vários usuários do seu pool herdado para seu pool piloto do Skype for Business Server 2019 usando o Painel de Controle do Skype for Business Server 2019 ou o Shell de Gerenciamento do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="a5c1a-105">**Neste artigo**</span><span class="sxs-lookup"><span data-stu-id="a5c1a-105">**In this article**</span></span>
  
[<span data-ttu-id="a5c1a-106">Para mover vários usuários usando o Painel de Controle do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5c1a-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="a5c1a-107">Para mover vários usuários usando o Shell de Gerenciamento do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5c1a-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="a5c1a-108">Para mover todos os usuários ao mesmo tempo usando o Shell de Gerenciamento do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5c1a-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="a5c1a-109">Para mover vários usuários usando o Painel de Controle do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5c1a-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="a5c1a-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="a5c1a-110"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="a5c1a-111">Abra o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="a5c1a-112">Clique **em Usuários,** em **Pesquisar** e em **Encontrar.**</span><span class="sxs-lookup"><span data-stu-id="a5c1a-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="a5c1a-113">Selecione dois usuários que você deseja mover para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a5c1a-114">Neste exemplo, vamos mover os usuários Chen Yang e Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Mover usuários para um pool de registro específico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="a5c1a-116">No menu **Ação**, selecione **Mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="a5c1a-117">Na lista drop-down, selecione o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="a5c1a-118">Clique em **Ação** e em **Mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="a5c1a-119">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-119">Click **OK**.</span></span>
    
     ![Mover Usuários, caixa de diálogo do pool do registrador de destino](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="a5c1a-121">Verifique se a **coluna do pool** registrador para os usuários agora contém o pool do Skype for Business Server 2019, que indica que os usuários foram movidos com êxito.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="a5c1a-122">Para mover vários usuários usando o Shell de Gerenciamento do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5c1a-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="a5c1a-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="a5c1a-123"><a name="sectionSection1"> </a></span></span>

1. <span data-ttu-id="a5c1a-124">Abra o Shell de Gerenciamento do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="a5c1a-125">Na linha de comando, digite o seguinte e substitua **User1** e **User2** por nomes de usuário específicos que você deseja mover e substitua pool_FQDN pelo nome do pool de destino. </span><span class="sxs-lookup"><span data-stu-id="a5c1a-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="a5c1a-126">Neste exemplo, vamos mover os usuários Hao Chen e Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Exemplo de cmdlet de Get-CsUser PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="a5c1a-128">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a5c1a-128">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="a5c1a-129">A identidade do **Pool de registradores** deve apontar agora para o pool especificado como **pool_FQDN** na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="a5c1a-130">A presença dessa identidade confirma que o usuário foi movido com sucesso.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="a5c1a-131">Repita a etapa para verificar se **o Usuário2** foi movido.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Saída do cmdlet -Identity Get-UsUser PowerShell](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="a5c1a-133">Para mover todos os usuários ao mesmo tempo usando o Shell de Gerenciamento do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="a5c1a-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="a5c1a-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="a5c1a-134"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="a5c1a-135">Neste exemplo, todos os usuários foram retornados ao pool herddo (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="a5c1a-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="a5c1a-136">Usando o Shell de Gerenciamento do Skype for Business Server 2019, moveremos todos os usuários ao mesmo tempo para o pool do Skype for Business Server 2019 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="a5c1a-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="a5c1a-137">Abra o Shell de Gerenciamento do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="a5c1a-138">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a5c1a-138">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet do PowerShell e resultados no Shell de Gerenciamento](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="a5c1a-140">Execute **Get-CsUser** para um dos usuários piloto.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="a5c1a-141">A **identidade do Pool** de Registradores Agora aponta para o pool que você pool_FQDN na etapa anterior. </span><span class="sxs-lookup"><span data-stu-id="a5c1a-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="a5c1a-142">A presença dessa identidade confirma que o usuário foi movido com sucesso.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="a5c1a-143">Além disso, podemos exibir a lista de usuários no Painel de Controle do Skype for Business Server 2019 e verificar se o valor do Pool de Registradores Agora aponta para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a5c1a-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Lista de usuários do Painel de Controle do Skype for Business Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

