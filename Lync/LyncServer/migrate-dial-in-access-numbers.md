---
title: Migrar os números de acesso discado
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
ms.openlocfilehash: 383fed15e2b67013ddd85356eb141a4c5dcf64e6
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="a387b-102">Migrar os números de acesso discado</span><span class="sxs-lookup"><span data-stu-id="a387b-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a387b-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="a387b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="a387b-104">Migrar números de acesso de discagem do Lync Server 2010 para o Lync Server 2013 requer a execução do cmdlet **move-CsApplicationEndpoint** para migrar os objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="a387b-104">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="a387b-105">Durante o período de coexistência do Lync Server 2010 e do Lync Server 2013, os números de acesso discado que você criou no Lync Server 2013 se comportam de forma semelhante aos números de acesso de discagem que você cria no Lync Server 2010, conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="a387b-105">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="a387b-106">Os números de acesso de discagem criados no Lync Server 2010, mas movidos para o Lync Server 2013 ou criados no Lync Server 2013 antes, durante ou após a migração têm as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="a387b-106">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="a387b-107">Não aparecem nos convites de reunião do Office Communications Server 2007 R2 e na página número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="a387b-107">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="a387b-108">Aparecem nos convites de reunião do Lync Server 2010 e na página número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="a387b-108">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="a387b-109">Aparecem nos convites de reunião do Lync Server 2013 e na página número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="a387b-109">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="a387b-110">Não podem ser exibidos ou modificados na ferramenta administrativa do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a387b-110">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="a387b-111">Pode ser exibido e modificado no painel de controle do Lync Server 2010 e no Shell de gerenciamento do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a387b-111">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="a387b-112">Pode ser exibido e modificado no painel de controle do Lync Server 2013 e no Shell de gerenciamento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a387b-112">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="a387b-113">Podem ser seqüenciados novamente dentro da região usando o cmdlet Set-CsDialinConferencingAccessNumber com o parâmetro Priority.</span><span class="sxs-lookup"><span data-stu-id="a387b-113">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="a387b-114">Você deve concluir a migração dos números de acesso de discagem que apontam para um pool do Lync Server 2010 antes de encerrar o pool do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a387b-114">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool.</span></span> <span data-ttu-id="a387b-115">Se você não concluir a migração do número de acesso de discagem, conforme descrito no procedimento a seguir, as chamadas de entrada para os números de acesso falharão.</span><span class="sxs-lookup"><span data-stu-id="a387b-115">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a387b-116">Você deve executar esse procedimento antes de encerrar o pool do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a387b-116">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a387b-117">Recomendamos que você mova os números de acesso de discagem quando o uso da rede estiver baixo, caso haja uma breve interrupção no serviço.</span><span class="sxs-lookup"><span data-stu-id="a387b-117">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="a387b-118">**Para identificar e mover os números de acesso de discagem**</span><span class="sxs-lookup"><span data-stu-id="a387b-118">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="a387b-119">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a387b-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a387b-120">Para mover cada número de acesso de discagem para um pool hospedado no Lync Server 2013, na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="a387b-120">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="a387b-121">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a387b-121">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="a387b-122">Na barra de navegação esquerda, clique em **Conferência**.</span><span class="sxs-lookup"><span data-stu-id="a387b-122">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="a387b-123">Clique na guia **número de acesso de discagem** .</span><span class="sxs-lookup"><span data-stu-id="a387b-123">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="a387b-124">Verifique se os números de acesso de discagem permanecem para o pool do Lync Server 2010 do qual você está migrando.</span><span class="sxs-lookup"><span data-stu-id="a387b-124">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a387b-125">Quando todos os números de acesso de discagem apontarem para o pool do Lync Server 2013, você poderá encerrar o pool do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a387b-125">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="a387b-126">**Verificar a migração do número de acesso de discagem usando o painel de controle do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="a387b-126">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="a387b-127">A partir de uma conta de usuário atribuída à função **CsUserAdministrator** ou à função **CsAdministrator** , faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a387b-127">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a387b-128">Abra o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a387b-128">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="a387b-129">Na barra de navegação esquerda, clique em **Conferência**.</span><span class="sxs-lookup"><span data-stu-id="a387b-129">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="a387b-130">Clique na guia **número de acesso de discagem** .</span><span class="sxs-lookup"><span data-stu-id="a387b-130">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="a387b-131">Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a387b-131">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="a387b-132">**Verificar a migração do número de acesso de discagem usando o Shell de gerenciamento do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="a387b-132">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="a387b-133">Abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a387b-133">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="a387b-134">Para retornar todos os números de acesso de conferência discada migrados, a partir da linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="a387b-134">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="a387b-135">Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a387b-135">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

