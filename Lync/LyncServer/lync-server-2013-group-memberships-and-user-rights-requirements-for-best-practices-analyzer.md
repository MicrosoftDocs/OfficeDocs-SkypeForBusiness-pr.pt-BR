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
ms.openlocfilehash: 2245cbbe32e8751948f32dc83dae7ca58f92091f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Associações de grupo e requisitos de direitos do usuário para o analisador de práticas recomendadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-21_

Para executar com êxito o Analisador de Práticas Recomendadas, a conta de usuário utilizada para fazer login deve ser membro do grupo Administradores no computador local. Além disso, para verificar o seu ambiente, a conta de usuário deve ser membro dos seguintes grupos:

  - **Administradores de domínio**   para enumerar informações de serviços de domínio do Active Directory e chamar os provedores de instrumentação de gerenciamento do Windows (WMI) em controladores de domínio e servidores de catálogo global.

  - **Administradores**   necessários em cada computador interno do Lync Server 2013 e cada servidor de borda para chamar os provedores de instrumentação de gerenciamento do Windows (WMI) e para acessar o registro.

  - **RTCUniversalReadOnlyAdmins**   direitos administrativos de somente leitura do Lync Server 2013, completo ou delegado.

  - **Somente modo de exibição do Exchange administrador**   completo ou delegado somente para exibição do Exchange na organização do Microsoft Exchange.

Se a sua conta de usuário não tem os direitos de usuário suficientes, você tem duas opções:

  - No prompt de comandos, use o comando **runas** para executar a ferramenta na conta com direitos de usuários suficientes. A sintaxe é a seguinte:
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - Na página **Conectar-se ao Active Directory**, defina as credenciais das contas que planeja usar para executar o Analisador de Práticas Recomendadas. Clique em **Mostrar opções de login avançadas**. Você pode inserir três contas: uma para conectar-se aos serviços de domínio do Active Directory, uma para conexão com os servidores de borda do Lync Server 2013 e outra para conexão com os servidores do Exchange. Se você não especificar nenhuma destas contas, a conta do usuário utilizada para fazer login e executar o Analisador de Práticas Recomendadas é usada.

</div>

<span> </span>

</div>

</div>

</div>

