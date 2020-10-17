---
title: 'Lync Server 2013: fazendo backup de repositórios de arquivos'
description: 'Lync Server 2013: fazendo backup de repositórios de arquivos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up file stores
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202167(v=OCS.15)
ms:contentKeyID: 51541449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba6a92d189c39242be1b2167ffc336d9eb406719
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563277"
---
# <a name="backing-up-file-stores-in-lync-server-2013"></a><span data-ttu-id="81e76-103">Fazendo backup de repositórios de arquivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81e76-103">Backing up file stores in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81e76-104">_**Última modificação do tópico:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="81e76-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="81e76-105">O backup dos repositórios de arquivos do Lync Server inclui todos os arquivos e pastas usados pelos componentes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="81e76-105">Backing up the Lync Server File Stores includes all the files and folders used by Lync Server components.</span></span>

<div>

## <a name="to-back-up-file-stores"></a><span data-ttu-id="81e76-106">Para fazer o backup dos Repositórios de Arquivos</span><span class="sxs-lookup"><span data-stu-id="81e76-106">To back up File Stores</span></span>

1.  <span data-ttu-id="81e76-107">Para localizar os locais específicos dos repositórios de arquivos do Lync Server, abra o construtor de topologias e examine o nó **repositórios de arquivos** .</span><span class="sxs-lookup"><span data-stu-id="81e76-107">To find the specific locations of your Lync Server File Stores, open Topology Builder and look in the **File stores** node.</span></span>

2.  <span data-ttu-id="81e76-108">Use o Robocopy ou outra ferramenta de gerenciamento de sistema de arquivos para copiar cada repositório de arquivos para o repositório de $Backup \\ .</span><span class="sxs-lookup"><span data-stu-id="81e76-108">Use Robocopy or another file system management tool to copy each File Store to $Backup\\filestore.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

