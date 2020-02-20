---
title: Configurando a gravação de detalhes da chamada e as configurações de qualidade da experiência
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0a7d6eb309c8afd13e671a12c98623c486b220d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="bae7a-102">Configurando a gravação de detalhes da chamada e as configurações de qualidade da experiência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bae7a-102">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bae7a-103">_**Última modificação do tópico:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="bae7a-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="bae7a-104">Depois de associar um repositório de monitoramento a um pool de front-ends, configurar o repositório de monitoramento e, em seguida, instalar e configurar o SQL Server Reporting Services e os relatórios de monitoramento, você poderá gerenciar o CDR (registro de detalhes de chamadas) e o QoE (qualidade da experiência) monitoramento usando o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bae7a-104">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Lync Server Management Shell.</span></span> <span data-ttu-id="bae7a-105">Os cmdlets do Shell de gerenciamento do Lync Server permitem habilitar e desabilitar o monitoramento de CDR e/ou QoE para um determinado site ou para toda a sua implantação do Lync Server; Isso pode ser feito com um comando tão simples quanto:</span><span class="sxs-lookup"><span data-stu-id="bae7a-105">Lync Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Lync Server deployment; that can be done with a command as simple as this:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

<span data-ttu-id="bae7a-106">Ao instalar o Microsoft Lync Server 2013, você também instalará um conjunto predefinido de definições de configuração global para CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="bae7a-106">When you install Microsoft Lync Server 2013, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="bae7a-107">Os valores padrão para algumas das configurações usados com mais frequência pelo Registro de Detalhes das Chamadas são exibidos na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="bae7a-107">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bae7a-108">Propriedade</span><span class="sxs-lookup"><span data-stu-id="bae7a-108">Property</span></span></th>
<th><span data-ttu-id="bae7a-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="bae7a-109">Description</span></span></th>
<th><span data-ttu-id="bae7a-110">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="bae7a-110">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bae7a-111">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="bae7a-111">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="bae7a-p103">Indica se o CDR está habilitado ou não. Se for Verdadeiro, todos os registros de CDR serão coletados e gravados no banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="bae7a-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="bae7a-114">True</span><span class="sxs-lookup"><span data-stu-id="bae7a-114">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae7a-115">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="bae7a-115">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="bae7a-p104">Indica se os registros CDR serão excluídos periodicamente do banco de dados. Se for Verdadeiro, os registros serão excluídos após o período especificado pelas propriedades KeepCallDetailForDays (para registros CDR) e KeepErrorReportForDays (para erros de CDR). Se for Falso, os registros CDR serão mantidos indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="bae7a-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="bae7a-119">True</span><span class="sxs-lookup"><span data-stu-id="bae7a-119">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bae7a-120">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="bae7a-120">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="bae7a-p105">Indica o número de dias durante os quais os registros CDR serão mantidos no banco de dados; quaisquer registros mais antigos do que o número especificado de dias serão automaticamente excluídos. No entanto, isso ocorrerá somente se a exclusão tiver sido habilitada.</span><span class="sxs-lookup"><span data-stu-id="bae7a-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="bae7a-123">KeepCallDetailForDays pode ser definido como qualquer valor inteiro entre 1 e 2562 dias (aproximadamente 7 anos).</span><span class="sxs-lookup"><span data-stu-id="bae7a-123">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span></p></td>
<td><p><span data-ttu-id="bae7a-124">60 dias</span><span class="sxs-lookup"><span data-stu-id="bae7a-124">60 days</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae7a-125">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="bae7a-125">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="bae7a-126">Indica o número de dias durante os quais esses relatórios de erro CDR serão mantidos; quaisquer relatórios mais antigos do que o número especificado de dias serão automaticamente excluídos.</span><span class="sxs-lookup"><span data-stu-id="bae7a-126">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="bae7a-127">Os relatórios de erros do CDR são relatórios de diagnóstico carregados por aplicativos cliente como o Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="bae7a-127">CDR error reports are diagnostic reports uploaded by client applications such as Microsoft Lync 2013.</span></span></p>
<p><span data-ttu-id="bae7a-128">É possível definir essa propriedade como qualquer valor inteiro entre 1 e 2562 dias.</span><span class="sxs-lookup"><span data-stu-id="bae7a-128">You can set this property to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="bae7a-129">60 dias</span><span class="sxs-lookup"><span data-stu-id="bae7a-129">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bae7a-130">Da mesma forma, os valores padrão para as configurações de QoE selecionadas são exibidas nesta tabela:</span><span class="sxs-lookup"><span data-stu-id="bae7a-130">Similarly, default values for selected QoE settings are shown in this table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bae7a-131">Propriedade</span><span class="sxs-lookup"><span data-stu-id="bae7a-131">Property</span></span></th>
<th><span data-ttu-id="bae7a-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="bae7a-132">Description</span></span></th>
<th><span data-ttu-id="bae7a-133">Valor padrão</span><span class="sxs-lookup"><span data-stu-id="bae7a-133">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bae7a-134">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="bae7a-134">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="bae7a-p107">Indica se o monitoramento de QoE está habilitado ou não. Se for Verdadeiro, todos os registros de QoE serão coletados e gravados no banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="bae7a-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="bae7a-137">True</span><span class="sxs-lookup"><span data-stu-id="bae7a-137">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bae7a-138">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="bae7a-138">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="bae7a-p108">Indica se os registros de QoE serão excluídos periodicamente do banco de dados. Se for Verdadeiro, os registros serão excluídos após o período especificado pela propriedade KeepQoEDataForDays. Se for Falso, os registros de QoE serão mantidos indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="bae7a-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="bae7a-142">True</span><span class="sxs-lookup"><span data-stu-id="bae7a-142">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bae7a-143">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="bae7a-143">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="bae7a-p109">Indica o número de dias durante os quais os registros de QoE serão mantidos no banco de dados; quaisquer registros mais antigos do que o número especificado de dias serão automaticamente excluídos. No entanto, isso ocorrerá somente se a exclusão tiver sido habilitada.</span><span class="sxs-lookup"><span data-stu-id="bae7a-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="bae7a-146">KeepCallDetailForDays pode ser definido como qualquer valor inteiro entre 1 e 2562 dias.</span><span class="sxs-lookup"><span data-stu-id="bae7a-146">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="bae7a-147">60 dias</span><span class="sxs-lookup"><span data-stu-id="bae7a-147">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bae7a-p110">Se for necessário modificar essas configurações globais, você poderá fazer isso usando os cmdlets Set-CsCdrConfiguration e Set-CsQoEConfiguration. Por exemplo, esse comando (executado a partir do Shell de Gerenciamento do Lync Server) desabilita o monitoramento de CDR no escopo global; isso é feito configurando a propriedade EnableCDR como Falso ($False):</span><span class="sxs-lookup"><span data-stu-id="bae7a-p110">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets. For example, this command (run from within the Lync Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

