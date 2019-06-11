---
title: 'Lync Server 2013: Pré-requisitos e funções de configuração de Comunicado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb5f909170e1de2566e21e9305175211c306fee6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Pré-requisitos e funções de configuração de Comunicado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-25_

O anúncio é um recurso de gerenciamento de chamadas de voz empresarial. Este tópico descreve o que você precisa ter em vigor antes de poder configurar as atribuições de anúncio e de função necessárias para executar tarefas de configuração.

Esta seção pressupõe que você leu a documentação de planejamento relacionada ao anúncio (consulte [planejando os recursos de gerenciamento de chamadas no Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="announcement-configuration-prerequisites"></a>Pré-requisitos de configuração do comunicado

O aplicativo de anúncio requer os seguintes componentes:

  - Serviço de aplicativos

  - Aplicativo Grupo de Resposta

  - Armazenamento de arquivos, para armazenar arquivos de áudio

Todos esses componentes são instalados por padrão quando você implanta o Enterprise Voice.

</div>

<div>

## <a name="announcement-configuration-roles"></a>Funções de configuração do anúncio

Você pode usar as seguintes ferramentas administrativas para configurar comunicados:

  - Painel de Controle do Lync Server

  - Shell de Gerenciamento do Lync Server

A configuração do aplicativo de anúncio requer uma das seguintes funções administrativas:

  - **CsVoiceAdministrator**   essa função de administrador pode criar, configurar e gerenciar todas as configurações e políticas relacionadas a voz, incluindo configurações de lançamento.

  - **CsServerAdministrator**   essa função de administrador pode gerenciar, monitorar e solucionar problemas de servidores e serviços e configurar todas as configurações de anúncio.

  - **CsAdministrator**   essa função de administrador pode executar todas as tarefas administrativas e modificar todas as configurações.

  - **CsViewOnlyAdministrator**   essa função de administrador pode exibir a implantação para monitorar a integridade da implantação.

<div>


> [!NOTE]  
> Para obter detalhes sobre direitos de usuário administrativo, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planejando o controle de acesso baseado em função no Lync Server 2013</A> na documentação de planejamento.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Implantando o Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  


[Planejando os recursos de gerenciamento de chamadas no Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

