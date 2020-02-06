---
title: Aplicar uma política de arquivamento aos usuários no Skype for Business Server
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
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Resumo: saiba como atribuir uma política de arquivamento aos usuários no Skype for Business Server.'
ms.openlocfilehash: 7be62aaf5b2b70108cb67a36559b242377d26117
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819003"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a><span data-ttu-id="b723e-103">Aplicar uma política de arquivamento aos usuários no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b723e-103">Apply an archiving policy to users in Skype for Business Server</span></span>

<span data-ttu-id="b723e-104">**Resumo:** Saiba como atribuir uma política de arquivamento aos usuários no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b723e-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server.</span></span>
  
<span data-ttu-id="b723e-105">Se você tiver criado uma ou mais políticas de usuário para arquivamento para usuários hospedados no Skype for Business Server, poderá implementar o suporte para arquivamento para usuários específicos aplicando as políticas apropriadas a esses usuários ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="b723e-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="b723e-106">Por exemplo, se você criar uma política para dar suporte ao arquivamento de comunicações internas, poderá aplicá-la a pelo menos um usuário ou grupo de usuários para dar suporte ao arquivamento das comunicações do Skype for Business Server do usuário.</span><span class="sxs-lookup"><span data-stu-id="b723e-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b723e-107">Se você tiver habilitado a integração do Microsoft Exchange para a implantação, as políticas de bloqueio do Exchange in loco controlarão se o arquivamento está habilitado para os usuários que estão hospedados no Exchange e que suas caixas de correio colocam no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="b723e-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="b723e-108">Para obter detalhes, consulte [planejar o arquivamento no Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [Configurar a integração com o armazenamento do Exchange para o Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="b723e-108">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="b723e-109">Aplicar uma política de usuário usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="b723e-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="b723e-110">Para aplicar uma política de usuário usando o Painel de Controle:</span><span class="sxs-lookup"><span data-stu-id="b723e-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="b723e-111">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b723e-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="b723e-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b723e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b723e-113">Na barra de navegação à esquerda, clique em **Usuários** e procure a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="b723e-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="b723e-114">Na tabela que lista os resultados da pesquisa, clique em conta de usuário, em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="b723e-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b723e-115">Em **Editar o usuário do Lync Server** na **política de arquivamento**, selecione a política de usuário de arquivamento que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="b723e-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b723e-116">As \*\* \<configurações\> automáticas\*\* aplicam as configurações de instalação do servidor padrão.</span><span class="sxs-lookup"><span data-stu-id="b723e-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="b723e-117">Essas configurações são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="b723e-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="b723e-118">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b723e-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="b723e-119">Aplicar uma política de usuário usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b723e-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="b723e-120">Você também pode aplicar uma política de usuário usando o cmdlet **Grant-CsArchivingPolicy** do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b723e-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="b723e-121">O comando a seguir atribui a política de arquivamento por usuário RedmondArchivingPolicy ao usuário Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="b723e-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="b723e-122">Este comando atribui a política de arquivamento por usuário RedmondArchivingPolicy a todos os usuários que possuem contas hospedadas no pool de registradores atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b723e-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="b723e-123">Para obter detalhes sobre o parâmetro de filtro usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="b723e-123">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="b723e-p105">O comando a seguir remove a política de arquivamento por usuário anteriormente atribuída a Ken Myer. Depois que a política de voz por usuário é removida, Ken Myer será automaticamente gerenciado usando uma política global ou, se existir, a política do seu site local. A política de site tem precedência sobre a política global.</span><span class="sxs-lookup"><span data-stu-id="b723e-p105">The following command removes any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="b723e-127">Para obter detalhes, consulte a documentação do cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="b723e-127">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

