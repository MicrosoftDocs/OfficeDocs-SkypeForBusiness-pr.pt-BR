---
title: 'Lync Server 2013: atualizando a lista de habilitação do Outlook'
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
ms.openlocfilehash: f44de6e3b7756935829b008c585474e08f6f9969
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>Atualizando a lista de habilitação do Outlook no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-07_

Você pode garantir que o suplemento de reunião online do Microsoft Lync 2013 sempre permaneça habilitado para os usuários criando uma política que o inclui na lista de gerenciamento de suplementos do Outlook. A política de lista de gerenciamento de suplementos está incluída nos arquivos de modelo administrativo do Office para o console de gerenciamento de política de grupo. Ele cria uma chave do registro em\\políticas\\\\de software\\HKCU\\Microsoft\\Office\\15,0 Outlook15\\resiliênciay addinlist. Você pode adicionar um valor para ucaddin. dll a essa chave e configurar o valor de ucaddin. dll para que ele esteja sempre habilitado e para que os usuários não possam desabilitá-lo manualmente

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>Para adicionar ucaddin. dll à lista de suplementos do Outlook

  - Para a chave do registro Addinlist, localizada em\\políticas\\\\de software\\HKCU\\Microsoft\\Office\\15,0 Outlook15\\resiliênciay addinlist, adicione o seguinte valor:
    
      - Tipo de registro =\_reg sz
    
      - Name = ucaddin. dll
    
      - Valor = 1 (especifica que o suplemento está sempre habilitado e não pode ser gerenciado pelo usuário final)

</div>

</div>

<span> </span>

</div>

</div>

</div>

