---
title: Excluir um site ou uma política de usuário para acesso de usuário externo
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você pode excluir qualquer política de site ou usuário listada no Painel de Controle do Skype for Business Server na página Política de Acesso Externo.
ms.openlocfilehash: 407e90af201055f371dc92485ab258bac851a258
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099017"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="59a7a-103">Excluir um site ou uma política de usuário para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="59a7a-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="59a7a-104">Se você criou ou configurou políticas de acesso de usuário externo que não vai mais usar, poderá fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="59a7a-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="59a7a-105">Excluir qualquer política local ou de usuário que você criou.</span><span class="sxs-lookup"><span data-stu-id="59a7a-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="59a7a-p101">Redefinir a política global para as configurações padrão. As configurações de política global padrão negam qualquer acesso de usuário externo. A política global não pode ser excluída.</span><span class="sxs-lookup"><span data-stu-id="59a7a-p101">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>


<span data-ttu-id="59a7a-109">Você pode excluir qualquer política de site ou usuário listada no Painel de Controle do Skype for Business Server na página **Política de Acesso** Externo.</span><span class="sxs-lookup"><span data-stu-id="59a7a-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="59a7a-110">Excluir a política global não causa sua exclusão propriamente dita, mas apenas a redefine para suas configurações padrão, que não incluem suporte para nenhuma opção de acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="59a7a-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="59a7a-111">Para obter detalhes sobre como redefinir a política global, consulte [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="59a7a-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="59a7a-112">Para excluir uma política de site ou de usuário para o acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="59a7a-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="59a7a-113">De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="59a7a-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="59a7a-114">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="59a7a-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="59a7a-115">Clique em **Acesso de Usuário Externo**, em **Política de Acesso Externo**.</span><span class="sxs-lookup"><span data-stu-id="59a7a-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="59a7a-116">Na guia **Política de Acesso Externo**, clique na política de site ou de usuário que deseja excluir, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="59a7a-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="59a7a-117">Quando for solicitado que você confirme a exclusão, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="59a7a-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="59a7a-118">Removendo políticas de PIN usando Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="59a7a-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="59a7a-119">As políticas de acesso externo podem ser excluídas usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="59a7a-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="59a7a-120">Esse cmdlet pode ser executado no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59a7a-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="59a7a-121">Para remover uma política de acesso externo específica</span><span class="sxs-lookup"><span data-stu-id="59a7a-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="59a7a-122">Este comando remove a política de acesso externo aplicada ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="59a7a-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="59a7a-123">Para remover todas as políticas de acesso externo aplicadas ao escopo por usuário</span><span class="sxs-lookup"><span data-stu-id="59a7a-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="59a7a-124">Este comando remove todas as políticas de acesso externo configuradas no escopo por usuário:</span><span class="sxs-lookup"><span data-stu-id="59a7a-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="59a7a-125">Para remover todas as políticas de acesso externo em que o acesso externo do usuário está desabilitado</span><span class="sxs-lookup"><span data-stu-id="59a7a-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="59a7a-126">Este comando exclui todas as políticas de acesso externo com acesso de usuário externo desabilitado:</span><span class="sxs-lookup"><span data-stu-id="59a7a-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="59a7a-127">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)</span><span class="sxs-lookup"><span data-stu-id="59a7a-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>