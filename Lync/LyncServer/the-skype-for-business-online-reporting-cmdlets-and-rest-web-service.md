---
title: Os cmdlets de relatório do Skype for Business Online e o serviço Web REST
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63cbce4dda006bb45606a09eef29d8c47946ad2a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>Os cmdlets de relatório do Skype for Business Online e o serviço Web REST

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-09-05_

Em conjunto com os recursos de relatórios, o Skype for Business Online fornece acesso a cinco cmdlets do Windows PowerShell que ajudam a gerar esses relatórios e também podem ser usados por administradores para retornar dados de relatórios personalizados. O Skype for Business online também inclui o REST (transferência de estado representational), que pode ser usado por desenvolvedores para recuperar informações de relatórios personalizados.

Os cmdlets de relatórios disponíveis para os administradores incluem:

  - Get-CsActiveUserReport, que fornece informações sobre o número de usuários ativos (ou seja, usuários que fizeram logon no Skype for Business Online e que participaram de pelo menos uma conferência ou sessão de comunicação ponto a ponto).

  - Get-CsAVConferenceTimeReport, que fornece informações sobre a quantidade de tempo (em minutos) que os usuários gastaram em conferências de áudio/vídeo.

  - Get-CsConferenceReport, que fornece informações sobre o número e o tipo de conferências em que os usuários participaram.

  - Get-CsP2PAVTimeReport, que fornece informações sobre a quantidade de tempo (em minutos) que os usuários gastam em sessões ponto a ponto que incluíam áudio e/ou vídeo.

  - Get-CsP2PSessionReport, que fornece informações sobre o número e o tipo de sessões ponto a ponto nas quais os usuários participaram.

A maioria dos administradores usará os relatórios disponíveis no centro de administração do Microsoft 365: não apenas esses relatórios são gerados automaticamente, mas também fornecem uma representação gráfica dos dados que costumam ser mais fáceis de interpretar do que os valores de números brutos retornados pelo cmdlets de relatório. No entanto, os administradores familiarizados com o Windows PowerShell podem usar os cmdlets de relatório para retornar dados que não estão prontamente disponíveis nos relatórios do Lync Online. Por exemplo, os cmdlets de relatório retornam informações sobre a duração da sessão (a quantidade de tempo, em minutos, que cada sessão lasted). As durações de sessão individual não estão disponíveis usando os relatórios do Lync Online. Da mesma forma, em modo de exibição diário, os relatórios do Lync Online exibem informações somente nos 14 dias precedentes. Se quiser rever os totais diários de um dia diferente (por exemplo, uma data de quatro meses atrás), você pode fazer isso usando os cmdlets de relatório.

Os administradores também podem estar interessados no artigo [usando o Excel para recuperar dados de relatórios do office 365](https://msdn.microsoft.com/library/dn781442.aspx), que explica como usar o recurso de consulta de dados OData no Microsoft Excel para criar um relatório personalizado do Office 365. Relatórios personalizados oferecem a capacidade de ditar quais dados (e quantos dados) são retornados do serviço de relatórios do Office 365. Relatórios personalizados também permitem que você faça coisas como especificar como os dados devem ser classificados e agrupados e fornecer acesso a informações que não são exibidas no centro de administração.

Os administradores com um plano de fundo de desenvolvimento podem usar o serviço Web REST para obter informações não exibidas no centro de administração do Skype for Business online. O serviço REST é semelhante ao serviço SOAP, pois cada tecnologia oferece uma maneira de transferir dados XML entre um cliente e um servidor. No entanto, o serviço REST tem pelo menos duas vantagens sobre o serviço SOAP. Para um, REST realiza transferências de dados XML usando um formato padronizado conhecido como o formato de agregação ATOM. Por outro lado, SOAP usando um formato não padrão ao transferir dados. Além disso, o REST pode transferir dados entre redes que bloqueiam verbos HTTP diferentes de GET e POST.

<div>

## <a name="see-also"></a>Confira também


[Relatórios do Lync Online](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))  


[O serviço Web de relatórios do Office 365](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[Aprendendo sobre o serviço Web de relatórios do Office 365](https://msdn.microsoft.com/library/office/jj984321.aspx)  
[Os cmdlets de relatório do Exchange Online](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)  
[Usar o Excel para Recuperar Dados de Relatório do Office 365](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

