---
title: Delegar o controle administrativo do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 5c295ed1233cb8a0900828cb1d1c074de1d0f16f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817267"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a><span data-ttu-id="5c6c6-102">Delegar o controle administrativo do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5c6c6-102">Delegate administrative control of Skype for Business Server</span></span> 

<span data-ttu-id="5c6c6-103">No Skype for Business Server, as tarefas administrativas são delegadas aos usuários usando o recurso controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="5c6c6-103">In Skype for Business Server, administrative tasks are delegated to users by using the role-based access control (RBAC) feature.</span></span> <span data-ttu-id="5c6c6-104">Quando você instala o Skype for Business Server, várias funções RBAC são criadas para você.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-104">When you install Skype for Business Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="5c6c6-105">Essas funções correspondem a grupos de segurança universais nos Serviços de Domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-105">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="5c6c6-106">Por exemplo, a função RBAC CsHelpDesk corresponde ao grupo CsHelpDesk localizado no contêiner usuários nos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-106">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="5c6c6-107">Além disso, cada função RBAC está associada a um conjunto de cmdlets do Windows PowerShell do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-107">In addition, each RBAC role is associated with a set of Skype for Business Server  Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5c6c6-108">Esses cmdlets representam as tarefas que podem ser realizadas pelos usuários que receberam a função RBAC fornecida.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-108">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="5c6c6-109">Por exemplo, a função CsHelpDesk foi atribuída aos cmdlets Lock-CsClientPin e UnlockCsClientPin.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-109">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="5c6c6-110">Isso significa que os usuários que receberam a função CsHelpDesk podem bloquear e desbloquear números de PIN do usuário.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-110">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="5c6c6-111">No entanto, a função CsHelpDesk não foi atribuída ao cmdlet New-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-111">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="5c6c6-112">Isso significa que os usuários que receberam a função CsHelpDesk não poderão criar novas políticas de voz.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-112">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="5c6c6-113">Exibir informações sobre as funções RBAC</span><span class="sxs-lookup"><span data-stu-id="5c6c6-113">Viewing information about RBAC roles</span></span>

<span data-ttu-id="5c6c6-114">Você pode recuperar informações básicas sobre as funções RBAC executando o seguinte comando no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="5c6c6-114">You can retrieve basic information about your RBAC roles by running the following command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRole`

<span data-ttu-id="5c6c6-115">Lembre-se de que a identidade da função RBAC (por exemplo, CsVoiceAdministrator) tem um mapeamento direto para um grupo de segurança localizado no contêiner usuários nos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-115">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="5c6c6-116">Para exibir uma lista dos cmdlets que foram atribuídos a uma função, use um comando semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="5c6c6-116">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="5c6c6-117">Atribuindo uma função RBAC a um usuário</span><span class="sxs-lookup"><span data-stu-id="5c6c6-117">Assigning an RBAC role to a user</span></span>

<span data-ttu-id="5c6c6-118">Para atribuir uma função RBAC a um usuário, você deve adicionar esse usuário ao grupo de segurança apropriado do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-118">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="5c6c6-119">Por exemplo, para atribuir a função CsLocationAdministrator a um usuário, você deve adicionar esse usuário ao grupo CsLocationAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-119">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="5c6c6-120">Isso pode ser feito executando o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="5c6c6-120">That can be done by carrying out the following procedure:</span></span>

1. <span data-ttu-id="5c6c6-121">Usando uma conta que tenha permissão para modificar a associação de um grupo do Active Directory, faça logon em um computador onde usuários e computadores do Active Directory tenham sido instalados.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-121">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>
2. <span data-ttu-id="5c6c6-122">Clique em **Iniciar**, em **todos os programas**, em **Ferramentas administrativas**e em **usuários e computadores do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-122">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
3. <span data-ttu-id="5c6c6-123">Em usuários e computadores do Active Directory, expanda o nome do seu domínio e clique no contêiner **usuários** .</span><span class="sxs-lookup"><span data-stu-id="5c6c6-123">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>
4. <span data-ttu-id="5c6c6-124">Clique com o botão direito do mouse no grupo de segurança **CsLocationAdministrator**e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-124">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>
5. <span data-ttu-id="5c6c6-125">Na caixa de diálogo **Propriedades** , na guia **Membros** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-125">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>
6. <span data-ttu-id="5c6c6-126">Na caixa de diálogo **Selecionar usuários, computadores, contatos ou grupos** , digite o nome de usuário ou o nome para exibição do usuário a ser adicionado ao grupo (por exemplo, Ken Myer) na caixa **digite os nomes de objeto a serem selecionados** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-126">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, Ken Myer) in the **Enter the object names to select** box, and then click **OK**.</span></span>
7. <span data-ttu-id="5c6c6-127">Na caixa de diálogo **Propriedades** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-127">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="5c6c6-128">Para verificar se a função RBAC foi atribuída, use o cmdlet Get-CsAdminRoleAssignment, passando o cmdlet do SamAccountName (nome de logon do Active Directory) do usuário.</span><span class="sxs-lookup"><span data-stu-id="5c6c6-128">To verify that the RBAC role has been assigned, use the Get-CsAdminRoleAssignment cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="5c6c6-129">Por exemplo, execute este comando dentro do Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="5c6c6-129">For example, run this command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
