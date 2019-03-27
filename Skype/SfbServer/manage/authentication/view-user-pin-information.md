---
title: Exibir usuário informações de PIN no Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Resumo: Exibir as informações de PIN de usuário no Skype para Business Server.'
ms.openlocfilehash: 2960e31a54dd531598254ccea41dda516e9f7335
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899691"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="86caa-103">Exibir usuário informações de PIN no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="86caa-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="86caa-104">**Resumo:** Usuário exibir informações de PIN no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="86caa-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="86caa-105">Para ingressar na conferência discada como usuário autenticado, um Skype para usuário Business Server com credenciais do Active Directory Domain Services (AD DS) requer um número de identificação pessoal (PIN).</span><span class="sxs-lookup"><span data-stu-id="86caa-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="86caa-106">Você pode exibir informações de PIN de um usuário do Skype de painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="86caa-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="86caa-107">Você pode exibir as informações de status de PIN, como se o PIN foi definido ou quando ele foi alterado pela última vez, mas não pode ver o PIN atual consultando o status de PIN.</span><span class="sxs-lookup"><span data-stu-id="86caa-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="86caa-108">Se um usuário tiver perdido seu PIN, você pode redefini-lo seguindo os procedimentos no [conjunto de discada um usuário PIN no Skype para Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="86caa-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="86caa-109">Para exibir o PIN de um usuário no Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="86caa-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="86caa-110">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="86caa-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="86caa-111">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="86caa-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="86caa-112">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="86caa-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="86caa-113">Use um dos seguintes métodos para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="86caa-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="86caa-114">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="86caa-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="86caa-115">Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="86caa-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="86caa-116">(Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:</span><span class="sxs-lookup"><span data-stu-id="86caa-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="86caa-117">a.</span><span class="sxs-lookup"><span data-stu-id="86caa-117">a.</span></span> <span data-ttu-id="86caa-118">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="86caa-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="86caa-119">b.</span><span class="sxs-lookup"><span data-stu-id="86caa-119">b.</span></span> <span data-ttu-id="86caa-120">Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="86caa-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="86caa-121">c.</span><span class="sxs-lookup"><span data-stu-id="86caa-121">c.</span></span> <span data-ttu-id="86caa-122">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="86caa-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="86caa-123">d.</span><span class="sxs-lookup"><span data-stu-id="86caa-123">d.</span></span> <span data-ttu-id="86caa-124">Dependendo da propriedade de usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados da pesquisa digitando-os ou clicando na seta da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="86caa-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="86caa-125">Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="86caa-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="86caa-126">f.</span><span class="sxs-lookup"><span data-stu-id="86caa-126">e.</span></span> <span data-ttu-id="86caa-127">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="86caa-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="86caa-p108">Se o PIN estiver bloqueado, você deverá desbloqueá-lo para poder defini-lo. Para desbloquear o PIN, clique no usuário, clique em **Ação** e depois em **Desbloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="86caa-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="86caa-130">Clique em um usuário nos resultados da pesquisa, em **Ação** e depois em **Exibir status do PIN**.</span><span class="sxs-lookup"><span data-stu-id="86caa-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="86caa-131">Exibindo informações de PIN do usuário pelos cmdlets usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="86caa-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="86caa-132">Você pode exibir as informações de PIN do usuário usando o cmdlet Get-CsClientPinInfo.</span><span class="sxs-lookup"><span data-stu-id="86caa-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="86caa-133">Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="86caa-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="86caa-134">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="86caa-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="86caa-135">O processo é o mesmo em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="86caa-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="86caa-136">Para exibir as informações de PIN do usuário</span><span class="sxs-lookup"><span data-stu-id="86caa-136">To view user PIN information</span></span>

<span data-ttu-id="86caa-137">Para exibir informações de PIN de um usuário, digite um comando semelhante ao seguinte no Skype do Shell de gerenciamento do servidor de negócios e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="86caa-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="86caa-138">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="86caa-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="86caa-139">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="86caa-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="86caa-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="86caa-140">See also</span></span>

[<span data-ttu-id="86caa-141">Definir discada um usuário PIN no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="86caa-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="86caa-142">Bloquear ou desbloquear um PIN em Skype do usuário para o servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="86caa-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)
