---
title: Redefinir a política global para acesso de usuário externo
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: Não é possível excluir completamente uma política global. Usar a opção **Excluir** na política global simplesmente a redefine para as configurações padrão, o que não inclui suporte a opções de acesso de usuário externo.
ms.openlocfilehash: 6c74690d86f7a300b79b755db7c6111eec7810f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098967"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="4dfb0-104">Redefinir a política global para acesso de usuário externo no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4dfb0-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="4dfb0-105">Se você criou ou configurou políticas de acesso de usuário externo que não vai mais usar, poderá fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4dfb0-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="4dfb0-106">Excluir qualquer política local ou de usuário que você criou.</span><span class="sxs-lookup"><span data-stu-id="4dfb0-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="4dfb0-p102">Redefinir a política global para as configurações padrão. As configurações de política global padrão negam qualquer acesso de usuário externo. A política global não pode ser excluída.</span><span class="sxs-lookup"><span data-stu-id="4dfb0-p102">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>

<span data-ttu-id="4dfb0-p103">Não é possível excluir completamente uma política global. Usar a opção **Excluir** na política global simplesmente a redefine para as configurações padrão, o que não inclui suporte a opções de acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="4dfb0-p103">You cannot completely delete a global policy. Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="4dfb0-112">Para redefinir a política global para as configurações padrão</span><span class="sxs-lookup"><span data-stu-id="4dfb0-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="4dfb0-113">De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="4dfb0-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4dfb0-114">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4dfb0-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="4dfb0-115">Na barra de navegação esquerda, clique em **Acesso do Usuário Externo**, em **Política de Acesso Externa**.</span><span class="sxs-lookup"><span data-stu-id="4dfb0-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="4dfb0-116">Na guia **Política de Acesso Externa**, clique em política global, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="4dfb0-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="4dfb0-p104">Quando lhe for solicitado confirmar a exclusão, clique em **OK**. Uma mensagem aparece na parte superior da página informando que a política global foi redefinida.</span><span class="sxs-lookup"><span data-stu-id="4dfb0-p104">When prompted to confirm the deletion, click **OK**. A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4dfb0-119">Redefinindo a Política de Acesso Externo Global usando Windows PowerShell Cmdlets</span><span class="sxs-lookup"><span data-stu-id="4dfb0-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4dfb0-120">A política de acesso externo global pode ser redefinida usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="4dfb0-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="4dfb0-121">Esse cmdlet pode ser executado no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dfb0-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="4dfb0-122">Para redefinir a política de acesso externo global</span><span class="sxs-lookup"><span data-stu-id="4dfb0-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="4dfb0-123">Esse comendo redefine a política de acesso externo global:</span><span class="sxs-lookup"><span data-stu-id="4dfb0-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="4dfb0-124">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)</span><span class="sxs-lookup"><span data-stu-id="4dfb0-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>