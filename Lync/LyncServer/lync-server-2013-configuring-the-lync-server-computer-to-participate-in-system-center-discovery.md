---
title: Configurando o computador do Lync Server para participar da descoberta do System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b8e95ead01c89f33346a66a8212245c2350894f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="bd74c-102">Configurando o computador do Lync Server 2013 para participar da descoberta do System Center</span><span class="sxs-lookup"><span data-stu-id="bd74c-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd74c-103">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="bd74c-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="bd74c-104">Para certificar-se de que seu novo agente do Lync Server participa do processo de descoberta para o System Center Operations Manager, você deve concluir o procedimento a seguir em cada computador em que o console do System Center Operations Manager tenha sido instalado:</span><span class="sxs-lookup"><span data-stu-id="bd74c-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="bd74c-105">Na guia **Administração**, clique em **Agente Gerenciado**.</span><span class="sxs-lookup"><span data-stu-id="bd74c-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="bd74c-p101">Clique com o botão direito no nome do computador e clique em **Propriedades**. Na caixa de diálogo **Propriedades**, na guia **Segurança**, selecione **Permitir que este agente haja como um proxy e descubra objetos gerenciados em outros computadores** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd74c-p101">Right-click the name of the computer, and then click **Properties**. In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="bd74c-p102">Após concluir a etapa 2, reinicie o serviço do Agente de Integridade. (Reiniciar o serviço "forçará" a descoberta da nova máquina. Se você não reiniciar o serviço, pode levar até 4 horas antes que uma nova máquina seja descoberta no Gerenciador de Operações do Centro do Sistema.) Após o serviço ter sido reiniciado, verifique se nenhum evento de erro foi registrado no log de eventos do Gerenciador de Operações neste computador.</span><span class="sxs-lookup"><span data-stu-id="bd74c-p102">After completing step 2, reboot the Health Agent service. (Rebooting the service will “force” discovery of the new machine. If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.). After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

