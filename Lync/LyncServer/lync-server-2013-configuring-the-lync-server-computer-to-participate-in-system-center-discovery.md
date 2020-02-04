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
ms.openlocfilehash: 8cec18903f1621d5a616debbbdd16f3c834ac21c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>Configurando o computador do Lync Server 2013 para participar da descoberta do System Center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-20_

Para garantir que seu novo agente do Lync Server participe do processo de descoberta do System Center Operations Manager, você deve concluir o procedimento a seguir em cada computador em que o console do System Center Operations Manager foi instalado:

1.  Na guia **Administração** , clique em **agente gerenciado**.

2.  Clique com o botão direito no nome do computador e clique em **Propriedades**. Na caixa de diálogo **Propriedades** , na guia **segurança** , selecione **permitir que esse agente atue como um proxy e descubra objetos gerenciados em outros computadores**e clique em **OK**.

Depois de concluir a etapa 2, reinicie o serviço de agente de integridade. (A reinicialização do serviço irá "forçar" a descoberta da nova máquina. Se você não reinicializar o serviço, pode levar até 4 horas para que o novo computador seja descoberto pelo System Center Operations Manager.). Após a reinicialização do serviço, verifique se nenhum evento de erro está sendo gravado no log de eventos do Operations Manager nesse computador.

</div>

<span> </span>

</div>

</div>

</div>

