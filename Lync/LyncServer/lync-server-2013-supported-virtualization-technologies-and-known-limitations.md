---
title: 'Lync Server 2013: tecnologias de virtualização suportadas e limitações conhecidas'
description: 'Lync Server 2013: tecnologias de virtualização suportadas e limitações conhecidas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 745fa535462d29342f4c0a58674ee6487db42a6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544607"
---
# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Tecnologias de virtualização suportadas e limitações conhecidas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2017-02-06_

O plug-in de VDI do Lync permite chamadas de áudio e vídeo para tecnologias de virtualização suportadas. Isso estende a funcionalidade descrita para o Microsoft Lync Server 2010 no White paper sobre [virtualização do cliente no Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) . Em conformidade com as regulamentações de telefone padrão, o suporte para o E911 também está incluído. As seções a seguir descrevem as tecnologias de virtualização compatíveis com o plug-in VDI do Lync e as limitações de recursos conhecidas.

<div>

## <a name="support-for-virtualization-technologies"></a>Suporte para tecnologias de virtualização

O plug-in de VDI do Lync suporta o Remoting completo de área de trabalho no cenário de área de trabalho virtual pessoal, mas não no cenário de sessão de área de trabalho remota. Esses cenários podem ser descritos da seguinte maneira:

  - **Com suporte: áreas de trabalho virtuais personalizadas ou VDI (Virtual Desktop Infrastructure).**     Neste cenário, cada usuário faz logon em uma área de trabalho virtual personalizável e pode salvar arquivos na área de trabalho que persistem entre as sessões. Os serviços de área de trabalho remota da Microsoft, o modo de exibição de horizonte VMware e o Citrix XenDesktop são implementações que foram testadas para uso com o Lync. Para obter informações sobre ambientes VDI específicos do fornecedor e hardware de cliente que foram testados pela Microsoft, consulte [infraestrutura qualificada para Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).

  - **Sem suporte: sessões da área de trabalho remota.**     Neste cenário, cada usuário faz logon em uma sessão de área de trabalho virtual genérica que não pode ser personalizada. As implementações de exemplo incluem sessões de área de trabalho remota da Microsoft (RDSH) e Citrix XenApp combinados com o receptor Citrix.

O plug-in do Lync VDI não oferece suporte a outras tecnologias de virtualização, como a virtualização de aplicativo, que permite o uso de um aplicativo sem exigir a instalação do aplicativo completo localmente. As implementações de exemplo incluem o Citrix XenApp e o Microsoft Application Virtualization (App-V). Não há suporte para o fluxo de aplicativos, comunicação remota de aplicativos e modos de virtualização mista (por exemplo, aplicativos remotos de área de trabalho remota).

Para permitir a extensibilidade, o plug-in do Lync VDI foi projetado para usar APIs independentes de plataforma chamadas DVCs (canais virtuais dinâmicos). Para cenários que não são explicitamente suportados pelo Lync, consulte instruções de suporte do provedor de soluções VDI.

</div>

<div>

## <a name="known-feature-limitations"></a>Limitações de recursos conhecidos

Veja a seguir as limitações conhecidas quando você usa o Lync 2013 em um ambiente de VDI:

  - Há suporte limitado para recursos de delegação de chamada e de anonimato de agente do grupo de resposta.

  - Não há suporte aos seguintes recursos:
    
      - Páginas de ajuste de dispositivo de áudio integrado e dispositivo de vídeo
    
      - Vídeo de várias exibições.
    
      - Gravação de conversas.
    
      - Serviços de área de trabalho remota (RDS).
    
      - Ingressar em reuniões anonimamente (ou seja, ingressar em reuniões do Lync hospedadas por uma organização que não se federa à sua organização).
    
      - Usando o plug-in do Lync VDI junto com um dispositivo do Lync Phone Edition.
    
      - Continuidade de chamadas em caso de indisponibilidade da rede.
    
      - Toques personalizados e recursos de música em espera.

  - O plug-in do Lync VDI não é suportado em um ambiente do Microsoft 365 ou do Office 365.

</div>

</div>

<span> </span>

</div>

</div>

</div>

