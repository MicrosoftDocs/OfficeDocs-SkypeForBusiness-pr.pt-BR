---
title: 'Lync Server 2013: Configurando seu ambiente do Lync Server 2013 para Porta da Web Administrativo do Sistema de Sala do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f0f415cfeca5b798a1e29ac6ebe09105fbf08b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-22_

Para usar o portal da Web administrativo do sistema de salas do Lync (LRS), você precisará instalar ou configurar os pré-requisitos a seguir.

<div>


> [!IMPORTANT]  
> Se o servidor estiver configurado com autenticação Kerberos e NTLM, e o LRS estiver em execução em um computador que não está associado ao domínio, a autenticação Kerberos falhará e o usuário não verá o status de LRS no portal administrativo. Para solucionar esse problema, configure o servidor com autenticação NTLM ou autenticação NTLM e TLS-DSK (sem Kerberos) ou ingresse no computador LRS ao domínio.



</div>

1.  Instale as atualizações cumulativas do Lync Server 2013:2013 de julho na topologia do Lync Server.
    
    Para obter a atualização ou ver o que está incluído nele, confira [atualizações para o Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).

2.  Crie um usuário do Active Directory habilitado para SIP.
    
    O portal da Web administrativo do LRS usa essas credenciais para consultar informações do Lync Server. O nome de usuário recomendado é LRSApp.

3.  Crie um grupo de segurança do Active Directory com o nome LRSSupportAdminGroup.
    
    Crie o grupo com Escopo do Grupo como Global e Tipo de Grupo como Segurança. Os usuários habilitados para SIP que forem adicionados a este grupo serão autorizados a ver a lista de salas e a executar determinados comandos, como coletar logs.

4.  Crie um grupo de segurança do Active Directory com o nome LRSFullAccessAdminGroup.
    
    Crie o grupo com o escopo do grupo como global e o tipo de grupo como Security. o SIP habilitado para usuários que são adicionados a este grupo tem autorização para usar toda a funcionalidade do portal de administração.
    
     
    
    ![Lista de grupos de administradores com função de grupo de segurança](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Lista de grupos de administradores com função de grupo de segurança")  
    
     

5.  Adicione LRSFullAccessAdminGroup como um membro de LRSSupportAdminGroup.
    
    ![Página de membros de propriedades LRSSupportAdminGroup](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Página de membros de propriedades LRSSupportAdminGroup")  
    
     

6.  Crie um usuário do Active Directory compatível com SIP com o nome LRSSupport. Adicione este usuário ao LRSSupportAdminGroup.
    
    ![Página de membros de propriedades LRSSupportAdminGroup](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Página de membros de propriedades LRSSupportAdminGroup")  
    
     

7.  Instale o ASP.NET MVC 4 para Visual Studio 2010 SP1 e o Visual Web Developer 2010 SP1, disponível no centro de [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)download da Microsoft em.

</div>

<span> </span>

</div>

</div>

</div>

