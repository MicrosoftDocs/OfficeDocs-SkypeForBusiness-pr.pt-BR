---
title: 'Lync Server 2013: componentes usados pelo grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bfefeabc1c9f64a4f1bf9fa794b269fbdcb0650
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a>Componentes usados pelo grupo de resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-11_

O aplicativo grupo de resposta é automaticamente habilitado quando você implanta o Enterprise Voice. Esta seção descreve os componentes que dão suporte ao aplicativo grupo de resposta.

<div>

## <a name="response-group-components"></a>Componentes do Grupo de Resposta

Os seguintes componentes do Microsoft Lync Server 2013 oferecem suporte ao aplicativo grupo de resposta:

  - ****   Serviço de aplicativo de serviço de aplicativo fornece uma plataforma para implantação, hospedagem e gerenciamento de aplicativos de comunicação unificada, como grupo de resposta. O serviço de aplicativo é instalado automaticamente em todos os servidores front-end em um pool de front-ends e em cada servidor Standard Edition.

  - **Aplicativo de grupo de resposta**   o aplicativo grupo de resposta é um dos aplicativos de comunicações unificadas hospedados pelo serviço de aplicativo. Ele é incluído automaticamente quando você implanta o grupo de resposta. O aplicativo grupo de resposta roteia e enfileira chamadas de entrada para grupos de agentes.

  - **Pacote de idiomas**   um pacote de idiomas é necessário para dar suporte a conversão de texto em fala e reconhecimento de fala. Essas tecnologias de fala são usadas ao configurar mensagens, como a mensagem de boas-vindas e outros prompts, e questões e respostas de IVR (resposta interativa de voz). Por padrão, os 26 pacotes de idiomas com suporte são instalados quando você implanta o Lync Server 2013.

  - **Arquivos de áudio os**   arquivos de áudio são usados para mensagens e música em espera.

  - ****   O grupo de resposta do repositório de arquivos usa o repositório de arquivos para armazenar arquivos de áudio. Vários pools de grupo de resposta podem usar a mesma instância do repositório de arquivos.

  - **Ferramenta de configuração do grupo de resposta**   a ferramenta de configuração do grupo de resposta é uma ferramenta baseada na Web que é usada para criar e configurar grupos de resposta. A ferramenta de configuração do grupo de resposta é incluída quando você instala os serviços Web.

  - **Painel de controle do Microsoft Lync Server 2013**   você pode usar o painel de controle do Lync Server para configurar e configurar grupos de agentes e filas para grupos de resposta.

  - **Shell de gerenciamento do Lync Server**   todas as configurações do grupo de resposta podem ser configuradas usando os cmdlets do Shell de gerenciamento do Lync Server.

  - **Os agentes formais do Microsoft Lync 2013**   (agentes que são necessários para entrar no grupo antes de aceitar chamadas para o grupo) usam o Lync 2013 para entrar e sair do grupo. Se um grupo de agentes estiver configurado para agentes formais, os agentes clicam em um item de menu no Lync 2013 para abrir o Internet Explorer e exibir um console de página da Web para entrar e sair do grupo.

  - ****   Os serviços Web de serviços Web são necessários para a ferramenta de configuração de grupo de resposta, o console de entrada e de saída dos agentes, o painel de controle do Lync Server e o serviço Web do cliente do grupo de resposta.

  - **Serviço Web do cliente do grupo de resposta**   o aplicativo de grupo de resposta fornece um serviço Web de cliente, que pode ser usado por aplicativos de terceiros para recuperar informações sobre agentes, associação de grupo de agentes, status de entrada de agentes, status da chamada para grupos e os grupos que oferecem suporte a chamadas anônimas. Lync 2013 e Lync 2010 Attendant use Response Group Client Web Service para recuperar a lista de grupos de resposta que os agentes podem usar para fazer chamadas anônimas. O serviço web de cliente é incluído durante a instalação dos Serviços Web.

</div>

</div>

<span> </span>

</div>

</div>

</div>

