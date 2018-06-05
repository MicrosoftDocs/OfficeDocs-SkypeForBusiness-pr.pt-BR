---
title: Alterar uma política de arquivamento existente no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Resumo: Saiba como alterar o usuário políticas de arquivamento para Skype para Business Server 2015.'
ms.openlocfilehash: 21774eaff8b58c585b347e1f657aa7afcc3b6106
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569404"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server-2015"></a><span data-ttu-id="dc9ad-103">Alterar uma política de arquivamento existente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc9ad-103">Change an existing archiving policy in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dc9ad-104">**Resumo:** Saiba como alterar o usuário políticas de arquivamento para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dc9ad-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="dc9ad-105">Quando você implanta Skype para Business Server 2015, você configurar políticas de arquivamento iniciais que determinam como o arquivamento é implementado para os usuários em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="dc9ad-105">When you first deploy Skype for Business Server 2015, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="dc9ad-106">Este tópico descreve como gerenciar e alterar as políticas.</span><span class="sxs-lookup"><span data-stu-id="dc9ad-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="dc9ad-107">Alterar políticas de arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="dc9ad-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="dc9ad-108">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="dc9ad-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="dc9ad-109">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="dc9ad-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="dc9ad-110">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="dc9ad-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="dc9ad-111">Na lista de políticas, faça um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="dc9ad-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="dc9ad-112">Para alterar a política da implantação inteira, clique em **Global** na lista de políticas, clique em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="dc9ad-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="dc9ad-113">Para alterar a política de um único site, clique no nome do site na lista de políticas, clique em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="dc9ad-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="dc9ad-114">Para alterar a política de um único usuário ou grupo de usuários, clique no nome do usuário ou do grupo de usuários na lista de políticas, clique em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="dc9ad-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="dc9ad-115">Na página **Editar política de arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="dc9ad-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="dc9ad-116">Para habilitar ou desabilitar o arquivamento interno da política, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.</span><span class="sxs-lookup"><span data-stu-id="dc9ad-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="dc9ad-117">Para habilitar ou desabilitar o arquivamento externo da política, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="dc9ad-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="dc9ad-118">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="dc9ad-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="dc9ad-119">As configurações de uma política do usuário se aplicam somente a usuários específicos e grupos de usuários aos quais você aplica a política.</span><span class="sxs-lookup"><span data-stu-id="dc9ad-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="dc9ad-120">Para obter detalhes, consulte [Aplicar uma política de arquivamento para usuários no Skype para Business Server 2015](apply-a-policy-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="dc9ad-120">For details, see [Apply an archiving policy to users in Skype for Business Server 2015](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="dc9ad-121">Alterar políticas de arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc9ad-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="dc9ad-122">Você também pode alterar políticas de arquivamento usando o cmdlet **Set-CsArchivingPolicy** do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc9ad-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="dc9ad-123">Habilitar políticas de arquivamento</span><span class="sxs-lookup"><span data-stu-id="dc9ad-123">Enable archiving policies</span></span>

<span data-ttu-id="dc9ad-124">Para habilitar o arquivamento de sessões de comunicações internas, defina o valor do parâmetro ArchiveInternal como Verdadeiro ($True):</span><span class="sxs-lookup"><span data-stu-id="dc9ad-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="dc9ad-125">Para habilitar o arquivamento de sessões de comunicações externas, defina o valor do parâmetro ArchiveExternal como Verdadeiro ($True):</span><span class="sxs-lookup"><span data-stu-id="dc9ad-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="dc9ad-126">Para habilitar o arquivamento de sessões de comunicações internas e externas, defina o valor dos parâmetros de ArchiveInternal e ArchiveExternal como verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="dc9ad-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="dc9ad-127">Desabilitar políticas de arquivamento</span><span class="sxs-lookup"><span data-stu-id="dc9ad-127">Disable archiving policies</span></span>

<span data-ttu-id="dc9ad-128">Para desabilitar o arquivamento como um todo, defina os parâmetros ArchiveInternal e ArchiveExternal como Falso ($False):</span><span class="sxs-lookup"><span data-stu-id="dc9ad-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```