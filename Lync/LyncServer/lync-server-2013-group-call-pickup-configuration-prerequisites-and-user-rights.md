---
title: Pré-requisitos de configuração de recebimento de chamadas de grupo e direitos de usuário
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2eb0af5b78d5d391ba055e557ad71da79484b5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Chamadas em grupo escolha pré-requisitos de configuração e direitos de usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-30_

O recebimento de chamadas em grupo é um recurso de gerenciamento de chamadas que é instalado por padrão quando você implanta o Enterprise Voice. Este tópico descreve o que você precisa ter em vigor antes de poder configurar o recebimento de chamadas em grupo e os direitos de usuário necessários para executar tarefas de configuração.

Esta seção pressupõe que você leu a documentação de planejamento relacionada à retirada de chamadas em grupo (consulte [planejar a coleta de chamadas em grupo no Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>Pré-requisitos de configuração de recebimento de chamadas de grupo

O recebimento de chamadas em grupo requer os seguintes componentes:

  - Serviço de aplicativos

  - Aplicativo de Estacionamento de Chamada

Esses componentes são instalados automaticamente quando você implanta o Enterprise Voice.

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>Direitos de usuário de configuração de recebimento de chamada de grupo

Use as seguintes ferramentas administrativas para configurar o recebimento de chamadas em grupo:

  - Shell de Gerenciamento do Lync Server

  - Ferramenta SEFAUtil Resource Kit

Use o Shell de gerenciamento do Lync Server para criar e gerenciar grupos de recebimento de chamadas na tabela órbita do estacionamento de chamada. Use a ferramenta kit de recursos do SEFAUtil para atribuir um grupo de encaminhamento de chamadas e habilitar o recurso de recebimento de chamadas em grupo para usuários ou para desabilitar a retirada de chamadas em grupo para usuários.

A configuração da retirada de chamadas em grupo requer qualquer uma das seguintes funções administrativas, dependendo da tarefa:

  - **CsVoiceAdministrator:** Essa função de administrador pode criar, configurar e gerenciar todas as configurações e políticas relacionadas a voz.

  - **CsUserAdministrator:** Essa função de administrador pode permitir que o recebimento de chamadas em grupo seja usuário. Essa função de administrador também tem acesso de exibição somente leitura a todas as configurações de voz.

  - **CsServerAdministrator:** Essa função de administrador pode gerenciar, monitorar e solucionar problemas de servidores e serviços.

  - **CsAdministrator:** Essa função de administrador pode executar todas as tarefas de CsVoiceAdministrator, CsServerAdministrator e CsUserAdministrator.

<div>


> [!NOTE]
> Para obter detalhes sobre direitos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planejando o controle de acesso baseado em função no Lync Server 2013</A> na documentação de planejamento.



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

