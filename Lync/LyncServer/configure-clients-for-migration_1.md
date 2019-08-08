---
title: Configurar clientes para migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710a5cf6cb23b91431b340c44ebe6ff2738b0822
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a>Configurar clientes para migração

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-21_

Este tópico contém as etapas de implantação de cliente recomendadas que você deve tomar antes de migrar para o Lync Server 2013. Essas alterações de configuração devem ser feitas no Office Communications Server 2007 R2. É muito importante executar essas etapas antes de migrar. Para obter detalhes, consulte [planejando para clientes e dispositivos no Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

<div>

## <a name="to-configure-clients-prior-to-migration"></a>Para configurar clientes antes da migração

1.  Implantar as atualizações mais recentes do Office Communications Server 2007 R2 Server, do cliente e do dispositivo (hotfixes):
    
      - [Aplicar atualizações do Office Communications Server 2007 R2](apply-office-communications-server-2007-r2-updates.md)
    
      - [Descrição do pacote de atualizações cumulativas do Communicator 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Obtendo atualizações de software para dispositivos](http://go.microsoft.com/fwlink/?linkid=335809)

2.  No Office Communications Server 2007 R2, use a filtragem de versão do cliente para permitir somente clientes do Office Communications Server 2007 R2 com as atualizações mais recentes instaladas para entrar.

3.  No Office Communications Server 2007 R2, use a filtragem de versão do cliente para impedir que os clientes do Lync Server 2013 entrem em entrar. Siga as etapas descritas em Configurando a [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) filtragem de versão do **cliente** em para adicionar os filtros de versão listados na tabela a seguir. Para cada filtro de versão, atribua o **bloco**de ação.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Cliente</th>
    <th>Cabeçalho do agente do usuário</th>
    <th>Versão</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15.*.*. *</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5.*.*. *</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4.*.*. *</p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

