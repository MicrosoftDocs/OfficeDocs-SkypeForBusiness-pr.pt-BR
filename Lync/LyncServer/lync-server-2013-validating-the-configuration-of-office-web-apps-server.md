---
title: 'Lync Server 2013: Validando a configuração do servidor do Office Web Apps'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34c774411fd825dd01595ef1e51ffa9c65c6eb8f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Validando a configuração do servidor do Office Web Apps no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-04-22_

Depois que o servidor do Office Web Apps tiver sido adicionado à topologia e depois que essa topologia tiver sido publicada, você verá dois eventos de log de eventos novos no log de eventos do Lync Server. Primeiro, um evento MCU de dados de LS (ID de evento 41034) deve ser adicionado; Este evento relatará que o servidor do Office Web Apps foi descoberto:

**Servidor de conferência da Web o servidor do Office Web Apps é descoberto, o conteúdo do PowerPoint está habilitado.**

Além disso, você deve ver outro evento LS Data MCU (ID 41032) que relata as URLs do Office Web Apps Server. Por exemplo, você deve ver algo semelhante a isso:

**Descoberta bem-sucedida do servidor do Office Web Apps do servidor de Webconferência.**

**Página do apresentador interno do servidor do Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Página de participantes internos do servidor do Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Página do apresentador externo do servidor do Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Página de participantes internos do servidor do Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Se você ver um evento LS Data MCU com o ID 41033, significa que a descoberta do Office Web Apps Server falhou. Nesse caso, o Microsoft Lync Server 2013 tentará quantas vezes forem necessárias para descobrir o servidor do Office Web Apps recém configurado. Se o processo de descoberta falhar repetidamente, você deve remover o Office Web Apps Server do seu documento de topologia, publicar a topologia atualizada e tentar adicionar o Office Web Apps Server novamente à topologia depois que os problemas de conectividade tiverem sido resolvidos.

Se o servidor do Office Web Apps parece estar configurado corretamente e foi reconhecido pelo processo de descoberta, é possível verificar se o servidor do Office Web Apps está funcionando conforme o esperado, compartilhando uma apresentação do PowerPoint entre um par de clientes do Microsoft Lync 2013. Se o Usuário A puder carregar e exibir a apresentação do PowerPoint e se o Usuário B puder participar da reunião e ver a apresentação, então o Office Web Apps Server está funcionando.

Mesmo que o Office Web Apps Server pareça estar configurado corretamente, é possível receber a mensagem de erro “Alguns recursos de compartilhamento não estão disponíveis devido a problemas de conectividade do servidor” ao tentar compartilhar uma apresentação do PowerPoint. Se você receber essa mensagem de erro, você deve reiniciar o servidor (ou servidores) de Front End associados ao novo Office Web Apps Server.

</div>

<span> </span>

</div>

</div>

</div>

