---
title: 'Fase 4: topologias de mesclagem'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 4: Merge topologies'
ms:assetid: 81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205044(v=OCS.15)
ms:contentKeyID: 48184668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 624bbfa52c5d4ed963fda895e7af3a544f0f3733
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-4-merge-topologies"></a><span data-ttu-id="db7c7-102">Fase 4: topologias de mesclagem</span><span class="sxs-lookup"><span data-stu-id="db7c7-102">Phase 4: Merge topologies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db7c7-103">_**Tópico da última modificação:** 2012-03-29_</span><span class="sxs-lookup"><span data-stu-id="db7c7-103">_**Topic Last Modified:** 2012-03-29_</span></span>

<span data-ttu-id="db7c7-104">Os tópicos a seguir descrevem as etapas necessárias para mesclar os pools do Microsoft Office Communications Server 2007 R2 para os pools do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db7c7-104">The following topics outline the steps needed to merge your Microsoft Office Communications Server 2007 R2 pools to Microsoft Lync Server 2013 pools.</span></span> <span data-ttu-id="db7c7-105">Primeiro, use o assistente de mesclagem do construtor de topologias para mesclar as informações da topologia.</span><span class="sxs-lookup"><span data-stu-id="db7c7-105">First, you use the Topology Builder Merge wizard to merge topology information.</span></span> <span data-ttu-id="db7c7-106">Esta ferramenta coleta informações sobre o ambiente do Office Communications Server 2007 R2, incluindo informações do servidor de borda, e publica essas informações em um banco de dados compartilhado com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db7c7-106">This tool collects information about your Office Communications Server 2007 R2 environment, including Edge Server information, and publishes that information to a database shared with Lync Server 2013.</span></span> <span data-ttu-id="db7c7-107">Após a publicação da topologia mesclada, o construtor de topologias é usado para exibir as informações de topologia do Office Communications Server 2007 R2 e informações sobre a topologia recém implantada do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db7c7-107">After you publish the merged topology, Topology Builder is used to view the Office Communications Server 2007 R2 topology information and information about the newly deployed Lync Server 2013 topology.</span></span> <span data-ttu-id="db7c7-108">Por fim, você usa cmdlets do Shell de gerenciamento do Lync Server para importar políticas e definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="db7c7-108">Finally, you use Lync Server Management Shell cmdlets to import policies and configuration settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="db7c7-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="db7c7-109">In This Section</span></span>

  - [<span data-ttu-id="db7c7-110">Instalar o pacote de compatibilidade com versões anteriores do WMI</span><span class="sxs-lookup"><span data-stu-id="db7c7-110">Install WMI Backward Compatibility package</span></span>](install-wmi-backward-compatibility-package.md)

  - [<span data-ttu-id="db7c7-111">Mesclar usando o assistente de mesclagem do construtor de topologia</span><span class="sxs-lookup"><span data-stu-id="db7c7-111">Merge using Topology Builder Merge wizard</span></span>](merge-using-topology-builder-merge-wizard.md)

  - [<span data-ttu-id="db7c7-112">Importar políticas e configurações</span><span class="sxs-lookup"><span data-stu-id="db7c7-112">Import policies and settings</span></span>](import-policies-and-settings.md)

  - [<span data-ttu-id="db7c7-113">Verificar informações de topologia</span><span class="sxs-lookup"><span data-stu-id="db7c7-113">Verify topology information</span></span>](verify-topology-information.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

