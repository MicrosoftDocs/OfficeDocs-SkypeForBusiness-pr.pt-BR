---
title: Mover um único usuário para o pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode mover um usuário do seu pool herdado para o pool piloto do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server 2019 ou o Shell de gerenciamento do Skype for Business Server 2019. No exemplo a seguir, na coluna pool de registradores, pool01.contoso.net é o pool herdado e todos os seis usuários estão conectados a esse pool. Use os procedimentos a seguir para mover um usuário para o pool do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server 2019 e o Shell de gerenciamento do Skype for Business Server.
ms.openlocfilehash: 23ce56f8bcf759aeeaa9e9a9b64820958c656c6a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298131"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="cff87-105">Mover um único usuário para o pool piloto</span><span class="sxs-lookup"><span data-stu-id="cff87-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="cff87-106">Você pode mover um usuário do seu pool herdado para o pool piloto do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server 2019 ou o Shell de gerenciamento do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cff87-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="cff87-107">No exemplo a seguir, na coluna **pool** de registradores, **pool01.contoso.net** é o pool herdado e todos os seis usuários estão conectados a esse pool.</span><span class="sxs-lookup"><span data-stu-id="cff87-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="cff87-108">Use os procedimentos a seguir para mover um usuário para o pool do Skype for Business Server 2019 usando o painel de controle do Skype for Business Server 2019 e o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cff87-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="cff87-109">Para mover um usuário usando o painel de controle do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="cff87-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="cff87-110">Faça logon no Servidor Front-end com uma conta que seja membro do grupo de RTCUniversalServerAdmins ou membro da função administrativa do CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cff87-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="cff87-111">Abra o **painel de controle do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="cff87-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="cff87-112">Clique em **usuários**, clique em **Pesquisar**e, em seguida, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="cff87-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="cff87-113">Selecione o usuário que você deseja mover para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cff87-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="cff87-114">Neste exemplo, moveremos a usuária Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="cff87-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="cff87-115">No menu **Ação**, selecione **Mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="cff87-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="cff87-116">Na lista suspensa, selecione o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cff87-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="cff87-117">Clique em **ação**e, em seguida, clique em **mover os usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="cff87-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="cff87-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="cff87-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="cff87-119">Verifique se a coluna do **pool** de registradores do usuário agora contém o pool do Skype for Business Server 2019, que indica que o usuário foi movido com êxito.</span><span class="sxs-lookup"><span data-stu-id="cff87-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="cff87-120">Para mover um usuário usando o Shell de gerenciamento do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="cff87-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="cff87-121">Abra o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cff87-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="cff87-122">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cff87-122">At the command line, type the following:</span></span> 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="cff87-123">Em seguida, na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cff87-123">Next, at the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="cff87-124">A identidade **RegistrarPool** agora aponta para o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cff87-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="cff87-125">A presença dessa identidade confirma que o usuário foi movido com êxito.</span><span class="sxs-lookup"><span data-stu-id="cff87-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="cff87-126">Para obter detalhes sobre o cmdlet **Get-CsUser** , execute: **Get-Help Get-CsUser-detailed**</span><span class="sxs-lookup"><span data-stu-id="cff87-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

