---
title: Configurando um nó de inspetor para participar da descoberta do System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ca3724f9b5bc8200e2ca006d9fa7445d7368ab7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="ef7d9-102">Configurando um nó de Inspetor no Lync Server 2013 para participar da descoberta do System Center</span><span class="sxs-lookup"><span data-stu-id="ef7d9-102">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef7d9-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ef7d9-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ef7d9-104">Para garantir que o nó do Inspetor participe do processo de descoberta do System Center Operations Manager, você deve concluir o procedimento a seguir em um computador em que o console do System Center Operations Manager foi instalado:</span><span class="sxs-lookup"><span data-stu-id="ef7d9-104">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="ef7d9-105">Na guia **Administração** , clique em **agente gerenciado**.</span><span class="sxs-lookup"><span data-stu-id="ef7d9-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="ef7d9-106">Clique com o botão direito do mouse no nome do computador do nó do Inspetor e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ef7d9-106">Right-click the name of the watcher node computer, and then click **Properties**.</span></span> <span data-ttu-id="ef7d9-107">Na caixa de diálogo **Propriedades** , na guia **segurança** , selecione **permitir que esse agente atue como um proxy e descubra objetos gerenciados em outros computadores**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef7d9-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="ef7d9-108">Depois de configurar o nó do inspetor para atuar como um proxy, reinicialize o computador do nó do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="ef7d9-108">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="ef7d9-109">Depois que o computador for reinicializado, verifique se nenhum evento de erro está sendo gravado no log de eventos do Operations Manager nesse computador.</span><span class="sxs-lookup"><span data-stu-id="ef7d9-109">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="ef7d9-110">Depois que o computador estiver em execução por 15 minutos ou então, use o console do Operations Manager para verificar se seus computadores do Lync Server estão listados na categoria **Lync** .</span><span class="sxs-lookup"><span data-stu-id="ef7d9-110">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

