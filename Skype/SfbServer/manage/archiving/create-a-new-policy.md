---
title: Criar uma nova política de arquivamento no Skype for Business Server
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
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Resumo: saiba como criar uma nova política de arquivamento para o Skype for Business Server.'
ms.openlocfilehash: fe3a80708d3810a085f1814e6d16ff3cd4c6057c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095415"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="f2d7a-103">Criar uma nova política de arquivamento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f2d7a-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="f2d7a-104">**Resumo:** Saiba como criar uma nova política de arquivamento para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="f2d7a-105">Você pode criar novas políticas de arquivamento usando o Painel de Controle ou usando Windows PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="f2d7a-106">Criar uma nova política de arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="f2d7a-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="f2d7a-107">Para criar uma nova política de arquivamento usando o Painel de Controle:</span><span class="sxs-lookup"><span data-stu-id="f2d7a-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="f2d7a-108">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="f2d7a-109">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f2d7a-110">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="f2d7a-111">Clique em **Nova** e execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="f2d7a-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="f2d7a-112">Para criar uma política de arquivamento no nível do site, clique em Política de **site** e, em Selecionar um **site,** clique no site ao qual a política deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="f2d7a-113">Para criar uma política de arquivamento em nível do usuário, clique em **Política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="f2d7a-114">Em **Nova Política de Arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f2d7a-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="f2d7a-115">Em **Nome**, especifique um nome para a nova política (por exemplo, externalContoso).</span><span class="sxs-lookup"><span data-stu-id="f2d7a-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="f2d7a-116">Em **Descrição**, forneça os detalhes sobre a política (por exemplo, a política de arquivamento de usuário externo da Contoso).</span><span class="sxs-lookup"><span data-stu-id="f2d7a-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="f2d7a-117">Para controlar o arquivamento das comunicações com usuários internos, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="f2d7a-118">Para controlar o arquivamento das comunicações com usuários externos, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="f2d7a-119">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f2d7a-120">As configurações de uma política de usuário somente se aplicam aos usuários e grupos de usuários específicos aos quais você aplicar a política.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="f2d7a-121">Para obter detalhes, [consulte Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="f2d7a-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="f2d7a-122">Criar uma nova política de arquivamento usando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f2d7a-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="f2d7a-123">Você também pode criar novas políticas de arquivamento usando o cmdlet **Windows PowerShell New-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="f2d7a-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="f2d7a-124">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsArchivingPolicy.](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="f2d7a-124">For more information, see the help topic for the [New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="f2d7a-125">Para criar uma nova política de arquivamento no nível do site</span><span class="sxs-lookup"><span data-stu-id="f2d7a-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="f2d7a-126">Este comando cria uma nova política de arquivamento para o site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="f2d7a-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="f2d7a-127">Para criar uma nova política de arquivamento no nível por usuário</span><span class="sxs-lookup"><span data-stu-id="f2d7a-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="f2d7a-128">Para criar uma nova política de arquivamento no nível por usuário, basta especificar uma Identidade exclusiva ao criar a política:</span><span class="sxs-lookup"><span data-stu-id="f2d7a-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="f2d7a-129">Para criar uma nova política de arquivamento que habilita o arquivamento de sessões de comunicação internas</span><span class="sxs-lookup"><span data-stu-id="f2d7a-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="f2d7a-130">Como nenhum parâmetros foi especificado (além do parâmetro obrigatório Identity) nos comandos anteriores, as novas políticas utilizarão os valores padrão para todas as suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="f2d7a-131">Para criar políticas que utilizam valores de propriedades diferentes, basta incluir o parâmetro e o valor de parâmetro apropriado.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="f2d7a-132">Por exemplo, o comando a seguir cria uma política de arquivamento que permite o arquivamento de sessões internas de mensagens instantâneas:</span><span class="sxs-lookup"><span data-stu-id="f2d7a-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="f2d7a-133">Para criar uma nova política de arquivamento que habilita o arquivamento de sessões de comunicação internas e externas</span><span class="sxs-lookup"><span data-stu-id="f2d7a-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="f2d7a-134">Vários valores de propriedade podem ser modificados, incluindo vários parâmetros.</span><span class="sxs-lookup"><span data-stu-id="f2d7a-134">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="f2d7a-135">Por exemplo, esse comando configura a nova política para arquivar sessões internas e externas de mensagens instantâneas:</span><span class="sxs-lookup"><span data-stu-id="f2d7a-135">For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```