---
title: 'Lync Server 2013: Configurando versões de cliente suportadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc604efae64d907879ad175b13d7fec9c6b9d99
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a>Configurando as versões de cliente suportadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-12-14_

No Lync Server 2013, você pode configurar políticas de versão do cliente para especificar as versões dos clientes com suporte no seu ambiente. Além disso, você pode usar a configuração de versão do cliente global para especificar uma ação padrão para clientes que ainda não têm uma política de versão definida e, portanto, não são explicitamente suportadas ou restritas.

Você também pode usar as políticas de versão do cliente para gerenciar as atualizações do cliente. Ao definir uma política de versão de cliente e usar as opções **permitir e atualizar** e **bloquear e atualizar**, os clientes receberão software atualizado do serviço de atualização do Windows Server (se você estiver usando esse serviço) ou do Microsoft Update.

<div>

## <a name="client-version-policy-settings"></a>Configurações de política de versão do cliente

A política de versão de cliente padrão requer que todos os clientes executem o Lync. Se os clientes do seu ambiente estiverem executando versões anteriores do Communicator, talvez seja necessário reconfigurar as regras de versão do cliente para impedir que os clientes e dispositivos sejam bloqueados ou atualizados inesperadamente ao se conectar ao Lync Server 2013. Você pode modificar a regra padrão ou pode adicionar uma regra superior na lista política de versão do cliente para substituir a regra padrão. Além disso, como as atualizações cumulativas (CUs) são lançadas, você deve configurar a política de versão do cliente para exigir as atualizações mais recentes. Para obter detalhes, consulte [especificando os aplicativos cliente que podem ser usados para fazer logon no Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) na documentação operações.

</div>

</div>

<span> </span>

</div>

</div>

</div>

