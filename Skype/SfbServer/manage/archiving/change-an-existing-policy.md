---
title: Alterar uma política de arquivamento existente no Skype for Business Server
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
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Resumo: Saiba como alterar as políticas de arquivamento do usuário para o Skype for Business Server.'
ms.openlocfilehash: 47c9d5938c22b93db48c96265831cbf24ecc24d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817701"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="8b064-103">Alterar uma política de arquivamento existente no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8b064-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="8b064-104">**Resumo:** Saiba como alterar as políticas de arquivamento do usuário para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8b064-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="8b064-105">Ao implantar pela primeira vez o Skype for Business Server, você configura políticas iniciais de arquivamento que determinam como o arquivamento é implementado para os usuários em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="8b064-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="8b064-106">Este tópico descreve como gerenciar e alterar políticas.</span><span class="sxs-lookup"><span data-stu-id="8b064-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="8b064-107">Alterar políticas de arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="8b064-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="8b064-108">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8b064-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="8b064-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8b064-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8b064-110">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="8b064-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="8b064-111">Na lista de políticas, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="8b064-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="8b064-112">Para alterar a política da implantação inteira, clique em **Global** na lista de políticas, clique em **Editar**, em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="8b064-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="8b064-113">Para alterar a política de um único site, clique no nome do site na lista de políticas, clique em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="8b064-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="8b064-114">Para alterar a política de um único usuário ou grupo de usuários, clique no nome do usuário ou do grupo de usuários na lista de políticas, clique em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="8b064-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="8b064-115">Na página **Editar política de arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8b064-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="8b064-116">Para habilitar ou desabilitar o arquivamento interno da política, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.</span><span class="sxs-lookup"><span data-stu-id="8b064-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="8b064-117">Para habilitar ou desabilitar o arquivamento externo da política, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="8b064-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="8b064-118">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8b064-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8b064-119">As configurações de uma política de usuário somente se aplicam aos usuários e grupos de usuários específicos aos quais você aplicar a política.</span><span class="sxs-lookup"><span data-stu-id="8b064-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="8b064-120">Para obter detalhes, [consulte Aplicar uma política de arquivamento aos usuários no Skype for Business Server.](apply-a-policy-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="8b064-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="8b064-121">Alterar políticas de arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b064-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="8b064-122">Você também pode alterar as políticas de arquivamento usando o cmdlet **Set-CsArchivingPolicy** do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b064-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="8b064-123">Habilitar políticas de arquivamento</span><span class="sxs-lookup"><span data-stu-id="8b064-123">Enable archiving policies</span></span>

<span data-ttu-id="8b064-124">Para habilitar o arquivamento de sessões de comunicação interna, de definir o valor do parâmetro ArchiveInternal como True ($True):</span><span class="sxs-lookup"><span data-stu-id="8b064-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="8b064-125">Para habilitar o arquivamento de sessões de comunicação externa, de definir o valor do parâmetro ArchiveExternal como True ($True):</span><span class="sxs-lookup"><span data-stu-id="8b064-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="8b064-126">Para habilitar o arquivamento de sessões de comunicação interna e externa, de definir o valor dos parâmetros ArchiveInternal e ArchiveExternal como True:</span><span class="sxs-lookup"><span data-stu-id="8b064-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="8b064-127">Desabilitar políticas de arquivamento</span><span class="sxs-lookup"><span data-stu-id="8b064-127">Disable archiving policies</span></span>

<span data-ttu-id="8b064-128">Para desabilitar completamente o arquivamento, de definir o valor dos parâmetros ArchiveInternal e ArchiveExternal como False ($False):</span><span class="sxs-lookup"><span data-stu-id="8b064-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
