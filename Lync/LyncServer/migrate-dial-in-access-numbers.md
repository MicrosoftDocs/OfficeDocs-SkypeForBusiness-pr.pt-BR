---
title: Migrar os números de acesso discado
description: Migrar números de acesso de discagem.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2c8bd34a30bc4b3f8999144cd84a1eee62e2ab1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579317"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="df94f-103">Migrar os números de acesso discado</span><span class="sxs-lookup"><span data-stu-id="df94f-103">Migrate dial-in access numbers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df94f-104">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="df94f-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="df94f-105">Migrar números de acesso de discagem do Lync Server 2010 para o Lync Server 2013 requer a execução do cmdlet **move-CsApplicationEndpoint** para migrar os objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="df94f-105">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="df94f-106">Durante o período de coexistência do Lync Server 2010 e do Lync Server 2013, os números de acesso discado que você criou no Lync Server 2013 se comportam de forma semelhante aos números de acesso de discagem que você cria no Lync Server 2010, conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="df94f-106">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="df94f-107">Os números de acesso de discagem criados no Lync Server 2010, mas movidos para o Lync Server 2013 ou criados no Lync Server 2013 antes, durante ou após a migração têm as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="df94f-107">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="df94f-108">Não aparecem nos convites de reunião do Office Communications Server 2007 R2 e na página número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="df94f-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="df94f-109">Aparecem nos convites de reunião do Lync Server 2010 e na página número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="df94f-109">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="df94f-110">Aparecem nos convites de reunião do Lync Server 2013 e na página número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="df94f-110">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="df94f-111">Não podem ser exibidos ou modificados na ferramenta administrativa do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="df94f-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="df94f-112">Pode ser exibido e modificado no painel de controle do Lync Server 2010 e no Shell de gerenciamento do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="df94f-112">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="df94f-113">Pode ser exibido e modificado no painel de controle do Lync Server 2013 e no Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df94f-113">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="df94f-114">Podem ser seqüenciados novamente dentro da região usando o cmdlet Set-CsDialinConferencingAccessNumber com o parâmetro Priority.</span><span class="sxs-lookup"><span data-stu-id="df94f-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="df94f-115">Você deve concluir a migração dos números de acesso de discagem que apontam para um pool do Lync Server 2010 antes de encerrar o pool do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="df94f-115">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool.</span></span> <span data-ttu-id="df94f-116">Se você não concluir a migração do número de acesso de discagem, conforme descrito no procedimento a seguir, as chamadas de entrada para os números de acesso falharão.</span><span class="sxs-lookup"><span data-stu-id="df94f-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="df94f-117">Você deve executar esse procedimento antes de encerrar o pool do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="df94f-117">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="df94f-118">Recomendamos que você mova os números de acesso de discagem quando o uso da rede estiver baixo, caso haja uma breve interrupção no serviço.</span><span class="sxs-lookup"><span data-stu-id="df94f-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="df94f-119">**Para identificar e mover os números de acesso de discagem**</span><span class="sxs-lookup"><span data-stu-id="df94f-119">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="df94f-120">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="df94f-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="df94f-121">Para mover cada número de acesso de discagem para um pool hospedado no Lync Server 2013, na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="df94f-121">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="df94f-122">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df94f-122">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="df94f-123">Na barra de navegação esquerda, clique em **Conferência**.</span><span class="sxs-lookup"><span data-stu-id="df94f-123">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="df94f-124">Clique na guia **número de acesso de discagem** .</span><span class="sxs-lookup"><span data-stu-id="df94f-124">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="df94f-125">Verifique se os números de acesso de discagem permanecem para o pool do Lync Server 2010 do qual você está migrando.</span><span class="sxs-lookup"><span data-stu-id="df94f-125">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="df94f-126">Quando todos os números de acesso de discagem apontarem para o pool do Lync Server 2013, você poderá encerrar o pool do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="df94f-126">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="df94f-127">**Verificar a migração do número de acesso de discagem usando o painel de controle do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="df94f-127">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="df94f-128">A partir de uma conta de usuário atribuída à função **CsUserAdministrator** ou à função **CsAdministrator** , faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="df94f-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="df94f-129">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df94f-129">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="df94f-130">Na barra de navegação esquerda, clique em **Conferência**.</span><span class="sxs-lookup"><span data-stu-id="df94f-130">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="df94f-131">Clique na guia **número de acesso de discagem** .</span><span class="sxs-lookup"><span data-stu-id="df94f-131">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="df94f-132">Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df94f-132">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="df94f-133">**Verificar a migração do número de acesso de discagem usando o Shell de gerenciamento do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="df94f-133">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="df94f-134">Abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="df94f-134">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="df94f-135">Para retornar todos os números de acesso de conferência discada migrados, a partir da linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="df94f-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="df94f-136">Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="df94f-136">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

