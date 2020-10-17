---
title: 'Lync Server 2013: protegendo o IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aae84d208df1d7c2945fee641b243bf7110902c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513188"
---
# <a name="protecting-iis-in-lync-server-2013"></a>Protegendo o IIS no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-12-05_

No Microsoft Office Communications Server 2007 e no Microsoft Office Communications Server 2007 R2, o IIS (serviços de informações da Internet) é executado sob uma conta de usuário padrão. Isso poderia causar problemas: se a senha tiver expirado, você poderia perder os Serviços Web, um problema que geralmente era difícil de diagnosticar. Para ajudar a evitar o problema de expirar senhas, o Microsoft Lync Server 2013 permite que você crie uma conta de computador (para um computador que não existe realmente) que possa servir como a entidade de autenticação para todos os computadores em um site que executa o IIS. Como essas contas utilizam o protocolo de autenticação Kerberos, elas são referidas como contas Kerberos e o novo processo de autenticação é conhecido como autenticação Kerberos de Web. Isso permite que você gerencie todos seus servidores IIS usando uma única conta.

Para executar os servidores sob essa entidade de autenticação, primeiro você deve criar uma conta de computador usando o cmdlet New-CsKerberosAccount; essa conta é então atribuída a um ou mais sites. Após a atribuição ter sido feita, a associação entre a conta e o site do Lync Server 2013 é habilitada executando o cmdlet Enable-CsTopology. Entre outras coisas, isso cria o SPN (nome da entidade de serviço) no AD DS (Serviços de Domínio Active Directory). Os SPNs fornecem uma maneira para os aplicativos cliente localizarem um determinado serviço. Para obter detalhes, consulte [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) na documentação de Operações.

<div>

## <a name="best-practices"></a>Práticas recomendadas

Para ajudar a aumentar a segurança do IIS, recomendamos que você implemente uma conta Kerberos para o IIS. Se você não implementar uma conta Kerberos, o IIS será executado sob uma conta de usuário padrão.

</div>

</div>

<span> </span>

</div>

</div>

</div>

