---
title: Configurando um nó do inspetor para participar da descoberta do System Center
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
ms.openlocfilehash: 49b34e623b885bb7e85afc258c1d533c2a8feb46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526998"
---
# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>Configurando um nó do Inspetor no Lync Server 2013 para participar da descoberta do System Center

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

Para garantir que o nó do Inspetor participa do processo de descoberta do System Center Operations Manager, você deve concluir o procedimento a seguir em um computador onde o console do System Center Operations Manager tenha sido instalado:

1.  Na guia **Administração**, clique em **Gerenciado por Agente**.

2.  Clique com o botão direito no nome do computador do nó do inspetor, e então clique em **Propriedades**. Na caixa de diálogo **Propriedades**, na guia **Segurança**, selecione **Permitir que este agente aja como um proxy e descubra objetos gerenciados em outros computadores**, e então clique em **OK**.

Após configurar o nó de observador para agir como um proxy, reinicie o computador do nó do inspetor. Após a reinicialização do computador, verifique se nenhum evento de erro está sendo registrado no log de eventos do Operations Manager nesse computador. Depois que o computador estiver em execução por 15 minutos, use o console do Operations Manager para verificar se os computadores do Lync Server estão listados na categoria **Lync** .

</div>

<span> </span>

</div>

</div>

</div>

