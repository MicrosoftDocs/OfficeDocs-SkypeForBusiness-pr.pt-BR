---
title: Atribuir uma política de acesso de usuário externo
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
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
description: Se um usuário tiver sido habilitado para o Skype for Business Server, você poderá configurar a Federação de SIP, o acesso de usuário remoto e a conectividade de mensagens instantâneas públicas no painel de controle do Skype for Business Server aplicando as políticas adequadas a usuários específicos.
ms.openlocfilehash: c03eb957679877ec512b042e0db624adbb3e6f52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043673"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="669aa-103">Atribuir uma política de acesso de usuário externo a um usuário habilitado do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="669aa-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="669aa-104">Se um usuário tiver sido habilitado para o Skype for Business Server, você poderá configurar a Federação de SIP, o acesso de usuário remoto e a conectividade de mensagens instantâneas públicas no painel de controle do Skype for Business Server aplicando as políticas adequadas a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="669aa-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="669aa-105">Por exemplo, se você tiver criado uma política para suportar o acesso de usuário remoto, deverá aplicá-la ao usuário antes que o usuário possa se conectar ao Skype for Business Server de um local remoto e colaborar com usuários internos do local remoto.</span><span class="sxs-lookup"><span data-stu-id="669aa-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="669aa-106">Para oferecer suporte ao acesso de usuário externo, você deve ativar o suporte para cada tipo de acesso de usuário externo ao qual deseja oferecer suporte e configurar as políticas apropriadas e outras opções para controlar o uso.</span><span class="sxs-lookup"><span data-stu-id="669aa-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="669aa-107">Para obter detalhes, consulte [Managing Federation and external Access to Skype for Business Server](../managing-federation-and-external-access.md).</span><span class="sxs-lookup"><span data-stu-id="669aa-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="669aa-108">Use o procedimento neste tópico para aplicar uma política de acesso de usuário externo criada anteriormente para uma ou mais contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="669aa-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="669aa-109">Para aplicar uma política de usuário externo a uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="669aa-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="669aa-110">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="669aa-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="669aa-111">Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="669aa-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="669aa-112">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="669aa-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="669aa-113">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="669aa-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="669aa-114">Em **Editar usuário do Skype for Business Server** na **política de acesso externo**, selecione a política de usuário que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="669aa-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="669aa-115">As configurações de \*\* \<>automática\*\* aplicam as configurações de política global ou de servidor padrão.</span><span class="sxs-lookup"><span data-stu-id="669aa-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="669aa-116">Atribuindo políticas de acesso externo por usuário usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="669aa-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="669aa-117">As políticas de acesso externo por usuário podem ser atribuídas usando o Windows PowerShell e o cmdlet Grant-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="669aa-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="669aa-118">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="669aa-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="669aa-119">Para atribuir uma política de acesso externo por usuário a um único usuário</span><span class="sxs-lookup"><span data-stu-id="669aa-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="669aa-120">Este comando atribui a política de acesso externo por usuário RedmondExternalAccessPolicy ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="669aa-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="669aa-121">Para atribuir uma política de acesso externo por usuário a vários usuários</span><span class="sxs-lookup"><span data-stu-id="669aa-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="669aa-122">Este comando atribui a política de acesso externo por usuário USAExternalAccessPolicy a todos os usuários com contas no OU UnitedStates no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="669aa-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="669aa-123">Para obter mais informações sobre o parâmetro OU usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="669aa-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="669aa-124">Para cancelar a atribuição de uma política de acesso externo por usuário</span><span class="sxs-lookup"><span data-stu-id="669aa-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="669aa-p105">Este comando cancela a atribuição de qualquer política de acesso externo por usuário atribuída a Ken Myer. Após o cancelamento da atribuição da política por usuário, Ken Myer será automaticamente gerenciado usando a política global ou a política de site local (se houver). Um política de site tem prioridade sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="669aa-p105">This command unassigns any per-user external access policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="669aa-128">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="669aa-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


