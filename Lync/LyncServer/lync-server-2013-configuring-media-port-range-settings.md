---
title: 'Lync Server 2013: definindo configurações de intervalo de porta de mídia'
description: 'Lync Server 2013: Configurando as configurações de intervalo de porta de mídia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a7670284c593197068c366f43bbb3faaaad8f63
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570737"
---
# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>Definindo as configurações de intervalo de porta de mídia no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-18_

As configurações de intervalo da porta de mídia podem impactar significantemente o desempenho do cliente e devem ser configuradas. Você pode definir essas configurações usando o Shell de gerenciamento do Lync Server.

### <a name="media-port-range-settings"></a>Configurações do Intervalo da Porta de Mídia

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuração</th>
<th>Descrição</th>
<th>Cmdlet do Shell de gerenciamento do Lync Server</th>
<th>Parâmetros do cmdlet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>Especifica se os intervalos de porta enviados pelo servidor devem ser usados pelo cliente para mídia e sinalização. Usado em conjunto com os subvalores MinMediaPort e MaxMediaPort.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>Especifica o número de porta inicial a usar para a mídia. Combina com o MaxMediaPort para especificar o intervalo de portas. O intervalo mínimo recomendado é de 40 portas.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (representa o número de porta inicial para usar na mídia do cliente)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>Especifica o maior número de porta para usar na mídia. Combina com MinMediaPort para especificar o intervalo de portas. O intervalo mínimo recomendado é de 40 portas.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (indica o número total de portas disponíveis para a mídia do cliente; o padrão é 40)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>Para definir as configurações do intervalo de porta da mídia

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o seguinte cmdlet:
    
        Get-CsConferencingConfiguration
    
    Esse cmdlet retorna as definições da configuração de conferência.

3.  Execute o cmdlet a seguir com os parâmetros e valores que você deseja alterar (para obter detalhes sobre os parâmetros para este cmdlet, consulte a documentação do Shell de gerenciamento do Lync Server):
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > Você pode criar conjuntos adicionais de definições de configuração de conferência para sites específicos. Use o cmdlet <STRONG>New- CsConferencingConfiguration</STRONG> com uma identidade de site. Ao criar novas definições de configuração de conferênciade para os sites, as configurações do site têm precedência sobre as configurações globais. Para obter detalhes, consulte a documentação do Shell de Gerenciamento do Lync Server.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

