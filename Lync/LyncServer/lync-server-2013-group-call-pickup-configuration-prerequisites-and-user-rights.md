---
title: Pré-requisitos de configuração de recebimento de chamadas de grupo e direitos de usuário
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b15be02b48c5e3f95a9b05475bea42284ec275
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498788"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Pré-requisitos de configuração de recebimento de chamadas de grupo e direitos de usuário no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-30_

O recebimento de chamadas em grupo é um recurso de gerenciamento de chamadas que é instalado por padrão ao implantar o Enterprise Voice. Este tópico descreve o que você precisa ter em vigor antes de poder configurar o recebimento de chamadas em grupo e os direitos de usuário necessários para executar tarefas de configuração.

Esta seção supõe que você leu a documentação de planejamento relacionada ao recebimento de chamadas em grupo (consulte [Planning for Group Call pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>Pré-requisitos de configuração de recebimento de chamadas de grupo

O recebimento de chamadas em grupo requer os seguintes componentes:

  - Serviço de aplicativos

  - Call Park application

Esses componentes são instalados automaticamente quando você implanta o Enterprise Voice.

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>Direitos de usuário de configuração de recebimento de chamadas de grupo

Use as seguintes ferramentas administrativas para configurar o recebimento de chamadas em grupo:

  - Shell de Gerenciamento do Lync Server

  - Ferramenta SEFAUtil Resource Kit

Use o Shell de gerenciamento do Lync Server para criar e gerenciar grupos de recebimento de chamada na tabela de órbita de estacionamento de chamada. Use a ferramenta SEFAUtil Resource Kit para atribuir um grupo de recebimento de chamadas e habilitar o recebimento de chamadas em grupo para usuários ou para desabilitar o recebimento de chamadas em grupo para usuários.

A configuração de recebimento de chamadas em grupo exige qualquer uma das seguintes funções administrativas, dependendo da tarefa:

  - **CsVoiceAdministrator:** Essa função de administrador pode criar, configurar e gerenciar todas as configurações e políticas relacionadas a voz.

  - **CsUserAdministrator:** Essa função de administrador pode habilitar o recebimento de chamadas em grupo para usuários. Esta função de administração também pode ter acesso de exibição somente leitura para todas as configurações de voz.

  - **CsServerAdministrator:** Essa função de administrador pode gerenciar, monitorar e solucionar problemas de servidores e serviços.

  - **CsAdministrator:** Essa função de administrador pode realizar todas as tarefas do CsVoiceAdministrator, CsServerAdministrator e CsUserAdministrator.

<div>


> [!NOTE]
> Para obter detalhes sobre os direitos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> na documentação de planejamento.



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

