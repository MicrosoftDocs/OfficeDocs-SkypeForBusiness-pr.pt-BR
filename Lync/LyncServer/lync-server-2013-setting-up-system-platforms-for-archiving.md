---
title: 'Lync Server 2013: Configurando plataformas do sistema para arquivamento'
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
ms.openlocfilehash: 13682b7507e133dd49c102bf6c25293ff5da2c08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a><span data-ttu-id="b1c9a-102">Configurando plataformas do sistema para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1c9a-102">Setting up system platforms for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1c9a-103">_**Tópico da última modificação:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="b1c9a-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="b1c9a-104">Antes de iniciar a implantação do arquivamento, você deve instalar o sistema operacional necessário e qualquer outro software de pré-requisito em hardware que atenda aos requisitos do sistema:</span><span class="sxs-lookup"><span data-stu-id="b1c9a-104">Before starting the deployment of Archiving, you must install the required operating system and any other prerequisite software on hardware that meets system requirements:</span></span>

  - <span data-ttu-id="b1c9a-105">**Plataforma Lync Server 2013**   as implantações do Lync Server 2013 não têm servidores de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="b1c9a-105">**Lync Server 2013 platform**   Lync Server 2013 deployments do not have Archiving Servers.</span></span> <span data-ttu-id="b1c9a-106">Em vez disso, os agentes de coleta de dados unificados são executados em servidores de front-end e servidores Standard Edition para capturar dados para arquivamento, portanto, não é preciso ter uma plataforma de sistema separada para hospedar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="b1c9a-106">Instead, Unified Data Collection Agents run on Front End Servers and Standard Edition servers to capture data for archiving, so no separate system platform is required to host Archiving.</span></span>

  - <span data-ttu-id="b1c9a-107">**Plataforma de armazenamento de dados**   no Lync Server 2013, você pode armazenar dados usando um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b1c9a-107">**Data storage platform**   In Lync Server 2013, you can store data by using either of the following:</span></span>
    
      - <span data-ttu-id="b1c9a-108">**Integração com**   o Microsoft Exchange se você deseja armazenar dados de arquivamento do Lync Server 2013 usando a implantação do Exchange 2013, em vez de ou além de configurar um banco de dados separado para armazenamento de dados de arquivamento, a implantação do Exchange deve estar executando o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b1c9a-108">**Microsoft Exchange integration**   If you want to store Lync Server 2013 Archiving data by using your Exchange 2013 deployment, instead of or in addition to setting up a separate database for storage of Archiving data, your Exchange deployment must be running Exchange 2013.</span></span> <span data-ttu-id="b1c9a-109">Para obter detalhes sobre a configuração de plataformas do sistema para o Exchange 2013, consulte a documentação do produto Exchange.</span><span class="sxs-lookup"><span data-stu-id="b1c9a-109">For details about setting up system platforms for Exchange 2013, see the Exchange product documentation.</span></span>
    
      - <span data-ttu-id="b1c9a-110">**SQL Server**   se você quiser usar um banco de dados separado do SQL Server para armazenamento de dados de arquivamento, em vez de usar a integração do Microsoft Exchange, você deve configurar a plataforma do sistema para o banco de dados antes da implantação do arquivamento.</span><span class="sxs-lookup"><span data-stu-id="b1c9a-110">**SQL Server**   If you want to use a separate SQL Server database for storage of archiving data, instead of or in addition to using Microsoft Exchange integration, you must set up the system platform for the database prior to deployment of Archiving.</span></span> <span data-ttu-id="b1c9a-111">Os requisitos da plataforma do sistema específico dependem se você usa o Microsoft SQL Server 2008 R2 ou o Microsoft SQL Server 2012 para o banco de dados de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="b1c9a-111">The specific system platform requirements depend on whether you use Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for the Archiving database.</span></span> <span data-ttu-id="b1c9a-112">Para obter detalhes sobre a configuração de plataformas do sistema para esses bancos de dados, consulte a documentação do Microsoft SQL Server 2008 R2 e do Microsoft SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="b1c9a-112">For details about setting up system platforms for these databases, see the Microsoft SQL Server 2008 R2 and Microsoft SQL Server 2012 product documentation.</span></span>

  - <span data-ttu-id="b1c9a-113">**Plataforma de servidor de arquivos**   Lync Server 2013 armazena arquivos de arquivamento do Lync Server no mesmo local que você especificar para armazenamento de arquivos ao configurar seus servidores front-end ou servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b1c9a-113">**File server platform**   Lync Server 2013 stores Lync Server archiving files in the same location that you specify for file storage when you set up your Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="b1c9a-114">Você não pode especificar um local separado para arquivar o armazenamento de arquivos, portanto, nenhuma plataforma de sistema separada é necessária para arquivar o armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b1c9a-114">You cannot specify a separate location for archiving file storage, so no separate system platform is required for Archiving file storage.</span></span> <span data-ttu-id="b1c9a-115">Se você usa a integração do Microsoft Exchange, o Exchange 2013 os arquivos das comunicações arquivadas do Lync são armazenados nos servidores Exchange 2013 para usuários hospedados nesses servidores Exchange.</span><span class="sxs-lookup"><span data-stu-id="b1c9a-115">If you use Microsoft Exchange integration, Exchange 2013 the files for archived Lync communications are stored on Exchange 2013 servers for users homed on those Exchange servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

