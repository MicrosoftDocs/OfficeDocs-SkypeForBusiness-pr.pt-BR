---
title: Migrar números de acesso de discagem
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Migrar números de acesso de discagem para Skype para Business Server 2019 requer executando o cmdlet Move-CsApplicationEndpoint para migrar os objetos de contato. Durante o install herdado e Skype para Business Server 2019 período de coexistência, números de acesso de discagem que você criou em Skype for Business Server 2019 se comportam de forma semelhante aos números de acesso de discagem criados na instalar herdada, conforme descrito neste seção.
ms.openlocfilehash: 7f7aef113018a27e70b88e166d365195c07dce9c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874707"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="22d32-104">Migrar números de acesso de discagem</span><span class="sxs-lookup"><span data-stu-id="22d32-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="22d32-105">Migrar números de acesso de discagem para Skype para Business Server 2019 requer executando o cmdlet **Move-CsApplicationEndpoint** para migrar os objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="22d32-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="22d32-106">Durante o install herdado e Skype para Business Server 2019 período de coexistência, números de acesso de discagem que você criou em Skype for Business Server 2019 se comportam de forma semelhante aos números de acesso de discagem criados na instalar herdada, conforme descrito neste seção.</span><span class="sxs-lookup"><span data-stu-id="22d32-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="22d32-107">Números de acesso de discagem que você criou no antigo instalar, mas movidos para Skype para Business Server 2019 ou que você criou em Skype for Business 2019 de servidor antes, durante ou após a migração, têm as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="22d32-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="22d32-108">Não aparecem nos convites de reunião do Office Communications Server 2007 R2 e a página de número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="22d32-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="22d32-109">Aparecem nos convites de reunião install herdado e página de número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="22d32-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="22d32-110">Aparecem nos Skype para convites de reunião de negócios Server 2019 e página de número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="22d32-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="22d32-111">Não podem ser exibidos ou modificados na ferramenta administrativa do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="22d32-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="22d32-112">Podem ser exibidos e modificados na instalar herdado painel de controle e na herdado instalar o Shell de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="22d32-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="22d32-113">Podem ser exibidos e modificados no Skype para painel de controle do Business Server 2019 e no Skype do Shell de gerenciamento do Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="22d32-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="22d32-114">Podem ser sequenciado novamente com a região usando o cmdlet Set-CsDialinConferencingAccessNumber com o parâmetro Priority.</span><span class="sxs-lookup"><span data-stu-id="22d32-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="22d32-115">Você deverá concluir a migrar os números de acesso de discagem que aponte para o antigo instalar pool antes de encerrar o pool herdado install.</span><span class="sxs-lookup"><span data-stu-id="22d32-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="22d32-116">Se você não concluir a migração do número de acesso de discagem conforme descrito no procedimento a seguir, as chamadas de entrada para os números de acesso falhará.</span><span class="sxs-lookup"><span data-stu-id="22d32-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22d32-117">Você deve executar esse procedimento antes de encerrar o pool herdado install.</span><span class="sxs-lookup"><span data-stu-id="22d32-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="22d32-118">É recomendável que você mova os números de acesso de discagem quando o uso da rede estiver baixo, caso haja um período curto de interrupção do serviço.</span><span class="sxs-lookup"><span data-stu-id="22d32-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="22d32-119">Identificar e mover os números de acesso de discagem</span><span class="sxs-lookup"><span data-stu-id="22d32-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="22d32-120">Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Skype para Business Server 2019**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="22d32-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="22d32-121">Para mover cada número de acesso de discagem para um pool hospedado no Skype para Business Server 2019, a partir da linha de comando execute:</span><span class="sxs-lookup"><span data-stu-id="22d32-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="22d32-122">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="22d32-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="22d32-123">Na barra de navegação esquerda, clique em **Conferência**.</span><span class="sxs-lookup"><span data-stu-id="22d32-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="22d32-124">Clique na guia **Número de acesso de discagem** .</span><span class="sxs-lookup"><span data-stu-id="22d32-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="22d32-125">Verifique se não há números de acesso discado permanecem para o pool herdado install do qual você está migrando.</span><span class="sxs-lookup"><span data-stu-id="22d32-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="22d32-126">Quando todos os números de acesso de discagem aponta para o Skype para Business Server 2019 pool, você poderá encerrar o pool herdado install.</span><span class="sxs-lookup"><span data-stu-id="22d32-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="22d32-127">Verifique se a migração de número de acesso de discagem usando o Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="22d32-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="22d32-128">Usando uma conta de usuário atribuída à função **CsUserAdministrator** ou **csadministrator** , faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="22d32-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="22d32-129">Abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="22d32-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="22d32-130">Na barra de navegação esquerda, clique em **Conferência**.</span><span class="sxs-lookup"><span data-stu-id="22d32-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="22d32-131">Clique na guia **Número de acesso de discagem** .</span><span class="sxs-lookup"><span data-stu-id="22d32-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="22d32-132">Verifique se que todos os números de acesso discado foram migrados para o pool hospedado no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="22d32-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="22d32-133">Verifique se a migração de número de acesso de discagem usando o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="22d32-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="22d32-134">Abra o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="22d32-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="22d32-135">Para retornar todos os números de acesso de conferência discada migrados, na linha de comando execute:</span><span class="sxs-lookup"><span data-stu-id="22d32-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="22d32-136">Verifique se que todos os números de acesso discado foram migrados para o pool hospedado no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="22d32-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


