---
title: 'Lync Server 2013: Pré-requisitos de Estacionamento de Chamadas e direitos de usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64a2f322ffec1d2ffa7aa238b76686391fc76ed7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Pré-requisitos de Estacionamento de Chamadas e direitos de usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-10_

O estacionamento de chamadas é um recurso de gerenciamento de chamadas que é instalado por padrão quando você implanta o Enterprise Voice. Este tópico descreve o que você precisa ter em vigor antes de poder configurar o estacionamento de chamadas e os direitos de usuário necessários para executar tarefas de configuração.

<div>


> [!IMPORTANT]  
> Os arquivos personalizados de música em espera para o aplicativo de estacionamento de chamadas não são submetidos a backup como parte do processo de recuperação de desastre do Lync Server 2013, e os arquivos serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados. Mantenha sempre uma cópia de backup separada dos arquivos de música de espera personalizados que você enviar ao Estacionamento de Chamada.



</div>

Esta seção pressupõe que você leu a documentação de planejamento relacionada ao estacionamento de chamadas (consulte [planejando os recursos de gerenciamento de chamadas no Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="call-park-configuration-prerequisites"></a>Pré-requisitos de configuração do parque da chamada

O estacionamento de chamadas requer os seguintes componentes:

  - Serviço de aplicativos

  - Aplicativo de Estacionamento de Chamada

Esses componentes são instalados automaticamente quando você implanta o Enterprise Voice.

Se você quiser que os chamadores ouvissem música enquanto a chamada estiver estacionada, um arquivo de música em espera também será necessário. Um arquivo de música em espera padrão é instalado automaticamente quando você implanta o Enterprise Voice. Você pode substituir o arquivo padrão pelo seu próprio arquivo de música em espera. O parque de chamadas usa o armazenamento de arquivos para armazenar o arquivo de áudio.

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>Direitos de usuário de configuração do estacionamento de chamada

Você pode usar as seguintes ferramentas administrativas para configurar o parque de chamadas:

  - Painel de Controle do Lync Server

  - Shell de Gerenciamento do Lync Server

Use essas ferramentas para configurar a tabela órbita do parque de chamadas e para definir outras configurações usadas pelo parque de chamadas.

A configuração do estacionamento de chamadas requer qualquer uma das seguintes funções administrativas, dependendo da tarefa:

  - **CsVoiceAdministrator:** Essa função de administrador pode criar, configurar e gerenciar todas as configurações e políticas relacionadas a voz.

  - **CsUserAdministrator:** Esta função de administrador pode habilitar o parque de chamadas na política de voz. Essa função de administrador também tem acesso de exibição somente leitura a todas as configurações de voz.

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

