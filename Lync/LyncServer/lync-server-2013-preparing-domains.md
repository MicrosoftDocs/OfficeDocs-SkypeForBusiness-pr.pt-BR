---
title: 'Lync Server 2013: preparando domínios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 173b1293fb4bf0353b4e6d9038d05c1480697d17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a>Preparando domínios para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-29_

A preparação do domínio é a etapa final da preparação dos serviços de domínio do Active Directory para o Lync Server 2013. A etapa de preparação do domínio adiciona ACEs (entradas de controle de acesso) a grupos universais que concedem permissões para hospedar e gerenciar usuários dentro do domínio. A preparação de domínio cria ACEs na raiz do domínio e três contêineres internos: Usuários, Computadores e Controladores de Domínio.

Você pode executar a preparação do domínio em qualquer computador no domínio em que você está implantando o Lync Server. Você deve preparar todos os domínios que serão hospedados no Lync Server ou usuários.

Se a herança de permissões estiver desabilitada ou se as permissões de usuário autenticado estiverem desabilitadas em sua organização, você deverá executar etapas adicionais durante a preparação do domínio. Para obter detalhes, consulte [preparação de serviços de domínio do Active Directory bloqueados no Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

Se sua organização usa unidades organizacionais (OU) em vez de três contêineres internos (ou seja, usuários, computadores e controladores de domínio), você deve conceder acesso de leitura às UOs para o grupo de usuários autenticados. O acesso de leitura aos contêineres é necessário para a preparação do domínio. Se o grupo usuários autenticados não tiver acesso de leitura à OU, execute o cmdlet **Grant-CsOuPermission** conforme ilustrado nos exemplos de código a seguir para conceder permissões de leitura para cada ou.

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

Para obter detalhes sobre o cmdlet **Grant-CsOuPermission** , consulte a documentação do Shell de gerenciamento do Lync Server.

<div class="">


> [!TIP]  
> Para obter detalhes sobre as ACEs criadas na raiz do domínio e nos contêineres usuários, computadores e controladores de domínio, confira <A href="lync-server-2013-changes-made-by-domain-preparation.md">as alterações feitas pela preparação do domínio no Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Executando a preparação do domínio para o Lync Server 2013](lync-server-2013-running-domain-preparation.md)

  - [Usando cmdlets para reverter a preparação do domínio para o Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

