---
title: 'Lync Server 2013: verificar certificados de servidor do Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b874c83adb2a1ddb511d8c6980cb12f01e0ef68
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>Verificar os certificados do servidor do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Agenda de verificação</p></td>
<td><p>Mensal</p></td>
</tr>
<tr class="even">
<td><p>Ferramenta de teste</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permissões obrigatórias</p></td>
<td><p>Ao executar localmente usando o Shell de gerenciamento do Lync Server, os usuários devem ser membros do grupo de segurança RTCUniversalServerAdmins.</p>
<p>Quando executado usando uma instância remota do Windows PowerShell, os usuários devem receber uma função RBAC que tenha permissão para executar o cmdlet Get-CsCertificate. Para ver uma lista de todas as funções RBAC que podem usar este cmdlet, execute o seguinte comando no prompt do Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrição

O cmdlet Get-CsCertificate permite recuperar informações sobre cada um dos seus certificados do Lync Server. Isso é especialmente importante porque os certificados têm uma data de vencimento interna. Por exemplo, os certificados emitidos de forma privada normalmente expiram após 12 meses. Se qualquer um dos seus certificados do Lync Server expirar, você perderá a funcionalidade de acompanhamento até que esse certificado seja renovado ou substituído.

</div>

<div>

## <a name="running-the-test"></a>Executar o teste

Para retornar informações sobre cada um dos seus certificados do Lync Server, basta executar o seguinte comando:

`Get-CsCertificate`

Ou você pode filtrar as informações do certificado de retorno com base na data de expiração. Por exemplo, esse comando limita os dados retornados aos certificados que expiram (não podem ser usados após) 1 de junho de 2014:

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

Para obter mais informações, consulte a documentação de ajuda para o cmdlet Get-CsCertificate.

Observe que, embora o cmdlet Test-CsCertificateConfiguration exista, ele não é muito útil para os administradores. (Em vez disso, o cmdlet é usado principalmente pelo assistente de certificado.) Embora o cmdlet funcione, as informações que ele retorna são de valor mínimo, conforme mostrado no seguinte exemplo de saída:

Uso de impressão digital

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 padrão

</div>

<div>

## <a name="reviewing-the-output"></a>Revisão da saída

O cmdlet Get-CsCertificate retorna informações semelhantes às seguintes para cada um dos seus certificados do Lync Server:

Emissor: CN = FabrikamCA

Não depois: 12/28/2015 3:35:41 PM

Não antes: 1/2/2014 12:49:37 PM

SerialNumber: 611BB01200000000000C

Subject: CN = LYNC-SE.fabrikam.com

Alternativonames: {sip.fabrikam.com, LYNC-SE.fabrikam.com,

meet.fabrikam.com, admin.fabrikam.com...}

Impressão digital: A9D51A2911C74FABFF7F2A8A994B20857D399107

Usar: padrão

Como regra, os principais problemas que envolvem os certificados do Lync Server envolvem datas e horas, como quando os certificados entram em vigor (não antes) ou quando expiram (não depois). Como essas datas e horários são tão importantes, talvez você queira limitar os dados retornados às informações como o uso do certificado, o número de série do certificado e a data de vencimento do certificado; em seguida, você pode revisar rapidamente todos os certificados e quando eles vão expirar. Para retornar apenas essas informações, use o comando junto com as opções, conforme mostrado:

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

Esse comando retorna dados semelhantes aos seguintes, com os certificados classificados em ordem de data de validade:

Usar SerialNumber não após

\--- ------------ --------

611BB01200000000000C 12/28/2015 3:35:41 PM padrão

WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM

Se você tiver problemas com o certificado, convém revisar os outros osnames configurados para um certificado. À primeira vista, isso parece ser um problema. Por padrão, e dependendo do tamanho da janela do console, o Get-CsCertificate pode não ser capaz de exibir todos os nomes:

Alternativonames: {sip.fabrikam.com, LYNC.fabrikam.com,

meet.fabrikam.com, admin. Fabrika...}

Para ver todos os nomes alternativos atribuídos a um certificado, use um comando semelhante a este:

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

Isso deve mostrar todos os nomes alternativos no certificado:

sip.fabrikam.com

LYNC.fabrikam.com

meet.fabrikam.com

admin.fabrikam.com

LYNC-SE.fabrikam.com

Dialin.fabrikam.com

</div>

<div>

## <a name="see-also"></a>Confira também


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

