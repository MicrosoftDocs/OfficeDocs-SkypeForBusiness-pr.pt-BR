---
title: Migrar números de acesso de discagem
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Migrar números de acesso de discagem para o Skype for Business Server 2019 requer a execução do cmdlet Move-CsApplicationEndpoint para migrar os objetos de contato. Durante a instalação herdada e o período de coexistência do Skype for Business Server 2019, os números de acesso discado que você criou no Skype for Business Server 2019 se comportam de forma semelhante aos números de acesso de discagem que você cria na instalação herdada, conforme descrito neste seção.
ms.openlocfilehash: 83cf8b75bcf9a8d4794ae0f95962f3627d8592c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280809"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="40f87-104">Migrar números de acesso de discagem</span><span class="sxs-lookup"><span data-stu-id="40f87-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="40f87-105">Migrar números de acesso de discagem para o Skype for Business Server 2019 requer a execução do cmdlet **move-CsApplicationEndpoint** para migrar os objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="40f87-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="40f87-106">Durante a instalação herdada e o período de coexistência do Skype for Business Server 2019, os números de acesso discado que você criou no Skype for Business Server 2019 se comportam de forma semelhante aos números de acesso de discagem que você cria na instalação herdada, conforme descrito neste seção.</span><span class="sxs-lookup"><span data-stu-id="40f87-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="40f87-107">Os números de acesso discado que você criou na instalação herdada, mas foram movidos para o Skype for Business Server 2019, ou que você criou no Skype for Business Server 2019 antes, durante ou após a migração, têm as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="40f87-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="40f87-108">Não aparecem nos convites para reunião do Office Communications Server 2007 R2 e na página número de acesso discada.</span><span class="sxs-lookup"><span data-stu-id="40f87-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="40f87-109">Exibido na página herdada de reunião de instalação convites e número de acesso discada.</span><span class="sxs-lookup"><span data-stu-id="40f87-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="40f87-110">Aparecem nos convites para reunião do Skype for Business Server 2019 e na página número de acesso discada.</span><span class="sxs-lookup"><span data-stu-id="40f87-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="40f87-111">Não pode ser exibido ou modificado na ferramenta administrativa do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="40f87-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="40f87-112">Pode ser exibido e modificado no painel de controle de instalação herdada e no Shell de gerenciamento de instalação herdado.</span><span class="sxs-lookup"><span data-stu-id="40f87-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="40f87-113">Pode ser visualizado e modificado no painel de controle do Skype for Business Server 2019 e no Shell de gerenciamento do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="40f87-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="40f87-114">Pode ser resequenciado na região usando o cmdlet Set-CsDialinConferencingAccessNumber com o parâmetro Priority.</span><span class="sxs-lookup"><span data-stu-id="40f87-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="40f87-115">Você deve concluir a migração dos números de acesso à discagem que apontam para o pool de instalação herdada antes de encerrar o pool de instalação herdado.</span><span class="sxs-lookup"><span data-stu-id="40f87-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="40f87-116">Se você não concluir a migração do número de acesso discado conforme descrito no procedimento a seguir, as chamadas de entrada para os números de acesso falharão.</span><span class="sxs-lookup"><span data-stu-id="40f87-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40f87-117">Você deve executar esse procedimento antes de descomissionar o pool de instalação herdado.</span><span class="sxs-lookup"><span data-stu-id="40f87-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="40f87-118">Recomendamos que você mova números de acesso discada quando o uso de rede for baixo, caso haja um curto período de interrupção do serviço.</span><span class="sxs-lookup"><span data-stu-id="40f87-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="40f87-119">Para identificar e mover números de acesso discado</span><span class="sxs-lookup"><span data-stu-id="40f87-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="40f87-120">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="40f87-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="40f87-121">Para mover cada número de acesso à discagem para um pool hospedado no Skype for Business Server 2019, a partir da linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="40f87-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="40f87-122">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="40f87-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="40f87-123">Na barra de navegação esquerda, clique em **Conferência**.</span><span class="sxs-lookup"><span data-stu-id="40f87-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="40f87-124">Clique na guia **número de acesso** à discagem.</span><span class="sxs-lookup"><span data-stu-id="40f87-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="40f87-125">Verifique se os números de acesso de discagem permanecem para o pool de instalação herdado do qual você está migrando.</span><span class="sxs-lookup"><span data-stu-id="40f87-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="40f87-126">Quando todos os números de acesso discado apontam para o pool do Skype for Business Server 2019, você pode descomissionar o pool de instalação herdado.</span><span class="sxs-lookup"><span data-stu-id="40f87-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="40f87-127">Verifique a migração do número de acesso discado usando o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40f87-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="40f87-128">Em uma conta de usuário que é atribuída à função **CsUserAdministrator** ou à função **CsAdministrator** , faça logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="40f87-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="40f87-129">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="40f87-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="40f87-130">Na barra de navegação esquerda, clique em **Conferência**.</span><span class="sxs-lookup"><span data-stu-id="40f87-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="40f87-131">Clique na guia **número de acesso** à discagem.</span><span class="sxs-lookup"><span data-stu-id="40f87-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="40f87-132">Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="40f87-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="40f87-133">Verificar a migração do número de acesso discado usando o Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40f87-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="40f87-134">Abrir o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="40f87-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="40f87-135">Para retornar todos os números de acesso de conferência discada migrados, a partir da linha de comando executar:</span><span class="sxs-lookup"><span data-stu-id="40f87-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="40f87-136">Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="40f87-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


