---
title: 'Lync Server 2013: Configurando opções de imagem padrão'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc6bb0368b97e41402f2e0abf0834cf23f078c08
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514808"
---
# <a name="configuring-default-picture-options-in-lync-server-2013"></a>Configurando opções de imagem padrão no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-22_

Por padrão, as imagens dos usuários são exibidas automaticamente. Se os usuários quiserem ocultar suas imagens, poderão selecionar a opção **ocultar minha imagem** no cliente do Lync. No entanto, essa configuração é ignorada por alguns outros aplicativos do Office.

Se a possibilidade de exibir imagens mesmo quando desativada pelo usuário é uma preocupação, você pode alterar as configurações de exibição de imagem do Lync globalmente ou para um site ou serviço para que as imagens dos usuários não sejam mostradas por padrão. Use o seguinte cmdlet do Shell de gerenciamento do Lync Server para que as imagens do usuário não sejam mostradas, a menos que explicitamente selecione a opção **mostrar minha imagem** no cliente:

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

Para obter mais informações sobre esse cmdlet, consulte [set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) na documentação do Shell de gerenciamento do Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

