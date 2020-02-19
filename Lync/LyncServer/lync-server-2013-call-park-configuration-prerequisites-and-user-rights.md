---
title: 'Lync Server 2013: pré-requisitos de configuração do estacionamento de chamadas e direitos de usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e39fd811a39a1221ec522c7ca3874d0de4f340b4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Pré-requisitos de configuração do estacionamento de chamadas e direitos de usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-10_

O estacionamento de chamada é um recurso de gerenciamento de chamadas que é instalado por padrão ao implantar o Enterprise Voice. Este tópico descreve o que você precisa ter em vigor antes de poder configurar o estacionamento de chamadas e os direitos de usuário necessários para executar tarefas de configuração.

<div>


> [!IMPORTANT]  
> Não é feito backup dos arquivos de música em espera personalizados para o aplicativo de estacionamento de chamada como parte do processo de recuperação de desastres do Lync Server 2013, e os arquivos serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados. Mantenha sempre uma cópia de backup separada dos arquivos de música em espera personalizados que você carregou para o estacionamento de chamadas.



</div>

Esta seção supõe que você leu a documentação de planejamento relacionada ao estacionamento de chamada (consulte [Planning for Call Management Features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).

<div>

## <a name="call-park-configuration-prerequisites"></a>Pré-requisitos de configuração do estacionamento de chamadas

O estacionamento de chamada requer os seguintes componentes:

  - Serviço de aplicativos

  - Call Park application

Esses componentes são instalados automaticamente quando você implanta o Enterprise Voice.

Se você deseja que os chamadores ouçam música enquanto a chamada estiver estacionada, um arquivo de música em espera também é necessário. Um arquivo de música em espera padrão é instalado automaticamente quando você implanta o Enterprise Voice. É possível substituir o arquivo padrão com seu próprio arquivo de música em espera. O estacionamento de chamada usa o repositório de arquivos para armazenar o arquivo de áudio.

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>Direitos do usuário de configuração do estacionamento de chamadas

Você pode usar as seguintes ferramentas administrativas para configurar o estacionamento de chamada:

  - Painel de Controle do Lync Server

  - Shell de Gerenciamento do Lync Server

Use essas ferramentas para configurar a tabela de órbita de estacionamento de chamadas e para definir outras configurações usadas pelo estacionamento de chamadas.

A configuração do estacionamento de chamadas exige qualquer uma das funções administrativas a seguir, dependendo da tarefa:

  - **CsVoiceAdministrator:** Essa função de administrador pode criar, configurar e gerenciar todas as configurações e políticas relacionadas a voz.

  - **CsUserAdministrator:** Essa função de administrador pode habilitar o estacionamento de chamada na política de voz. Esta função de administração também pode ter acesso de exibição somente leitura para todas as configurações de voz.

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

