---
title: Configurar a gravação de detalhes da chamada e as configurações de qualidade da experiência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Resumo: saiba como configurar CDR e QoE no Skype for Business Server.'
ms.openlocfilehash: 3e0ff3e8dab09f38d71f9b5211f900e0f0e5fe9f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790049"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="92f5b-103">Configurar a gravação de detalhes da chamada e as configurações de qualidade da experiência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="92f5b-103">Configure call detail recording and Quality of Experience settings in Skype for Business Server</span></span>
 
<span data-ttu-id="92f5b-104">**Resumo:** Saiba como configurar CDR e QoE no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="92f5b-104">**Summary:** Learn how to configure CDR and QoE in Skype for Business Server.</span></span>
  
<span data-ttu-id="92f5b-105">Configurar o monitoramento de CDR e QoE usando relatórios do SQL Server Reporting Services para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="92f5b-105">Configure CDR and QoE monitoring using SQL Server Reporting Services reports for Skype for Business Server.</span></span>
  
## <a name="configure-cdr-and-qoe"></a><span data-ttu-id="92f5b-106">Configurar o CDR e QoE</span><span class="sxs-lookup"><span data-stu-id="92f5b-106">Configure CDR and QoE</span></span>

<span data-ttu-id="92f5b-107">Depois de associar um repositório de monitoramento a um pool de front-end, configurar o repositório de monitoramento e, em seguida, instalar e configurar os relatórios do SQL Server Reporting Services e do monitoramento, você pode gerenciar a CDR (gravação de detalhes de chamadas) e a qualidade da experiência (QoE) monitorando usando o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="92f5b-107">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Skype for Business Server Management Shell.</span></span> <span data-ttu-id="92f5b-108">Os cmdlets do Shell de gerenciamento do Skype for Business Server permitem habilitar e desabilitar o monitoramento CDR e/ou QoE para um determinado site ou para toda a implantação do Skype for Business Server; Isso pode ser feito com um comando tão simples quanto isto:</span><span class="sxs-lookup"><span data-stu-id="92f5b-108">Skype for Business Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Skype for Business Server deployment; that can be done with a command as simple as this:</span></span>
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

<span data-ttu-id="92f5b-109">Ao instalar o Skype for Business Server, você também instalará uma coleção predefinida de configurações globais de configuração para CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="92f5b-109">When you install Skype for Business Server, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="92f5b-110">Os valores padrão para algumas das configurações usados com mais frequência pelo Registro de Detalhes das Chamadas são exibidos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="92f5b-110">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>
  
|<span data-ttu-id="92f5b-111">**Propriedade**</span><span class="sxs-lookup"><span data-stu-id="92f5b-111">**Property**</span></span>|<span data-ttu-id="92f5b-112">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="92f5b-112">**Description**</span></span>|<span data-ttu-id="92f5b-113">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="92f5b-113">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="92f5b-114">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="92f5b-114">EnableCDR</span></span>  <br/> |<span data-ttu-id="92f5b-p103">Indica se o CDR está habilitado ou não. Se for True, todos os registros de CDR serão coletados e gravados no banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="92f5b-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="92f5b-117">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="92f5b-117">True</span></span>  <br/> |
|<span data-ttu-id="92f5b-118">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="92f5b-118">EnablePurging</span></span>  <br/> |<span data-ttu-id="92f5b-p104">Indica se os registros CDR serão excluídos periodicamente do banco de dados. Se for True, os registros serão excluídos após o período especificado pelas propriedades KeepCallDetailForDays (para registros CDR) e KeepErrorReportForDays (para erros de CDR). Se for Falso, os registros CDR serão mantidos indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="92f5b-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="92f5b-122">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="92f5b-122">True</span></span>  <br/> |
|<span data-ttu-id="92f5b-123">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="92f5b-123">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="92f5b-p105">Indica o número de dias durante os quais os registros CDR serão mantidos no banco de dados; quaisquer registros mais antigos do que o número especificado de dias serão automaticamente excluídos. No entanto, isso ocorrerá somente se a exclusão tiver sido habilitada.</span><span class="sxs-lookup"><span data-stu-id="92f5b-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="92f5b-126">KeepCallDetailForDays pode ser definido como qualquer valor inteiro entre 1 e 2.562 dias (aproximadamente sete anos).</span><span class="sxs-lookup"><span data-stu-id="92f5b-126">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span>  <br/> |<span data-ttu-id="92f5b-127">60 dias</span><span class="sxs-lookup"><span data-stu-id="92f5b-127">60 days</span></span>  <br/> |
|<span data-ttu-id="92f5b-128">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="92f5b-128">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="92f5b-129">Indica o número de dias durante os quais os relatórios de erro do CDR são mantidos; todos os relatórios anteriores ao número de dias especificado serão excluídos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="92f5b-129">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="92f5b-130">Os relatórios de erro CDR são relatórios de diagnóstico carregados por aplicativos cliente, como o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="92f5b-130">CDR error reports are diagnostic reports uploaded by client applications such as Skype for Business Server.</span></span>  <br/> <span data-ttu-id="92f5b-131">É possível definir essa propriedade como qualquer valor inteiro entre 1 e 2562 dias.</span><span class="sxs-lookup"><span data-stu-id="92f5b-131">You can set this property to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="92f5b-132">60 dias</span><span class="sxs-lookup"><span data-stu-id="92f5b-132">60 days</span></span>  <br/> |
   
