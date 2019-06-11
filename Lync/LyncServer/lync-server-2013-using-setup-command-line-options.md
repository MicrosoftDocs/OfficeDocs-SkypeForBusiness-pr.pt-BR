---
title: 'Lync Server 2013: usando as opções de linha de comando de configuração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5087c8ac777e5e2fd3259f925a4217a4d47dd800
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="9c385-102">Usando as opções de linha de comando de configuração no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c385-102">Using Setup command-line options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c385-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9c385-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9c385-p101">A linha de comando Setup.exe é usada em poucas operações na instalação do Office. Em vez de usar as opções da linha de comando Setup, você geralmente usa a Ferramenta de personalização do Office e o arquivo Config.xml file para instalação do produto e personalização de recursos.</span><span class="sxs-lookup"><span data-stu-id="9c385-p101">The Setup.exe command line is used for very few operations in Office setup. Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="9c385-106">A linha de comando Setup.exe do Office reconhece as opções de linha de comando descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9c385-106">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="9c385-107">Opções de linha de comando Setup do Office</span><span class="sxs-lookup"><span data-stu-id="9c385-107">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c385-108">Opção de linha de comando Setup</span><span class="sxs-lookup"><span data-stu-id="9c385-108">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="9c385-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="9c385-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c385-110">/admin</span><span class="sxs-lookup"><span data-stu-id="9c385-110">/admin</span></span></p></td>
<td><p><span data-ttu-id="9c385-111">Executa a Ferramenta de personalização do Office para criar um arquivo de personalização de Setup (arquivo .msp).</span><span class="sxs-lookup"><span data-stu-id="9c385-111">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c385-112">/adminfile [caminho]</span><span class="sxs-lookup"><span data-stu-id="9c385-112">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="9c385-p102">Aplica o arquivo de personalização de Setup à instalação. Você pode especificar um caminho de arquivo de personalização específico (arquivo .msp) ou a pasta onde você armazena os arquivos de personalização.</span><span class="sxs-lookup"><span data-stu-id="9c385-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c385-115">/config [caminho]</span><span class="sxs-lookup"><span data-stu-id="9c385-115">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="9c385-116">Especifica o arquivo Config.xml que o Setup usa durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="9c385-116">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="9c385-117">Use a opção/config para especificar o arquivo config. xml personalizado para instalações do Lync 2013, por exemplo:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="9c385-117">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c385-118">/Modify Lync</span><span class="sxs-lookup"><span data-stu-id="9c385-118">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="9c385-119">Usado com um arquivo Config.xml modificado para executar o Setup em modo de manutenção e fazer alterações à instalação existente do Office.</span><span class="sxs-lookup"><span data-stu-id="9c385-119">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="9c385-120">Por exemplo, você pode usar a opção/Modify para adicionar ou remover recursos do Lync.</span><span class="sxs-lookup"><span data-stu-id="9c385-120">For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c385-121">/Repair Lync</span><span class="sxs-lookup"><span data-stu-id="9c385-121">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="9c385-122">Executa a instalação a partir do computador do usuário para reparar o Lync.</span><span class="sxs-lookup"><span data-stu-id="9c385-122">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c385-123">/Uninstall Lync</span><span class="sxs-lookup"><span data-stu-id="9c385-123">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="9c385-124">Executa a instalação para remover o Lync do computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="9c385-124">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9c385-125">Para obter detalhes sobre como usar as opções de linha de comando <http://go.microsoft.com/fwlink/p/?linkid=267515>de configuração, consulte.</span><span class="sxs-lookup"><span data-stu-id="9c385-125">For details about using the setup command-line options, see <http://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

