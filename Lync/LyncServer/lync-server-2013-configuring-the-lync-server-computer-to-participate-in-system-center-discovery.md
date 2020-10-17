---
title: Configurando o computador do Lync Server para participar da descoberta do System Center
description: Configurar o computador do Lync Server para participar da descoberta do System Center.
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
ms.openlocfilehash: 44d25ba3de673084b2e64e17790a2776cbe57f07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556847"
---
# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>Configurando o computador do Lync Server 2013 para participar da descoberta do System Center

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-20_

Para certificar-se de que seu novo agente do Lync Server participa do processo de descoberta para o System Center Operations Manager, você deve concluir o procedimento a seguir em cada computador em que o console do System Center Operations Manager tenha sido instalado:

1.  Na guia **Administração**, clique em **Agente Gerenciado**.

2.  Clique com o botão direito no nome do computador e clique em **Propriedades**. Na caixa de diálogo **Propriedades**, na guia **Segurança**, selecione **Permitir que este agente haja como um proxy e descubra objetos gerenciados em outros computadores** e clique em **OK**.

Após concluir a etapa 2, reinicie o serviço do Agente de Integridade. (Reiniciar o serviço "forçará" a descoberta da nova máquina. Se você não reiniciar o serviço, pode levar até 4 horas antes que uma nova máquina seja descoberta no Gerenciador de Operações do Centro do Sistema.) Após o serviço ter sido reiniciado, verifique se nenhum evento de erro foi registrado no log de eventos do Gerenciador de Operações neste computador.

</div>

<span> </span>

</div>

</div>

</div>

