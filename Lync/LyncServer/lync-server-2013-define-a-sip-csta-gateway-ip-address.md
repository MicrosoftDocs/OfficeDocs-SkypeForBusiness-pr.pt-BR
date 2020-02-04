---
title: 'Lync Server 2013: Definir um endereço SIP de gateway SIP/CSTA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c50958f2c7c44045e25ff4ac9619f3ad73a5f302
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>Definir um endereço SIP de gateway SIP/CSTA no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Se o Lync Server se conectar ao gateway SIP/CSTA implantado para controle de chamada remota usando uma conexão TCP (Transmission Control Protocol), você deve definir o endereço IP do gateway no construtor de topologias. Esta etapa não é necessária para gateways que dão suporte a conexões de Transport Layer Security (TLS). Para qualquer gateway que ofereça suporte a conexões TLS, você pode ignorar esse procedimento e continuar a implantação do controle de chamada remota seguindo as etapas em [habilitar usuários do Lync para controle de chamada remota no Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>Para definir o endereço IP do gateway SIP/CSTA usando o construtor de topologias

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

3.  Escolha a opção para baixar uma topologia existente.

4.  Expanda o nó **servidores de aplicativos confiáveis** .

5.  Clique com o botão direito do mouse no pool de aplicativos confiável que você criou, conforme descrito em [Configurar uma entrada de aplicativo confiável para o controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)e, em seguida, clique em **Editar propriedades**.

6.  Desmarque a caixa de seleção **habilitar a replicação de dados de configuração para este pool** .

7.  Clique em **limitar o uso do serviço a endereços IP selecionados**. A configuração padrão é **usar todos os endereços IP configurados**.

8.  Na caixa de texto **endereço IP primário** , digite o endereço IP do gateway de SIP/CSTA.

9.  Para atualizar a topologia no repositório de gerenciamento central, na árvore de console, clique em **Lync Server**e, em seguida, no painel **ações** , clique em **publicar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar uma rota estática para controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Configurar uma entrada de aplicativo confiável para controle de chamada remota no Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

