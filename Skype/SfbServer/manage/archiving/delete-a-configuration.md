---
title: Excluir uma configuração de arquivamento no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Resumo: Saiba como excluir uma configuração de arquivamento no Skype para Business Server.'
ms.openlocfilehash: f8cb64cf7523cfaec26006560b4f77f39d904ead
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21018932"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="510bf-103">Excluir uma configuração de arquivamento no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="510bf-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="510bf-104">**Resumo:** Saiba como excluir uma configuração de arquivamento no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="510bf-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="510bf-p101">Você pode excluir uma configuração de site ou de pool, mas não a configuração global. Se você excluir a configuração global, ela será automaticamente redefinida para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="510bf-p101">You can delete a site configuration or pool configuration, but you cannot delete the global configuration. If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="510bf-107">Excluir uma configuração de arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="510bf-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="510bf-108">Para excluir uma configuração de arquivamento usando o Painel de Controle:</span><span class="sxs-lookup"><span data-stu-id="510bf-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="510bf-109">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="510bf-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="510bf-110">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="510bf-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="510bf-111">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="510bf-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="510bf-112">Na lista de configuração de arquivamento, clique na configuração de site ou pool que deseja excluir, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="510bf-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="510bf-113">Você também pode clicar na configuração global, mas selecione essa opção somente se quiser redefinir a configuração global com os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="510bf-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="510bf-114">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="510bf-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="510bf-115">Excluir uma configuração de arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="510bf-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="510bf-116">Você também pode excluir uma configuração de arquivamento usando o cmdlet **Remove-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="510bf-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="510bf-p102">Por exemplo, o seguinte comando remove as configurações de arquivamento aplicadas ao site Redmond. Quando uma política configurada no escopo do site é excluída, os usuários previamente gerenciados pela política de site passarão a ser governados pela política global de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="510bf-p102">For example, the following command removes the archiving configuration settings applied to the Redmond site. When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="510bf-119">O seguinte comando remove todas as definições de configuração de arquivamento aplicadas ao escopo do site:</span><span class="sxs-lookup"><span data-stu-id="510bf-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="510bf-120">O próximo comando remove todas as definições de configuração de arquivamento onde o arquivamento do Exchange foi desativado:</span><span class="sxs-lookup"><span data-stu-id="510bf-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="510bf-121">Você também pode usar o cmdlet **Remove-CsArchivingConfiguration** para redefinir as configurações globais com o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="510bf-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="510bf-122">Por exemplo, suponhamos que você tenha habilitado o arquivamento de sessões de IM no nível global; o seguinte comando redefinirá o valor para o padrão Nenhum, que desabilitará o arquivamento no nível global:</span><span class="sxs-lookup"><span data-stu-id="510bf-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="510bf-123">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="510bf-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>