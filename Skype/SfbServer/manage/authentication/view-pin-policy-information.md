---
title: Exibir informações de política de PIN no Skype for Business Server
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
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Resumo: Exibir informações de política de PIN de um usuário para o Skype for Business Server.'
ms.openlocfilehash: 80383ce7e78ba8806119121f8c27c6e469363003
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119530"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="9a5d6-103">Exibir informações de política de PIN no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9a5d6-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="9a5d6-104">**Resumo:** Exibir informações de política de PIN de um usuário para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9a5d6-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="9a5d6-105">Você pode usar a **guia Política de PIN** para exibir a autenticação de número de identificação pessoal (PIN) de usuários que estão se conectando ao Skype for Business com telefones IP.</span><span class="sxs-lookup"><span data-stu-id="9a5d6-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="9a5d6-106">Para usar a autenticação PIN, certifique-se de que **Habilitar Autenticação PIN** esteja selecionado nas configurações do Web Service.</span><span class="sxs-lookup"><span data-stu-id="9a5d6-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="9a5d6-107">Siga estas etapas para modificar uma política de PIN de nível do usuário ou nível local.</span><span class="sxs-lookup"><span data-stu-id="9a5d6-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="9a5d6-108">Para exibir informações sobre uma política de PIN no Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9a5d6-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9a5d6-109">De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9a5d6-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="9a5d6-110">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9a5d6-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9a5d6-111">Na barra de navegação esquerda, clique em **Segurança** e em **Política de PIN**.</span><span class="sxs-lookup"><span data-stu-id="9a5d6-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="9a5d6-112">Na página **Política de PIN**, clique em uma política, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="9a5d6-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9a5d6-113">Exibindo políticas de PIN usando Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="9a5d6-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9a5d6-114">Você também pode exibir políticas de PIN usando o Windows PowerShell e o cmdlet Get-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="9a5d6-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="9a5d6-115">Esse cmdlet pode ser executado no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a5d6-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9a5d6-116">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog "Início Rápido: Gerenciando o [Microsoft Lync Server 2010 usando o PowerShell Remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="9a5d6-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="9a5d6-117">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9a5d6-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="9a5d6-118">Para exibir políticas de PIN</span><span class="sxs-lookup"><span data-stu-id="9a5d6-118">To view PIN policies</span></span>

<span data-ttu-id="9a5d6-119">Para exibir informações sobre todas as políticas de PIN, digite o seguinte comando no Shell de Gerenciamento do Skype for Business Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="9a5d6-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy
  ```

<span data-ttu-id="9a5d6-120">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="9a5d6-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="9a5d6-121">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Get-CsPinPolicy.](/powershell/module/skype/get-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9a5d6-121">For more information, see the help topic for the [Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9a5d6-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="9a5d6-122">See also</span></span>

[<span data-ttu-id="9a5d6-123">Criar uma nova política de PIN no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9a5d6-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)