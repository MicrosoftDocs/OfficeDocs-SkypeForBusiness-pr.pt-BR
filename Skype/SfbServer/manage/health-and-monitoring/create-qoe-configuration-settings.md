---
title: Criar definições de configuração de qualidade da experiência no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Resumo: Saiba mais sobre configurações de Quality of Experience (QoE) no Skype para Business Server.'
ms.openlocfilehash: 678f57ba06008244bf9872ee44b26ea0c1e9a0f2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968192"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c11ce-103">Criar definições de configuração de qualidade da experiência no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="c11ce-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="c11ce-104">**Resumo:** Saiba mais sobre configurações de Quality of Experience (QoE) no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="c11ce-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="c11ce-p101">As métricas de Qualidade da Experiência (QoE) rastreiam a qualidade das chamadas de áudio e vídeo feitas na organização, inclusive o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de tremulação (diferenças no atraso de pacotes). Essas métricas são armazenadas em um banco de dados separado de outros dados (como registros de detalhes das chamadas), permitindo a habilitação e desabilitação da QoE, independente de outros registros de dados.</span><span class="sxs-lookup"><span data-stu-id="c11ce-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="c11ce-107">Quando você instala o Skype para Business Server, uma única coleção global de definições de configuração de QoE é criada para você.</span><span class="sxs-lookup"><span data-stu-id="c11ce-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="c11ce-108">Os administradores também podem ter a opção de criar configurações personalizadas no escopo local.</span><span class="sxs-lookup"><span data-stu-id="c11ce-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="c11ce-109">Sempre que essas configurações do escopo do site forem usadas, elas prevalecerão sobre as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="c11ce-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="c11ce-110">Por exemplo, se você criar configurações de escopo de site para o site da cidade de Redmond, essas configurações (em vez das globais) serão usadas para gerenciar a QoE em Redmond.</span><span class="sxs-lookup"><span data-stu-id="c11ce-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="c11ce-111">Configurações de QoE podem ser criadas usando qualquer um dos Skype para painel de controle do Business Server ou o cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c11ce-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="c11ce-112">Se você estiver usando o Skype para painel de controle do Business Server para criar novas configurações as seguintes opções estarão disponíveis para você:</span><span class="sxs-lookup"><span data-stu-id="c11ce-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="c11ce-113">**Configuração de UI**</span><span class="sxs-lookup"><span data-stu-id="c11ce-113">**UI setting**</span></span>|<span data-ttu-id="c11ce-114">**Parâmetro do PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c11ce-114">**PowerShell parameter**</span></span>|<span data-ttu-id="c11ce-115">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c11ce-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c11ce-116">Nome</span><span class="sxs-lookup"><span data-stu-id="c11ce-116">Name</span></span>  <br/> |<span data-ttu-id="c11ce-117">Identidade</span><span class="sxs-lookup"><span data-stu-id="c11ce-117">Identity</span></span>  <br/> |<span data-ttu-id="c11ce-p104">Identificador exclusivo das configurações a serem criadas. As configurações de QoE só podem ser criadas no escopo do site.</span><span class="sxs-lookup"><span data-stu-id="c11ce-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="c11ce-120">Habilitar monitoramento de dados de QoE</span><span class="sxs-lookup"><span data-stu-id="c11ce-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="c11ce-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="c11ce-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="c11ce-122">Especifica se os registros QoE serão coletados e salvos no banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="c11ce-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="c11ce-123">Habilitar limpeza de dados de QoE</span><span class="sxs-lookup"><span data-stu-id="c11ce-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="c11ce-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="c11ce-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="c11ce-125">Especifica se os registros serão apagados ao final do período definido na propriedade **Manter dados de QoE por um período máximo de (dias)**.</span><span class="sxs-lookup"><span data-stu-id="c11ce-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="c11ce-126">Manter dados de QoE por um período máximo de (dias)</span><span class="sxs-lookup"><span data-stu-id="c11ce-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="c11ce-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="c11ce-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="c11ce-p105">O número de dias durante os quais os dados de QoE permanecerão armazenados antes de serem apagados do banco de dados. Esse valor será ignorado se a limpeza estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="c11ce-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="c11ce-130">O cmdlet New-CsQoEConfiguration inclui opções adicionais não estão disponíveis no Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="c11ce-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="c11ce-131">Para obter mais informações, consulte o tópico de Ajuda [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c11ce-131">For more information, see the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c11ce-132">Para criar definições de configuração de QoE usando Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="c11ce-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c11ce-133">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c11ce-133">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="c11ce-134">Para obter detalhes, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="c11ce-134">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="c11ce-135">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="c11ce-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c11ce-136">Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.</span><span class="sxs-lookup"><span data-stu-id="c11ce-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="c11ce-137">Na página **Dados de Qualidade da Experiência**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c11ce-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="c11ce-138">Em **Selecionar um site**, clique no site ao qual a política deverá ser aplicada e depois em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c11ce-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="c11ce-139">Em **Criar Nova Configuração da Qualidade da Experiência**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c11ce-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="c11ce-140">Selecione **Habilitar monitoramento de dados de QoE** para habilitar o monitoramento.</span><span class="sxs-lookup"><span data-stu-id="c11ce-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="c11ce-141">Selecione **Habilitar limpeza de dados de QoE** para habilitar a limpeza.</span><span class="sxs-lookup"><span data-stu-id="c11ce-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="c11ce-142">Em **Manter dados de QoE por um período máximo de (dias)**, selecione o número máximo de dias durante os quais os registros de QoE deverão ser mantidos.</span><span class="sxs-lookup"><span data-stu-id="c11ce-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="c11ce-143">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c11ce-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c11ce-144">Criando definições de configuração de QoE usando Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c11ce-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c11ce-145">Você pode criar definições de configuração de QoE usando o Windows PowerShell e o cmdlet New-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="c11ce-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="c11ce-146">Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c11ce-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c11ce-147">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="c11ce-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="c11ce-148">O processo é o mesmo em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="c11ce-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="c11ce-149">Para criar um novo conjunto de configurações de QoE</span><span class="sxs-lookup"><span data-stu-id="c11ce-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="c11ce-150">Este comando cria um novo conjunto de configurações de QoE que será aplicado ao site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="c11ce-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="c11ce-151">Para criar um conjunto de configurações de QoE com o monitoramento de QoE desabilitado</span><span class="sxs-lookup"><span data-stu-id="c11ce-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="c11ce-p109">Como nenhum parâmetro (além do parâmetro Identity obrigatório) foi especificado no comando anterior, o novo conjunto de configurações usará os valores padrão para todas as respectivas propriedades. Para criar configurações que usem outros valores de propriedade, basta incluir o parâmetro e o valor de parâmetro desejados. Por exemplo, para criar um conjunto de configurações de QoE que, por padrão, permita a desabilitação do registro de QoE, use um comando como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c11ce-p109">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="c11ce-155">Para especificar vários valores de propriedade ao criar um novo conjunto de configurações de QoE</span><span class="sxs-lookup"><span data-stu-id="c11ce-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="c11ce-p110">Você pode especificar vários valores de propriedade incluindo vários parâmetros. Por exemplo, o seguinte comando define as novas configurações para manter os dados de QoE por 30 dias e para apagar os dados antigos às 3:00 AM:</span><span class="sxs-lookup"><span data-stu-id="c11ce-p110">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="c11ce-158">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c11ce-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  

