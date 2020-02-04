---
title: 'Lync Server 2013: Pré-requisitos para habilitar autenticação Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adb722f69dcd975d7f346b6e4db8f8ff140f4ac3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>Pré-requisitos para habilitar autenticação Kerberos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Antes de habilitar a autenticação Kerberos, certifique-se de concluir todas as preparações de configuração e infraestrutura:

  - O esquema do Active Directory é estendido para o Lync Server 2013.

  - A preparação da floresta do Active Directory é concluída para o Lync Server 2013.

  - A preparação do domínio do Active Directory foi concluída para o Lync Server 2013.

  - O repositório de gerenciamento central foi instalado e está disponível com êxito.

  - A topologia foi criada e publicada usando o construtor de topologias.

  - Os servidores e funções que exigem serviços Web foram definidos e implantados, incluindo servidores front-end, servidores de edição padrão e directors.

  - Os serviços de informações da Internet (IIS) são configurados e implantados com os serviços de função recomendados para dar suporte a serviços Web no Lync Server 2013.

Depois que os pré-requisitos forem atendidos, você deve estar pronto para criar uma ou mais contas para serviços Web a serem usados para a autenticação Kerberos para a implantação. No mínimo, você precisa criar uma conta de autenticação Kerberos para cada implantação. No entanto, você pode criar uma conta para cada site para fornecer autenticação Kerberos local no site. Você só pode especificar uma conta de autenticação Kerberos por site.

</div>

<span> </span>

</div>

</div>

</div>

