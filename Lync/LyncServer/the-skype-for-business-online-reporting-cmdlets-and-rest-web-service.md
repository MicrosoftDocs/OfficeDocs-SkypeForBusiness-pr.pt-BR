---
title: Os cmdlets de relatório do Skype for Business Online e o serviço Web REST
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a140ed48ac662daea14d602f0830b2fbc4bf1c05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>Os cmdlets de relatório do Skype for Business Online e o serviço Web REST

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-09-05_

Juntamente com os recursos de relatório, o Skype for Business Online fornece acesso a cinco cmdlets do Windows PowerShell que ajudam a gerar esses relatórios e também podem ser usados por administradores para retornar dados de relatório personalizados. O Skype for Business online também inclui o restante (transferência de estado representational), que pode ser usado por desenvolvedores para recuperar informações de relatório personalizadas.

Os cmdlets de relatório disponíveis para os administradores incluem:

  - Get-CsActiveUserReport, que fornece informações sobre o número de usuários ativos (ou seja, usuários que se conectaram ao Skype for Business Online e que participaram de pelo menos uma conferência ou sessão de comunicação ponto a ponto).

  - Get-CsAVConferenceTimeReport, que fornece informações sobre a quantidade de tempo (em minutos) que os usuários passaram em conferências de áudio/vídeo.

  - Get-CsConferenceReport, que fornece informações sobre o número e o tipo de conferências em que os usuários participaram.

  - Get-CsP2PAVTimeReport, que fornece informações sobre a quantidade de tempo (em minutos) que os usuários gastaram em sessões ponto a ponto que incluíam áudio e/ou vídeo.

  - Get-CsP2PSessionReport, que fornece informações sobre o número e o tipo de sessões ponto a ponto nas quais os usuários participaram.

A maioria dos administradores usará os relatórios disponíveis no centro de administração do Office 365: não apenas esses relatórios são gerados automaticamente, mas também fornecem uma representação gráfica dos dados que geralmente são mais fáceis de interpretar do que os valores numéricos brutos retornados pela cmdlets de relatório. No entanto, os administradores familiarizados com o Windows PowerShell podem usar os cmdlets de relatório para retornar os dados que não estão disponíveis nos relatórios do Lync Online. Por exemplo, os cmdlets de relatório retornam informações sobre a duração da sessão (a quantidade de tempo, em minutos, que cada sessão durar). As durações de sessão individual não estão disponíveis usando os relatórios do Lync Online. Da mesma forma, no modo de exibição diário, os relatórios do Lync Online exibem informações somente pelos 14 dias precedentes. Se quiser revisar os totais diários para um dia diferente (por exemplo, uma data de quatro meses atrás), você pode fazer isso usando cmdlets de relatório.

Os administradores também podem estar interessados no artigo [usando o Excel para recuperar os dados de relatório do office 365](http://msdn.microsoft.com/en-us/library/dn781442.aspx), que explica como usar o recurso de consulta de dados OData no Microsoft Excel para criar um relatório personalizado do Office 365. Relatórios personalizados dão a capacidade de ditar quais dados (e quantos dados) são retornados do serviço de relatório do Office 365. Os relatórios personalizados também permitem que você faça coisas como especificar como os dados devem ser classificados e agrupados e fornecer acesso a informações que não são exibidas no centro de administração do Office 365.

Os administradores com um plano de fundo de desenvolvimento podem usar o serviço Web REST para obter informações não exibidas no centro de administração do Skype for Business online. O serviço REST é semelhante ao serviço SOAP, pois cada tecnologia fornece uma maneira de transferir dados XML entre um cliente e um servidor. No entanto, o serviço REST tem pelo menos duas vantagens sobre o serviço SOAP. Para um, REST executa transferências de dados XML usando um formato padronizado conhecido como o formato de distribuição do ATOM. Por outro lado, use o SOAP usando um formato não padrão ao transferir dados. Além disso, REST é capaz de transferir dados entre redes que bloqueiam verbos HTTP diferentes de GET e POST.

<div>

## <a name="see-also"></a>Confira também


[Relatórios do Lync Online](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))  


[O serviço Web de relatório do Office 365](http://msdn.microsoft.com/en-us/library/office/jj984325.aspx)  
[Aprendendo sobre o serviço Web de relatório do Office 365](http://msdn.microsoft.com/en-us/library/office/jj984321.aspx)  
[Cmdlets de relatório do Exchange Online](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)  
[Usar o Excel para recuperar dados de relatório do Office 365](http://msdn.microsoft.com/en-us/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

