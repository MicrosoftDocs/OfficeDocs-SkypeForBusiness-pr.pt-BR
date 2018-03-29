---
title: Bloquear ou desbloquear um PIN de usuário no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Resumo: Bloquear ou desbloquear discada um usuário PIN para Skype para Business Server 2015.'
ms.openlocfilehash: 5bd4a334f9c0b543d9b4cade8631f992a920dfb1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server-2015"></a><span data-ttu-id="07a24-103">Bloquear ou desbloquear um PIN de usuário no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="07a24-103">Lock or unlock a user PIN in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="07a24-104">**Resumo:** Bloquear ou desbloquear discada um usuário PIN para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="07a24-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="07a24-105">Você pode bloquear ou desbloquear o PIN de um usuário da seção de **usuários** do Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="07a24-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="07a24-106">Bloquear o PIN de um usuário no Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="07a24-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="07a24-107">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="07a24-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="07a24-108">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="07a24-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="07a24-109">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="07a24-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="07a24-110">Use um dos seguintes métodos para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="07a24-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="07a24-111">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="07a24-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="07a24-112">Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="07a24-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="07a24-113">(Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:</span><span class="sxs-lookup"><span data-stu-id="07a24-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="07a24-114">a.</span><span class="sxs-lookup"><span data-stu-id="07a24-114">a.</span></span> <span data-ttu-id="07a24-115">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="07a24-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="07a24-116">b.</span><span class="sxs-lookup"><span data-stu-id="07a24-116">b.</span></span> <span data-ttu-id="07a24-117">Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="07a24-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="07a24-118">c.</span><span class="sxs-lookup"><span data-stu-id="07a24-118">c.</span></span> <span data-ttu-id="07a24-119">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="07a24-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="07a24-120">d.</span><span class="sxs-lookup"><span data-stu-id="07a24-120">d.</span></span> <span data-ttu-id="07a24-121">Dependendo da propriedade de usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados da pesquisa digitando-os ou clicando na seta da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="07a24-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="07a24-122">Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="07a24-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="07a24-123">f.</span><span class="sxs-lookup"><span data-stu-id="07a24-123">e.</span></span> <span data-ttu-id="07a24-124">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="07a24-124">Click **Find**.</span></span>
    
   <span data-ttu-id="07a24-125">f.</span><span class="sxs-lookup"><span data-stu-id="07a24-125">f.</span></span> <span data-ttu-id="07a24-126">Clique no usuário, em **Ação** e, em seguida, em **Bloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="07a24-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="07a24-127">Para desbloquear o PIN de um usuário no Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="07a24-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="07a24-128">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="07a24-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="07a24-129">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="07a24-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="07a24-130">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="07a24-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="07a24-131">Use um dos seguintes métodos para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="07a24-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="07a24-132">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="07a24-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="07a24-133">Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="07a24-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="07a24-134">(Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:</span><span class="sxs-lookup"><span data-stu-id="07a24-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="07a24-135">a.</span><span class="sxs-lookup"><span data-stu-id="07a24-135">a.</span></span> <span data-ttu-id="07a24-136">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="07a24-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="07a24-137">b.</span><span class="sxs-lookup"><span data-stu-id="07a24-137">b.</span></span> <span data-ttu-id="07a24-138">Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="07a24-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="07a24-139">c.</span><span class="sxs-lookup"><span data-stu-id="07a24-139">c.</span></span> <span data-ttu-id="07a24-140">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="07a24-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="07a24-141">d.</span><span class="sxs-lookup"><span data-stu-id="07a24-141">d.</span></span> <span data-ttu-id="07a24-142">Dependendo da propriedade de usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados da pesquisa digitando-os ou clicando na seta da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="07a24-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="07a24-143">Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="07a24-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="07a24-144">f.</span><span class="sxs-lookup"><span data-stu-id="07a24-144">e.</span></span> <span data-ttu-id="07a24-145">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="07a24-145">Click **Find**.</span></span>
    
   <span data-ttu-id="07a24-146">f.</span><span class="sxs-lookup"><span data-stu-id="07a24-146">f.</span></span> <span data-ttu-id="07a24-147">Clique no usuário, clique em **Ação** e, então, clique em **Desbloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="07a24-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="07a24-148">Bloquear e desbloquear PINs de usuário usando Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="07a24-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="07a24-149">Você pode bloquear e desbloquear PINs de usuário usando o Windows PowerShell e os cmdlets Lock-CsClientPin e Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="07a24-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="07a24-150">Você pode executar esses cmdlets do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07a24-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="07a24-151">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="07a24-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="07a24-152">O processo é o mesmo em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="07a24-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="07a24-153">Para bloquear um PIN de usuário</span><span class="sxs-lookup"><span data-stu-id="07a24-153">To lock a user PIN</span></span>

- <span data-ttu-id="07a24-154">Para bloquear o PIN de um usuário, use o cmdlet Lock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="07a24-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="07a24-155">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="07a24-155">For example:</span></span>
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="07a24-156">Para desbloquear um PIN de usuário</span><span class="sxs-lookup"><span data-stu-id="07a24-156">To unlock a user PIN</span></span>

- <span data-ttu-id="07a24-157">Para desbloquear o PIN de um usuário, use o cmdlet Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="07a24-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="07a24-158">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="07a24-158">For example:</span></span>
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="07a24-159">Para obter mais informações, consulte o tópico de ajuda para os cmdlets [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) e [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="07a24-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>