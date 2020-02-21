---
title: Configurar os clientes para migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63ad4dfd4b69966a6d206ab19330d7088aff434
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a>Configurar os clientes para migração

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-21_

Este tópico contém as etapas de implantação de cliente recomendadas que você deve tomar antes de migrar para o Lync Server 2013. Essas alterações de configuração devem ser feitas no Office Communications Server 2007 R2. É muito importante que essas etapas sejam executadas antes da migração. Para obter detalhes, consulte [Planning for clients and Devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).

<div>

## <a name="to-configure-clients-prior-to-migration"></a>Para configurar clientes antes da migração

1.  Implantar as atualizações mais recentes do servidor do Office Communications Server 2007 R2, cliente e dispositivo (hotfixes):
    
      - [Aplicar atualizações do Office Communications Server 2007 R2](apply-office-communications-server-2007-r2-updates.md)
    
      - [Descrição do pacote de atualização cumulativa para o Communicator 2007 R2](https://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [Obtendo atualizações de software para dispositivos](https://go.microsoft.com/fwlink/?linkid=335809)

2.  No Office Communications Server 2007 R2, use filtragem de versão de cliente para permitir que somente os clientes do Office Communications Server 2007 R2 com as atualizações mais recentes instaladas entrem.

3.  No Office Communications Server 2007 R2, use filtragem de versão de cliente para bloquear clientes do Lync Server 2013 de entrar. Siga as etapas descritas em **Configurando a filtragem de versão do cliente** em [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) para adicionar os filtros de versão listados na tabela a seguir. Para cada filtro de versão, atribua a ação **Bloquear**.
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Client</th>
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

