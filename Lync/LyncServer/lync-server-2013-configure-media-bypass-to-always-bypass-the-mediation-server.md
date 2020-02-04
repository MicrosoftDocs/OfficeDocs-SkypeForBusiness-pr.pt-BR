---
title: 'Lync Server 2013: configurar o bypass de mídia para sempre ignorar o servidor de mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0023fba32b24243dc4bf2a12659700ace6dea91a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Configure media bypass in Lync Server 2013 to always bypass the Mediation Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-25_

<div>


> [!NOTE]  
> Este tópico pressupõe que você já configurou o bypass de mídia para qualquer conexão de tronco a um par (um gateway PSTN (rede telefônica pública comutada), um PBX IP ou um controle de borda de sessão (SBC) em um provedor de serviços de telefonia pela Internet (ITSP)) para um determinado site ou serviço para o qual você deseja que a mídia ignore o servidor de mediação.<BR>Você não pode configurar mídia para sempre ignorar o servidor de mediação enquanto também habilita o controle de admissão de chamadas. Essas configurações são incompatíveis e, portanto, são configurações mutuamente excludentes na interface do usuário do painel de controle do Lync Server.



</div>

Além de habilitar a bypass de mídia para conexões de tronco individuais associadas a um par para o servidor de mediação, você também deve definir configurações globais para bypass de mídia. Se você usar as etapas deste tópico para definir configurações globais para bypass de mídia, pressupõe-se que você tenha uma boa conectividade entre pontos de extremidade do Lync e qualquer ponto para o qual você configurou a mídia ignorada na conexão do tronco.

Se você não tiver uma boa conectividade entre os pontos de extremidade do Lync Server e todos os pares do servidor de mediação cujas respectivas conexões de tronco tenham sido habilitadas para o bypass de mídia, você deve configurar as definições de bypass de mídia global para usar as informações de site e região quando empregando o bypass de mídia. Isso permite que você tenha mais controle ao determinar quando a mídia ignora o servidor de mediação. Para fazer isso, use as etapas em [Configurar o bypass de mídia para configurações globais no Lync server 2013 para usar as informações de site e região](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) e [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) em vez disso.

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Para habilitar o desvio de mídia globalmente para que sempre ignore o servidor de mediação

1.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação esquerda, clique em **Configuração de rede**.

3.  Clique duas vezes na configuração **Global** na lista.

4.  Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar desvio de mídia**.

5.  Clique em **Sempre desviar**.

6.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar bypass de mídia no Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Opções de bypass de mídia global no Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
[Bypass de mídia e Servidor de Mediação no Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  


[Planejamento de bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

