---
title: 'Lync Server 2013: Protegendo o IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 711adaec00e37cbd826f8aabcadc45948548c3f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a>Protegendo o IIS no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-12-05_

No Microsoft Office Communications Server 2007 e no Microsoft Office Communications Server 2007 R2, os serviços de informações da Internet (IIS) são executados em uma conta de usuário padrão. Isso teve o potencial de causar problemas: se essa senha tiver expirado, você poderá perder seus serviços Web, um problema que muitas vezes era difícil de diagnosticar. Para ajudar a evitar o problema de senhas expiradas, o Microsoft Lync Server 2013 permite que você crie uma conta de computador (para um computador que não existe realmente) que possa servir como a entidade de autenticação para todos os computadores em um site que executa o IIS. Como essas contas utilizam o protocolo de autenticação Kerberos, elas são referidas como contas Kerberos e o novo processo de autenticação é conhecido como autenticação Kerberos de Web. Isso permite gerenciar todos os servidores IIS usando uma única conta.

Para executar seus servidores nesse objeto de autenticação, primeiro você deve criar uma conta de computador usando o cmdlet New-CsKerberosAccount; Esta conta é atribuída a um ou mais sites. Após a atribuição ter sido feita, a associação entre a conta e o site do Lync Server 2013 será habilitada executando o cmdlet Enable-CsTopology. Entre outras coisas, isso cria o SPN (nome da entidade de serviço) obrigatório nos serviços de domínio Active Directory (AD DS). Os SPNs proporcionam aos aplicativos cliente uma maneira de localizar um determinado serviço. Para obter detalhes, consulte [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) na documentação de operações.

<div>

## <a name="best-practices"></a>Práticas recomendadas

Para ajudar a aumentar a segurança do IIS, recomendamos que você implemente uma conta Kerberos para o IIS. Se você não implementar uma conta Kerberos, o IIS será executado em uma conta de usuário padrão.

</div>

</div>

<span> </span>

</div>

</div>

</div>

