---
title: 'Lync Server 2013: instalar o portal da Web administrativo do sistema de salas do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24757a87279f64dd903ed4fdfb26169b606f899c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Instalando o portal da Web administrativo do sistema de salas do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-04-09_

Você pode baixar o portal da Web administrativo do sistema de salas do Microsoft Lync no centro [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044)de download da Microsoft em.

Para instalar o portal da Web administrativo do sistema de salas do Lync, use as etapas a seguir.

1.  Configure a porta de aplicativo confiável executando o seguinte cmdlet no Shell de gerenciamento do Lync Server:
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  Para instalar o portal de sala de reunião, baixe o **LyncRoomAdminPortal. exe** e execute-o como administrador.

3.  Abra o arquivo Web. config no seguinte local:
    
    % Arquivos de programa\\% Microsoft Lync Server\\2013 manipulador\\de sala de\\reunião\\de Web Components int do portal\\

4.  No arquivo Web. config, altere o PortalUserName para o nome de usuário criado na etapa 2 na seção "Configurando pré-requisitos para o portal de administração do sistema de salas do Lync" (o nome recomendado na etapa é LRSApp):
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  Como o portal de administração do LRS é um aplicativo confiável, você não precisa fornecer a senha na configuração do Portal. Se este usuário estiver usando um registrador diferente do registrador local, você precisará especificar o registrador para ele adicionando a seguinte linha no arquivo Web. config:
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  Se a porta usada for diferente de 5061, adicione a seguinte linha no arquivo Web. config:
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>Verificando a instalação do portal da Web administrativo do sistema de salas do Lync

Para verificar a instalação do portal da Web administrativo do sistema de salas do Lync, faça o seguinte:


1.  Em um servidor front-end, navegue até a seguinte URL:
    
    https://\<FE-servidor\>/lRS
    
    Você não verá nenhum erro, conforme mostrado na imagem a seguir:
    
    ![Tela de entrada do portal de administração do sistema de salas do Lync](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Tela de entrada do portal de administração do sistema de salas do Lync")

2.  Se você não vir nenhum erro, tente acessar a seguinte URL de qualquer outro computador na topologia:
    
    https://\<FE-servidor\>/lRS
    
    Para acessar a página, você precisará adicionar os registros DNS, conforme descrito em "registros de DNS necessários para entrada automática de cliente" em [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056).

</div>

</div>

<span> </span>

</div>

</div>

</div>

