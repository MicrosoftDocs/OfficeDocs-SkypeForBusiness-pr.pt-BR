---
title: Redefinir a política global para acesso de usuário externo
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: Não é possível excluir completamente uma política global. Usar a opção **excluir** na política global somente redefine a política global para as configurações padrão, que não incluem suporte para qualquer opção de acesso de usuário externo.
ms.openlocfilehash: e0e59c4de1b7a4bacbef30b4caa3d26c29b81e84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818262"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="14cec-104">Redefinir a política global para o acesso de usuários externos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="14cec-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="14cec-105">Se você criou ou configurou políticas de acesso externo do usuário que não deseja mais usar, pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="14cec-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="14cec-106">Exclua qualquer site ou política de usuário que você criou.</span><span class="sxs-lookup"><span data-stu-id="14cec-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="14cec-107">Redefina a política global para as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="14cec-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="14cec-108">As configurações de política global padrão negam qualquer acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="14cec-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="14cec-109">A política global não pode ser excluída.</span><span class="sxs-lookup"><span data-stu-id="14cec-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="14cec-110">Não é possível excluir completamente uma política global.</span><span class="sxs-lookup"><span data-stu-id="14cec-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="14cec-111">Usar a opção **excluir** na política global somente redefine a política global para as configurações padrão, que não incluem suporte para qualquer opção de acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="14cec-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="14cec-112">Para redefinir a política global para as configurações padrão</span><span class="sxs-lookup"><span data-stu-id="14cec-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="14cec-113">Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="14cec-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="14cec-114">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="14cec-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="14cec-115">Na barra de navegação à esquerda, clique em **acesso ao usuário externo**, clique em **política de acesso externo**.</span><span class="sxs-lookup"><span data-stu-id="14cec-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="14cec-116">Na guia **política de acesso externo** , clique na política global, clique em **Editar**e, em seguida, clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="14cec-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="14cec-117">Quando for solicitado a confirmar a exclusão, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="14cec-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="14cec-118">Uma mensagem é exibida na parte superior da página informando que a política global foi redefinida.</span><span class="sxs-lookup"><span data-stu-id="14cec-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="14cec-119">Redefinindo a política de acesso externo global usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="14cec-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="14cec-120">A política de acesso externo global pode ser redefinida usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="14cec-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="14cec-121">Esse cmdlet pode ser executado do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14cec-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="14cec-122">Para redefinir a política de acesso externo global</span><span class="sxs-lookup"><span data-stu-id="14cec-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="14cec-123">Este comando redefine a política global de acesso externo:</span><span class="sxs-lookup"><span data-stu-id="14cec-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="14cec-124">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="14cec-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


