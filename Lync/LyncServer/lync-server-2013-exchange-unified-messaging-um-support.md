---
title: 'Lync Server 2013: Suporte da Unificação de Mensagens (UM) do Exchange'
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
ms.openlocfilehash: 8925bd8a07693800c49ff2d818d3677b33452b97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Suporte da Unificação de Mensagens (UM) do Exchange no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

O Lync Server 2013 oferece suporte à integração com o Exchange Unified Messaging (UM) para combinar mensagens de voz e mensagens de email em uma única infra-estrutura de mensagens. No Exchange 2013, o UM do Exchange consiste no serviço UM do Exchange, que é instalado e executado no servidor de caixa de correio, e o roteador de chamada de UM, que é instalado e executado no servidor de acesso para cliente. Para implantações do Lync Server 2013 Enterprise Voice, o Exchange UM combina mensagens de voz e mensagens de email em uma única loja que pode ser acessada por meio de um telefone (ou seja, o Outlook Voice Access) ou um computador. O Exchange UM e o Lync Server 2013 trabalham juntos para fornecer atendimento de chamada, Outlook Voice Access e serviços de atendedor automático para usuários do Enterprise Voice.

Além do suporte para a integração com implantações locais do Exchange UM, o Lync Server 2013 é compatível com a integração com o Exchange UM hospedado. Isso permite que você forneça mensagens de voz para seus usuários se migrar alguns ou todos eles para um provedor de serviços do Exchange hospedado, como o Microsoft Exchange Online.

O Lync Server 2013 suporta as seguintes versões:

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (obrigatório) ou com Service Pack mais recente (recomendado)

  - Microsoft Exchange Server 2007 com Service Pack 1 (SP1) (necessário) ou Service Pack mais recente (recomendado)

Você não pode colocar o Exchange UM com o Lync Server 2013 ou um banco de dados do Lync Server 2013. Você pode instalar o Exchange UM e o Lync Server 2013 em florestas separadas.

<div>


> [!NOTE]  
> O Exchange UM pode não ser necessário para implantações do Enterprise Voice que tenham um PBX implantado, porque o PBX pode continuar a fornecer correio de voz e serviços relacionados a todos os usuários. Se, eventualmente, desative o PBX (por exemplo, se você implantar o entroncamento SIP para conectividade PSTN (rede telefônica pública comutada)), será necessário reconfigurar o Exchange UM para fornecer correio de voz para os usuários que usaram anteriormente o sistema de caixa postal do PBX.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Componentes e topologias para o Sistema de Mensagens Instantâneas local no Lync Server 2013](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Suporte à integração Exchange UM hospedado no Lync Server 2013](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

