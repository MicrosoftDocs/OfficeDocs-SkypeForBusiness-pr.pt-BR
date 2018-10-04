---
title: Mover um usuário único ao pool piloto
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode mover um usuário de seu pool herdado para seu Skype para pool de piloto Business Server 2019 usando Skype para painel de controle do Business Server 2019 ou Skype para Business Server 2019 Management Shell. No exemplo abaixo, na coluna pool registrador, pool01. contoso.NET é o pool herdado e seis desses usuários conectados a esse pool. Use os procedimentos a seguir para mover um usuário para sua Skype para pool de negócios Server 2019 usando Skype para painel de controle do Business Server 2019 e Skype do Shell de gerenciamento do servidor de negócios.
ms.openlocfilehash: 6742c5fc00c9d53030ac32ee698686bb8b11fa07
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372742"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="3aab8-105">Mover um usuário único ao pool piloto</span><span class="sxs-lookup"><span data-stu-id="3aab8-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="3aab8-106">Você pode mover um usuário de seu pool herdado para seu Skype para pool de piloto Business Server 2019 usando Skype para painel de controle do Business Server 2019 ou Skype para Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3aab8-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="3aab8-107">No exemplo abaixo, na coluna **pool de registradores** , **pool01. contoso.NET** é o pool herdado e seis desses usuários conectados a esse pool.</span><span class="sxs-lookup"><span data-stu-id="3aab8-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="3aab8-108">Use os procedimentos a seguir para mover um usuário para sua Skype para pool de negócios Server 2019 usando Skype para painel de controle do Business Server 2019 e Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="3aab8-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="3aab8-109">Para mover um usuário usando o Skype para o painel de controle do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="3aab8-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="3aab8-110">Faça logon no Servidor Front-end com uma conta que seja membro do grupo de RTCUniversalServerAdmins ou membro da função administrativa do CsAdministrator ou CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3aab8-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="3aab8-111">Abra o **Skype para painel de controle do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="3aab8-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="3aab8-112">Clique em **usuários**, clique em **Pesquisar**e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="3aab8-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="3aab8-113">Selecione um usuário que você deseja mover para o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="3aab8-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="3aab8-114">Neste exemplo, podemos moverá Sara Davis do usuário.</span><span class="sxs-lookup"><span data-stu-id="3aab8-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="3aab8-115">No menu **Ação**, selecione **Mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="3aab8-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="3aab8-116">Na lista suspensa, selecione o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="3aab8-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="3aab8-117">Clique em **ação**e, em seguida, clique em **mover usuários selecionados para o pool**.</span><span class="sxs-lookup"><span data-stu-id="3aab8-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="3aab8-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3aab8-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="3aab8-119">Verifique se a coluna **pool de registrador** para o usuário agora contém o Skype para Business Server 2019 pool, que indica que o usuário foi movido com êxito.</span><span class="sxs-lookup"><span data-stu-id="3aab8-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="3aab8-120">Para mover um usuário usando o Skype para o Shell de gerenciamento do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="3aab8-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="3aab8-121">Abra o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="3aab8-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="3aab8-122">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3aab8-122">At the command line, type the following:</span></span> 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="3aab8-123">Em seguida, na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3aab8-123">Next, at the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="3aab8-124">A identidade **RegistrarPool** agora aponta para o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="3aab8-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="3aab8-125">A presença dessa identidade confirma que o usuário foi movido com êxito.</span><span class="sxs-lookup"><span data-stu-id="3aab8-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="3aab8-126">Para obter detalhes sobre o cmdlet **Get-CsUser** , execute: **Get-Help Get-CsUser-detalhadas**</span><span class="sxs-lookup"><span data-stu-id="3aab8-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

