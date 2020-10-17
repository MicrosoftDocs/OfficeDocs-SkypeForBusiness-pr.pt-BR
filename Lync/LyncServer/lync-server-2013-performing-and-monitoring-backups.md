---
title: 'Lync Server 2013: executando e monitorando backups'
description: 'Lync Server 2013: executando e monitorando backups.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb8ce99e850f0918974be08eb10796ef1397225
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557227"
---
# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Executando e monitorando backups no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-15_

Suas prioridades de negócios devem conduzir a especificação de requisitos de backup e restauração para sua organização. Executar backups dos servidores e dados é a primeira linha de defesa no planejamento de um desastre.

Computadores que executam serviços do Lync Server 2013 ou funções de servidor devem ter uma cópia da topologia atual, definições de configuração atuais e políticas atuais para que possam funcionar em sua função de indicado. O Lync Server é responsável por verificar se essas informações são passadas para cada computador que precisa delas.

Os cmdlets **Export-CsConfiguration** e **Import-CsConfiguration** são usados para fazer backup e restaurar sua topologia do Lync Server, definições de configuração e políticas durante uma atualização do repositório de gerenciamento central. Os cmdlets **Export-CsConfiguration** permitem exportar dados para um. Arquivo ZIP. Você pode usar o cmdlet **Import-CsConfiguration** para lê-lo. ZIP arquivo e restaurar a topologia, as definições de configuração e as políticas para o repositório de gerenciamento central. Depois, os serviços de replicação do Lync Server replicarão as informações restauradas para outros computadores que estejam executando os serviços do Lync Server.

A capacidade de exportar e importar dados de configuração também é usada durante a configuração inicial de computadores localizados em sua rede de perímetro (por exemplo, servidores de borda). Ao configurar um computador na rede de perímetro, você deve primeiro executar uma replicação manual usando os cmdlets do CsConfiguration: você deve exportar os dados de configuração usando o **Export-CsConfiguration** e, em seguida, copiar o. ZIP no computador da rede de perímetro. Depois disso, use **Import-CsConfiguration** e o parâmetro LocalStore para importar os dados. Você só precisa fazer isso uma vez. Após isso, a replicação ocorrerá automaticamente.

Quem pode executar este cmdlet: Por padrão, membros dos seguintes grupos estão autorizados a executar o cmdlet **Export-CsConfiguration** localmente: RTCUniversalServerAdmins. Para retornar uma lista de todas as funções RBAC, esse cmdlet é atribuído (incluindo qualquer função RBAC personalizada que você criou sozinho), execute o seguinte comando no prompt do Windows PowerShell:

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

Todos os bancos de dados back-end do SQL 2012 devem ser copiados de acordo com as [práticas recomendadas do SQL](https://go.microsoft.com/fwlink/p/?linkid=290716).

Testes regulares do plano de recuperação de desastres para sua infraestrutura do Lync Server 2013 devem ser executados em um ambiente de laboratório que imita o ambiente de produção o mais próximo possível. Consulte as tarefas mensais para obter mais informações sobre testes de recuperação de desastres.

Observe que a frequência de backup pode ser ajustada, com base nos seus objetivos de ponto e ponto de recuperação. Como prática recomendada, faça instantâneos regulares e periódicos durante o dia. Geralmente, você deve executar backups completos a cada 24 horas.

<div>

## <a name="see-also"></a>Confira também


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[Práticas recomendadas do SQL](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

