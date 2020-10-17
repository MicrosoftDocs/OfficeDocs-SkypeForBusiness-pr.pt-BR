---
title: 'Lync Server 2013: Iniciar serviços nos servidores'
description: 'Lync Server 2013: Iniciar serviços nos servidores.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c238d7ddbba66604314d146a2e7f86eaa85eeb9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541907"
---
# <a name="start-services-on-servers-for-lync-server-2013"></a><span data-ttu-id="22bb8-103">Iniciar serviços em servidores para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22bb8-103">Start services on servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22bb8-104">_**Última modificação do tópico:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="22bb8-104">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="22bb8-105">Para concluir com êxito este procedimento, você deve estar conectado como um usuário que seja membro do grupo RTCUniversalServerAdmins ou com as permissões delegadas corretas.</span><span class="sxs-lookup"><span data-stu-id="22bb8-105">To successfully complete this procedure you should be logged in as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="22bb8-106">Para obter detalhes sobre como delegar permissões, consulte o tópico [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="22bb8-106">For details about delegating permissions, see the topic [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

<span data-ttu-id="22bb8-107">Após instalar o repositório de configuração local em seus servidores, instalar os componentes do Lync Server 2013 e configurar certificados em um servidor front-end ou servidor front-end, você deve iniciar os serviços do Lync Server 2013 no servidor.</span><span class="sxs-lookup"><span data-stu-id="22bb8-107">After you install the Local Configuration store on your servers, install the Lync Server 2013 components, and configure certificates on a Front End Server or Front End Server, you must start the Lync Server 2013 services on the server.</span></span> <span data-ttu-id="22bb8-108">Use o procedimento a seguir para iniciar os serviços em cada servidor de front-end em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="22bb8-108">Use the following procedure to start services on each Front End Server in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a><span data-ttu-id="22bb8-109">Para iniciar os serviços em um servidor Standard Edition ou front-end</span><span class="sxs-lookup"><span data-stu-id="22bb8-109">To start services on a Standard Edition or Front End Server</span></span>

1.  <span data-ttu-id="22bb8-110">No assistente de implantação do Lync Server, na página **Lync server 2013** , clique em **executar** ao lado de **etapa 4: Iniciar serviços**.</span><span class="sxs-lookup"><span data-stu-id="22bb8-110">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click **Run** next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="22bb8-111">Na página **Iniciar serviços** , clique em **Avançar** para iniciar os serviços do Lync Server no servidor.</span><span class="sxs-lookup"><span data-stu-id="22bb8-111">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="22bb8-112">Na página **Executando comandos**, após todos os serviços serem iniciados com sucesso, clique em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="22bb8-112">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="22bb8-113">O comando para iniciar os serviços no servidor é o melhor método para relatar que os serviços foram realmente iniciados.</span><span class="sxs-lookup"><span data-stu-id="22bb8-113">The command to start the services on the server is a best effort method to report that the services have in fact started.</span></span> <span data-ttu-id="22bb8-114">Talvez ele não reflita o estado real do serviço.</span><span class="sxs-lookup"><span data-stu-id="22bb8-114">It might not reflect the actual state of the service.</span></span> <span data-ttu-id="22bb8-115">Recomendamos o uso da etapa <STRONG>Status do Serviço (Opcional)</STRONG> imediatamente após <STRONG>Iniciar Serviços</STRONG> para abrir o MMC (Console de Gerenciamento da Microsoft) e confirmar se os serviços foram iniciados com êxito.</span><span class="sxs-lookup"><span data-stu-id="22bb8-115">We recommend that you use the step <STRONG>Service Status (Optional)</STRONG> immediately following <STRONG>Start Services</STRONG> to open the Microsoft Management Console (MMC) and confirm that the services have started successfully.</span></span> <span data-ttu-id="22bb8-116">Se algum serviço do Lync Server não tiver começado, clique com o botão direito do mouse no serviço no MMC e, em seguida, clique em <STRONG>Iniciar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="22bb8-116">If any Lync Server service has not started, you can right-click that service in the MMC, and then click <STRONG>Start</STRONG>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

