---
title: 'Lync Server 2013: executando e monitorando backups'
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
ms.openlocfilehash: 3181a266e5792d190186e9f09b2cab5852156cbe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Executar e monitorar backups no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-15_

Suas prioridades de negócios devem conduzir a especificação de requisitos de backup e restauração para a sua organização. Executar backups dos servidores e dos dados é a primeira linha de defesa para planejar um desastre.

Os computadores que executam serviços do Lync Server 2013 ou funções de servidor devem ter uma cópia da topologia atual, configurações de configuração atuais e políticas atuais para poderem funcionar na função de sua função. O Lync Server é responsável por verificar se essas informações são passadas para cada computador que precisar.

Os cmdlets **Export-CsConfiguration** e **Import-CsConfiguration** são usados para fazer backup e restaurar a topologia do Lync Server, as configurações e políticas durante uma atualização do repositório de gerenciamento central. Os cmdlets **Export-CsConfiguration** permitem que você exporte dados para um. Arquivo ZIP. Em seguida, você pode usar o cmdlet **Import-CsConfiguration** para lê-lo. ZIP File e restaurar a topologia, as configurações e as políticas para o repositório de gerenciamento central. Depois disso, os serviços de replicação do Lync Server replicarão as informações restauradas para outros computadores que executam serviços do Lync Server.

A capacidade de exportar e importar dados de configuração também é usada durante a configuração inicial de computadores localizados na sua rede de perímetro (por exemplo, servidores de borda). Ao configurar um computador na rede de perímetro, você deve primeiro executar uma replicação manual usando os cmdlets CsConfiguration: você deve exportar os dados de configuração usando **Export-CsConfiguration** e, em seguida, copiar o. Arquivo ZIP para o computador na rede de perímetro. Depois disso, você pode usar **Import-CsConfiguration** e o parâmetro LocalStore para importar os dados. Você só precisa fazer isso uma vez. Depois disso, a duplicação ocorrerá automaticamente.

Quem pode executar este cmdlet: por padrão, os membros dos grupos a seguir estão autorizados a executar o cmdlet **Export-CsConfiguration** localmente: RTCUniversalServerAdmins. Para retornar uma lista de todas as funções RBAC, esse cmdlet é atribuído (incluindo qualquer função RBAC personalizada que você tenha criado), execute o seguinte comando no prompt do Windows PowerShell:

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

Todos os bancos de dados back-end do SQL 2012 devem ser reproduzidos de acordo com [as práticas recomendadas do SQL](http://go.microsoft.com/fwlink/p/?linkid=290716).

O teste regular do plano de recuperação de desastres para sua infraestrutura do Lync Server 2013 deve ser executado em um ambiente de laboratório que imita o ambiente de produção o mais próximo possível. Consulte as tarefas mensais para obter mais informações sobre testes de recuperação de desastres.

Observe que a frequência de backup pode ser ajustada, com base nos objetivos do ponto de restauração e ponto de recuperação. Como prática recomendada, faça instantâneos periódicos periódicos ao longo do dia. Geralmente, você deve executar backups completos a cada 24 horas.

<div>

## <a name="see-also"></a>Confira também


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[Práticas recomendadas do SQL](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

