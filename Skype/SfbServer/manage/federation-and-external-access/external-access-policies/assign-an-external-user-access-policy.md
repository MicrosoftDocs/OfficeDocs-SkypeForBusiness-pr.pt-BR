---
title: Atribuir uma política de acesso de usuário externo
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se um usuário tiver sido habilitado para Skype para Business Server, você pode configurar a federação SIP, acesso de usuário remoto e pública mensagens instantâneas conectividade (IM) no Skype para painel de controle do Business Server, aplicando as políticas adequadas a usuários específicos.
ms.openlocfilehash: f07a407fee6f32f4cd4207c93ca19341e409ea78
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881497"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="41864-103">Atribuir uma política de acesso de usuário externo a um Skype para usuário comercial habilitado</span><span class="sxs-lookup"><span data-stu-id="41864-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="41864-104">Se um usuário tiver sido habilitado para Skype para Business Server, você pode configurar a federação SIP, acesso de usuário remoto e pública mensagens instantâneas conectividade (IM) no Skype para painel de controle do Business Server, aplicando as políticas adequadas a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="41864-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="41864-105">Por exemplo, se você criou uma política para suportar o acesso de usuário remoto, você deve aplicá-lo ao usuário antes que o usuário pode se conectar ao Skype para Business Server de um local remoto e colaborar com usuários internos do local remoto.</span><span class="sxs-lookup"><span data-stu-id="41864-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="41864-106">Para suportar o acesso de usuário externo, você deve habilitar o suporte para cada tipo de acesso de usuário externo que você deseja suportar e configurar as políticas adequadas e outras opções para controlar seu uso.</span><span class="sxs-lookup"><span data-stu-id="41864-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="41864-107">Para obter detalhes, consulte [Gerenciando federação e acesso externo à Skype para Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="41864-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="41864-108">Use o procedimento neste tópico para aplicar uma política de acesso de usuário externo criada anteriormente para uma ou mais contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="41864-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="41864-109">Para aplicar uma política de usuário externo para uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="41864-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="41864-110">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="41864-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="41864-111">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="41864-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="41864-112">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="41864-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="41864-113">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="41864-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="41864-114">Em **Editar Skype para usuário de servidor de negócios** em **política de acesso externo**, selecione a política de usuário que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="41864-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="41864-115">O \*\* \<Automatic>\*\* configurações se aplicam as configurações de política global ou de servidor padrão.</span><span class="sxs-lookup"><span data-stu-id="41864-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="41864-116">Atribuindo políticas de acesso externo por usuário usando Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41864-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="41864-117">Políticas de acesso externo por usuário podem ser atribuídas usando o Windows PowerShell e o cmdlet Grant-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="41864-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="41864-118">Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41864-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="41864-119">Para atribuir uma política de acesso externo por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="41864-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="41864-120">Este comando atribui a política de acesso externo por usuário RedmondExternalAccessPolicy ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="41864-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="41864-121">Para atribuir uma política de acesso externo por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="41864-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="41864-122">Este comando atribui a política de acesso externo por usuário USAExternalAccessPolicy a todos os usuários que tiverem contas na unidade Organizacional Estados Unidos no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="41864-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="41864-123">Para obter mais informações sobre o parâmetro OU usado neste comando, consulte a documentação para o cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="41864-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="41864-124">Para retirar a atribuição de uma política de acesso externo por usuário</span><span class="sxs-lookup"><span data-stu-id="41864-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="41864-125">Este comando remove a atribuição de qualquer política de acesso externo por usuário previamente atribuída a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="41864-125">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="41864-126">Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local.</span><span class="sxs-lookup"><span data-stu-id="41864-126">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="41864-127">Uma política de site tem precedência sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="41864-127">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="41864-128">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="41864-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


