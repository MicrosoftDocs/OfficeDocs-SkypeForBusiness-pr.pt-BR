---
title: 'Lync Server 2013: usando opções de linha de comando da instalação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c181c16e5480d1dc7659ed3778faf738eed70949
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="944d4-102">Usando opções de linha de comando da instalação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="944d4-102">Using Setup command-line options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="944d4-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="944d4-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="944d4-104">A linha de comando Setup. exe é usada para muito poucas operações na instalação do Office.</span><span class="sxs-lookup"><span data-stu-id="944d4-104">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="944d4-105">Em vez de usar as opções de linha de comando da instalação, você geralmente usará a ferramenta de personalização do Office e o arquivo config. xml para a configuração do produto e a personalização de recursos.</span><span class="sxs-lookup"><span data-stu-id="944d4-105">Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="944d4-106">A linha de comando Setup. exe do Office reconhece as opções de linha de comando descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="944d4-106">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="944d4-107">Opções de linha de comando da instalação do Office</span><span class="sxs-lookup"><span data-stu-id="944d4-107">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="944d4-108">Opção de linha de comando de instalação</span><span class="sxs-lookup"><span data-stu-id="944d4-108">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="944d4-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="944d4-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="944d4-110">/admin</span><span class="sxs-lookup"><span data-stu-id="944d4-110">/admin</span></span></p></td>
<td><p><span data-ttu-id="944d4-111">Executa a Ferramenta de Personalização do Office para criar um arquivo de personalização da Instalação (arquivo .msp).</span><span class="sxs-lookup"><span data-stu-id="944d4-111">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="944d4-112">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="944d4-112">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="944d4-p102">Aplica o arquivo de personalização da Instalação específico para a instalação. É possível especificar um caminho de um arquivo de personalização específico (arquivo .msp) ou para a pasta na qual você armazena os arquivos de personalização.</span><span class="sxs-lookup"><span data-stu-id="944d4-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="944d4-115">/config [path]</span><span class="sxs-lookup"><span data-stu-id="944d4-115">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="944d4-116">Especifica o arquivo Config.xml que a Instalação usa durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="944d4-116">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="944d4-117">Use a opção/config para especificar o arquivo config. XML que você personalizou para instalações do Lync 2013, por exemplo:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="944d4-117">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="944d4-118">/Modify Lync</span><span class="sxs-lookup"><span data-stu-id="944d4-118">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="944d4-119">Usado com um arquivo Config.xml modificado para executar a instalação no modo de manutenção e fazer alterações em uma instalação existente do Office.</span><span class="sxs-lookup"><span data-stu-id="944d4-119">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="944d4-120">Por exemplo, você pode usar a opção/Modify para adicionar ou remover recursos do Lync.</span><span class="sxs-lookup"><span data-stu-id="944d4-120">For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="944d4-121">/Repair Lync</span><span class="sxs-lookup"><span data-stu-id="944d4-121">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="944d4-122">Executa a instalação do computador do usuário para reparar o Lync.</span><span class="sxs-lookup"><span data-stu-id="944d4-122">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="944d4-123">/Uninstall Lync</span><span class="sxs-lookup"><span data-stu-id="944d4-123">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="944d4-124">Executa a instalação para remover o Lync do computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="944d4-124">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="944d4-125">Para obter detalhes sobre como usar as opções de linha de comando <https://go.microsoft.com/fwlink/p/?linkid=267515>da instalação, consulte.</span><span class="sxs-lookup"><span data-stu-id="944d4-125">For details about using the setup command-line options, see <https://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

