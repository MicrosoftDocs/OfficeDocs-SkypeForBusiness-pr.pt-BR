---
title: 'Lync Server 2013: pré-requisitos e funções de configuração do anúncio'
description: 'Lync Server 2013: pré-requisitos de configuração do comunicado e funções.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8e6e7009adc6826c255e28ddda925b0e9be5fd6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561887"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Pré-requisitos e funções de configuração de comunicado no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-25_

O comunicado é um recurso de gerenciamento de chamadas do Enterprise Voice. Este tópico descreve o que você precisa ter em vigor antes de configurar o comunicado e as atribuições de função necessárias para executar tarefas de configuração.

Esta seção supõe que você leu a documentação de planejamento relacionada ao anúncio (consulte [Planning for Call Management Features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="announcement-configuration-prerequisites"></a>Pré-requisitos de Configuração do Comunicado

O aplicativo de comunicado requer os seguintes componentes:

  - Serviço de aplicativos

  - Aplicativo do Grupo de Resposta

  - Repositório de Arquivos (para armazenar arquivos de áudio)

Todos estes componentes são instalados por padrão ao implantar o Enterprise Voice.

</div>

<div>

## <a name="announcement-configuration-roles"></a>Funções da configuração do Comunicado

Você pode usar as seguintes ferramentas administrativas para configurar os Comunicados:

  - Painel de Controle do Lync Server

  - Shell de Gerenciamento do Lync Server

A configuração do aplicativo de anúncio requer uma das seguintes funções administrativas:

  - **CsVoiceAdministrator**     Essa função de administrador pode criar, configurar e gerenciar todas as configurações e políticas relacionadas a voz, incluindo configurações de anúncio.

  - **CsServerAdministrator**     Essa função de administrador pode gerenciar, monitorar e solucionar problemas de servidores e serviços e definir todas as configurações de comunicado.

  - **CsAdministrator**     Essa função de administrador pode realizar todas as tarefas administrativas e modificar todas as configurações.

  - **CsViewOnlyAdministrator**     Essa função de administrador pode exibir a implantação para monitorar a integridade da implantação.

<div>


> [!NOTE]  
> Para obter detalhes sobre os direitos de usuário administrativo, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> na documentação de planejamento.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Implantando o Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  


[Planejamento de recursos de gerenciamento de chamadas no Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

