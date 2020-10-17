---
title: Importar políticas e configurações
description: Importar políticas e configurações.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e014b7e8f0498742104118eec9eb313394ae6a94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569027"
---
# <a name="import-policies-and-settings"></a><span data-ttu-id="47e68-103">Importar políticas e configurações</span><span class="sxs-lookup"><span data-stu-id="47e68-103">Import policies and settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47e68-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="47e68-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="47e68-105">Após mesclar as informações de topologia do Office Communications Server 2007 R2 com o pool piloto do Lync Server 2013, você precisará executar um cmdlet do Shell de gerenciamento do Lync Server 2013 para migrar suas políticas e definições de configuração do Office Communications Server 2007 R2 para o pool piloto do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47e68-105">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="47e68-106">O cmdlet **Import-CsLegacyConfiguration** importa políticas, rotas de voz, planos de discagem, URLs do Communicator Web Access e números de acesso discado para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47e68-106">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="47e68-107">Para migrar as configurações e políticas</span><span class="sxs-lookup"><span data-stu-id="47e68-107">To migrate policies and settings</span></span>

1.  <span data-ttu-id="47e68-108">No servidor front-end do Lync Server 2013, inicie o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="47e68-108">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="47e68-109">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="47e68-109">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="47e68-110">Após a importação das políticas, use o procedimento a seguir para ver as políticas importadas no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="47e68-110">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="47e68-111">Para ver as políticas importadas</span><span class="sxs-lookup"><span data-stu-id="47e68-111">To view imported policies</span></span>

1.  <span data-ttu-id="47e68-112">Abra o painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47e68-112">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="47e68-113">Clique em **Roteamento de Voz** e veja as políticas importadas.</span><span class="sxs-lookup"><span data-stu-id="47e68-113">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="47e68-114">Clique em **Conferência** e veja as políticas importadas.</span><span class="sxs-lookup"><span data-stu-id="47e68-114">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="47e68-115">Click **Federation and External Access** and view the imported policies.</span><span class="sxs-lookup"><span data-stu-id="47e68-115">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="47e68-116">Clique em **Monitoramento e Arquivamento** e veja as políticas importadas.</span><span class="sxs-lookup"><span data-stu-id="47e68-116">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

