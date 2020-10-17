---
title: 'Lync Server 2013: configurar bypass de mídia para sempre ignorar o servidor de mediação'
description: 'Lync Server 2013: Configure o bypass de mídia para sempre ignorar o servidor de mediação.'
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
ms.openlocfilehash: 6b4981c7b12700d2f0bbf0bf05c8a51623bb8ba9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552687"
---
# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a>Configurar o bypass de mídia no Lync Server 2013 para sempre ignorar o servidor de mediação

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-25_

<div>


> [!NOTE]  
> Este tópico assume que você já configurou o desvio de mídia em qualquer conexão de tronco para um par (um gateway PSTN (Rede Telefônica Pública Comutada), um IP-PBX ou SBC (Controlador de Borda da Sessão) no ITSP (Provedor de Serviços de Telefonia da Internet)) de um local ou serviço específico no qual deseja que a mídia ignore o servidor de mediação.<BR>Você não pode configurar a mídia para sempre desviar do Servidor de Mediação, enquanto também ativa o controle de admissão de chamada. Essas configurações são incompatíveis e, portanto, são configurações mutuamente exclusivas na interface de usuário do painel de controle do Lync Server.



</div>

Além de ativar o desvio de mídia para as conexões de tronco individuais associadas a um ponto para o Servidor de Mediação, você também deve definir as configurações globais para o desvio de mídia. Se você usar as etapas deste tópico para definir as configurações globais para bypass de mídia, pressupõe-se que você tem uma boa conectividade entre os pontos de extremidade do Lync e qualquer ponto para o qual você configurou o bypass de mídia na conexão do tronco.

Se você não tem uma boa conectividade entre os pontos de extremidade do Lync Server e todos os pares para o servidor de mediação cujas respectivas conexões de tronco foram habilitadas para bypass de mídia, você deve definir as configurações de bypass de mídia global para usar as informações do site e da região ao empregar o bypass de mídia. Isso permite maior controle ao determinar quando a mídia desvia do servidor de mediação. Para fazer isso, use as etapas em [configurar as configurações globais de bypass de mídia no Lync server 2013 para usar informações de site e região](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) e [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) em vez disso.

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>Para habilitar o desvio de mídia globalmente para que sempre ignore o servidor de mediação

1.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação da esquerda, clique em **Configuração da Rede**.

3.  Clique duas vezes na configuração **Global** na lista.

4.  Na página **Editar Configuração Global**, marque a caixa de seleção **Ativar desvio de mídia**.

5.  Clique em **Sempre desviar**.

6.  Clique em **Comprometer**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar bypass de mídia no Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Opções de bypass de mídia global no Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
[Bypass de mídia e servidor de mediação no Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  


[Planejamento de bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

