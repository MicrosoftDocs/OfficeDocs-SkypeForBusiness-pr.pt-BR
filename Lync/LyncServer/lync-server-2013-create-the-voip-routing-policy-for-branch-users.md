---
title: 'Lync Server 2013: criar a política de roteamento VoIP para usuários de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c55f52c104c4a9e49abb8b4989cfa4901dfe02dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>Criar a política de roteamento VoIP para usuários de filial no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-23_

É recomendável criar uma política VoIP separada para os usuários de locais de filial. Essa política deve conter rotas para saída do gateway de aparelho de filial persistente ou gateway externo de servidor de filial persistente e rotas de backup para saída de um gateway no site central. Independentemente de onde o usuário está registrado, seja no registrador de aplicativos de filial persistente ou servidor de filial persistente ou no cluster de registradores de backup no site central, a política de VoIP do usuário está sempre em vigor.

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>Para configurar a política de roteamento do VoIP para usuários de filiais

1.  Criar um plano de discagem de nível de usuário e atribuí-lo aos usuários da filial. (Consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md) na documentação de operações.)

2.  Atribua regras de normalização que correspondam aos hábitos de discagem dos usuários nesse site. Se o aparelho de filial persistente ou o usuário do servidor de filial persistente passar o pool de registradores de backup no site central, o mesmo plano de discagem estará em vigor. (Consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md) na documentação de operações.)

3.  Configure uma rota de voz que se egresso do gateway de aparelho de filial persistente ou do gateway externo do servidor de filial persistente. (Consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md) na documentação de operações.)

4.  Defina uma rota de chamada de backup no aparelho de filial persistente ou gateway de servidor de filial persistente para apontar para o pool de registrador de backup (colocado com o servidor de mediação) no site central. (Consulte seu aparelho de filial persistente ou documentação do fornecedor do servidor de filial persistente.)
    
    <div>
    

    > [!NOTE]  
    > Essa configuração de rota de chamada de backup ajuda a garantir que as chamadas de entrada para o usuário da filial funcionem quando o aparelho de filial persistente ou servidor de filial persistente não estiver disponível (por exemplo, se estiver desativado para manutenção). Se o servidor de registrador e mediação no aparelho de filial persistente ou servidor de filial persistente não estiverem disponíveis e o usuário estiver registrado com o pool de registradores de backup no site central, as chamadas de entrada ainda poderão ser encaminhadas para o usuário.

    
    </div>

**Próxima etapa**: [definir configurações de reencaminhamento de caixa postal no Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

