---
title: 'Lync Server 2013: Preparando domínios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cd8c09346c8f5b562a72e77b9ba40915b480c91
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a>Preparando domínios para Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-29_

Preparação do domínio é a etapa final na preparação dos serviços de domínio Active Directory para o Lync Server 2013. A etapa de preparação do domínio adiciona entradas de controle de acesso (ACEs) necessárias aos grupos universais que concedem permissões para hospedar e gerenciar usuários no domínio. A preparação do domínio cria ACEs no domínio raiz e três contêiners integrados: Usuário, Computadores e Controladores de Domínio.

Você pode executar a preparação do domínio em qualquer computador do domínio no qual você está implantando o Lync Server. Você deve preparar cada domínio que hospedará o Lync Server ou os usuários.

Se a herança de permissões estiver desabilitada ou as permissões de usuário autenticadas estiverem desabilitadas em sua organização, você deverá executar etapas adicionais durante a preparação do domínio. Para obter detalhes, consulte [preparando um serviço de domínio do Active Directory bloqueado no Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

Se sua organização usa unidades organizacionais (OU) em vez de três recipientes internos (ou seja, usuários, computadores e controladores de domínio), você deve conceder acesso de leitura às UOs do grupo usuários autenticados. O acesso de leitura aos recipientes é necessário para a preparação do domínio. Se o grupo usuários autenticados não tiver acesso de leitura à OU, execute o cmdlet **Grant-CsOuPermission** conforme ilustrado nos exemplos de código a seguir para conceder permissões de leitura para cada UO.

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

Para obter detalhes sobre o cmdlet **Grant-CsOuPermission** , consulte a documentação do Shell de gerenciamento do Lync Server.

<div class="">


> [!TIP]  
> Para obter detalhes sobre os ases criados na raiz do domínio e nos contêineres usuários, computadores e controladores de domínio, consulte <A href="lync-server-2013-changes-made-by-domain-preparation.md">alterações feitas pela preparação do domínio no Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Executando preparação de domínio para Lync Server 2013](lync-server-2013-running-domain-preparation.md)

  - [Usando cmdlets para reverter a preparação do domínio para o Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

