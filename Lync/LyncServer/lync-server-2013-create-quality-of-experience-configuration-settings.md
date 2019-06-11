---
title: 'Lync Server 2013: criar definições de configuração de qualidade de experiência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 947fb50c057fdcc04fe7d1b30d25bc8f5a5f4a02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="9df23-102">Criar definições de configuração de qualidade de experiência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9df23-102">Create Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9df23-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9df23-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9df23-p101">As métricas de Qualidade da Experiência (QoE) rastreiam a qualidade das chamadas de áudio e vídeo feitas na organização, inclusive o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de tremulação (diferenças no atraso de pacotes). Essas métricas são armazenadas em um banco de dados separado de outros dados (como registros de detalhes das chamadas), permitindo a habilitação e desabilitação da QoE, independente de outros registros de dados.</span><span class="sxs-lookup"><span data-stu-id="9df23-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="9df23-106">Ao instalar o Microsoft Lync Server 2013, uma única coleção global de definições de configuração de QoE é criada para você.</span><span class="sxs-lookup"><span data-stu-id="9df23-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="9df23-107">Os administradores também podem ter a opção de criar configurações personalizadas no escopo local.</span><span class="sxs-lookup"><span data-stu-id="9df23-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="9df23-108">Sempre que essas configurações do escopo do site forem usadas, elas prevalecerão sobre as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="9df23-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="9df23-109">Por exemplo, se você criar configurações de escopo de site para o site da cidade de Redmond, essas configurações (em vez das globais) serão usadas para gerenciar a QoE em Redmond.</span><span class="sxs-lookup"><span data-stu-id="9df23-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>

<span data-ttu-id="9df23-110">As definições de configuração de QoE podem ser criadas usando o painel de controle do Lync Server ou o cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="9df23-110">QoE configuration settings can be created by using either Lync Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span> <span data-ttu-id="9df23-111">Se você estiver usando o painel de controle do Lync Server para criar novas configurações, as seguintes opções estarão disponíveis para você:</span><span class="sxs-lookup"><span data-stu-id="9df23-111">If you are using Lync Server Control Panel to create new settings the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9df23-112">Configuração de UI</span><span class="sxs-lookup"><span data-stu-id="9df23-112">UI Setting</span></span></th>
<th><span data-ttu-id="9df23-113">Parâmetro do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9df23-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="9df23-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="9df23-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9df23-115">Nome</span><span class="sxs-lookup"><span data-stu-id="9df23-115">Name</span></span></p></td>
<td><p><span data-ttu-id="9df23-116">Identidade</span><span class="sxs-lookup"><span data-stu-id="9df23-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="9df23-p104">Identificador exclusivo das configurações a serem criadas. As configurações de QoE só podem ser criadas no escopo do site.</span><span class="sxs-lookup"><span data-stu-id="9df23-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9df23-119">Habilitar monitoramento de dados de QoE</span><span class="sxs-lookup"><span data-stu-id="9df23-119">Enable monitoring of QoE data</span></span></p></td>
<td><p><span data-ttu-id="9df23-120">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="9df23-120">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="9df23-121">Especifica se os registros QoE serão coletados e salvos no banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="9df23-121">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9df23-122">Habilitar limpeza de dados de QoE</span><span class="sxs-lookup"><span data-stu-id="9df23-122">Enable purging of QoE data</span></span></p></td>
<td><p><span data-ttu-id="9df23-123">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="9df23-123">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="9df23-124">Especifica se os registros serão apagados ao final do período definido na propriedade <strong>Manter dados de QoE por um período máximo de (dias)</strong>.</span><span class="sxs-lookup"><span data-stu-id="9df23-124">Specifies whether records will be purged after the duration defined in the <strong>Keep QoE data for a maximum duration (days)</strong> property has elapsed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9df23-125">Manter dados de QoE por um período máximo de (dias)</span><span class="sxs-lookup"><span data-stu-id="9df23-125">Keep QoE data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="9df23-126">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="9df23-126">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="9df23-p105">O número de dias durante os quais os dados de QoE permanecerão armazenados antes de serem apagados do banco de dados. Esse valor será ignorado se a limpeza estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="9df23-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="9df23-129">O cmdlet New-CsQoEConfiguration inclui opções adicionais que não estão disponíveis no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9df23-129">The New-CsQoEConfiguration cmdlet includes additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="9df23-130">Para obter mais informações, consulte o tópico da ajuda <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="9df23-130">For more information, see the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> help topic.</span></span>



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="9df23-131">Para criar definições de configuração de QoE usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="9df23-131">To create QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9df23-132">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9df23-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="9df23-133">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9df23-133">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="9df23-134">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9df23-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9df23-135">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9df23-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9df23-136">Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.</span><span class="sxs-lookup"><span data-stu-id="9df23-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="9df23-137">Na página **Dados de Qualidade da Experiência**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9df23-137">On the **Quality of Experience Data** page, click **New**.</span></span>

5.  <span data-ttu-id="9df23-138">Em **Selecionar um site**, clique no site ao qual a política deverá ser aplicada e depois em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9df23-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>

6.  <span data-ttu-id="9df23-139">Em **Criar Nova Configuração da Qualidade da Experiência**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9df23-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
      - <span data-ttu-id="9df23-140">Selecione **Habilitar monitoramento de dados de QoE** para habilitar o monitoramento.</span><span class="sxs-lookup"><span data-stu-id="9df23-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
      - <span data-ttu-id="9df23-141">Selecione **Habilitar limpeza de dados de QoE** para habilitar a limpeza.</span><span class="sxs-lookup"><span data-stu-id="9df23-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
      - <span data-ttu-id="9df23-142">Em **Manter dados de QoE por um período máximo de (dias)**, selecione o número máximo de dias durante os quais os registros de QoE deverão ser mantidos.</span><span class="sxs-lookup"><span data-stu-id="9df23-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>

7.  <span data-ttu-id="9df23-143">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9df23-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9df23-144">Criar definições de configuração de QoE usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9df23-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9df23-145">Você pode criar definições de configuração de QoE usando o Windows PowerShell e o cmdlet New-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9df23-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="9df23-146">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9df23-146">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9df23-147">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="9df23-147">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="9df23-148">Para criar um novo conjunto de configurações de QoE</span><span class="sxs-lookup"><span data-stu-id="9df23-148">To create a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="9df23-149">Este comando cria um novo conjunto de configurações de QoE que será aplicado ao site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="9df23-149">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="9df23-150">Para criar um conjunto de configurações de QoE com o monitoramento de QoE desabilitado</span><span class="sxs-lookup"><span data-stu-id="9df23-150">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="9df23-p110">Como nenhum parâmetro (além do parâmetro Identity obrigatório) foi especificado no comando anterior, o novo conjunto de configurações usará os valores padrão para todas as respectivas propriedades. Para criar configurações que usem outros valores de propriedade, basta incluir o parâmetro e o valor de parâmetro desejados. Por exemplo, para criar um conjunto de configurações de QoE que, por padrão, permita a desabilitação do registro de QoE, use um comando como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9df23-p110">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="9df23-154">Para especificar vários valores de propriedade ao criar um novo conjunto de configurações de QoE</span><span class="sxs-lookup"><span data-stu-id="9df23-154">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="9df23-p111">Você pode especificar vários valores de propriedade incluindo vários parâmetros. Por exemplo, o seguinte comando define as novas configurações para manter os dados de QoE por 30 dias e para apagar os dados antigos às 3:00 AM:</span><span class="sxs-lookup"><span data-stu-id="9df23-p111">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

<span data-ttu-id="9df23-157">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="9df23-157">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

