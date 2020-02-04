---
title: 'Lync Server 2013: Criar a política de roteamento VoIP para usuários de filiais'
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
ms.openlocfilehash: d1cc8f0a6c4d960b4dacf6f62f283d806a6dd6f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>Criar a política de roteamento VoIP para usuários de filiais no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-23_

Recomendamos a criação de uma política de voz sobre IP (VoIP) separada para os usuários em sites de filiais. Essa política deve conter rotas para egresso do gateway de Appliance da ramificação sobreviventes ou do gateway externo do servidor de ramificação sobreviventes e rotas de backup para egresso de um gateway no site central. Independentemente de onde o usuário estiver registrado, seja no registrador do aplicativo de ramificação sobreviventes ou no servidor de ramificação sobreviventes ou no cluster de registrador de backup no site central, a política de VoIP do usuário estará sempre em vigor.

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>Para configurar a política de roteamento de VoIP para usuários de filiais

1.  Crie um plano de discagem de nível de usuário e atribua-o a usuários da ramificação. (Consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md) na documentação de operações.)

2.  Atribua regras de normalização correspondentes aos hábitos de discagem dos usuários nesse site. Se o aplicativo de ramificação sobreviventes ou o usuário do servidor de ramificação sobreviventes passar no pool de registrador de backup no site central, o mesmo plano de discagem estará em vigor. (Consulte [criar um plano de discagem no Lync Server 2013](lync-server-2013-create-a-dial-plan.md) na documentação de operações.)

3.  Configure uma rota de voz que egresso do gateway de equipamento de ramificação sobreviventes ou do gateway externo do servidor de ramificação sobreviventes. (Consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md) na documentação de operações.)

4.  Defina uma rota de chamada de backup no aparelho de ramificação sobreviventes ou gateway de servidor de ramificação sobreviventes para apontar para o pool de registrador de backup (posicionado com o servidor de mediação) no site central. (Consulte o seu aparelho de ramificação sobreviventes ou a documentação do fornecedor do servidor de ramificação sobreviventes.)
    
    <div>
    

    > [!NOTE]  
    > Esta configuração de rota de chamada de backup ajuda a garantir que as chamadas de entrada para o usuário da ramificação funcionarão quando o aplicativo Ramificable ou o servidor de ramificação sobreviventes não estiver disponível (por exemplo, se estiver inoperante para manutenção). Se o servidor de registrador e mediação na ramificação da ramificação sobreviventes ou no servidor de ramificação sobreviventes não estiver disponível, e o usuário estiver registrado no pool de registradores de backup no site central, as chamadas recebidas ainda poderão ser encaminhadas para o usuário.

    
    </div>

**Próxima etapa**: [Configurar o recurso configurações de redirecionamento de caixa postal no Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

