---
title: 'Lync Server 2013: Habilitando o servidor do Office Web Apps e o Lync Server 2013'
description: 'Lync Server 2013: Habilitando o servidor do Office Web Apps e o Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1bf4e09dc29bf344b78df50595258f0663cd731
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546517"
---
# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a>Configurando a integração com o servidor do Office Web Apps e o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-08-19_

O Lync Server 2013 emprega o servidor do Office Web Apps para lidar com apresentações do PowerPoint. Para obter informações sobre as vantagens dessa abordagem, consulte [Overview of Web Conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).

Para usar esses novos recursos, os administradores devem instalar o Office Web Apps Server e devem configurar o Lync Server 2013 para se comunicar com o servidor do Office Web Apps. Esta documentação fornece informações sobre como configurar o Lync Server 2013 para funcionar com o servidor do Office Web Apps. O que esta documentação não fornece é informações sobre como instalar o próprio servidor do Office Web Apps; para essas informações, consulte o site de implantação do Microsoft Office Web Apps em <https://go.microsoft.com/fwlink/p/?linkid=257525> . Esse guia inclui informações completas de pré-requisito para o servidor do Office Web Apps; Observe que o servidor do Office Web Apps deve ser instalado em um computador autônomo que não esteja executando o Lync Server, o Microsoft SQL Server ou qualquer outro aplicativo de servidor. (Você não deve ter nenhuma versão do Microsoft Office instalada nesse computador.) Qualquer computador usado para executar o servidor do Office Web Apps também deve ter um conjunto específico de software instalado (incluindo o .NET Framework 4,5 e o Windows PowerShell 3,0); esses requisitos, juntamente com as informações sobre a configuração de certificados e os serviços de informações da Internet (IIS), são discutidos em detalhes no site de implantação do Microsoft Office Web Apps em <https://go.microsoft.com/fwlink/p/?linkid=257525> .

<div>


> [!NOTE]  
> A iteração mais recente do servidor do Office Web Apps é chamada de servidor do Office Online, com suporte no Lync Server 2013. Para obter mais detalhes, consulte a <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">documentação do servidor do Office Online</A>.



</div>

Este documento abrange as seguintes áreas de tópico:

  - [Configurando o Lync Server 2013 para funcionar com o servidor do Office Web Apps](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [Publicar o servidor do Office Web Apps no Lync Server 2013 usando um servidor de proxy reverso](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Validando a configuração do servidor do Office Web Apps no Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Configurando clientes do Lync Server 2013 para uso com o servidor do Office Web Apps](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

