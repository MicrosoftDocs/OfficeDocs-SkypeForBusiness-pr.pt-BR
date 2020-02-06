---
title: Excluir um site ou uma política de usuário para acesso de usuário externo
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você pode excluir qualquer política de site ou de usuário listada no painel de controle do Skype for Business Server na página de política de acesso externo.
ms.openlocfilehash: 2472058009622834e20a1657167c7061b9706579
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818282"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="71107-103">Excluir um site ou uma política de usuário para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="71107-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="71107-104">Se você criou ou configurou políticas de acesso externo do usuário que não deseja mais usar, pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="71107-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="71107-105">Exclua qualquer site ou política de usuário que você criou.</span><span class="sxs-lookup"><span data-stu-id="71107-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="71107-106">Redefina a política global para as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="71107-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="71107-107">As configurações de política global padrão negam qualquer acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="71107-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="71107-108">A política global não pode ser excluída.</span><span class="sxs-lookup"><span data-stu-id="71107-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="71107-109">Você pode excluir qualquer política de site ou de usuário listada no painel de controle do Skype for Business Server na página de **política de acesso externo** .</span><span class="sxs-lookup"><span data-stu-id="71107-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="71107-110">A exclusão da política global não a exclui realmente, mas só a redefine para as configurações padrão, que não incluem suporte para qualquer opção de acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="71107-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="71107-111">Para obter detalhes sobre como redefinir a política global, consulte [redefinir a política global para acesso de usuários externos](reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="71107-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="71107-112">Para excluir uma política de site ou de usuário para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="71107-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="71107-113">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="71107-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="71107-114">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="71107-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="71107-115">Clique em **acesso de usuário externo**, clique em **política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="71107-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="71107-116">Na guia **política de acesso externo** , clique no site ou na política de usuário que você deseja excluir, clique em **Editar**e, em seguida, clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="71107-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="71107-117">Quando for solicitado a confirmar a exclusão, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="71107-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="71107-118">Removendo políticas de PIN usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="71107-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="71107-119">As políticas de acesso externo podem ser excluídas usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="71107-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="71107-120">Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71107-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="71107-121">Para remover uma política de acesso externo específica</span><span class="sxs-lookup"><span data-stu-id="71107-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="71107-122">Este comando Remove a política de acesso externo aplicada ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="71107-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="71107-123">Para remover todas as políticas de acesso externo aplicadas ao escopo por usuário</span><span class="sxs-lookup"><span data-stu-id="71107-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="71107-124">Esse comando Remove todas as políticas de acesso externo configuradas no escopo por usuário:</span><span class="sxs-lookup"><span data-stu-id="71107-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="71107-125">Para remover todas as políticas de acesso externo em que o acesso do usuário externo está desabilitado</span><span class="sxs-lookup"><span data-stu-id="71107-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="71107-126">Este comando exclui todas as políticas de acesso externo em que o acesso de usuário externo foi desabilitado:</span><span class="sxs-lookup"><span data-stu-id="71107-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="71107-127">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="71107-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
