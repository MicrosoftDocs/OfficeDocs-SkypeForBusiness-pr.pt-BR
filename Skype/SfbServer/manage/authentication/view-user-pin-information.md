---
title: Exibir informações de PIN do usuário no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Resumo: exibir informações de PIN do usuário no Skype for Business Server.'
ms.openlocfilehash: 236148de5b100220731d723df3217205b258879e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818683"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="e7328-103">Exibir informações de PIN do usuário no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e7328-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="e7328-104">**Resumo:** Exibir informações de PIN do usuário no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e7328-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="e7328-105">Para ingressar em uma conferência discada como um usuário autenticado, um usuário do Skype for Business Server com as credenciais dos serviços de domínio Active Directory (AD DS) requer um PIN (número de identificação pessoal).</span><span class="sxs-lookup"><span data-stu-id="e7328-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="e7328-106">Você pode exibir as informações de PIN de um usuário no painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e7328-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7328-107">Você pode exibir as informações de status de PIN, como se o PIN foi definido ou quando ele foi alterado pela última vez, mas não pode ver o PIN atual consultando o status de PIN.</span><span class="sxs-lookup"><span data-stu-id="e7328-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="e7328-108">Se um usuário perde o PIN, você pode redefini-lo seguindo os procedimentos em [definir o PIN de conferência discada do usuário no Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="e7328-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="e7328-109">Para exibir o PIN de um usuário no painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e7328-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e7328-110">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="e7328-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e7328-111">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e7328-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e7328-112">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="e7328-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="e7328-113">Use um dos seguintes métodos para localizar um usuário:</span><span class="sxs-lookup"><span data-stu-id="e7328-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="e7328-114">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="e7328-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="e7328-115">Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="e7328-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="e7328-116">(Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:</span><span class="sxs-lookup"><span data-stu-id="e7328-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="e7328-117">a.</span><span class="sxs-lookup"><span data-stu-id="e7328-117">a.</span></span> <span data-ttu-id="e7328-118">Clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="e7328-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="e7328-119">b.</span><span class="sxs-lookup"><span data-stu-id="e7328-119">b.</span></span> <span data-ttu-id="e7328-120">Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="e7328-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="e7328-121">c.</span><span class="sxs-lookup"><span data-stu-id="e7328-121">c.</span></span> <span data-ttu-id="e7328-122">Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).</span><span class="sxs-lookup"><span data-stu-id="e7328-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="e7328-123">d.</span><span class="sxs-lookup"><span data-stu-id="e7328-123">d.</span></span> <span data-ttu-id="e7328-124">Dependendo da propriedade de usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados da pesquisa digitando-os ou clicando na seta da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="e7328-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e7328-125">Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em **Adicionar filtro**.</span><span class="sxs-lookup"><span data-stu-id="e7328-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="e7328-126">vocálico.</span><span class="sxs-lookup"><span data-stu-id="e7328-126">e.</span></span> <span data-ttu-id="e7328-127">Clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="e7328-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e7328-p108">Se o PIN estiver bloqueado, você deverá desbloqueá-lo para poder defini-lo. Para desbloquear o PIN, clique no usuário, clique em **Ação** e depois em **Desbloquear PIN**.</span><span class="sxs-lookup"><span data-stu-id="e7328-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="e7328-130">Clique em um usuário nos resultados da pesquisa, em **Ação** e depois em **Exibir status do PIN**.</span><span class="sxs-lookup"><span data-stu-id="e7328-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e7328-131">Exibir informações de PIN do usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7328-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="e7328-132">Você pode exibir as informações de PIN do usuário usando o cmdlet Get-CsClientPinInfo.</span><span class="sxs-lookup"><span data-stu-id="e7328-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="e7328-133">Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7328-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e7328-134">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="e7328-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="e7328-135">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e7328-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="e7328-136">Para exibir as informações de PIN do usuário</span><span class="sxs-lookup"><span data-stu-id="e7328-136">To view user PIN information</span></span>

<span data-ttu-id="e7328-137">Para exibir as informações de PIN de um usuário, digite um comando semelhante ao seguinte no Shell de gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="e7328-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="e7328-138">Isso retornará informações parecidas com:</span><span class="sxs-lookup"><span data-stu-id="e7328-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="e7328-139">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e7328-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e7328-140">Confira também</span><span class="sxs-lookup"><span data-stu-id="e7328-140">See also</span></span>

[<span data-ttu-id="e7328-141">Definir o PIN de conferência discada de um usuário no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e7328-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="e7328-142">Bloquear ou desbloquear um PIN de usuário no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e7328-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)
