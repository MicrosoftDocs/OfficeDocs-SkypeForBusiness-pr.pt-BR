---
title: 'Lync Server 2013: pré-requisitos de software para o Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b504c498b2f07915f741e6c3172e911c7d40dae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519618"
---
# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Pré-requisitos de software para o Enterprise Voice no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-03_

Verifique se a infraestrutura em que você pretende implantar o Enterprise Voice atende aos seguintes pré-requisitos de software:

  - O Lync Server 2013 Standard Edition ou Enterprise Edition está instalado e operacional em sua rede.

  - Todos os servidores de borda são implantados e operados em sua rede de perímetro, incluindo servidores de borda executando o serviço de borda de acesso, serviço de borda A/V, serviço de borda de Webconferência e um proxy reverso.

  - O Microsoft Exchange Server 2007 Service Pack 3 (SP3), o Microsoft Exchange Server 2010 ou o Microsoft Exchange Server 2013 é necessário para integrar a Unificação de mensagens do Exchange ao Lync Server e fornecer notificações ricas e informações de log de chamadas aos pontos de extremidade do Lync.

  - Um ou mais usuários foram criados e habilitados para o Lync Server.

  - Os clientes e dispositivos do Lync foram implantados com êxito.

  - O construtor de topologias está instalado em um servidor em sua rede.

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>Próximas etapas: Verificar pré-requisitos de segurança e configuração

Depois de verificar os pré-requisitos de software para o Enterprise Voice, você pode usar a documentação para continuar a preparação para a implantação do Enterprise Voice:

1.  Verifique a segurança, a configuração do usuário e o hardware perquisites, conforme descrito em [Security and Configuration Prerequisites for Enterprise Voice in Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).

2.  Instale o servidor de mediação, conforme descrito em [install the files for Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md), mas *somente* se você deseja implantar um servidor de mediação autônomo ou pool porque os servidores de mediação são instalados como parte do processo de implantação do servidor de front-end ou Standard Edition quando colocado.

3.  Configure as conexões de tronco para fornecer conectividade PSTN para os usuários, conforme descrito em [Configuring Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

