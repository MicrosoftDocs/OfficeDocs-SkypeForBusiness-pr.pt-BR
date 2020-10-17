---
title: Associações de grupo e requisitos de direitos do usuário para o analisador de práticas recomendadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1a72a7fdc73aeda96a2875ac48fd51b6023ddba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506068"
---
# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Associações de grupo e requisitos de direitos do usuário para o analisador de práticas recomendadas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-21_

Para executar com êxito o Analisador de Práticas Recomendadas, a conta de usuário utilizada para fazer login deve ser membro do grupo Administradores no computador local. Além disso, para verificar o seu ambiente, a conta de usuário deve ser membro dos seguintes grupos:

  - **Administradores**     de domínio Para enumerar as informações dos serviços de domínio do Active Directory e chamar os provedores de instrumentação de gerenciamento do Windows (WMI) nos controladores de domínio e servidores de catálogo global.

  - **Os administradores**     Obrigatório em cada computador interno do Lync Server 2013 e em cada servidor de borda para chamar os provedores de instrumentação de gerenciamento do Windows (WMI) e acessar o registro.

  - **RTCUniversalReadOnlyAdmins**     Direitos administrativos de somente leitura do Lync Server 2013, completo ou delegado.

  - Administrador somente para **exibição do Exchange**     Administrador somente para exibição do Exchange completo ou delegado na organização do Microsoft Exchange.

Se a sua conta de usuário não tem os direitos de usuário suficientes, você tem duas opções:

  - No prompt de comandos, use o comando **runas** para executar a ferramenta na conta com direitos de usuários suficientes. A sintaxe é a seguinte:
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - Na página **Conectar-se ao Active Directory**, defina as credenciais das contas que planeja usar para executar o Analisador de Práticas Recomendadas. Clique em **Mostrar opções de login avançadas**. Você pode inserir três contas: uma para conectar-se aos serviços de domínio do Active Directory, uma para conexão com os servidores de borda do Lync Server 2013 e outra para conexão com os servidores do Exchange. Se você não especificar nenhuma destas contas, a conta do usuário utilizada para fazer login e executar o Analisador de Práticas Recomendadas é usada.

</div>

<span> </span>

</div>

</div>

</div>

