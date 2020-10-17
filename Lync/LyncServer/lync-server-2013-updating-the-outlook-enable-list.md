---
title: 'Lync Server 2013: atualizando a lista de habilitação do Outlook'
description: 'Lync Server 2013: atualizando a lista de habilitação do Outlook.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96edc327fa1b63d5da95eb6ea36a2296659910d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546227"
---
# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>Atualizando a lista de habilitação do Outlook no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-07_

Você pode garantir que o suplemento de reunião online para Microsoft Lync 2013 sempre permaneça habilitado para usuários criando uma política que o inclua na lista de gerenciamento de suplementos do Outlook. A política de Lista de Gerenciamento de Suplementos vem incluída nos arquivos de modelos administrativos do Office do Console de Gerenciamento de Política de Grupo. Ele cria uma chave de registro em \\ políticas de software HKCU \\ \\ Microsoft \\ Office \\ 15,0 \\ Outlook15 \\ resiliênciay \\ addinlist. Você pode adicionar um valor para o ucaddin.dll a essa chave e configurar o valor de ucaddin.dll para que ele esteja sempre habilitado e, para que os usuários não possam desabilitá-lo manualmente

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>Para adicionar ucaddin.dll à lista de suplementos do Outlook

  - Para a chave do registro Addinlist, localizada em \\ políticas de software HKCU \\ \\ Microsoft \\ Office \\ 15,0 \\ Outlook15 \\ resiliênciay \\ addinlist, adicione o seguinte valor:
    
      - Tipo de registro = REG \_ sz
    
      - Nome = ucaddin.dll
    
      - Valor = 1 (especifica que o suplemento sempre esteja habilitado e não possa ser gerenciado pelos usuários)

</div>

</div>

<span> </span>

</div>

</div>

</div>

