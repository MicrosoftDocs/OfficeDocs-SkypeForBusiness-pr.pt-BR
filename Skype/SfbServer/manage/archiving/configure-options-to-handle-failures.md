---
title: Configurar opções de arquivamento para lidar com falhas no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Resumo: saiba como bloquear sessões de mensagens instantâneas e de conferência no caso de uma falha do Skype for Business Server que impediria o arquivamento.'
ms.openlocfilehash: ed8a59a8c19ace9a83b699e1b69515f52c3af010
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992748"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="9b03a-103">Configurar opções de arquivamento para lidar com falhas no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9b03a-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="9b03a-104">**Resumo:** Saiba como bloquear mensagens de chat e de conferência no caso de uma falha do Skype for Business Server que impede o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="9b03a-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="9b03a-105">Se o arquivamento for um requisito para sua organização, você poderá bloquear as sessões de chat e de conferência no caso de uma falha do Skype for Business Server que impediria o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="9b03a-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="9b03a-106">Isso às vezes é chamado de modo crítico.</span><span class="sxs-lookup"><span data-stu-id="9b03a-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="9b03a-107">Por exemplo, se houver um problema com um serviço de armazenamento, o IM seria bloqueado para usuários cujas comunicações estivessem habilitadas para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="9b03a-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="9b03a-108">Tanto sessões de IM quanto de conferência são restauradas após a correção das falhas.</span><span class="sxs-lookup"><span data-stu-id="9b03a-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="9b03a-109">Configurar modo crítico usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="9b03a-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="9b03a-110">Para especificar se sessões de comunicação devem ser permitidas caso uma falha impossibilite o arquivamento:</span><span class="sxs-lookup"><span data-stu-id="9b03a-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="9b03a-111">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="9b03a-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="9b03a-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9b03a-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9b03a-113">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="9b03a-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="9b03a-114">Clique no nome da configuração apropriada de pool, site ou global na lista de configurações de arquivamento, clique em **Editar** e depois clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="9b03a-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="9b03a-115">Para definir como o arquivamento se comporta quando ocorre uma falha, marque ou desmarque a caixa de seleção **Bloquear sessões de webconferência e mensagens instantâneas (IM) se o arquivamento falhar**.</span><span class="sxs-lookup"><span data-stu-id="9b03a-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="9b03a-116">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9b03a-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="9b03a-117">Configurar modo crítico usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b03a-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="9b03a-118">Você também pode especificar se as sessões de comunicação devem ser permitidas em caso de falha que impedem o arquivamento usando o cmdlet **set-CsArchivingConfiguration** com o parâmetro BlockOnArchiveFailure.</span><span class="sxs-lookup"><span data-stu-id="9b03a-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="9b03a-119">Por exemplo, o comando a seguir desabilita as comunicações no caso de uma falha de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="9b03a-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="9b03a-120">O seguinte comando habilita as comunicações em caso de falha no arquivamento:</span><span class="sxs-lookup"><span data-stu-id="9b03a-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="9b03a-121">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9b03a-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

