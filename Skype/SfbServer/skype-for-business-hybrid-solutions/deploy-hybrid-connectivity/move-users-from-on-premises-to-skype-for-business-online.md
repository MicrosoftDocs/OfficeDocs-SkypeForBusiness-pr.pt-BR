---
title: Mover usuários do local para o Skype for Business Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/12/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
description: 'Resumo: Saiba como migrar configurações do usuário e movam usuários para Skype para negócios Online.'
ms.openlocfilehash: dada94d1bc198a86a06c468dc959fa0684e706d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="8d8a5-103">Mover usuários do local para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8d8a5-103">Move users from on premises to Skype for Business Online</span></span>
 
<span data-ttu-id="8d8a5-104">**Resumo:** Saiba como migrar configurações do usuário e movam usuários para Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-104">**Summary:** Learn how to migrate user settings and move users to Skype for Business Online.</span></span>
  
<span data-ttu-id="8d8a5-p101">Antes de realmente mover o usuário para o Office 365, primeiro você deve confirmar se ele está sincronizado com a nuvem, e atribuir uma licença a ele. Para fazer isso, use o Centro de Administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-p101">Before actually moving the user to Office 365, you should first confirm that the user accounts are synchronized to the cloud, and assign them a license. To do this, you use the Office 365 Admin Center.</span></span>
  
### <a name="to-confirm-that-an-on-premises-user-account-has-been-synchronized-with-office-365"></a><span data-ttu-id="8d8a5-107">Para confirmar que uma conta de usuário local foi sincronizada com o Office 365</span><span class="sxs-lookup"><span data-stu-id="8d8a5-107">To confirm that an on-premises user account has been synchronized with Office 365</span></span>

