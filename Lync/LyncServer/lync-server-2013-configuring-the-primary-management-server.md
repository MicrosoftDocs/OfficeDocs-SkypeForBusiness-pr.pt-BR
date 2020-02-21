---
title: 'Lync Server 2013: Configurando o servidor de gerenciamento principal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the primary management server
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48183986
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18ec967418effe53399070bc8e6f414cd2d927cd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-primary-management-server-in-lync-server-2013"></a>Configurando o servidor de gerenciamento primário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-03-19_

Para aproveitar ao máximo os novos recursos de monitoramento de integridade incluídos no Microsoft Lync Server 2013 os administradores devem primeiro designar um computador para atuar como servidor de gerenciamento principal; nesse computador, você deve instalar o System Center Operations Manager 2007 R2 ou o System Center Operations Manager 2012. Além disso, você deve instalar uma versão com suporte do SQL Server para funcionar como o banco de dados back-end do Operations Manager. Se você estiver usando o System Center Operations Manager 2012, poderá usar qualquer uma das seguintes versões do SQL Server como banco de dados back-end:

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

Se você estiver usando o System Center Operations Manager 2007 R2, é recomendável instalar o SQL Server 2005 Service Pack 4 ou o SQL Server 2008 Service Pack 3. Você também pode usar o SQL Server 2008 R2 como banco de dados de backend para o System Center Operations Manager 2007 R2. Consulte o apêndice 1 desta documentação para saber mais sobre como configurar o SQL Server 2008 R2 para trabalhar com o System Center Operations Manager 2007 R2.

Ao instalar o System Center Operations Manager 2012 ou o System Center Operations Manager 2007 R2, você precisa instalar todos os componentes desse produto, incluindo:

  - Banco de dados operacional

  - Servidor

  - Console

  - \s-1 \plain Windows PowerShellcmdlets

  - Console da Web

  - Reporting

  - Data warehouse

Esses componentes e respectivas instalações não serão debatidas em detalhes neste documento. Para obter detalhes sobre o System Center Operations Manager 2007 R2, consulte a documentação do Operations Manager 2007 R2 em <https://go.microsoft.com/fwlink/p/?linkid=257526> e a documentação do <https://go.microsoft.com/fwlink/p/?linkid=257527>System Center Operations Manager 2012 em. Siga estas instruções se você for usar o SQL Server 2005 ou o SQL Server 2008 Service Pack 1 como banco de dados back-end.

Se você estiver usando o System Center Operations Manager 2012, poderá usar o SQL Server 2012 como banco de dados de back-end. Para obter detalhes sobre o SQL Server 2012, consulte manuais online para o SQL [https://go.microsoft.com/fwlink/p/?LinkId=257528](https://go.microsoft.com/fwlink/p/?linkid=257528)Server 2012 em.

Tenha em mente que você só pode ter um único servidor de gerenciamento principal por implantação do Lync Server. Além disso, embora você possa usar o System Center Operations Manager 2012 ou o System Center Operations Manager 2007 R2, não é possível executar os dois aplicativos simultaneamente, você deve escolher um ou outro. Por exemplo, se você estiver executando o System Center Operations Manager 2012, todos os agentes do System Center também devem estar executando o System Center Operations Manager 2012. Você não pode ter alguns agentes executando o System Center Operations Manager 2012 e outros agentes executando o System Center Operations Manager 2007 R2.

</div>

<span> </span>

</div>

</div>

</div>

