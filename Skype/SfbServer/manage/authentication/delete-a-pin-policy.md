---
title: Excluir uma política de PIN no Skype for Business Server
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
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: 'Resumo: exclua o PIN de conferência discada de um usuário para o Skype for Business Server.'
ms.openlocfilehash: b85d2bb29f8a1a28279a59f72957d201886d1dc4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096787"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="a466d-103">Excluir uma política de PIN no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a466d-103">Delete a PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="a466d-104">**Resumo:** Exclua o PIN de conferência discada de um usuário para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a466d-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="a466d-105">Siga estas etapas para excluir uma política de PIN (número de identificação pessoal).</span><span class="sxs-lookup"><span data-stu-id="a466d-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a466d-106">Não é possível excluir a política PIN global.</span><span class="sxs-lookup"><span data-stu-id="a466d-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="a466d-107">Para excluir uma política de PIN no Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a466d-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="a466d-108">De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a466d-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="a466d-109">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a466d-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a466d-110">Na barra de navegação esquerda, clique em **Segurança** e em **Política de PIN**.</span><span class="sxs-lookup"><span data-stu-id="a466d-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="a466d-111">Na página **Política de PIN** e no campo de pesquisa, digite o nome todo ou parcial da política que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="a466d-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="a466d-112">Na lista de políticas, clique na política que você deseja, em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="a466d-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="a466d-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a466d-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a466d-114">Removendo políticas de PIN usando Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="a466d-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a466d-115">Você pode excluir políticas de PIN usando Windows PowerShell e o cmdlet Remove-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="a466d-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="a466d-116">Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a466d-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a466d-117">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog "Início Rápido: Gerenciando o [Microsoft Lync Server 2010 usando o PowerShell Remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="a466d-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a466d-118">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a466d-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="a466d-119">Para remover uma política de PIN específica</span><span class="sxs-lookup"><span data-stu-id="a466d-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="a466d-120">Este comando remove a política de PIN com a Identidade RedmondPinPolicy:</span><span class="sxs-lookup"><span data-stu-id="a466d-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="a466d-121">Para remover todas as políticas de PIN aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="a466d-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="a466d-122">Este comando remove todas as políticas de PIN configuradas no escopo do site:</span><span class="sxs-lookup"><span data-stu-id="a466d-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="a466d-123">Para remover todas as políticas de PIN que permitem o uso de padrões comuns</span><span class="sxs-lookup"><span data-stu-id="a466d-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="a466d-124">Isso remove todas as políticas de PIN que permitem o uso dos padrões comuns:G</span><span class="sxs-lookup"><span data-stu-id="a466d-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="a466d-125">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsPinPolicy.](/powershell/module/skype/remove-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a466d-125">For more information, see the help topic for the [Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
