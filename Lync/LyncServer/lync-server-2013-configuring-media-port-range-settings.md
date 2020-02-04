---
title: 'Lync Server 2013: Configurando as configurações de intervalo de porta de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80e835bfcf12495c75612ecee93d87cf3c421651
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="717a3-102">Configurando as configurações de intervalo de porta de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="717a3-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="717a3-103">_**Tópico da última modificação:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="717a3-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="717a3-104">As configurações de intervalo de porta de mídia podem afetar significativamente o desempenho do cliente e devem ser configuradas.</span><span class="sxs-lookup"><span data-stu-id="717a3-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="717a3-105">Você pode definir essas configurações usando o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="717a3-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="717a3-106">Configurações de intervalo de porta de mídia</span><span class="sxs-lookup"><span data-stu-id="717a3-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="717a3-107">Configuração</span><span class="sxs-lookup"><span data-stu-id="717a3-107">Setting</span></span></th>
<th><span data-ttu-id="717a3-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="717a3-108">Description</span></span></th>
<th><span data-ttu-id="717a3-109">Cmdlet do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="717a3-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="717a3-110">Parâmetros do cmdlet</span><span class="sxs-lookup"><span data-stu-id="717a3-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="717a3-111">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="717a3-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="717a3-112">Especifica se os intervalos de porta enviados pelo servidor devem ser usados pelo cliente para mídia e sinalização.</span><span class="sxs-lookup"><span data-stu-id="717a3-112">Specifies whether the port ranges sent by the server should be used by the client for media and signaling.</span></span> <span data-ttu-id="717a3-113">Usado em conjunto com os subvalors MinMediaPort e MaxMediaPort.</span><span class="sxs-lookup"><span data-stu-id="717a3-113">Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="717a3-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="717a3-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="717a3-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="717a3-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="717a3-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="717a3-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="717a3-117">Especifica o número de porta inicial a ser usado para mídia.</span><span class="sxs-lookup"><span data-stu-id="717a3-117">Specifies the starting port number to use for media.</span></span> <span data-ttu-id="717a3-118">Combina com MaxMediaPort para especificar o intervalo de portas.</span><span class="sxs-lookup"><span data-stu-id="717a3-118">Combines with MaxMediaPort to specify the range of ports.</span></span> <span data-ttu-id="717a3-119">O intervalo mínimo recomendado é de 40 portas.</span><span class="sxs-lookup"><span data-stu-id="717a3-119">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="717a3-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="717a3-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="717a3-121">ClientMediaPort (representa o número da porta inicial a ser usado para a mídia do cliente)</span><span class="sxs-lookup"><span data-stu-id="717a3-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="717a3-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="717a3-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="717a3-123">Especifica o número da porta mais alta a ser usado para mídia.</span><span class="sxs-lookup"><span data-stu-id="717a3-123">Specifies the highest port number to use for media.</span></span> <span data-ttu-id="717a3-124">Combina com MinMediaPort para especificar o intervalo de portas.</span><span class="sxs-lookup"><span data-stu-id="717a3-124">Combines with MinMediaPort to specify the range of ports.</span></span> <span data-ttu-id="717a3-125">O intervalo mínimo recomendado é de 40 portas.</span><span class="sxs-lookup"><span data-stu-id="717a3-125">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="717a3-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="717a3-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="717a3-127">ClientMediaPortRange (indica o número total de portas disponíveis para a mídia do cliente; o padrão é 40)</span><span class="sxs-lookup"><span data-stu-id="717a3-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="717a3-128">Para definir as configurações de intervalo de porta de mídia</span><span class="sxs-lookup"><span data-stu-id="717a3-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="717a3-129">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="717a3-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="717a3-130">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="717a3-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="717a3-131">Este cmdlet retorna as configurações de configuração de conferência.</span><span class="sxs-lookup"><span data-stu-id="717a3-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="717a3-132">Execute o cmdlet a seguir com os parâmetros e valores que você deseja alterar (para obter detalhes sobre os parâmetros para esse cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server):</span><span class="sxs-lookup"><span data-stu-id="717a3-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="717a3-133">Você pode criar conjuntos adicionais de definições de configuração de conferência para sites específicos.</span><span class="sxs-lookup"><span data-stu-id="717a3-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="717a3-134">Use o cmdlet <STRONG>New-CsConferencingConfiguration</STRONG> com uma identidade de site.</span><span class="sxs-lookup"><span data-stu-id="717a3-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="717a3-135">Quando você cria novas configurações de conferência para sites, as configurações do site prevalecem sobre as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="717a3-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="717a3-136">Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="717a3-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

