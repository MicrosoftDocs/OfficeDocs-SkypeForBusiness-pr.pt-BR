---
title: Bloquear ou desbloquear um PIN de usuário no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Resumo: Bloqueie ou desbloqueie o PIN de conferência discada de um usuário para o Skype for Business Server.'
ms.openlocfilehash: 73bd9affa159fba4ab35844896b9662eea3e1780
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828361"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="c9cbc-103">Bloquear ou desbloquear um PIN de usuário no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c9cbc-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="c9cbc-104">**Resumo:** Bloquear ou desbloquear o PIN de conferência discada de um usuário para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="c9cbc-105">Você pode bloquear ou desbloquear o PIN de um usuário na seção **Usuários** do Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="c9cbc-106">Para bloquear o PIN de um usuário no Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c9cbc-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c9cbc-107">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c9cbc-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c9cbc-109">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="c9cbc-110">Utilize um dos métodos a seguir para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="c9cbc-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="c9cbc-111">Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="c9cbc-112">Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="c9cbc-113">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="c9cbc-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="c9cbc-114">a.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-114">a.</span></span> <span data-ttu-id="c9cbc-115">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="c9cbc-116">b.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-116">b.</span></span> <span data-ttu-id="c9cbc-117">Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="c9cbc-118">c.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-118">c.</span></span> <span data-ttu-id="c9cbc-119">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="c9cbc-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="c9cbc-120">d.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-120">d.</span></span> <span data-ttu-id="c9cbc-121">Dependendo da propriedade de usuário selecionada, insira o critério que deseja utilizar para filtrar os resultados da busca digitando ou clicando na seta na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c9cbc-122">Para adicionar cláusulas de pesquisa à sua consulta, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="c9cbc-123">e.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-123">e.</span></span> <span data-ttu-id="c9cbc-124">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-124">Click **Find**.</span></span>
    
   <span data-ttu-id="c9cbc-125">f.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-125">f.</span></span> <span data-ttu-id="c9cbc-126">Clique no usuário, em **Ação** e, em seguida, em **Bloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="c9cbc-127">Para desbloquear o PIN de um usuário no Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c9cbc-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c9cbc-128">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c9cbc-129">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c9cbc-130">Na barra de navegação à esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="c9cbc-131">Utilize um dos métodos a seguir para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="c9cbc-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="c9cbc-132">Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="c9cbc-133">Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="c9cbc-134">(Opcional) Especifique critérios de busca adicionais para limitar os resultados:</span><span class="sxs-lookup"><span data-stu-id="c9cbc-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="c9cbc-135">a.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-135">a.</span></span> <span data-ttu-id="c9cbc-136">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="c9cbc-137">b.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-137">b.</span></span> <span data-ttu-id="c9cbc-138">Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="c9cbc-139">c.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-139">c.</span></span> <span data-ttu-id="c9cbc-140">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="c9cbc-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="c9cbc-141">d.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-141">d.</span></span> <span data-ttu-id="c9cbc-142">Dependendo da propriedade de usuário selecionada, insira o critério que deseja utilizar para filtrar os resultados da busca digitando ou clicando na seta na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c9cbc-143">Para adicionar cláusulas de pesquisa à sua consulta, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="c9cbc-144">e.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-144">e.</span></span> <span data-ttu-id="c9cbc-145">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-145">Click **Find**.</span></span>
    
   <span data-ttu-id="c9cbc-146">f.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-146">f.</span></span> <span data-ttu-id="c9cbc-147">Clique no usuário, clique em **Ação** e, então, clique em **Desbloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c9cbc-148">Bloquear e desbloquear PINs de usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9cbc-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c9cbc-149">Você pode bloquear e desbloquear PINs de usuário usando o Windows PowerShell e os cmdlets Lock-CsClientPin e Unlock-CsClientPin usuário.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="c9cbc-150">Você pode executar esses cmdlets no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c9cbc-151">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="c9cbc-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c9cbc-152">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="c9cbc-153">Para bloquear um PIN de usuário</span><span class="sxs-lookup"><span data-stu-id="c9cbc-153">To lock a user PIN</span></span>

- <span data-ttu-id="c9cbc-154">Para bloquear o PIN de um usuário, use o Lock-CsClientPin cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="c9cbc-155">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9cbc-155">For example:</span></span>
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="c9cbc-156">Para desbloquear um PIN de usuário</span><span class="sxs-lookup"><span data-stu-id="c9cbc-156">To unlock a user PIN</span></span>

- <span data-ttu-id="c9cbc-157">Para desbloquear o PIN de um usuário, use o Unlock-CsClientPin cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c9cbc-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="c9cbc-158">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c9cbc-158">For example:</span></span>
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="c9cbc-159">Para obter mais informações, consulte o tópico de ajuda para os cmdlets [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) e [Unlock-CsClientPin.](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c9cbc-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