<span data-ttu-id="bae7a-150">Observe que a desabilitação do monitoramento não desassocia o repositório de monitoramento do pool Front-End, nem desinstala ou afeta de outra forma o banco de dados de monitoramento backend.</span><span class="sxs-lookup"><span data-stu-id="bae7a-150">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="bae7a-151">Quando você usa o Shell de gerenciamento do Lync Server para desabilitar o monitoramento de CDR ou QoE, você realmente impede que o Lync Server colete e arquive dados de monitoramento temporariamente.</span><span class="sxs-lookup"><span data-stu-id="bae7a-151">When you use Lync Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Lync Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="bae7a-152">Se quiser continuar, nesse caso, a coleta e o arquivamento de dados CDR, tudo o que você precisa fazer é definir a propriedade EnableCDR de volta para Verdadeiro ($True):</span><span class="sxs-lookup"><span data-stu-id="bae7a-152">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="bae7a-153">Da mesma maneira, esse comando desabilita a exclusão de registros QoE no escopo global:</span><span class="sxs-lookup"><span data-stu-id="bae7a-153">Similarly, this command disables the purging of QoE records at the global scope:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

<span data-ttu-id="bae7a-p112">Além das configurações globais, as configurações de CDR e QoE podem ser atribuídas ao escopo do site. Isso fornece flexibilidade de gerenciamento adicional quando se trata de monitoramento; por exemplo, um administrador pode habilitar o monitoramento de CDR para o site Redmond, mas desabilitar o monitoramento de CDR para o site Dublin. Para criar novas configurações de CDR no escopo do site, use um comando parecido com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bae7a-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

<span data-ttu-id="bae7a-p113">Lembre-se de que as configurações definidas no escopo do site têm precedência sobre as configurações definidas no escopo global. Por exemplo, suponha que o monitoramento CDR esteja habilitado no escopo global, mas desabilitado no escopo do site (para o site Redmond). Isso significa que as informações de registro de detalhe da chamada não serão arquivadas para usuários no site Redmond. No entanto, usuários em outros sites (ou seja, usuários gerenciados pelas configurações globais em vez das configurações do site Redmond) terão suas informações de registro de detalhe da chamada arquivadas.</span><span class="sxs-lookup"><span data-stu-id="bae7a-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>

<span data-ttu-id="bae7a-161">As novas configurações de QoE podem ser criadas no escopo do site usando um comando como este:</span><span class="sxs-lookup"><span data-stu-id="bae7a-161">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

<span data-ttu-id="bae7a-162">Para obter mais informações, digite os seguintes comandos no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="bae7a-162">For more information, type the following commands from within the Lync Server Management Shell:</span></span>

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

