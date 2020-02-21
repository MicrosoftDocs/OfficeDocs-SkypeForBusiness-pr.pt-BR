---
title: Testar e relatar prontidão funcional para autenticação Kerberos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e160af5920f58b3813bd168c7f4fbe2e0f0cf95c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a>Testar e relatar prontidão funcional para autenticação Kerberos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-01-16_

Para concluir com sucesso este procedimento, você deve ter feito logon como usuário membro do grupo RTCUniversalServerAdmins.

Você pode usar o cmdlet **Test-CsKerberosAccountAssignment** do Windows PowerShell para testar e relatar a prontidão funcional de uma atribuição de site para autenticação Kerberos. Esse comando consulta o site especificado no parâmetro Identity necessário. O parâmetro de relatório opcional faz com que o cmdlet grave um relatório HTML em\\C: logs no computador no qual o comando é executado. O parâmetro Verbose opcional mostra as informações de atividade na tela.

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a>Para testar e relatar a prontidão funcional da autenticação Kerberos de um site

1.  Como membro do grupo RTCUniversalServerAdmins, faça logon em um computador no domínio que executa o Lync Server 2013 ou no computador onde as ferramentas administrativas estão instaladas.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

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

