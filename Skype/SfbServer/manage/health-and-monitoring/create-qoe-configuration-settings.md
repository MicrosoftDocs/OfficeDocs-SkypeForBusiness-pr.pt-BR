---
title: Criar configurações de Qualidade de Experiência no Skype for Business Server
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
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Resumo: Saiba mais sobre as configurações de QoE (Qualidade da Experiência) no Skype for Business Server.'
ms.openlocfilehash: 8cce0731112166ae232b6273b556d37d693564e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095345"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="50212-103">Criar configurações de Qualidade de Experiência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="50212-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="50212-104">**Resumo:** Saiba mais sobre as configurações de QoE (Qualidade da Experiência) no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="50212-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="50212-p101">Os atributos métricos da Qualidade da Experiência (QoE) rastreiam a qualidade das chamadas de áudio e vídeo feitas na organização, inclusive o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de "jitter" (diferenças no atraso de pacotes). Esses atributos métricos são armazenados em um banco de dados separado de outros dados (como registros de detalhes das chamadas), permitindo a habilitação e desabilitação do QoE, independentemente de outros registros de dados.</span><span class="sxs-lookup"><span data-stu-id="50212-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="50212-107">Quando você instala o Skype for Business Server, uma única coleção global de configurações de QoE é criada para você.</span><span class="sxs-lookup"><span data-stu-id="50212-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="50212-108">Os administradores também podem ter a opção de criar configurações personalizadas no escopo local.</span><span class="sxs-lookup"><span data-stu-id="50212-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="50212-109">Sempre que estas configurações de escopo local são usadas, elas têm precedência sobre as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="50212-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="50212-110">Por exemplo, se você criar configurações com escopo de site para o site redmond, essas configurações (em vez das configurações globais) serão usadas para gerenciar a QoE em Redmond.</span><span class="sxs-lookup"><span data-stu-id="50212-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="50212-111">As configurações de QoE podem ser criadas usando o Painel de Controle do Skype for Business Server ou o cmdlet [New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="50212-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="50212-112">Se você estiver usando o Painel de Controle do Skype for Business Server para criar novas configurações, as seguintes opções estarão disponíveis para você:</span><span class="sxs-lookup"><span data-stu-id="50212-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="50212-113">**Configuração da interface do usuário**</span><span class="sxs-lookup"><span data-stu-id="50212-113">**UI setting**</span></span>|<span data-ttu-id="50212-114">**Parâmetro PowerShell**</span><span class="sxs-lookup"><span data-stu-id="50212-114">**PowerShell parameter**</span></span>|<span data-ttu-id="50212-115">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="50212-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="50212-116">Nome</span><span class="sxs-lookup"><span data-stu-id="50212-116">Name</span></span>  <br/> |<span data-ttu-id="50212-117">Identidade</span><span class="sxs-lookup"><span data-stu-id="50212-117">Identity</span></span>  <br/> |<span data-ttu-id="50212-118">Identificador exclusivo para as configurações a serem criadas.</span><span class="sxs-lookup"><span data-stu-id="50212-118">Unique identifier for the settings to be created.</span></span> <span data-ttu-id="50212-119">As configurações de QoE só podem ser criadas no escopo do site.</span><span class="sxs-lookup"><span data-stu-id="50212-119">QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="50212-120">Habilitar o monitoramento de dados QoE</span><span class="sxs-lookup"><span data-stu-id="50212-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="50212-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="50212-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="50212-122">Especifica se os registros QoE serão coletados e salvos no banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="50212-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="50212-123">Habilitar a purgação de dados QoE</span><span class="sxs-lookup"><span data-stu-id="50212-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="50212-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="50212-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="50212-125">Especifica se os registros serão limpos após a duração definida na propriedade **Manter dados QoE por uma duração máxima (dias)** decorrido.</span><span class="sxs-lookup"><span data-stu-id="50212-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="50212-126">Manter dados QoE para duração máxima (dias)</span><span class="sxs-lookup"><span data-stu-id="50212-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="50212-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="50212-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="50212-128">O número de dias em que os dados de QoE serão armazenados antes de serem limpos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="50212-128">Number of days QoE data will be stored before being purged from the database.</span></span> <span data-ttu-id="50212-129">Esse valor será ignorado se a purgação estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="50212-129">This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="50212-130">O New-CsQoEConfiguration cmdlet inclui opções adicionais não disponíveis no Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="50212-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="50212-131">Para obter mais informações, consulte o [tópico de ajuda New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="50212-131">For more information, see the [New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="50212-132">Para criar configurações de QoE usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="50212-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="50212-133">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="50212-133">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="50212-134">Para obter detalhes, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="50212-134">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="50212-135">Abra uma janela do navegador e insira a URL do administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="50212-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="50212-136">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Dados da Qualidade da Experiência**.</span><span class="sxs-lookup"><span data-stu-id="50212-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="50212-137">Na página **Dados de Qualidade da Experiência,** clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="50212-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="50212-138">Em **Selecionar um Site,** clique no site ao qual a política deve ser aplicada e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="50212-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="50212-139">Em **Nova Configuração de Qualidade de Experiência,** faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="50212-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="50212-140">Selecione **Habilitar o monitoramento de dados QoE** para ativar o monitoramento.</span><span class="sxs-lookup"><span data-stu-id="50212-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="50212-141">Selecione **Habilitar a purgação de dados QoE** para ativar a purgação.</span><span class="sxs-lookup"><span data-stu-id="50212-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="50212-142">Em **Manter QoE para duração máxima (dias),** selecione o número máximo de dias em que os registros QoE devem ser mantidos.</span><span class="sxs-lookup"><span data-stu-id="50212-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="50212-143">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="50212-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="50212-144">Criando configurações de QoE usando Windows PowerShell Cmdlets</span><span class="sxs-lookup"><span data-stu-id="50212-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="50212-145">Você pode criar configurações de QoE usando o Windows PowerShell e o cmdlet New-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="50212-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="50212-146">Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50212-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="50212-147">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog "Início Rápido: Gerenciando o [Microsoft Lync Server 2010 usando o PowerShell Remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="50212-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="50212-148">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="50212-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="50212-149">Para criar uma nova coleção de configurações de QoE</span><span class="sxs-lookup"><span data-stu-id="50212-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="50212-150">Este comando cria uma nova coleção de definições de configuração de QoE aplicadas ao site redmond:</span><span class="sxs-lookup"><span data-stu-id="50212-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="50212-151">Para criar uma nova coleção de configurações de QoE em que o monitoramento de QoE está desabilitado</span><span class="sxs-lookup"><span data-stu-id="50212-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="50212-152">Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando anterior, o novo conjunto de definições de configurações usará os valores padrões para todas suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="50212-152">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="50212-153">Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e o valor de parâmetro adequado.</span><span class="sxs-lookup"><span data-stu-id="50212-153">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="50212-154">Por exemplo, para criar uma coleção de configurações de Qualidade de Experiência que, por padrão, permite desabilitar a gravação de QoE use um comando como este:</span><span class="sxs-lookup"><span data-stu-id="50212-154">For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="50212-155">Para especificar vários valores de propriedade ao criar uma nova coleção de configurações de QoE</span><span class="sxs-lookup"><span data-stu-id="50212-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="50212-156">Você pode vários valores de propriedade incluindo vários parâmetros.</span><span class="sxs-lookup"><span data-stu-id="50212-156">You can multiple property values by including multiple parameters.</span></span> <span data-ttu-id="50212-157">Por exemplo, este comando configura as novas configurações para manter os dados QoE por 30 dias e para limpar dados antigos às 3:00:</span><span class="sxs-lookup"><span data-stu-id="50212-157">For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="50212-158">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="50212-158">For more information, see the help topic for the [New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
