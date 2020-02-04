---
title: 'Lync Server 2013: Pré-requisitos de software para Enterprise Voice'
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
ms.openlocfilehash: cb85a8da9fe0d009f46ef23b919aeb9fd006fab4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Pré-requisitos de software para Enterprise Voice no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-03_

Verifique se a infraestrutura na qual você pretende implantar o Enterprise Voice atende aos seguintes pré-requisitos de software:

  - O Lync Server 2013 Standard Edition ou Enterprise Edition está instalado e operacional em sua rede.

  - Todos os servidores de borda são implantados e operacionais em sua rede de perímetro, incluindo os servidores de borda executando o serviço de borda de acesso, o serviço de borda A/V, o serviço de borda de Webconferência e um proxy reverso.

  - O Microsoft Exchange Server 2007 Service Pack 3 (SP3), Microsoft Exchange Server 2010 ou Microsoft Exchange Server 2013 é necessário para integrar a Unificação de mensagens do Exchange ao Lync Server e para fornecer notificações avançadas e informações de registro de chamadas para o Pontos de extremidade do Lync.

  - Um ou mais usuários foram criados e habilitados para o Lync Server.

  - Os clientes e dispositivos do Lync foram implantados com êxito.

  - O construtor de topologias está instalado em um servidor na sua rede.

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>Próximas etapas: verificar pré-requisitos de segurança e configuração

Depois de verificar os pré-requisitos de software para o Enterprise Voice, você pode usar a documentação para continuar preparando-se para a implantação do Enterprise Voice:

1.  Verifique a segurança, a configuração do usuário e as perquisites de hardware, conforme descrito em [pré-requisitos de configuração e segurança para o Enterprise Voice no Lync Server 2013](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md).

2.  Instale o servidor de mediação, conforme descrito em [instalar os arquivos para o servidor de mediação no Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md), mas *somente* se você quiser implantar um servidor ou pool autônomo de mediação, pois os servidores de mediação são instalados como parte do processo de implantação do servidor do front-end ou da edição padrão quando posicionado.

3.  Configure conexões de tronco para fornecer conectividade PSTN para usuários, conforme descrito em [Configurando troncos no Lync Server 2013](lync-server-2013-configuring-trunks.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

