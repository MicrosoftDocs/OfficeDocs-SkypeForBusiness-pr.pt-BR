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

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>Configurando um nó de Inspetor no Lync Server 2013 para participar da descoberta do System Center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

Para garantir que o nó do Inspetor participe do processo de descoberta do System Center Operations Manager, você deve concluir o procedimento a seguir em um computador em que o console do System Center Operations Manager foi instalado:

1.  Na guia **Administração** , clique em **agente gerenciado**.

2.  Clique com o botão direito do mouse no nome do computador do nó do Inspetor e, em seguida, clique em **Propriedades**. Na caixa de diálogo **Propriedades** , na guia **segurança** , selecione **permitir que esse agente atue como um proxy e descubra objetos gerenciados em outros computadores**e clique em **OK**.

Depois de configurar o nó do inspetor para atuar como um proxy, reinicialize o computador do nó do Inspetor. Depois que o computador for reinicializado, verifique se nenhum evento de erro está sendo gravado no log de eventos do Operations Manager nesse computador. Depois que o computador estiver em execução por 15 minutos ou então, use o console do Operations Manager para verificar se seus computadores do Lync Server estão listados na categoria **Lync** .

</div>

<span> </span>

</div>

</div>

</div>

