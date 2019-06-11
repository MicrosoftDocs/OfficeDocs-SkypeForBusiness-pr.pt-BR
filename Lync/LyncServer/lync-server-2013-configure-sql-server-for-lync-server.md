---
title: 'Lync Server 2013: Configurar o SQL Server para Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0154b468540873f9b8ae6796f30336327809d394
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>Configurar o SQL Server para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-08-12_

Os tópicos desta seção abordam como implantar e configurar o SQL Server para usar em uma implantação empresarial do Lync Server. Os servidores de edição padrão usam uma versão posicionada do SQL Server Express do SQL Server que está certa para as cargas de trabalho de um servidor Standard Edition.

O repositório de gerenciamento central do Lync Server 2013 mantém dados do usuário para todos os servidores da Enterprise Edition dentro de um pool e foi projetado para estar localizado em um servidor back-end baseado no SQL Server. Como um repositório centralizado, o repositório de gerenciamento central não pode ser instalado no mesmo computador que qualquer outra função do Lync Server 2013. O repositório de gerenciamento central não pode residir em um servidor Enterprise Edition no pool. O repositório de gerenciamento central é criado automaticamente quando você publica a topologia pela primeira vez e seleciona a opção para criar os bancos de dados. O computador que você designa como o servidor back-end já deve estar executando o software de banco de dados do SQL Server para que a instalação seja bem-sucedida.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Posicionamento de dados do Servidor SQL e do arquivo de log para Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Configurar SQL Server no Lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Permissões de implantação para Servidor SQL no Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Instalação de banco de dados usando o Shell de Gerenciamento do Lync Server no Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Compreendendo os requisitos de firewall para Servidor SQL com Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Configurar o cluster do SQL Server para o Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