<span data-ttu-id="92f5b-133">Da mesma forma, os valores padrão para as configurações de QoE selecionadas são exibidas nesta tabela:</span><span class="sxs-lookup"><span data-stu-id="92f5b-133">Similarly, default values for selected QoE settings are shown in this table:</span></span>
  
|<span data-ttu-id="92f5b-134">**Propriedade**</span><span class="sxs-lookup"><span data-stu-id="92f5b-134">**Property**</span></span>|<span data-ttu-id="92f5b-135">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="92f5b-135">**Description**</span></span>|<span data-ttu-id="92f5b-136">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="92f5b-136">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="92f5b-137">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="92f5b-137">EnableQoE</span></span>  <br/> |<span data-ttu-id="92f5b-p107">Indica se o monitoramento de QoE está habilitado ou não. Se for True, todos os registros de QoE serão coletados e gravados no banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="92f5b-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="92f5b-140">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="92f5b-140">True</span></span>  <br/> |
|<span data-ttu-id="92f5b-141">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="92f5b-141">EnablePurging</span></span>  <br/> |<span data-ttu-id="92f5b-p108">Indica se os registros de QoE serão excluídos periodicamente do banco de dados. Se for True, os registros serão excluídos após o período especificado pela propriedade KeepQoEDataForDays. Se for Falso, os registros de QoE serão mantidos indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="92f5b-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="92f5b-145">True</span><span class="sxs-lookup"><span data-stu-id="92f5b-145">True</span></span>  <br/> |
|<span data-ttu-id="92f5b-146">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="92f5b-146">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="92f5b-p109">Indica o número de dias durante os quais os registros de QoE serão mantidos no banco de dados; quaisquer registros mais antigos do que o número especificado de dias serão automaticamente excluídos. No entanto, isso ocorrerá somente se a exclusão tiver sido habilitada.</span><span class="sxs-lookup"><span data-stu-id="92f5b-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="92f5b-149">KeepCallDetailForDays pode ser definido como qualquer valor inteiro entre 1 e 2562 dias.</span><span class="sxs-lookup"><span data-stu-id="92f5b-149">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="92f5b-150">60 dias</span><span class="sxs-lookup"><span data-stu-id="92f5b-150">60 days</span></span>  <br/> |
   
<span data-ttu-id="92f5b-151">Se for necessário modificar essas configurações globais, você poderá fazer isso usando os cmdlets Set-CsCdrConfiguration e Set-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="92f5b-151">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets.</span></span> <span data-ttu-id="92f5b-152">Por exemplo, esse comando (executado no Shell de gerenciamento do Skype for Business Server) desabilita o monitoramento de CDR no escopo global; Isso é feito definindo a propriedade EnableCDR como false ($False):</span><span class="sxs-lookup"><span data-stu-id="92f5b-152">For example, this command (run from within the Skype for Business Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

<span data-ttu-id="92f5b-153">Observe que desabilitar o monitoramento não desassocia o repositório de monitoramento do pool de Front-Ends, nem desinstala ou afeta o banco de dados de monitoramento back-end.</span><span class="sxs-lookup"><span data-stu-id="92f5b-153">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="92f5b-154">Quando você usa o Shell de gerenciamento do Skype for Business Server para desabilitar o monitoramento de CDR ou QoE, você realmente interrompe o Skype for Business Server temporariamente de coletar e arquivar dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="92f5b-154">When you use Skype for Business Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Skype for Business Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="92f5b-155">Se você quiser, nesse caso, continuar a coleta e o arquivamento de dados CDR, tudo o que precisa fazer é definir a propriedade EnableCDR de volta para True ($True):</span><span class="sxs-lookup"><span data-stu-id="92f5b-155">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

<span data-ttu-id="92f5b-156">Da mesma maneira, esse comando desabilita a exclusão de registros QoE no escopo global:</span><span class="sxs-lookup"><span data-stu-id="92f5b-156">Similarly, this command disables the purging of QoE records at the global scope:</span></span>
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

<span data-ttu-id="92f5b-p112">Além das configurações globais, as configurações de CDR e QoE podem ser atribuídas ao escopo do site. Isso fornece flexibilidade de gerenciamento adicional quando se trata de monitoramento; por exemplo, um administrador pode habilitar o monitoramento de CDR para o site Redmond, mas desabilitar o monitoramento de CDR para o site Dublin. Para criar novas configurações de CDR no escopo do site, use um comando parecido com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="92f5b-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

<span data-ttu-id="92f5b-p113">Lembre-se de que as configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global. Por exemplo, suponha que o monitoramento CDR esteja habilitado no escopo global, mas desabilitado no escopo do site (para o site Redmond). Isso significa que as informações de registro de detalhe da chamada não serão arquivadas para usuários no site Redmond. No entanto, usuários em outros sites (ou seja, usuários gerenciados pelas configurações globais em vez das configurações do site Redmond) terão suas informações de registro de detalhe da chamada arquivadas.</span><span class="sxs-lookup"><span data-stu-id="92f5b-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>
  
<span data-ttu-id="92f5b-164">As novas configurações de QoE podem ser criadas no escopo do site usando um comando como este:</span><span class="sxs-lookup"><span data-stu-id="92f5b-164">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

<span data-ttu-id="92f5b-165">Para obter mais informações, digite os seguintes comandos no Shell de gerenciamento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="92f5b-165">For more information, type the following commands from within the Skype for Business Server Management Shell:</span></span>
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
