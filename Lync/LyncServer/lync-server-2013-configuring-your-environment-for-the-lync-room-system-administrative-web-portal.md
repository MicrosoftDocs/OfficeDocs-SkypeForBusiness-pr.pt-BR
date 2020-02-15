---
title: 'Lync Server 2013: Configurando seu ambiente para o portal da Web administrativo do sistema de salas do Lync'
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
ms.openlocfilehash: 5c42b5541fb28646e4c01d9d070b67f6fe103234
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a>Configurando seu ambiente do Lync Server 2013 para o portal da Web administrativo do sistema de salas do Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-22_

Para usar o portal da Web administrativo do sistema de salas do Lync (LRS), será necessário instalar ou configurar os pré-requisitos a seguir.

<div>


> [!IMPORTANT]  
> Se o servidor estiver configurado com autenticação Kerberos e NTLM e o LRS estiver em execução em um computador que não ingressou no domínio, a autenticação Kerberos falhará e o usuário não verá o status de LRS no portal administrativo. Para resolver esse problema, configure o servidor com autenticação NTLM ou autenticação NTLM e TLS-DSK (sem Kerberos) ou Ingresse o computador do LRS no domínio.



</div>

1.  Instale as atualizações cumulativas do Lync Server 2013:2013 de julho na topologia do Lync Server.
    
    Para obter a atualização ou ver o que está incluído nele, consulte [atualizações para o Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).

2.  Criar um usuário do Active Directory habilitado para SIP.
    
    O portal da Web administrativo do LRS usa essas credenciais para consultar informações do Lync Server. O nome de usuário recomendado é LRSApp.

3.  Crie um grupo de segurança do Active Directory com o nome LRSSupportAdminGroup.
    
    Crie o grupo com o escopo de grupo como segurança global e tipo de grupo como segurança. Os usuários habilitados para SIP que forem adicionados a esse grupo serão autorizados a ver a lista de salas e executar certos comandos, como coletar logs.

4.  Crie um grupo de segurança do Active Directory com o nome LRSFullAccessAdminGroup.
    
    Criar o grupo com o escopo de grupo como global e o tipo de grupo como Security. SIP habilitados para usuários que são adicionados a este grupo são autorizados a usar toda a funcionalidade do portal de administração.
    
     
    
    ![Lista de grupos de administração com a função de grupo de segurança](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Lista de grupos de administração com a função de grupo de segurança")  
    
     

5.  Adicione LRSFullAccessAdminGroup como membro de LRSSupportAdminGroup.
    
    ![Página Membros de propriedades LRSSupportAdminGroup](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Página Membros de propriedades LRSSupportAdminGroup")  
    
     

6.  Crie um usuário do Active Directory habilitado para SIP com o nome LRSSupport. Adicione este usuário ao LRSSupportAdminGroup.
    
    ![Página Membros de propriedades LRSSupportAdminGroup](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Página Membros de propriedades LRSSupportAdminGroup")  
    
     

7.  Instale o ASP.NET MVC 4 para o Visual Studio 2010 SP1 e o Visual Web Developer 2010 SP1, disponível no centro [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)de download da Microsoft em.

</div>

<span> </span>

</div>

</div>

</div>

