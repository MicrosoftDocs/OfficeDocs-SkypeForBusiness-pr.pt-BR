---
title: Excluir um site ou uma política de usuário para acesso de usuário externo
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode excluir qualquer política de site ou de usuário que está listada no Skype para painel de controle do servidor de negócios na página política de acesso externo.
ms.openlocfilehash: 53087985ee0723a6291582c3a584be0986119918
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222853"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="fc248-103">Excluir um site ou uma política de usuário para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="fc248-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="fc248-104">Se você criou ou configurou políticas de acesso de usuário externo que você não deseja mais usar, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fc248-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="fc248-105">Exclua qualquer política de site ou de usuário que você criou.</span><span class="sxs-lookup"><span data-stu-id="fc248-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="fc248-106">Redefina a política global para as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="fc248-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="fc248-107">As configurações de política global padrão negam qualquer acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="fc248-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="fc248-108">A política global não pode ser excluída.</span><span class="sxs-lookup"><span data-stu-id="fc248-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="fc248-109">Você pode excluir qualquer política de site ou de usuário que está listada no Skype para painel de controle do servidor de negócios na página **Política de acesso externo** .</span><span class="sxs-lookup"><span data-stu-id="fc248-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="fc248-110">Excluindo a política global não realmente excluí-lo, mas apenas o redefine com as configurações padrão, que não incluem o suporte para quaisquer opções de acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="fc248-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="fc248-111">Para obter detalhes sobre como redefinir a política global, consulte [Redefinir a política global para acesso de usuário externo](reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="fc248-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="fc248-112">Para excluir uma política de site ou usuário para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="fc248-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="fc248-113">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="fc248-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fc248-114">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="fc248-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="fc248-115">Clique em **Acesso de usuário externo**, **Política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="fc248-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="fc248-116">Na guia **Política de acesso externo** , clique na política de site ou de usuário que você deseja excluir, clique em **Editar**e, em seguida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="fc248-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="fc248-117">Quando solicitado a confirmar a exclusão, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="fc248-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fc248-118">Remover políticas de PIN usando Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc248-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fc248-119">Políticas de acesso externo podem ser excluídas, usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="fc248-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="fc248-120">Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc248-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="fc248-121">Para remover uma política de acesso externo específica</span><span class="sxs-lookup"><span data-stu-id="fc248-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="fc248-122">Este comando remove a política de acesso externo aplicada ao site Redmond:</span><span class="sxs-lookup"><span data-stu-id="fc248-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="fc248-123">Para remover todas as do external acessar políticas aplicadas ao escopo por usuário</span><span class="sxs-lookup"><span data-stu-id="fc248-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="fc248-124">Este comando remove todas as políticas de acesso externo configuradas no escopo por usuário:</span><span class="sxs-lookup"><span data-stu-id="fc248-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="fc248-125">Para remover todas as políticas de acesso externo onde o acesso de usuário externo está desabilitado</span><span class="sxs-lookup"><span data-stu-id="fc248-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="fc248-126">Este comando exclui todas as políticas de acesso externo onde usuário externo access foi desativado:</span><span class="sxs-lookup"><span data-stu-id="fc248-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="fc248-127">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="fc248-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
