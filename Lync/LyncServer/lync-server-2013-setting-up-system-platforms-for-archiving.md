---
title: 'Lync Server 2013: Configurando plataformas do sistema para arquivamento'
description: 'Lync Server 2013: Configurando plataformas do sistema para arquivamento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f210083451ae8fcb87c53e52b5512de6f1f18d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554177"
---
# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a><span data-ttu-id="c29d3-103">Configurando plataformas do sistema para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c29d3-103">Setting up system platforms for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c29d3-104">_**Última modificação do tópico:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="c29d3-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="c29d3-105">Antes de iniciar a implantação do Arquivamento, você deve instalar o sistema operacional necessário e qualquer outro software pré-requisito no hardware que atende os requisitos do sistema:</span><span class="sxs-lookup"><span data-stu-id="c29d3-105">Before starting the deployment of Archiving, you must install the required operating system and any other prerequisite software on hardware that meets system requirements:</span></span>

  - <span data-ttu-id="c29d3-106">Plataforma do Lync **Server 2013**     As implantações do Lync Server 2013 não têm servidores de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="c29d3-106">**Lync Server 2013 platform**   Lync Server 2013 deployments do not have Archiving Servers.</span></span> <span data-ttu-id="c29d3-107">Em vez disso, os agentes de coleta de dados unificados são executados em servidores front-end e servidores Standard Edition para capturar dados para arquivamento, portanto, nenhuma plataforma de sistema separada é necessária para hospedar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="c29d3-107">Instead, Unified Data Collection Agents run on Front End Servers and Standard Edition servers to capture data for archiving, so no separate system platform is required to host Archiving.</span></span>

  - <span data-ttu-id="c29d3-108">Plataforma de armazenamento de **dados**     No Lync Server 2013, você pode armazenar dados usando um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="c29d3-108">**Data storage platform**   In Lync Server 2013, you can store data by using either of the following:</span></span>
    
      - <span data-ttu-id="c29d3-109">**Integração com**     o Microsoft Exchange Se você quiser armazenar dados de arquivamento do Lync Server 2013 usando sua implantação do Exchange 2013, em vez de ou além de configurar um banco de dados separado para armazenamento de dados de arquivamento, sua implantação do Exchange deverá estar executando o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c29d3-109">**Microsoft Exchange integration**   If you want to store Lync Server 2013 Archiving data by using your Exchange 2013 deployment, instead of or in addition to setting up a separate database for storage of Archiving data, your Exchange deployment must be running Exchange 2013.</span></span> <span data-ttu-id="c29d3-110">Para obter detalhes sobre como configurar plataformas de sistema para o Exchange 2013, consulte a documentação do produto Exchange.</span><span class="sxs-lookup"><span data-stu-id="c29d3-110">For details about setting up system platforms for Exchange 2013, see the Exchange product documentation.</span></span>
    
      - <span data-ttu-id="c29d3-111">**SQL Server**     Se você quiser usar um banco de dados separado do SQL Server para armazenamento de dados de arquivamento, em vez de ou além de usar a integração do Microsoft Exchange, você deve configurar a plataforma do sistema para o banco de dados antes da implantação do arquivamento.</span><span class="sxs-lookup"><span data-stu-id="c29d3-111">**SQL Server**   If you want to use a separate SQL Server database for storage of archiving data, instead of or in addition to using Microsoft Exchange integration, you must set up the system platform for the database prior to deployment of Archiving.</span></span> <span data-ttu-id="c29d3-112">Os requisitos específicos da plataforma do sistema dependem se você usa o Microsoft SQL Server 2008 R2 ou o Microsoft SQL Server 2012 para o banco de dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="c29d3-112">The specific system platform requirements depend on whether you use Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for the Archiving database.</span></span> <span data-ttu-id="c29d3-113">Para obter detalhes sobre como configurar plataformas de sistema para esses bancos de dados, consulte a documentação do produto Microsoft SQL Server 2008 R2 e Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="c29d3-113">For details about setting up system platforms for these databases, see the Microsoft SQL Server 2008 R2 and Microsoft SQL Server 2012 product documentation.</span></span>

  - <span data-ttu-id="c29d3-114">Plataforma de servidor de **arquivos**     O Lync Server 2013 armazena arquivos de arquivamento do Lync Server no mesmo local especificado para armazenamento de arquivos quando você configura seus servidores front-end ou servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c29d3-114">**File server platform**   Lync Server 2013 stores Lync Server archiving files in the same location that you specify for file storage when you set up your Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="c29d3-115">Não é possível especificar um local separado para arquivar o armazenamento de arquivos, portanto, nenhuma plataforma de sistema separada é necessária para arquivar o armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c29d3-115">You cannot specify a separate location for archiving file storage, so no separate system platform is required for Archiving file storage.</span></span> <span data-ttu-id="c29d3-116">Se você usar a integração com o Microsoft Exchange, o Exchange 2013 os arquivos para comunicações arquivadas do Lync são armazenados nos servidores do Exchange 2013 para usuários hospedados nesses servidores do Exchange.</span><span class="sxs-lookup"><span data-stu-id="c29d3-116">If you use Microsoft Exchange integration, Exchange 2013 the files for archived Lync communications are stored on Exchange 2013 servers for users homed on those Exchange servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

