---
title: Configurar opções de arquivamento para lidar com falhas no Skype for Business Server
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 'Resumo: Saiba como bloquear sessões de IM e conferência no caso de uma falha do Skype for Business Server que impeça o arquivamento.'
ms.openlocfilehash: 9a39c5f54fbdd4a738f4e67e7f70ff199a204672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817671"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="bbe27-103">Configurar opções de arquivamento para lidar com falhas no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bbe27-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="bbe27-104">**Resumo:** Saiba como bloquear IM e sessões de conferência no caso de uma falha do Skype for Business Server que impeça o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="bbe27-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="bbe27-105">Se o arquivamento for um requisito para sua organização, você poderá bloquear sessões de IM e conferência em caso de falha do Skype for Business Server que impeça o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="bbe27-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="bbe27-106">Isso algumas vezes é chamado de modo crítico.</span><span class="sxs-lookup"><span data-stu-id="bbe27-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="bbe27-107">Por exemplo, se houver um problema com um serviço de armazenamento, as IMs serão bloqueadas para usuários cujas comunicações estão habilitadas para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="bbe27-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="bbe27-108">As mensagens instantâneas e conferências são recuperadas automaticamente após as falhas serem corrigidas.</span><span class="sxs-lookup"><span data-stu-id="bbe27-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="bbe27-109">Configurar o modo crítico usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="bbe27-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="bbe27-110">Para especificar se as sessões de comunicação devem ser permitidas em caso de falha que impeça o arquivamento:</span><span class="sxs-lookup"><span data-stu-id="bbe27-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="bbe27-111">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="bbe27-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="bbe27-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bbe27-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="bbe27-113">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="bbe27-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="bbe27-114">Clique no nome da configuração global, de site ou de pool apropriada na lista de configurações de arquivamento, clique em **Editar** e em **Mostrar detalhes.**</span><span class="sxs-lookup"><span data-stu-id="bbe27-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="bbe27-115">Para definir como o arquivamento se comporta quando ocorre uma falha, marque ou desmarque a caixa de seleção **Bloquear sessões de conferência da Web e mensagens instantâneas (IM) se o arquivamento falhar**.</span><span class="sxs-lookup"><span data-stu-id="bbe27-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="bbe27-116">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="bbe27-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="bbe27-117">Configurar o modo crítico usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbe27-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="bbe27-118">Também é possível especificar se as sessões de comunicação devem ser permitidas em caso de falha que impeça o arquivamento usando o cmdlet **Set-CsArchivingConfiguration** com o parâmetro BlockOnArchiveFailure.</span><span class="sxs-lookup"><span data-stu-id="bbe27-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="bbe27-119">Por exemplo, o seguinte comando desabilita as comunicações no caso de uma falha de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="bbe27-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="bbe27-120">O próximo comando habilita as comunicações no caso de uma falha de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="bbe27-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="bbe27-121">Para obter mais informações, consulte o tópico de Ajuda para o cmdlet [Set-CsArchivingConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="bbe27-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

