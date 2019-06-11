---
title: 'Lync Server 2013: Tecnologias de virtualização suportadas e limitações conhecidas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b5c99151be45f70d1d95fa0a89835ebb6f7d352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Tecnologias de virtualização suportadas e limitações conhecidas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2017-02-06_

O plug-in VDI do Lync permite chamadas de áudio e vídeo para tecnologias de virtualização compatíveis. Isso estende a funcionalidade descrita para o Microsoft Lync Server 2010 no White Paper [virtualização do cliente no Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) . Em conformidade com os regulamentos de telefonia padrão, o suporte para o E911 também está incluído. As seções a seguir descrevem as tecnologias de virtualização que são compatíveis com o plug-in VDI do Lync e as limitações de recursos conhecidos.

<div>

## <a name="support-for-virtualization-technologies"></a>Suporte para Tecnologias de Virtualização

O plug-in VDI do Lync é compatível com o Remoting da área de trabalho virtual no cenário de área de trabalho virtual pessoal, mas não no cenário da sessão da área de trabalho remota. Esses cenários podem ser descritos como segue:

  - **Com suporte: desktops virtuais ou VDI (Virtual Desktop Infrastructure) personalizados.**    Nesse cenário, cada usuário faz logon em uma área de trabalho virtual personalizável e pode salvar arquivos na área de trabalho que persistem em sessões. Os serviços de área de trabalho remota da Microsoft, o modo de exibição horizonte do VMware e o Citrix XenDesktop são implementações que foram testadas para uso com o Lync. Para obter informações sobre ambientes VDI específicos do fornecedor e hardware cliente que foram testados pela Microsoft, consulte [infraestrutura qualificada para Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).

  - **Sem suporte: sessões da área de trabalho remota.**    Nesse cenário, cada usuário se conecta a uma sessão genérica da área de trabalho virtual que não pode ser personalizada. Exemplos de implantações incluem Sessões de Área de Trabalho Remota da Microsoft (RDSH) e Citrix XenApp juntamente com o Citrix Receiver.

O plug-in VDI do Lync não oferece suporte a outras tecnologias de virtualização, como a virtualização de aplicativos, que permite o uso de um aplicativo sem a necessidade de instalação do aplicativo completo localmente. Exemplos de implementações incluem o Citrix XenApp e a Microsoft Application Virtualization (App-V). Aplicação de streaming, comunicação remota de aplicativos e modelos de virtualização mistos (por exemplo, comunicação remota de aplicativos em toda a área de trabalho remota) não são suportados.

Para permitir a extensibilidade, o plug-in VDI do Lync foi projetado para usar APIs independentes de plataforma chamadas DVCs (canais virtuais dinâmicos). Para cenários que não são explicitamente suportados pelo Lync, consulte declarações de suporte do provedor de soluções VDI.

</div>

<div>

## <a name="known-feature-limitations"></a>Limitações conhecidas dos recursos

Veja a seguir as limitações conhecidas quando você usa o Lync 2013 em um ambiente VDI:

  - Há suporte limitado para recursos de delegação de chamada e de anonimato do agente do grupo de resposta.

  - Não há suporte aos seguintes recursos:
    
      - Páginas de ajuste de dispositivo de áudio integrado e dispositivo de vídeo
    
      - Vídeo com modo de exibição múltipla.
    
      - Gravação de conversas.
    
      - Serviços de área de trabalho remota (RDS).
    
      - Ingressar em reuniões anonimamente (isto é, ingressando em reuniões do Lync hospedadas por uma organização que não se federa à sua organização).
    
      - Usar o plug-in VDI do Lync juntamente com um dispositivo Lync Phone Edition.
    
      - Continuidade de chamadas em caso de indisponibilidade da rede.
    
      - Toques personalizados e recursos de música em espera.

  - O plug-in VDI do Lync não é compatível com um ambiente do Office 365.

</div>

</div>

<span> </span>

</div>

</div>

</div>

