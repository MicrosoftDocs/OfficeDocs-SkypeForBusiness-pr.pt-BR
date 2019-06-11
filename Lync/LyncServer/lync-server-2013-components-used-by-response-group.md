---
title: 'Lync Server 2013: Componentes usados pelo Grupo de Respostas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f52ceb18c355f6d867b5b3b4485434df83683d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a>Componentes usados pelo Grupo de Resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-11_

O aplicativo grupo de resposta é habilitado automaticamente quando você implanta o Enterprise Voice. Esta seção descreve os componentes que dão suporte ao aplicativo de grupo de resposta.

<div>

## <a name="response-group-components"></a>Componentes do grupo de resposta

Os seguintes componentes do Microsoft Lync Server 2013 suportam o aplicativo do grupo de resposta:

  - ****   O serviço de aplicativo de serviço de aplicativo fornece uma plataforma para implantação, hospedagem e gerenciamento de aplicativos de comunicação unificada, como o grupo de resposta. O serviço de aplicativo é instalado automaticamente em todos os servidores front-end em um pool Front-end e em cada servidor Standard Edition.

  - **Aplicativo de grupo de resposta**   o aplicativo grupo de resposta é um dos aplicativos de comunicação unificada hospedados pelo serviço de aplicativo. Ela é incluída automaticamente quando você implanta o grupo de resposta. O aplicativo grupo de resposta roteia e enfileira chamadas recebidas para grupos de agentes.

  - **Pacote de idiomas**   um pacote de idiomas é necessário para dar suporte a conversão de texto em fala e reconhecimento de fala. Essas tecnologias de fala são usadas quando você configura mensagens, como a mensagem de boas-vindas e outros avisos e perguntas e respostas de reação interativas de voz (IVR). Por padrão, os 26 pacotes de idiomas com suporte são instalados quando você implanta o Lync Server 2013.

  - **Arquivos de áudio**   os arquivos de áudio são usados para mensagens e música em espera.

  - ****   Grupo de resposta do repositório de arquivos usa o repositório de arquivos para armazenar arquivos de áudio. Vários pools de grupos de resposta podem usar a mesma instância do repositório de arquivos.

  - **Ferramenta de configuração do grupo de resposta**   a ferramenta de configuração do grupo de resposta é uma ferramenta baseada na Web que é usada para criar e configurar grupos de resposta. A ferramenta de configuração de grupo de resposta é incluída durante a instalação de serviços Web.

  - **Painel de controle do Microsoft Lync Server 2013**   você pode usar o painel de controle do Lync Server para configurar e configurar filas e grupos de agente para grupos de resposta.

  - **Shell de gerenciamento do Lync Server**   todas as configurações do grupo de resposta podem ser configuradas usando cmdlets do shell do Shell de gerenciamento do Lync Server.

  - **Os agentes formais do Microsoft Lync 2013**   (agentes que são necessários para entrar no grupo antes de aceitarem chamadas para o grupo) usam o Lync 2013 para entrar e sair do grupo. Se um grupo de agente estiver configurado para agentes formais, os agentes clicarão em um item de menu no Lync 2013 para abrir o Internet Explorer e exibir um console de página da Web para entrar e sair do grupo.

  - ****   Os serviços Web de serviços Web são necessários para a ferramenta de configuração de grupo de resposta, o console de entrada e de saída dos agentes, o painel de controle do Lync Server e o serviço Web de cliente do grupo de resposta.

  - ****   Aplicativo de grupo de resposta de serviço Web de cliente de grupo de resposta fornece um serviço Web de cliente, que pode ser usado por aplicativos de terceiros para recuperar informações sobre agentes, associação de grupo de agente, status de entrada do agente, status da chamada para grupos, e os grupos que dão suporte a chamadas anônimas. Lync 2013 e Lync 2010 Attendant use o serviço Web de cliente de grupo de resposta para recuperar a lista de grupos de resposta que os agentes podem usar para fazer chamadas anônimas. O serviço Web cliente é incluído durante a instalação de serviços Web.

</div>

</div>

<span> </span>

</div>

</div>

</div>

