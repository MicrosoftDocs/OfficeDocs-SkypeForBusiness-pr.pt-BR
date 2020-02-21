---
title: 'Lync Server 2013: componentes usados pelo aplicativo comunicado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61f0de957889f108ff7b7cec3ad71e984fd61f11
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Componentes usados pelo aplicativo comunicado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-13_

No Lync Server 2013, o aplicativo de anúncio é um componente do aplicativo grupo de resposta. Ao implantar o Enterprise Voice, o aplicativo de anúncio é automaticamente instalado e ativado junto com o aplicativo grupo de resposta. Esta seção descreve os componentes que dão suporte ao aplicativo comunicado.

<div>

## <a name="announcement-application-components"></a>Componentes de Aplicativo de Comunicado

Os seguintes componentes do Lync Server oferecem suporte ao aplicativo announcement:

  - ****   Serviço de aplicativo de serviço de aplicativo fornece uma plataforma para implantação, hospedagem e gerenciamento de aplicativos de comunicação unificada. O serviço de aplicativo é instalado automaticamente em todos os servidores front-end em um pool de front-ends e em cada servidor Standard Edition.

  - **Aplicativo de grupo de resposta**   o aplicativo grupo de resposta é um dos aplicativos de comunicações unificadas hospedados pelo serviço de aplicativo. Quando um intervalo de números de telefone não atribuído é configurado para rotear para um comunicado, o aplicativo grupo de resposta é necessário para rotear as chamadas feitas para o número de telefone. (O aplicativo grupo de resposta não é necessário se todos os intervalos estiverem configurados para rotear para a Unificação de mensagens (UM) do Exchange.

  - ****   Arquivos de áudio os arquivos de áudio são usados para os comunicados.

  - **Repositório de arquivos**   o aplicativo de comunicado usa o repositório de arquivos para armazenar seus arquivos de áudio.

  - **Painel de controle do Lync Server**   você pode usar o painel de controle do Lync Server para configurar a tabela de número não atribuído.

  - **Shell de gerenciamento do Lync Server**   você pode usar os cmdlets do Shell de gerenciamento do Lync Server para definir as configurações de anúncio e a tabela de número não atribuído.

</div>

</div>

<span> </span>

</div>

</div>

</div>

