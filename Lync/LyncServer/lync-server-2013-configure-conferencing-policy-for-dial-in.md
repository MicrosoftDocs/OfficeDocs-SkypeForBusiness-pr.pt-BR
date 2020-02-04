---
title: 'Lync Server 2013: Configurar política de conferência para discagem'
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
ms.openlocfilehash: 107c5fcf4b341c652cd4044fe47f4b650cf5adb4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>Configurar política de conferência para discagem no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-03-21_

A política de conferência é uma configuração de conta de usuário que especifica a experiência de conferência para os participantes. Você pode criar políticas de conferência com um escopo de site ou um escopo de usuário. As configurações de política de conferência englobam vários aspectos do agendamento da conferência e da participação. Várias configurações de política de conferência oferecem suporte à conferência discada para participantes. Ao configurar a conferência discada, você deve verificar se estes campos foram definidos adequadamente para sua organização e modificá-los conforme necessário.

Verifique os seguintes campos na sua política de conferência:

  - **Permitir que os participantes convidem usuários**   anônimos essa configuração permite que os organizadores de reunião convidem participantes anônimos (ou seja, não autenticados) para reuniões. Essa configuração é opcional para conferência discada. Essa configuração é selecionada por padrão na política de conferência global padrão.

  - **Habilitar a conferência**   discada PSTN essa configuração permite que os usuários ingressem na parte de áudio de uma conferência discando da PSTN. Essa configuração é necessária para conferência discada. Essa configuração é selecionada por padrão na política de conferência global padrão.

  - **Permitir que participantes anônimos disquem**   essa configuração permite que usuários anônimos que já tenham ingressado na reunião disquem para um número de telefone para ingressar na parte de áudio da conferência. Essa configuração é opcional para conferência discada. Essa configuração não é selecionada por padrão na política de conferência global padrão.

  - **Permitir que os participantes que não estão habilitados para**   o recurso de discagem para chamadas do Enterprise Voice permitam que os participantes da reunião e os organizadores não estejam habilitados para o Enterprise Voice para discar para um número de telefone para ingressar na parte de áudio da conferência. A chamada de discagem está autorizada com base na política de voz atribuída do organizador. Essa configuração não é selecionada por padrão na política de conferência global padrão. A configuração do valor padrão é desabilitada.
    
    <div>
    

    > [!NOTE]  
    > Para habilitar esse recurso, o organizador da reunião que não está habilitado para o Enterprise Voice deve ter uma política de voz apropriada atribuída a ele para autorizar qualquer discagem de uma conferência organizada por esse usuário. Uma política de voz pode ser atribuída a um usuário que não está habilitado para o Enterprise Voice do Shell de gerenciamento do Lync Server. Se o usuário não tiver uma política de voz explicitamente atribuída a ele, a política de voz do site será usada para autorizar a solicitação de discagem. Se não houver uma política de voz do site, a política de voz global será usada.&nbsp;

    
    </div>

O procedimento nesta seção explica como modificar a política de conferência. Para obter detalhes sobre como configurar todas as configurações que definem a experiência do participante na política de conferência padrão, consulte [criar ou modificar uma coleção de definições de configuração de reunião no Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md). Para obter detalhes sobre como criar uma política de conferência para um usuário ou grupo de usuários específico, consulte [criar ou modificar uma política de conferência no Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md). Para obter uma lista de todas as configurações de política de conferência disponíveis, consulte [referência de configurações de política de conferência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>Para modificar a política de conferência para discagem

1.  Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **cs-ServerAdministrator** ou **CsAdministrator** .

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Conferência**.

4.  Na guia **política de conferência** , clique duas vezes em um nome de política de conferência para abrir a caixa de diálogo **Editar política de conferência** .

5.  Verifique se os campos para conferência discada são adequados para sua organização e modifique as configurações, se necessário.

6.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

