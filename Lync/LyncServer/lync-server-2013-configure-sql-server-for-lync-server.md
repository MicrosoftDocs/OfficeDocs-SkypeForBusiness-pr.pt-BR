---
title: 'Lync Server 2013: configurar o SQL Server para o Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c35f1d82913c71523412c791d9b6a945f443e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535128"
---
# <a name="configure-sql-server-for-lync-server-2013"></a>Configurar o SQL Server para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-08-12_

Os tópicos desta seção discutem como implantar e configurar o SQL Server para usar em uma implantação corporativa do Lync Server. Os servidores Standard Edition usam uma versão do SQL Server Express posicionada do SQL Server, que é o tamanho certo para as cargas de trabalho de um servidor Standard Edition.

O repositório de gerenciamento central do Lync Server 2013 contém dados de usuário para todos os servidores Enterprise Edition dentro de um pool e foi projetado para estar localizado em um servidor back-end baseado em SQL Server. Como um repositório centralizado, o repositório de gerenciamento central não pode ser instalado no mesmo computador que qualquer outra função do Lync Server 2013. O repositório de gerenciamento central não pode residir em um servidor Enterprise Edition no pool. O repositório de gerenciamento central é criado automaticamente quando você publica a topologia pela primeira vez e seleciona criar os bancos de dados. O computador que você designou como servidor de back-end já deve estar executando o software de banco de dados do SQL Server para que a instalação seja bem-sucedida.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Posicionamento de arquivos de log e dados do SQL Server para o Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Configurar o SQL Server no Lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Permissões de implantação para o SQL Server no Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Instalação de banco de dados usando o Shell de gerenciamento do Lync Server no Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Noções básicas sobre requisitos de firewall para o SQL Server com o Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Configurar o cluster do SQL Server para o Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

