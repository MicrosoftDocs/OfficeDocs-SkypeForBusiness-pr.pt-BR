---
title: Excluir uma coleção existente de definições de configuração de CDR no Skype for Business Server
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
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Resumo: saiba como remover as configurações de configuração de CDR no Skype for Business Server.'
ms.openlocfilehash: d9e990018d97f8e631f3a95718a76aa83d7d619e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818021"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="7372e-103">Excluir uma coleção existente de definições de configuração de CDR no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7372e-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="7372e-104">**Resumo:** Saiba como remover as configurações de configuração de CDR no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7372e-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="7372e-p101">O registro de detalhes das chamadas (CDR) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.</span><span class="sxs-lookup"><span data-stu-id="7372e-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="7372e-107">Quando você instala o Skype for Business Server, uma única coleção global de definições de configuração de CDR é criada para você.</span><span class="sxs-lookup"><span data-stu-id="7372e-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="7372e-108">Os administradores têm a opção de criar coleções de definições personalizadas que podem ser aplicadas a sites individuais.</span><span class="sxs-lookup"><span data-stu-id="7372e-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="7372e-109">Através do design, as definições configuradas no escopo do site têm precedência sobre aquelas no escopo global.</span><span class="sxs-lookup"><span data-stu-id="7372e-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="7372e-110">Se você excluir as definições no escopo do site, então o CDR será gerenciado nesse site usando as definições globais.</span><span class="sxs-lookup"><span data-stu-id="7372e-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="7372e-111">Observe que você também pode "excluir" as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="7372e-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="7372e-112">No entanto, as definições globais não serão realmente removidas.</span><span class="sxs-lookup"><span data-stu-id="7372e-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="7372e-113">Em vez disso, todas as propriedades nessa coleção serão redefinidas para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="7372e-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="7372e-114">Por exemplo, como padrão, a limpeza está ativada em uma coleção de definições de configuração de CDR.</span><span class="sxs-lookup"><span data-stu-id="7372e-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="7372e-115">Suponha que você modifique a coleção global de forma que a limpeza seja desativada.</span><span class="sxs-lookup"><span data-stu-id="7372e-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="7372e-116">Se você excluir as definições globais mais tarde, todas as propriedades serão redefinidas para seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="7372e-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="7372e-117">Neste caso, isso significa que a limpeza será novamente ativada.</span><span class="sxs-lookup"><span data-stu-id="7372e-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="7372e-118">Você pode remover as configurações de configuração de CDR usando o painel de controle do Skype for Business Server ou o cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="7372e-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="7372e-119">Para remover as configurações de configuração de CDR com o painel de controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7372e-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7372e-120">No painel de controle do Skype for Business Server, clique em **monitoramento e arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="7372e-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="7372e-p104">Na guia **Registro de Detalhes de Chamada**, selecione a coleção (ou coleções) de definições de CDR a ser removida. Para selecionar várias coleções, clique na primeira coleção, mantenha pressionada a tecla CTRL e clique em mais coleções.</span><span class="sxs-lookup"><span data-stu-id="7372e-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="7372e-123">Clique em **Editar** e então em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="7372e-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="7372e-124">Na caixa de diálogo painel de controle do Skype for Business Server, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7372e-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7372e-125">Como remover as definições de configuração de CDR usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7372e-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7372e-126">Você pode excluir as configurações de registro de detalhes da chamada usando o Windows PowerShell e o cmdlet **Remove-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="7372e-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="7372e-127">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7372e-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7372e-128">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="7372e-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="7372e-129">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7372e-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="7372e-130">Para remover uma coleção especificada das definições de configuração de CDR</span><span class="sxs-lookup"><span data-stu-id="7372e-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="7372e-131">Este comando remove as definições de configuração de CDR aplicadas ao site da Redmond:</span><span class="sxs-lookup"><span data-stu-id="7372e-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="7372e-132">Para remover todas as definições de configuração de CDR aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="7372e-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="7372e-133">Este comando remove todas as definições de configuração de CDR aplicadas ao escopo do site:</span><span class="sxs-lookup"><span data-stu-id="7372e-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="7372e-134">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="7372e-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7372e-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="7372e-135">See also</span></span>

[<span data-ttu-id="7372e-136">Limpar manualmente a gravação de detalhes da chamada e os bancos de dados de qualidade da experiência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7372e-136">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

