---
title: 'Lync Server 2013: definindo configurações de intervalo de porta de mídia'
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
ms.openlocfilehash: f345b97851aac264bb3b7ef05978d80d851099ec
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="ad9d5-102">Definindo as configurações de intervalo de porta de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad9d5-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad9d5-103">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="ad9d5-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="ad9d5-104">As configurações de intervalo da porta de mídia podem impactar significantemente o desempenho do cliente e devem ser configuradas.</span><span class="sxs-lookup"><span data-stu-id="ad9d5-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="ad9d5-105">Você pode definir essas configurações usando o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ad9d5-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="ad9d5-106">Configurações do Intervalo da Porta de Mídia</span><span class="sxs-lookup"><span data-stu-id="ad9d5-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad9d5-107">Configuração</span><span class="sxs-lookup"><span data-stu-id="ad9d5-107">Setting</span></span></th>
<th><span data-ttu-id="ad9d5-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="ad9d5-108">Description</span></span></th>
<th><span data-ttu-id="ad9d5-109">Cmdlet do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="ad9d5-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="ad9d5-110">Parâmetros do cmdlet</span><span class="sxs-lookup"><span data-stu-id="ad9d5-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad9d5-111">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="ad9d5-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="ad9d5-p102">Especifica se os intervalos de porta enviados pelo servidor devem ser usados pelo cliente para mídia e sinalização. Usado em conjunto com os subvalores MinMediaPort e MaxMediaPort.</span><span class="sxs-lookup"><span data-stu-id="ad9d5-p102">Specifies whether the port ranges sent by the server should be used by the client for media and signaling. Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="ad9d5-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="ad9d5-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="ad9d5-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="ad9d5-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad9d5-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="ad9d5-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="ad9d5-p103">Especifica o número de porta inicial a usar para a mídia. Combina com o MaxMediaPort para especificar o intervalo de portas. O intervalo mínimo recomendado é de 40 portas.</span><span class="sxs-lookup"><span data-stu-id="ad9d5-p103">Specifies the starting port number to use for media. Combines with MaxMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="ad9d5-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="ad9d5-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="ad9d5-121">ClientMediaPort (representa o número de porta inicial para usar na mídia do cliente)</span><span class="sxs-lookup"><span data-stu-id="ad9d5-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad9d5-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="ad9d5-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="ad9d5-p104">Especifica o maior número de porta para usar na mídia. Combina com MinMediaPort para especificar o intervalo de portas. O intervalo mínimo recomendado é de 40 portas.</span><span class="sxs-lookup"><span data-stu-id="ad9d5-p104">Specifies the highest port number to use for media. Combines with MinMediaPort to specify the range of ports. The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="ad9d5-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="ad9d5-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="ad9d5-127">ClientMediaPortRange (indica o número total de portas disponíveis para a mídia do cliente; o padrão é 40)</span><span class="sxs-lookup"><span data-stu-id="ad9d5-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="ad9d5-128">Para definir as configurações do intervalo de porta da mídia</span><span class="sxs-lookup"><span data-stu-id="ad9d5-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="ad9d5-129">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ad9d5-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ad9d5-130">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ad9d5-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="ad9d5-131">Esse cmdlet retorna as definições da configuração de conferência.</span><span class="sxs-lookup"><span data-stu-id="ad9d5-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="ad9d5-132">Execute o cmdlet a seguir com os parâmetros e valores que você deseja alterar (para obter detalhes sobre os parâmetros para este cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server):</span><span class="sxs-lookup"><span data-stu-id="ad9d5-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad9d5-133">Você pode criar conjuntos adicionais de definições de configuração de conferência para sites específicos.</span><span class="sxs-lookup"><span data-stu-id="ad9d5-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="ad9d5-134">Use o cmdlet <STRONG>New- CsConferencingConfiguration</STRONG> com uma identidade de site.</span><span class="sxs-lookup"><span data-stu-id="ad9d5-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="ad9d5-135">Ao criar novas definições de configuração de conferênciade para os sites, as configurações do site têm precedência sobre as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="ad9d5-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="ad9d5-136">Para obter detalhes, consulte a documentação do Shell de Gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ad9d5-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

