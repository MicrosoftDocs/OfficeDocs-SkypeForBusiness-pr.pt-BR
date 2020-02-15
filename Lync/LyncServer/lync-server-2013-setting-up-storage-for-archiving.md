---
title: 'Lync Server 2013: configurar armazenamento para arquivamento'
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
ms.openlocfilehash: 5a3633ee21fc26fe21557731ece31cf5a0bbb171
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a>Configurando o armazenamento para arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-12-17_

O armazenamento de arquivamento do Lync Server 2013 inclui o seguinte:

  - ****   O armazenamento de dados de armazenamento de dados é necessário para armazenar o conteúdo de im.

  - ****   O armazenamento de arquivos de armazenamento de arquivos é necessário para armazenar a conferência (reunião) armazenamento de dados de conteúdo e armazenamento de arquivos.

<div>

## <a name="setting-up-data-storage"></a>Configurando o armazenamento de dados

Os requisitos para a configuração do armazenamento de dados para arquivamento no Lync Server 2013 dependem de como você deseja armazenar dados de arquivamento:

  - Integre o arquivamento do Lync Server 2013 com sua implantação do Exchange para armazenar dados de arquivamento usando o armazenamento do Exchange.

  - Configurar servidores de banco de dados do SQL Server separados para armazenar dados de arquivamento.

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a>Configurando o repositório do Exchange para arquivamento de dados

A configuração do Exchange para armazenamento de dados de arquivamento exige que sua implantação do Exchange esteja executando o Exchange 2013. Além disso, as caixas de correio do usuário devem estar hospedadas no servidor Exchange 2013 e suas caixas de correio devem ser colocadas no bloqueio in-loco. Para obter detalhes sobre como configurar o Exchange 2013, consulte a documentação do produto Exchange.

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a>Configurando o repositório dos Servidores de banco de dados do SQL Server para arquivamento de dados

O arquivamento no Lync Server 2013 requer o software de banco de dados do SQL Server para armazenar os dados arquivados, a menos que você integre sua implantação com o Exchange.

Para bancos de dados de arquivamento do SQL Server, você deve instalar o SQL Server no computador que hospedará o banco de dados de arquivamento. É possível usar a mesma instância do SQL utilizada para o banco de dados de back-end de um pool de Front Ends. Para obter um melhor desempenho, você deve implantar o banco de dados de arquivamento em um computador separado do armazenamento de Gerenciamento Central. Para obter detalhes sobre a colocação de componentes do Lync Server 2013, consulte [suporte à colocação de servidor suportado no Lync server 2013](lync-server-2013-supported-server-collocation.md) na documentação de suporte.

Cada servidor de banco de dados deve estar executando uma versão com suporte do SQL Server. Para obter detalhes sobre as versões com suporte, consulte [Technical Requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) na documentação de planejamento.

Você deve configurar as plataformas do SQL Server antes de implantar e habilitar o arquivamento. Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia. Também é possível criar o banco de dados posteriormente, incluindo-o como parte do procedimento de instalação. Para obter detalhes sobre o SQL Server, consulte o TechCenter do [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)SQL Server em.

<div>


> [!NOTE]  
> Certifique-se de que o tipo de inicialização do serviço SQL Server Agent seja automático e que o serviço SQL Server Agent esteja em execução para a instância SQL que está segurando o banco de dados de arquivamento, para que o trabalho de manutenção padrão de arquivamento do SQL Server possa ser executado na base agendada sob o controle do serviço do SQL Server Agent.



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a>Configurando o armazenamento de arquivos

O arquivamento usa o compartilhamento de arquivo do Lync Server 2013 que você especificou ao configurar seu pool de front-ends ou servidor Standard Edition. Não é possível alterar o compartilhamento de arquivos usado para o Arquivamento. Para obter detalhes sobre os sistemas de armazenamento de arquivos com suporte, consulte [File Storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) na documentação de suporte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

