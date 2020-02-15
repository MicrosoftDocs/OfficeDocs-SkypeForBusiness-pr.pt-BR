---
title: 'Lync Server 2013: criar ou modificar um conjunto de definições de configuração de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 234225364c8701432271c2cf5a48c9bb6d403103
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="e9283-102">Criar ou modificar um conjunto de definições de configuração de CDR no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9283-102">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9283-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e9283-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e9283-p101">O registro de detalhes da chamada (CDR) permite rastrear o uso de coisas como sessões de mensagem instantânea ponto a ponto, chamadas de telefone Protocolo Voz por Internet (VoIP) e chamadas de conferência. Este dados de uso inclui informações sobre quem ligou para quem, quando realizou a ligação e quanto tempo foi a conversa.</span><span class="sxs-lookup"><span data-stu-id="e9283-p101">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="e9283-106">Ao instalar o Microsoft Lync Server 2013, um único conjunto global de definições de configuração de CDR é criado para você.</span><span class="sxs-lookup"><span data-stu-id="e9283-106">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="e9283-107">Os administradores também podem ter a opção de criar configurações personalizadas no escopo local.</span><span class="sxs-lookup"><span data-stu-id="e9283-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="e9283-108">Sempre que estas configurações de escopo local são usadas, elas têm precedência sobre as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="e9283-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="e9283-109">Por exemplo, se você criar configurações de escopo local para o local Redmond, estas configurações (ao invés das configurações globais) serão usadas para gerenciar CDR em Redmond.</span><span class="sxs-lookup"><span data-stu-id="e9283-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="e9283-110">Você pode criar definições de configuração de CDR usando o painel de controle do Lync Server ou o cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="e9283-110">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="e9283-111">Você pode usar o painel de controle do Lync Server ou o cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) para modificar as configurações existentes.</span><span class="sxs-lookup"><span data-stu-id="e9283-111">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="e9283-112">Se você estiver usando o painel de controle do Lync Server para criar ou modificar as configurações, as seguintes opções estarão disponíveis para você:</span><span class="sxs-lookup"><span data-stu-id="e9283-112">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9283-113">Configuração de UI</span><span class="sxs-lookup"><span data-stu-id="e9283-113">UI Setting</span></span></th>
<th><span data-ttu-id="e9283-114">Parâmetro do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9283-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="e9283-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="e9283-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9283-116">Nome</span><span class="sxs-lookup"><span data-stu-id="e9283-116">Name</span></span></p></td>
<td><p><span data-ttu-id="e9283-117">Identidade</span><span class="sxs-lookup"><span data-stu-id="e9283-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="e9283-p104">Identificador exclusivo das definições de configuração CDR sendo criada. Estas configurações podem ser criadas apenas no escopo local.</span><span class="sxs-lookup"><span data-stu-id="e9283-p104">Unique identifier for the CDR configuration settings being created. These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9283-120">Habilitar monitoramento de CDRs</span><span class="sxs-lookup"><span data-stu-id="e9283-120">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="e9283-121">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="e9283-121">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="e9283-122">Indica se o CDR está ou não habilitado.</span><span class="sxs-lookup"><span data-stu-id="e9283-122">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9283-123">Habilitar exclusão de CDRs</span><span class="sxs-lookup"><span data-stu-id="e9283-123">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="e9283-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="e9283-124">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="e9283-125">Indica se os registros CDR serão ou não periodicamente excluídos do banco de dados de CDR.</span><span class="sxs-lookup"><span data-stu-id="e9283-125">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9283-126">Manter CDRs pela duração máxima (dias)</span><span class="sxs-lookup"><span data-stu-id="e9283-126">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="e9283-127">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="e9283-127">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="e9283-p105">Indica o número de dias que os registros CDR serão mantidos no banco de dados de CDR. Qualquer registro anterior ao número de dias especificado será automaticamente excluído. (Observe que excluir ocorrerá apenas se a exclusão tiver habilitada.)</span><span class="sxs-lookup"><span data-stu-id="e9283-p105">Indicates the number of days that CDR records will be kept in the CDR database. Any records older than the specified number of days will automatically be deleted. (Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9283-131">Manter os dados do relatório de erro pela duração máxima (dias)</span><span class="sxs-lookup"><span data-stu-id="e9283-131">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="e9283-132">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="e9283-132">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="e9283-p106">Indica o número de dias que os relatórios de erros do CDR são mantidos. Qualquer relatório mais antigo do que o número de dias especificado será automaticamente excluído. Os relatórios de CDR são relatórios de diagnósticos, carregados por aplicativos cliente.</span><span class="sxs-lookup"><span data-stu-id="e9283-p106">Indicates the number of days that CDR error reports are kept. Any reports older than the specified number of days will automatically be deleted. CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e9283-136">Os cmdlets New-CsCdrConfiguration e Set-CsCdrConfiguration incluem opções adicionais não disponíveis no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9283-136">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="e9283-137">Consulte os tópicos de ajuda <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">set-CsCdrConfiguration</A> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e9283-137">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="e9283-138">Para criar definições de configuração de CDR usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="e9283-138">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e9283-139">No painel de controle do Lync Server, clique em **monitoramento e arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="e9283-139">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="e9283-140">Na guia **registro de detalhes das chamadas** , clique em **novo**.</span><span class="sxs-lookup"><span data-stu-id="e9283-140">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="e9283-p108">Na caixa de diálogo **Selecionar um local**, selecione o local onde as novas definições de configuração devem ser criadas. Se a caixa de diálogo estiver vazia, isto significa que todos os seus locais já foram atribuídos com um conjunto de definições de configuração CDR. Cada local é limitado para um único conjunto. Neste caso, é possível excluir e recriar as configurações ou apenas modificar as configurações existentes.</span><span class="sxs-lookup"><span data-stu-id="e9283-p108">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created. If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings. Each site is limited to a single such collection. In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="e9283-145">Na caixa de diálogo **Nova configuração CDR**, faça as seleções desejadas e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e9283-145">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="e9283-146">Para modificar as definições de configuração de CDR existentes usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="e9283-146">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e9283-147">No painel de controle do Lync Server, clique em **monitoramento e arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="e9283-147">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="e9283-148">Clique duas vezes no conjunto de configurações a ser modificado ou selecione o conjunto, clique em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="e9283-148">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="e9283-149">Observe que você pode apenas modificar um único conjunto por vez.</span><span class="sxs-lookup"><span data-stu-id="e9283-149">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="e9283-150">Para fazer as mesmas alterações em várias coleções, use o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e9283-150">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="e9283-151">Na caixa de diálogo**Editar configuração de CDR**, certifique-se de fazer as seleções desejadas e clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e9283-151">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e9283-152">Criar definições de configuração de CDR usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9283-152">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e9283-153">Você pode criar definições de configuração de CDR também podem ser criadas usando o Windows PowerShell e o cmdlet **New-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e9283-153">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="e9283-154">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9283-154">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e9283-155">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="e9283-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="e9283-156">Para criar um novo conjunto de definições de configuração CDR</span><span class="sxs-lookup"><span data-stu-id="e9283-156">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="e9283-157">Este comando cria um novo conjunto de definições de configuração CDR aplicadas ao local Redmond:</span><span class="sxs-lookup"><span data-stu-id="e9283-157">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="e9283-158">Para criar um conjunto de definições de configuração CDR que desabilitam o registro de detalhes da chamada</span><span class="sxs-lookup"><span data-stu-id="e9283-158">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="e9283-p111">Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando anterior, o novo conjunto de definições de configurações usará os valores padrões para todas suas propriedades. Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e o valor de parâmetro adequado. Por exemplo, para criar um conjunto de definições de configuração de Detalhe da Chamada que, por padrão, permite desabilitar o registro de Detalhes da chamada, use um comando como este:</span><span class="sxs-lookup"><span data-stu-id="e9283-p111">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="e9283-162">Para especificar vários valores de propriedade ao criar um novo conjunto de definições de configuração CDR</span><span class="sxs-lookup"><span data-stu-id="e9283-162">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="e9283-p112">É possível modificar vários valores de propriedade incluindo vários parâmetros. Por exemplo, este comando define as novas configurações para manter registros de Detalhe da Chamada por 30 dias e relatórios de erro por 90 dias:</span><span class="sxs-lookup"><span data-stu-id="e9283-p112">You can modify multiple property values by including multiple parameters. For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="e9283-165">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="e9283-165">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

