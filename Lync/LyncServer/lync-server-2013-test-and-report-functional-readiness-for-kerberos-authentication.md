---
title: Testar e relatar prontidão funcional para autenticação Kerberos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30dda07eb0152f43f60627fcee3a75b14745eea2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a>Testar e relatar prontidão funcional para autenticação Kerberos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-01-16_

Para concluir esse procedimento com êxito, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins.

Você pode usar o cmdlet **Test-CsKerberosAccountAssignment** do Windows PowerShell para testar e relatar a prontidão funcional de uma atribuição de site para a autenticação Kerberos. Esse comando consulta o site especificado no parâmetro Identity necessário. O parâmetro de relatório opcional faz com que o cmdlet escreva um relatório HTML para\\C: registra o computador no qual o comando é executado. O parâmetro detalhado opcional relata as informações de atividade para a tela.

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a>Para testar e relatar a prontidão funcional para a autenticação Kerberos de um site

1.  Como membro do grupo RTCUniversalServerAdmins, faça logon em um computador no domínio que está executando o Lync Server 2013 ou no computador onde as ferramentas administrativas estão instaladas.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Na linha de comando, execute o seguinte comando:
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    Por exemplo:
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

