---
title: 'Lync Server 2013: suporte à integração do Exchange e do SharePoint'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c4d378337643adf79557bd4bbb649a01948de27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Suporte à integração do Exchange e do SharePoint no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2017-01-18_

O Lync Server 2013 e o Lync 2013 podem comunicar-se com segurança com outros aplicativos e produtos de servidor, incluindo o Office 2013, o Exchange Server 2013, o Exchange Server 2016 e o SharePoint, caso você integre esses produtos. A integração do Lync Server 2013 e do Office oferece aos usuários acesso ao contexto às funcionalidades de mensagens instantâneas (IM), presença avançada, telefonia e conferência do Lync. Os usuários do Office podem acessar os recursos do Lync no cliente de mensagens e colaboração do Outlook 2013 e em outros programas do Office ou em uma página do SharePoint. Os usuários também podem exibir um registro de conversas do Lync na pasta histórico da conversa do Outlook. Quando integrado com o Exchange 2013, o Exchange 2016 ou o Exchange Online, o Lync Server 2013 também é compatível com o seguinte:

  - Repositório de contatos unificado, que permite aos usuários armazenar todas as informações de contato no Exchange ou no Exchange Online para que as informações estejam disponíveis globalmente no Lync 2013, Exchange, Outlook e Outlook Web App.

  - Histórico de conversas e histórico de webconferências, que é armazenado nas pastas de usuário do Exchange.

  - O conteúdo arquivado do Lync, como mensagens instantâneas e conteúdo da reunião, pode ser armazenado no armazenamento do Exchange.

<div>


> [!NOTE]  
> O Lync Server 2013 dá suporte à integração com versões anteriores do Microsoft Exchange Server e do SharePoint Server, mas nem toda a funcionalidade tem suporte com essas versões anteriores, como a integração do armazenamento de arquivamento com o Microsoft Exchange.<BR>Se você estiver migrando seus usuários para o Exchange 2013 ou o Exchange 2016, poderá usar o armazenamento do Exchange e o armazenamento do Lync Server de forma provisória enquanto concluir a migração. Não há suporte para o uso permanente do armazenamento do Exchange e do Lync Server.



</div>

A integração do Lync Server 2013 com o Exchange Server e do SharePoint Server requer a autenticação de servidor para servidor entre servidores que executam o Lync Server 2013, o Exchange Server e o SharePoint Server. O Lync Server 2013 oferece suporte ao protocolo OAuth (autorização aberta) para autenticação e autorização de servidor para servidor. Para a autenticação de servidor para servidor local entre dois servidores da Microsoft, não é necessário usar um servidor de token de terceiros. O Lync Server 2013, o Exchange Server e o SharePoint Server têm um servidor de token interno que pode ser usado para fins de autenticação entre si. Por exemplo, o Lync Server 2013 pode emitir e assinar um token de segurança por si só e usar esse token ao se comunicar com o Exchange. Nesse caso, não é necessário usar um servidor de token de terceiros.

O Lync Server 2013 dá suporte a dois cenários de autenticação de servidor para servidor. Isso inclui configuração de autenticação de servidor para servidor entre os seguintes:

  - Uma instalação local do Lync Server 2013 e uma instalação local do Exchange Server 2013, Exchange Server 2016 e/ou SharePoint Server.

  - Um par de componentes do Office (por exemplo, entre o Microsoft Exchange 365 e o Microsoft Lync Server 365 ou entre o Microsoft Lync Server 365 e o Microsoft SharePoint 365).

<div>


> [!NOTE]  
> Não há suporte para a autenticação de servidor para servidor entre um servidor local e um componente do Office 365 neste lançamento do Lync Server 2013. Entre outras coisas, isso significa que você não pode configurar a autenticação de servidor para servidor entre uma instalação local do Lync Server 2013 e do Microsoft Exchange 365.



</div>

Para obter detalhes sobre a autenticação de servidor para servidor, consulte Gerenciando a autenticação de servidor [para servidor (OAuth) e aplicativos de parceiros no Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) na documentação de implantação ou documentação de operações.

</div>

<span> </span>

</div>

</div>

</div>

