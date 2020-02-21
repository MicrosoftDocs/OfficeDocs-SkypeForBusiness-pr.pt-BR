---
title: 'Lync Server 2013: configurar a política de conferência para discagem'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33f84ec3cb900b4283f30d67e318ab10d3625326
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>Configurar a política de conferência para discagem no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-03-21_

A política de conferência é uma configuração de conta de usuário que especifica a experiência de conferência para os participantes. Você pode criar políticas de conferência com um escopo de site ou um escopo de usuário. As configurações de política de conferência englobam vários aspectos do agendamento da conferência e da participação. Várias configurações de política de conferência oferecem suporte à conferência discada para participantes. Ao configurar a conferência discada, você deve verificar se estes campos foram definidos adequadamente para sua organização e modificá-los conforme necessário.

Verifique os seguintes campos em sua política de conferência:

  - **Permitir que os participantes convidem usuários**   anônimos essa configuração permite que organizadores de reunião convidem participantes anônimos (ou seja, não autenticados) para reuniões. Esta configuração é opcional para conferências discadas. Essa configuração é selecionada por padrão na política de conferência global padrão.

  - **Habilitar conferência**   discada PSTN essa configuração permite que os usuários ingressem na parte de áudio de uma conferência discando da PSTN. Essa configuração é necessária para conferência discada. Essa configuração é selecionada por padrão na política de conferência global padrão.

  - **Permitir que os participantes anônimos façam a discagem**   esta configuração permite que usuários anônimos que já estão associados à reunião disquem para entrar em um número de telefone para ingressar na parte de áudio da conferência. Esta configuração é opcional para conferências discadas. Esta configuração não é selecionada por padrão na política de conferência global padrão.

  - **Permitir que participantes não habilitados para**   o Enterprise Voice para discar esta configuração permite que os participantes da reunião e organizadores não habilitados para o Enterprise Voice façam a discagem para um número de telefone para ingressar na parte de áudio da conferência. A chamada externa é autorizada baseando-se nas políticas de voz atribuída do organizador. Esta configuração não é selecionada por padrão na política de conferência global padrão. O valor padrão da configuração é desativado.
    
    <div>
    

    > [!NOTE]  
    > Para habilitar esse recurso, um organizador da reunião que não esteja habilitado para o Enterprise Voice deverá ter uma política de voz apropriada atribuída a eles para autorizar qualquer discagem de uma conferência organizada por esse usuário. Uma política de voz pode ser atribuída a um usuário que não está habilitado para o Enterprise Voice do Shell de gerenciamento do Lync Server. Se o usuário não tiver uma política de voz explicitamente atribuída a ele, a política de voz do site será usada para autorizar a solicitação de discagem. Se não houver nenhuma política de voz do site, a política de voz global será usada.&nbsp;

    
    </div>

O procedimento nesta seção descreve como modificar uma política de conferência. Para obter detalhes sobre como configurar todas as configurações que definem a experiência de participante na política de conferência padrão, consulte [create or Modify a Collection of Meeting Configuration Settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md). Para obter detalhes sobre como criar uma política de conferência para um usuário ou grupo de usuários específico, consulte [create or Modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md). Para obter uma lista de todas as configurações de política de conferência disponíveis, consulte [referência de configurações de política de conferência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>Para modificar a política de conferência para discagem interna

1.  Conecte-se ao computador como membro do grupo RTCUniversalServerAdmins ou da função **Cs-ServerAdministrator** ou **CsAdministrator**.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Conferências**.

4.  Na guia **Política de Conferência**, dê um duplo clique no nome de uma política de conferência para abrir a caixa de diálogo **Editar Política de Conferência**.

5.  Verifique se os campos para conferência discada estão de acordo com a sua organização e modifique as configurações se necessário.

6.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

