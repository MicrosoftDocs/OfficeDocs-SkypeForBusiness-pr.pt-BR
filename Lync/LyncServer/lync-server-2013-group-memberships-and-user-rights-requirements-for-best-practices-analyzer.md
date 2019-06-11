---
title: Associações de grupo e requisitos de direitos de usuário para o analisador de práticas recomendadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c60f6256cead59b16f443994143d40bdbc00393
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Associações de grupo e requisitos de direitos de usuário para o analisador de práticas recomendadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-21_

Para executar com êxito o analisador de práticas recomendadas, a conta de usuário que você usa para fazer logon deve ser um membro do grupo Administradores no computador local. Além disso, para verificar seu ambiente, a conta de usuário deve ser um membro dos seguintes grupos:

  - **Administradores de domínio**   para enumerar as informações dos serviços de domínio Active Directory e para chamar os provedores de instrumentação de gerenciamento do Windows (WMI) nos controladores de domínio e nos servidores de catálogo global.

  - **Os administradores**   são necessários em cada computador interno do Lync Server 2013 e em cada servidor de borda para chamar os provedores de instrumentação de gerenciamento do Windows (WMI) e acessar o registro.

  - **RTCUniversalReadOnlyAdmins**   direitos administrativos do Lync Server 2013, completos ou delegados, somente leitura.

  - **Modo de exibição do Exchange somente administrador**   completo ou delegado modo de exibição do Exchange somente administrador na organização do Microsoft Exchange.

Se a sua conta de usuário não tiver direitos de usuário suficientes, você terá duas opções:

  - Em um prompt de comando, use o comando **runas** para executar a ferramenta em uma conta que tem direitos de usuário suficientes. A sintaxe é a seguinte:
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - Na página **conectar-se ao Active Directory** , defina as credenciais das contas que você planeja usar para executar o analisador de práticas recomendadas. Clique em **Mostrar opções avançadas de login**. Você pode inserir três contas: uma para conectar-se aos serviços de domínio do Active Directory, uma para conexão com servidores de borda do Lync Server 2013 e outra para conexão com os servidores Exchange. Se você não especificar nenhuma dessas contas, a conta de usuário que você usou para fazer logon e executar o analisador de práticas recomendadas será usada.

</div>

<span> </span>

</div>

</div>

</div>

