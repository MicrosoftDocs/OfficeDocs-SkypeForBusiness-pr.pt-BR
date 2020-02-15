---
title: Criar ou modificar um conjunto de definições de configuração de atualização de dispositivo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3f58e67a0d1fc8f6b01fecfbab7c7ff7dd8f31d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="0e582-102">Criar ou modificar um conjunto de definições de configuração de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e582-102">Create or modify a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e582-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0e582-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0e582-104">As configurações de atualização de dispositivo podem ser criadas (somente no escopo do site) usando o Windows PowerShell e o cmdlet **New-CsDeviceUpdateConfiguration** e modificadas usando-se o cmdlet **set-CsDeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0e582-104">Device update configuration settings can be created (at the site scope only) by using Windows PowerShell and the **New-CsDeviceUpdateConfiguration** cmdlet and modified by using the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="0e582-105">Esses cmdlets podem ser executados a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e582-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="0e582-106">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="0e582-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="0e582-107">Para criar definições de configuração de atualização de dispositivo que usam os valores padrão</span><span class="sxs-lookup"><span data-stu-id="0e582-107">To create device update configuration settings that use the default values</span></span>

  - <span data-ttu-id="0e582-108">Este comando cria um novo conjunto de definições de configuração de atualização de dispositivo para o site Redmond:</span><span class="sxs-lookup"><span data-stu-id="0e582-108">This command creates a new set of device update configuration settings for the Redmond site:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="0e582-109">Como nenhum parâmetro diferente do parâmetro Identity obrigatório foi especificado no comando anterior, o novo conjunto de definições de configuração usará os valores padrão para todas as suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="0e582-109">Because no parameters other than the mandatory Identity parameter were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a><span data-ttu-id="0e582-110">Para alterar um único valor de propriedade ao criar definições de configuração de atualização de dispositivo</span><span class="sxs-lookup"><span data-stu-id="0e582-110">To change a single property value when creating device update configuration settings</span></span>

  - <span data-ttu-id="0e582-111">Para criar configurações que usam valores de propriedades diferentes, basta incluir o parâmetro e o valor de parâmetro adequados.</span><span class="sxs-lookup"><span data-stu-id="0e582-111">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="0e582-112">Por exemplo, para criar um conjunto de definições de configuração de atualização de dispositivo que, por padrão, exclua arquivos de log antigos a cada 21 dias, use um comando como este:</span><span class="sxs-lookup"><span data-stu-id="0e582-112">For example, to create a collection of device update configuration settings that, by default, deletes old log files every 21 days, use a command like this one:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a><span data-ttu-id="0e582-113">Para alterar vários valores de propriedade ao criar definições de configuração de atualização de dispositivo</span><span class="sxs-lookup"><span data-stu-id="0e582-113">To change multiple property values when creating device update configuration settings</span></span>

  - <span data-ttu-id="0e582-114">Vários valores de propriedade podem ser modificados, incluindo vários parâmetros.</span><span class="sxs-lookup"><span data-stu-id="0e582-114">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="0e582-115">Por exemplo, este comando define o intervalo de limpeza de log como 21 dias e o intervalo de liberação de log para 30 minutos:</span><span class="sxs-lookup"><span data-stu-id="0e582-115">For example, this command sets the log cleanup interval to 21 days and the log flush interval to 30 minutes:</span></span>
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

<span data-ttu-id="0e582-116">Para obter detalhes sobre como modificar as definições de configuração de dispositivo existente, consulte o tópico de ajuda para o cmdlet [set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="0e582-116">For details about modifying existing device configuration settings, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="0e582-117">Para obter detalhes sobre como criar conjuntos de definições de configuração, consulte o tópico de ajuda para o cmdlet [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="0e582-117">For details about creating collections of configuration settings, see the Help topic for the [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

