---
title: Excluir uma política de arquivamento existente no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Resumo: saiba como excluir uma política de arquivamento do Skype for Business Server.'
ms.openlocfilehash: 7d71fd9ca03f743cd51e0161cd1a3b437be43cb2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817611"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="d0f8b-103">Excluir uma política de arquivamento existente no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d0f8b-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="d0f8b-104">**Resumo:** Saiba como excluir uma política de arquivamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d0f8b-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="d0f8b-105">Você pode excluir uma política de usuário ou uma política de site, mas não a política global.</span><span class="sxs-lookup"><span data-stu-id="d0f8b-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="d0f8b-106">Se você excluir a política global, o Skype for Business Server redefinirá automaticamente a política para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="d0f8b-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="d0f8b-107">Excluir uma política usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="d0f8b-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="d0f8b-108">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="d0f8b-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="d0f8b-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d0f8b-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d0f8b-110">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="d0f8b-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="d0f8b-111">Na lista de políticas de arquivamento, clique na política de usuário ou site que deseja excluir, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="d0f8b-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="d0f8b-112">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d0f8b-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="d0f8b-113">Excluir uma política usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0f8b-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="d0f8b-114">Você também pode excluir políticas de arquivamento usando o cmdlet **Remove-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="d0f8b-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="d0f8b-115">Por exemplo, o comando a seguir exclui a política com a Identidade site:Redmond.</span><span class="sxs-lookup"><span data-stu-id="d0f8b-115">For example, the following command deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="d0f8b-116">Quando uma política configurada no nível do site é excluída, os usuários gerenciados anteriormente pela política de site serão governados automaticamente pela política de arquivamento global:</span><span class="sxs-lookup"><span data-stu-id="d0f8b-116">When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="d0f8b-117">Este comando remove todas as políticas de arquivamento aplicadas ao nível por usuário:</span><span class="sxs-lookup"><span data-stu-id="d0f8b-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="d0f8b-118">Este comando remove todas as políticas de arquivamento onde o arquivamento interno foi desativado:</span><span class="sxs-lookup"><span data-stu-id="d0f8b-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="d0f8b-119">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsArchivingPolicy.](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d0f8b-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
