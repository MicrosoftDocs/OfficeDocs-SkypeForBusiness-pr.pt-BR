---
title: Migrar os números de acesso discado
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
description: Migrar números de acesso de discagem para o Skype for Business Server 2019 requer a execução do cmdlet Move-CsApplicationEndpoint para migrar os objetos de contato. Durante o período de coexistência de instalação herdada e Skype for Business Server 2019, os números de acesso de discagem criados no Skype for Business Server 2019 se comportam de forma semelhante aos números de acesso de discagem que você cria na instalação herdada, conforme descrito nesta seção.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752693"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="a8059-104">Migrar os números de acesso discado</span><span class="sxs-lookup"><span data-stu-id="a8059-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="a8059-105">Migrar números de acesso de discagem para o Skype for Business Server 2019 requer a execução do cmdlet **move-CsApplicationEndpoint** para migrar os objetos de contato.</span><span class="sxs-lookup"><span data-stu-id="a8059-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="a8059-106">Durante o período de coexistência de instalação herdada e Skype for Business Server 2019, os números de acesso de discagem criados no Skype for Business Server 2019 se comportam de forma semelhante aos números de acesso de discagem que você cria na instalação herdada, conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="a8059-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="a8059-107">Os números de acesso de discagem que você criou na instalação herdada, mas movidos para o Skype for Business Server 2019, ou que você criou no Skype for Business Server 2019 antes, durante ou após a migração, têm as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="a8059-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="a8059-108">Não aparecem nos convites de reunião do Office Communications Server 2007 R2 e na página número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="a8059-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="a8059-109">Aparecem nos convites de reunião de instalação herdados e na página número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="a8059-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="a8059-110">Aparecem nos convites de reunião do Skype for Business Server 2019 e na página número de acesso de discagem.</span><span class="sxs-lookup"><span data-stu-id="a8059-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="a8059-111">Não podem ser exibidos ou modificados na ferramenta administrativa do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="a8059-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="a8059-112">Pode ser exibido e modificado no painel de controle de instalação herdado e no Shell de gerenciamento de instalação herdado.</span><span class="sxs-lookup"><span data-stu-id="a8059-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="a8059-113">Pode ser exibido e modificado no painel de controle do Skype for Business Server 2019 e no Shell de gerenciamento do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8059-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="a8059-114">Podem ser seqüenciados novamente dentro da região usando o cmdlet Set-CsDialinConferencingAccessNumber com o parâmetro Priority.</span><span class="sxs-lookup"><span data-stu-id="a8059-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="a8059-115">Você deve concluir a migração dos números de acesso de discagem que apontam para o pool de instalação herdado antes de encerrar o pool de instalação herdado.</span><span class="sxs-lookup"><span data-stu-id="a8059-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="a8059-116">Se você não concluir a migração do número de acesso de discagem, conforme descrito no procedimento a seguir, as chamadas de entrada para os números de acesso falharão.</span><span class="sxs-lookup"><span data-stu-id="a8059-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8059-117">Você deve executar esse procedimento antes de encerrar o pool de instalação herdado.</span><span class="sxs-lookup"><span data-stu-id="a8059-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="a8059-118">Recomendamos que você mova os números de acesso de discagem quando o uso da rede estiver baixo, caso haja uma breve interrupção no serviço.</span><span class="sxs-lookup"><span data-stu-id="a8059-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="a8059-119">Para identificar e mover os números de acesso de discagem</span><span class="sxs-lookup"><span data-stu-id="a8059-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="a8059-120">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Skype for Business Server 2019**e em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="a8059-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a8059-121">Para mover cada número de acesso de discagem para um pool hospedado no Skype for Business Server 2019, na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="a8059-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="a8059-122">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a8059-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="a8059-123">Na barra de navegação esquerda, clique em **Conferência**.</span><span class="sxs-lookup"><span data-stu-id="a8059-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="a8059-124">Clique na guia **número de acesso de discagem** .</span><span class="sxs-lookup"><span data-stu-id="a8059-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="a8059-125">Verifique se os números de acesso de discagem permanecem para o pool de instalação herdado do qual você está migrando.</span><span class="sxs-lookup"><span data-stu-id="a8059-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a8059-126">Quando todos os números de acesso de discagem apontarem para o pool do Skype for Business Server 2019, você poderá encerrar o pool de instalação herdado.</span><span class="sxs-lookup"><span data-stu-id="a8059-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a8059-127">Verificar a migração do número de acesso de discagem usando o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a8059-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a8059-128">A partir de uma conta de usuário atribuída à função **CsUserAdministrator** ou à função **CsAdministrator** , faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a8059-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="a8059-129">Abra o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a8059-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="a8059-130">Na barra de navegação esquerda, clique em **Conferência**.</span><span class="sxs-lookup"><span data-stu-id="a8059-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="a8059-131">Clique na guia **número de acesso de discagem** .</span><span class="sxs-lookup"><span data-stu-id="a8059-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="a8059-132">Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8059-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a8059-133">Verificar a migração do número de acesso de discagem usando o Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a8059-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="a8059-134">Abra o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a8059-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="a8059-135">Para retornar todos os números de acesso de conferência discada migrados, a partir da linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="a8059-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="a8059-136">Verifique se todos os números de acesso de discagem foram migrados para o pool hospedado no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a8059-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


