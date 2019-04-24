---
title: Redefinir a política global para acesso de usuário externo
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Completamente, você não pode excluir uma política global. Apenas usando a opção **Excluir** a política global redefine a política global para as configurações padrão, que não incluem o suporte para quaisquer opções de acesso de usuário externo.
ms.openlocfilehash: 048d1f1aabd2e188cefa25358068ea6ec150b8f3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197622"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="1d14c-104">Redefinir a política global para acesso de usuário externo no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="1d14c-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="1d14c-105">Se você criou ou configurou políticas de acesso de usuário externo que você não deseja mais usar, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1d14c-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="1d14c-106">Exclua qualquer política de site ou de usuário que você criou.</span><span class="sxs-lookup"><span data-stu-id="1d14c-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="1d14c-107">Redefina a política global para as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="1d14c-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="1d14c-108">As configurações de política global padrão negam qualquer acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="1d14c-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="1d14c-109">A política global não pode ser excluída.</span><span class="sxs-lookup"><span data-stu-id="1d14c-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="1d14c-110">Completamente, você não pode excluir uma política global.</span><span class="sxs-lookup"><span data-stu-id="1d14c-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="1d14c-111">Apenas usando a opção **Excluir** a política global redefine a política global para as configurações padrão, que não incluem o suporte para quaisquer opções de acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="1d14c-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="1d14c-112">Para redefinir a política global para as configurações padrão</span><span class="sxs-lookup"><span data-stu-id="1d14c-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="1d14c-113">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="1d14c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d14c-114">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="1d14c-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="1d14c-115">Na barra de navegação à esquerda, clique em **Acesso de usuário externo**, **Política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="1d14c-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="1d14c-116">Na guia **Política de acesso externo** , clique na política global, clique em **Editar**e, em seguida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="1d14c-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="1d14c-117">Quando solicitado a confirmar a exclusão, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="1d14c-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="1d14c-118">Uma mensagem é exibida na parte superior da página informando que a política global foi redefinida.</span><span class="sxs-lookup"><span data-stu-id="1d14c-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1d14c-119">Redefinido a política de acesso externo Global usando Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d14c-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1d14c-120">Pode ser redefinida a política de acesso externo global usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="1d14c-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="1d14c-121">Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1d14c-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="1d14c-122">Para redefinir a política de acesso externo global</span><span class="sxs-lookup"><span data-stu-id="1d14c-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="1d14c-123">Esse comendo redefine a política de acesso externo global:</span><span class="sxs-lookup"><span data-stu-id="1d14c-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="1d14c-124">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="1d14c-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


