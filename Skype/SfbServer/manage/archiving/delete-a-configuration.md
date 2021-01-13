---
title: Excluir uma configuração de arquivamento no Skype for Business Server
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Resumo: saiba como excluir uma configuração de arquivamento no Skype for Business Server.'
ms.openlocfilehash: a9d24a17ec769f5686502beb325e021c8b0f39c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817621"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="26017-103">Excluir uma configuração de arquivamento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="26017-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="26017-104">**Resumo:** Saiba como excluir uma configuração de arquivamento no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="26017-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="26017-105">Você pode excluir uma configuração de site ou configuração de pool, mas não pode excluir a configuração global.</span><span class="sxs-lookup"><span data-stu-id="26017-105">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="26017-106">Se você excluir a configuração global, ela será automaticamente redefinida para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="26017-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="26017-107">Excluir uma configuração de arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="26017-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="26017-108">Para excluir uma configuração de arquivamento usando o Painel de Controle:</span><span class="sxs-lookup"><span data-stu-id="26017-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="26017-109">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="26017-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="26017-110">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="26017-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="26017-111">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="26017-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="26017-112">Na lista de configuração de arquivamento, clique na configuração de site ou pool que deseja excluir, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="26017-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="26017-113">Você também pode clicar na configuração Global, mas escolha essa opção somente se quiser redefinir a configuração Global para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="26017-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="26017-114">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="26017-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="26017-115">Excluir uma configuração de arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="26017-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="26017-116">Você também pode excluir uma configuração de arquivamento usando o cmdlet **Remove-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="26017-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="26017-117">Por exemplo, o comando a seguir remove as definições de configuração de arquivamento aplicadas ao site Redmond.</span><span class="sxs-lookup"><span data-stu-id="26017-117">For example, the following command removes the archiving configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="26017-118">Quando uma política configurada no escopo do site é excluída, os usuários gerenciados anteriormente pela política de site serão governados automaticamente pela política de arquivamento global:</span><span class="sxs-lookup"><span data-stu-id="26017-118">When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="26017-119">O comando a seguir remove todas as definições de configuração de arquivamento aplicadas ao escopo de serviço:</span><span class="sxs-lookup"><span data-stu-id="26017-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="26017-120">O próximo comando remove todas as definições de configuração de arquivamento onde o arquivamento do Exchange foi desabilitado:</span><span class="sxs-lookup"><span data-stu-id="26017-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="26017-121">Você também pode usar o cmdlet **Remove-CsArchivingConfiguration** para redefinir as configurações globais para valores padrão.</span><span class="sxs-lookup"><span data-stu-id="26017-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="26017-122">Por exemplo, suponha que você tenha habilitado o arquivamento de sessões de IM no nível global; o comando a seguir redefini o valor para o padrão Nenhum, o que desabilitará o arquivamento no nível global:</span><span class="sxs-lookup"><span data-stu-id="26017-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="26017-123">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsArchivingConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="26017-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
