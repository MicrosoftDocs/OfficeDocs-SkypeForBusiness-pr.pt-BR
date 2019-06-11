---
title: 'Lync Server 2013: Validando a configuração do servidor do Office Web Apps'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35844ae2ae73937d6840e480dc57393b91d13eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Validando a configuração do servidor do Office Web Apps no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-04-22_

Após a publicação do Office Web Apps Server na topologia e após a publicação da topologia, você verá dois novos eventos do log de eventos no log de eventos do Lync Server. Primeiro, um evento LS Data MCU (ID 41034) deve ser adicionado; esse evento relatará que o Servidor do Office Web Apps foi descoberto:

**O Servidor do Office Web Apps do servidor de webconferência foi descoberto, o conteúdo do PowerPoint está habilitado.**

Além disso, você deve ver outro evento LS Data MCU (ID 41032) que relata as URLs do Office Web Apps Server. Por exemplo, você deve ver algo semelhante a isso:

**Descoberta bem-sucedida do Servidor do Office Web Apps dp Servidor de Conferência da Web.**

**Página do apresentador interno do servidor do Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Página de participantes do servidor do Office Web Apps Server Internal:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Página do apresentador externo do Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Página de participantes do servidor do Office Web Apps Server Internal:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Se você vir um evento de MCU de dados LS com a ID do evento 41033, isso significa que o descobrimento do servidor do Office Web Apps falhou. Nesse caso, o Microsoft Lync Server 2013 experimentará quantas vezes forem necessárias para descobrir o servidor Office Web Apps recém configurado. Se o processo de descoberta falhar repetidamente, remova o servidor do Office Web Apps do documento de topologia, publique a topologia atualizada e tente adicionar o servidor do Office Web Apps novamente à topologia após a resolução dos problemas de conectividade.

Se o Office Web Apps Server parece estar configurado corretamente e foi reconhecido pelo processo de descoberta, você pode verificar se o servidor do Office Web Apps está funcionando como esperado compartilhando uma apresentação do PowerPoint entre um par de clientes do Microsoft Lync 2013. Se o usuário A conseguir carregar e exibir a apresentação do PowerPoint e se o usuário B puder entrar na reunião e ver essa apresentação, o Office Web Apps Server está funcionando.

Mesmo que o Office Web Apps Server pareça estar configurado corretamente, você pode possivelmente receber a mensagem de erro "alguns recursos de compartilhamento estão indisponíveis devido a problemas de conectividade do servidor" quando você tenta compartilhar uma apresentação do PowerPoint. Se você receber a mensagem de erro, reinicie o servidor front-end (ou servidores) associado ao novo servidor do Office Web Apps.

</div>

<span> </span>

</div>

</div>

</div>

