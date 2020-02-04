---
title: 'Lync Server 2013: Configurando o armazenamento para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a380ce6c863c54739e74488bfa3b3979664e78
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a>Configurando o armazenamento para arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-12-17_

O arquivamento de armazenamento do Lync Server 2013 inclui o seguinte:

  - ****   É necessário armazenamento de dados de armazenamento de dados para armazenar o conteúdo de mensagens instantâneas.

  - ****   O armazenamento de arquivos de armazenamento de arquivos é necessário para armazenar o armazenamento de dados de conteúdo de conferência (reunião) e armazenamento de arquivos.

<div>

## <a name="setting-up-data-storage"></a>Configurando o armazenamento de dados

Os requisitos para a configuração do armazenamento de dados para o arquivamento no Lync Server 2013 dependem de como você deseja armazenar dados de arquivamento:

  - Integre o arquivamento do Lync Server 2013 com a implantação do Exchange para armazenar o arquivamento de dados usando o armazenamento do Exchange.

  - Configurar servidores de banco de dados SQL Server separados para armazenar dados de arquivamento.

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a>Configurando o armazenamento do Exchange para arquivar dados

A configuração do Exchange para armazenamento de dados de arquivamento requer que sua implantação do Exchange esteja executando o Exchange 2013. Além disso, as caixas de correio do usuário devem ser hospedadas no servidor Exchange 2013 e suas caixas de correio devem ser colocadas no bloqueio in-loco. Para obter detalhes sobre como configurar o Exchange 2013, consulte a documentação do produto Exchange.

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a>Configurando servidores de banco de dados SQL Server para armazenamento de dados de arquivamento

O arquivamento no Lync Server 2013 exige que o software de banco de dados do SQL Server armazene os dados arquivados, a menos que você integre a implantação com o Exchange.

Para bancos de dados de arquivamento do SQL Server, você deve instalar o SQL Server no computador que irá hospedar o banco de dados de arquivamento. Você pode usar a mesma instância SQL que você usa para o banco de dados back-end de um pool de front-ends. Para obter o melhor desempenho, você deve implantar o banco de dados de arquivamento em um computador separado do repositório de gerenciamento central. Para obter detalhes sobre a colocação de componentes do Lync Server 2013, consulte [colocação do servidor com suporte no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.

Cada servidor de banco de dados deve estar executando uma versão com suporte do SQL Server. Para obter detalhes sobre as versões com suporte, consulte [requisitos técnicos para arquivamento no Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) na documentação de planejamento.

Você deve configurar as plataformas do SQL Server antes de implantar e habilitar o arquivamento. Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia. Você também pode criar o banco de dados posteriormente, incluindo como parte do procedimento de instalação. Para obter detalhes sobre o SQL Server, consulte o TechCenter do [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)SQL Server em.

<div>


> [!NOTE]  
> Verifique se o tipo de inicialização do serviço do SQL Server Agent é automático e se o serviço do SQL Server Agent está em execução para a instância do SQL que está segurando o banco de dados de arquivamento, para que o trabalho de manutenção padrão do SQL Server possa ser executado em sua base de dados agendada controle do serviço do SQL Server Agent.



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a>Configurar o armazenamento de arquivos

O arquivamento usa o compartilhamento de arquivos do Lync Server 2013 especificado quando você configura seu pool de front-end ou o servidor Standard Edition. Não é possível alterar o compartilhamento de arquivos usado para arquivamento. Para obter detalhes sobre sistemas de armazenamento de arquivos com suporte, consulte [suporte de armazenamento de arquivos no Lync Server 2013](lync-server-2013-file-storage-support.md) na documentação de suporte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

