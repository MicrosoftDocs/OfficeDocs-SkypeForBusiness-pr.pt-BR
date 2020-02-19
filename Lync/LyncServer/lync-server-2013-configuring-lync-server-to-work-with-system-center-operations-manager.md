---
title: Configurando o Lync Server para trabalhar com o System Center Operations Manager
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: accadd3f12c9f07ec5dfa295a037ce50a72f11ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>Configurando o Lync Server 2013 para trabalhar com o System Center Operations Manager

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

Para configurar sua infraestrutura do Microsoft Lync Server 2013 para trabalhar com o System Center Operations Manager, você deve fazer três coisas:

  - Identifique e configure seu servidor de gerenciamento do System Center Operations Manager principal. A configuração do servidor de gerenciamento inclui a instalação do System Center Operations Manager 2012 ou do System Center Operations Manager 2007 R2, bem como a configuração de um banco de dados back-end usando o SQL Server. A versão real do SQL Server que você precisa usar depende da versão do System Center Operations Manager que você está usando. Para obter detalhes, consulte [Configuring the Primary Management Server in Lync server 2013](lync-server-2013-configuring-the-primary-management-server.md).

  - Identifique e configure os computadores do Lync Server que você deseja monitorar. Para monitorar um computador do Lync Server usando o System Center Operations Manager, você deve instalar os arquivos de agente do System Center Operations Manager e configurar cada servidor para atuar como um proxy.

  - Identifique e configure os computadores que você deseja que atue como nós do *Inspetor*do Lync Server. Os nós do Inspetor são computadores que executam periodicamente as transações sintéticas do Lync Server, que são cmdlets do Windows PowerShell que verificam se os principais componentes do Lync Server, como a capacidade de fazer logon no sistema ou a capacidade de trocar mensagens instantâneas são funcionando conforme o esperado.

Os tópicos nesta seção contêm instruções para executar cada uma dessas tarefas.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurando o servidor de gerenciamento primário no Lync Server 2013](lync-server-2013-configuring-the-primary-management-server.md)

  - [Instalando os pacotes de gerenciamento do Lync Server 2013](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Configurando os computadores do Lync Server que serão monitorados no Lync Server 2013](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Instalando e configurando nós do Inspetor no Lync Server 2013](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

