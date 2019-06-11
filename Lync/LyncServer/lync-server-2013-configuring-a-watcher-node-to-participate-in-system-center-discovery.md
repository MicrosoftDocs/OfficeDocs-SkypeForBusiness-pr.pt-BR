---
title: Configurando um nó de inspetor para participar da descoberta do System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66be6bd0336471626f2ca4e41a89c3a45b073f05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="14d2c-102">Configurando um nó de Inspetor no Lync Server 2013 para participar da descoberta do System Center</span><span class="sxs-lookup"><span data-stu-id="14d2c-102">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14d2c-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="14d2c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="14d2c-104">Para garantir que o nó do Inspetor participe do processo de descoberta do System Center Operations Manager, você deve concluir o procedimento a seguir em um computador em que o console do System Center Operations Manager foi instalado:</span><span class="sxs-lookup"><span data-stu-id="14d2c-104">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="14d2c-105">Na guia **Administração** , clique em **agente gerenciado**.</span><span class="sxs-lookup"><span data-stu-id="14d2c-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="14d2c-106">Clique com o botão direito do mouse no nome do computador do nó do Inspetor e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="14d2c-106">Right-click the name of the watcher node computer, and then click **Properties**.</span></span> <span data-ttu-id="14d2c-107">Na caixa de diálogo **Propriedades** , na guia **segurança** , selecione **permitir que esse agente atue como um proxy e descubra objetos gerenciados em outros computadores**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="14d2c-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="14d2c-108">Depois de configurar o nó do inspetor para atuar como um proxy, reinicialize o computador do nó do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="14d2c-108">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="14d2c-109">Depois que o computador for reinicializado, verifique se nenhum evento de erro está sendo gravado no log de eventos do Operations Manager nesse computador.</span><span class="sxs-lookup"><span data-stu-id="14d2c-109">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="14d2c-110">Depois que o computador estiver em execução por 15 minutos ou então, use o console do Operations Manager para verificar se seus computadores do Lync Server estão listados na categoria **Lync** .</span><span class="sxs-lookup"><span data-stu-id="14d2c-110">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