1. <span data-ttu-id="8d8a5-108">Usando uma conta de administração de locatário, abra o [Centro de administração do Office 365](https://portal.office.com/) para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-108">Using an tenant admin account, open the [Office 365 admin center](https://portal.office.com/) for your tenant.</span></span>
    
2. <span data-ttu-id="8d8a5-109">No painel de navegação à esquerda, clique em **Usuários** e, em seguida, **Usuários Ativos**.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-109">On the left navigation pane, click **Users** and then **Active Users**.</span></span>
    
3. <span data-ttu-id="8d8a5-110">Clique em **Pesquisar um Usuário**e digite o nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-110">Click **Search for a User**, and type the name of the user.</span></span>
    
4. <span data-ttu-id="8d8a5-111">Confirme que você visualizou o usuário e que seu status é **Sincronizado com Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-111">Confirm that you see the user, and that their status is **Synched with Active Directory**.</span></span>
    
    <span data-ttu-id="8d8a5-112">Se o usuário ainda não está sincronizado, a próxima sincronização automática deve acontecer no prazo de três horas.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-112">If the user is not yet synchronized, the next automatic synchronization should happen within three hours.</span></span> <span data-ttu-id="8d8a5-113">Você também pode forçar uma sincronização antes.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-113">You can also force a synchronization sooner.</span></span> <span data-ttu-id="8d8a5-114">Para obter mais informações, consulte [Forçar sincronização de diretórios](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span><span class="sxs-lookup"><span data-stu-id="8d8a5-114">For more information, see [Force Directory Synchronization](https://msdn.microsoft.com/en-us/library/azure/jj151771.aspx).</span></span>
    
<span data-ttu-id="8d8a5-115">Para atribuir a licença no Office 365, consulte [Atribuir licenças para o Office 365 para empresas](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="8d8a5-115">To assign the license in Office 365, see [Assign licenses for Office 365 for Business](https://support.office.com/en-us/article/Assign-or-unassign-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
## <a name="migrate-user-settings-to-skype-for-business-online"></a><span data-ttu-id="8d8a5-116">Migrar configurações do usuário para o Skype para negócios Online</span><span class="sxs-lookup"><span data-stu-id="8d8a5-116">Migrate user settings to Skype for Business Online</span></span>

<span data-ttu-id="8d8a5-117">Antes de começar a migração de usuários para o Skype for Business Online, você deve fazer o backup dos dados de usuário associados com as contas a serem movidos.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-117">Before you start migrating users to Skype for Business Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="8d8a5-118">Nem todos os dados de usuário são movidos junto com a conta.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-118">Not all user data is moved with the user account.</span></span> <span data-ttu-id="8d8a5-119">Para obter informações, consulte [requisitos de Backup e restauração: dados](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span><span class="sxs-lookup"><span data-stu-id="8d8a5-119">For information, see [Backup and Restoration Requirements: Data](http://technet.microsoft.com/library/ecfb8e4d-cb4f-476d-9772-4486bd683c04.aspx).</span></span>
  
<span data-ttu-id="8d8a5-p104">As configurações do usuário são movidas com a conta do usuário. Algumas configurações locais não são movidas com a conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-p104">User settings are moved with the user account. Some on-premises settings are not moved with the user account.</span></span>
  
## <a name="move-pilot-users-to-skype-for-business-online"></a><span data-ttu-id="8d8a5-122">Mover usuários piloto para Skype para negócios Online</span><span class="sxs-lookup"><span data-stu-id="8d8a5-122">Move pilot users to Skype for Business Online</span></span>

<span data-ttu-id="8d8a5-123">Antes de começar mover usuários para Skype para Business Online, convém mover alguns usuários piloto para confirmar que o ambiente está configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-123">Before you begin to move users to Skype for Business Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="8d8a5-124">Será então possível verificar se os recursos e serviços funcionam conforme o esperado antes de tentar mover usuários adicionais.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-124">You can then verify that the features and services function as expected before attempting to move additional users.</span></span>
  
<span data-ttu-id="8d8a5-125">Para mover um usuário local para seu Skype para locatário Business Online, execute os cmdlets a seguir no Skype do Shell de gerenciamento do servidor de negócios, utilizando as credenciais de administrador para o seu locatário do Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-125">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="8d8a5-126">Substitua "username@contoso.com" pela informação do usuário que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-126">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds 
```

## <a name="move-users-to-skype-for-business-online"></a><span data-ttu-id="8d8a5-127">Mover usuários para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8d8a5-127">Move users to Skype for Business Online</span></span>

<span data-ttu-id="8d8a5-128">Você pode mover vários usuários usando o cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) com o parâmetro - Filter para selecionar os usuários com uma propriedade específica atribuída às contas de usuário, como RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-128">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet with the -Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="8d8a5-129">Em seguida, você pode direcionar os usuários retornados para o cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-129">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser?view=skype-ps) cmdlet, as shown in the following example.</span></span>
  
```
Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds 
```

<span data-ttu-id="8d8a5-130">Você também pode usar o parâmetro - OU para recuperar todos os usuários na unidade Organizacional especificada, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-130">You can also use the -OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>
  
```
Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds 
```

## <a name="verify-online-user-settings-and-features"></a><span data-ttu-id="8d8a5-131">Verifique as configurações e os recursos do usuário online</span><span class="sxs-lookup"><span data-stu-id="8d8a5-131">Verify online user settings and features</span></span>

<span data-ttu-id="8d8a5-132">Você pode verificar que o usuário foi movido com sucesso das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="8d8a5-132">You can verify that the user was moved successfully in the following ways:</span></span>
  
- <span data-ttu-id="8d8a5-p108">Exibir o status do usuário no Painel de Controle do Skype for Business Online. O indicador visual para usuários no local e online é diferente.</span><span class="sxs-lookup"><span data-stu-id="8d8a5-p108">View the status of the user in the Skype for Business Online Control Panel. The visual indicator for on-premises users and online users is different.</span></span>
    
- <span data-ttu-id="8d8a5-135">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8d8a5-135">Run the following cmdlet:</span></span>
    
  ```
  Get-CsUser -Identity
  ```


