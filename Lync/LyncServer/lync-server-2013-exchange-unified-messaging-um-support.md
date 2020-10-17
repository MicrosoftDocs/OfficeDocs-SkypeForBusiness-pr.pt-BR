---
title: 'Lync Server 2013: suporte à unificação de mensagens (UM) do Exchange'
description: 'Lync Server 2013: suporte à unificação de mensagens (UM) do Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 563517bb72167bbab0b08eba3b1359ae3ab52836
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564797"
---
# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Suporte à unificação de mensagens (UM) do Exchange no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

O Lync Server 2013 oferece suporte à integração com a Unificação de mensagens (UM) do Exchange para combinar mensagens de voz e mensagens de email em uma única infraestrutura de mensagens. No Exchange 2013, o UM do Exchange consiste no serviço UM do Exchange, que é instalado e executado no servidor de caixa de correio, e o roteador de chamada de UM, que é instalado e executado no servidor de acesso para cliente. Para as implantações do Lync Server 2013 Enterprise Voice, o Exchange UM combina mensagens de voz e mensagens de email em um único repositório que pode ser acessado por um telefone (ou seja, Outlook Voice Access) ou um computador. O Exchange UM e o Lync Server 2013 trabalham juntos para fornecer atendimento de chamadas, Outlook Voice Access e serviços de atendedor automático para usuários do Enterprise Voice.

Além do suporte para integração com implantações locais do UM do Exchange, o Lync Server 2013 oferece suporte à integração com a UM do Exchange hospedada. Isso permite que você forneça mensagens de voz aos seus usuários se migrar alguns ou todos eles para um provedor de serviço do Exchange hospedado, como o Microsoft Exchange Online.

O Lync Server 2013 oferece suporte às seguintes versões:

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (obrigatório) ou com o Service Pack mais recente (recomendado)

  - Microsoft Exchange Server 2007 com Service Pack 1 (SP1) (obrigatório) ou Service Pack mais recente (recomendado)

Você não pode colocar o UM do Exchange com o Lync Server 2013 ou um banco de dados do Lync Server 2013. Você pode instalar o UM do Exchange e o Lync Server 2013 em florestas separadas.

<div>


> [!NOTE]  
> O Exchange UM pode não ser necessário para implantações do Enterprise Voice que tenham um PBX implantado, pois o PBX pode continuar a fornecer caixa postal e serviços relacionados a todos os usuários. Se você eventualmente desativar o PBX (por exemplo, se você implantar o tronco SIP para conectividade PSTN (rede telefônica pública comutada), deverá reconfigurar o UM do Exchange para fornecer caixa postal aos usuários que usavam o sistema de caixa postal do PBX.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Componentes e topologias para Unificação de mensagens no local no Lync Server 2013](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Suporte à integração de UM do Exchange hospedado no Lync Server 2013](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

