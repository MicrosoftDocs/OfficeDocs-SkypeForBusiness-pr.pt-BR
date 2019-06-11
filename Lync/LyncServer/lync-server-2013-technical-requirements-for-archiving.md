---
title: 'Lync Server 2013: requisitos técnicos para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4847815f10a48b954d3d83348d95cc137f4b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Requisitos técnicos para arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-09_

Os requisitos técnicos do Lync Server 2013 incluem o seguinte:

  - Requisitos de infraestrutura.

  - Software obrigatório que deve ser instalado para arquivamento.

  - Requisitos de armazenamento de dados para arquivamento.

  - Redimensionamento de requisitos e considerações para a implantação de arquivamento.

  - Requisitos de desempenho e considerações para seus bancos de dados de arquivamento.

<div>


> [!NOTE]  
> As informações de dimensionamento e desempenho não estão disponíveis neste lançamento do Lync Server 2013.



</div>

<div>

## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura

Os requisitos da infraestrutura de arquivamento do Lync Server 2013 são os mesmos para a implantação do Lync Server 2013. Para obter detalhes, consulte determinando os [requisitos de infraestrutura do Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) na documentação de planejamento.

</div>

<div>

## <a name="archiving-prerequisites"></a>Pré-requisitos de arquivamento

O Lync Server 2013 simplifica os pré-requisitos de arquivamento devido ao seguinte:

  - O servidor de arquivamento não é mais uma função de servidor. Em vez disso, os agentes de coleta de dados unificados são executados nos servidores de front-end em um pool e servidores Standard Edition para capturar dados para arquivamento, para que você não configure plataformas de sistema separadas para arquivamento.

  - O arquivamento usa o armazenamento de arquivos do Lync Server 2013 para armazenamento temporário de arquivos de conteúdo da reunião, para que você não configure um armazenamento de arquivos separado para o arquivamento.

  - No Lync Server 2013, o enfileiramento de mensagens não é necessário.

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>Requisitos de armazenamento de dados para arquivamento

Além disso, você precisa configurar a infraestrutura para arquivar o armazenamento. Isso inclui um dos seguintes procedimentos:

  - **Armazenamento do Microsoft Exchange**. Meeting content files, such as PowerPoint presentations, are archived as attachments. Se você quiser usar a integração do Microsoft Exchange para que os dados do arquivo morto do Lync sejam armazenados com dados de conformidade do Exchange, você deve usar o Exchange 2013 para a implantação do Exchange e garantir que o tamanho de armazenamento máximo seja compatível com o armazenamento dos arquivos de conteúdo da reunião. Se você implantar o arquivamento usando a opção de integração do Microsoft Exchange, os dados do arquivo morto do Lync serão armazenados com os dados de conformidade do Exchange 2013 somente para os usuários que estiverem hospedados em seus servidores Exchange 2013. Você deve implantar o Exchange 2013 antes de implantar e habilitar o arquivamento usando a opção de integração do Microsoft Exchange. Se optar por usar o armazenamento do Exchange 2013, você não precisará implantar bancos de dados do SQL Server separados para arquivamento, a menos que você tenha usuários do Lync que não são hospedados em seus servidores Exchange 2013.

  - **Armazenamento de banco de dados do SQL Server para arquivamento**. Para dar suporte a usuários que não são hospedados em servidores Exchange 2013 ou se você não quiser usar a opção de integração do Microsoft Exchange, você deve implantar o armazenamento de arquivamento usando um banco de dados do SQL Server. O Lync Server 2013 é compatível com as seguintes versões de 64 bits do SQL Server:
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 padrão
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express e Microsoft SQL Server 2012 Express não são compatíveis com o arquivamento. Não há suporte para as versões de 32 bits do SQL Server. Para obter mais requisitos e restrições do SQL Server, consulte <A href="lync-server-2013-database-software-support.md">suporte a software de banco de dados no Lync Server 2013</A> na documentação de planejamento ou na documentação de suporte.

    
    </div>
    
    Você deve configurar as plataformas do SQL Server antes de implantar e habilitar o arquivamento. Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia. Você também pode criar o banco de dados posteriormente, incluindo como parte do procedimento de instalação. Para obter detalhes sobre o SQL Server, consulte o TechCenter do [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)SQL Server em.

</div>

</div>

<span> </span>

</div>

</div>

</div>

