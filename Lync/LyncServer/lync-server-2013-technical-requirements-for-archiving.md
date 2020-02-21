---
title: 'Lync Server 2013: requisitos técnicos para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d2ba284f64b311ad48191cf251d1b3d903f595a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Requisitos técnicos para arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-09_

Os requisitos técnicos do Lync Server 2013 incluem o seguinte:

  - Requisitos de infraestrutura.

  - Software que é pré-requisito e que deve estar instalado para o arquivamento.

  - Requisitos de armazenamento de dados para arquivamento.

  - Requisitos de dimensionamento e considerações para a implantação de arquivamento.

  - Requisitos de desempenho e considerações para os bancos de dados de arquivamento.

<div>


> [!NOTE]  
> As informações de escala e desempenho não estão disponíveis nesta versão do Lync Server 2013.



</div>

<div>

## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura

Os requisitos de infraestrutura de arquivamento do Lync Server 2013 são os mesmos para a implantação do Lync Server 2013. Para obter detalhes, consulte [determinando seus requisitos de infraestrutura para o Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) na documentação de planejamento.

</div>

<div>

## <a name="archiving-prerequisites"></a>Pré-requisitos de arquivamento

O Lync Server 2013 simplifica os pré-requisitos para arquivamento por causa do seguinte:

  - O servidor de arquivamento não é mais uma função do servidor. Em vez disso, o agente de coleta de dados unificada é executado em um pool e em servidores Standard Edition para registrar dados para arquivamento, de forma que não é preciso configurar plataformas de sistemas separados para arquivamento.

  - O arquivamento usa o armazenamento de arquivos do Lync Server 2013 para armazenamento temporário de arquivos de conteúdo de reunião, portanto, você não configura um repositório de arquivos separado para arquivamento.

  - No Lync Server 2013, o enfileiramento de mensagens não é necessário.

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>Requisitos de armazenamento de dados para arquivamento

Além disso, você deve configurar a infraestrutura para o armazenamento de arquivamento. Isso inclui uma ou ambas as opções abaixo:

  - **Armazenamento do Microsoft Exchange**. Conteúdo de reuniões, como apresentações em PowerPoint, são arquivados como anexos. Se você quiser usar a integração do Microsoft Exchange para que os dados de arquivo morto do Lync sejam armazenados com dados de conformidade do Exchange, você deve usar o Exchange 2013 para sua implantação do Exchange e garantir que o tamanho máximo de armazenamento seja compatível com o armazenamento dos arquivos de conteúdo da reunião. Se você implantar o arquivamento usando a opção de integração do Microsoft Exchange, os dados de arquivo morto do Lync serão armazenados com dados de conformidade do Exchange 2013 somente para os usuários hospedados em seus servidores do Exchange 2013. Você deve implantar o Exchange 2013 antes de implantar e habilitar o arquivamento usando a opção de integração do Microsoft Exchange. Se você optar por usar o armazenamento do Exchange 2013, não será necessário implantar bancos de dados separados do SQL Server para arquivamento, a menos que você tenha usuários do Lync que não estejam hospedados em seus servidores do Exchange 2013.

  - **Armazenamento de banco de dados do SQL Server para arquivamento**. Para dar suporte a usuários que não estão hospedados em servidores Exchange 2013, ou se você não deseja usar a opção de integração do Microsoft Exchange, você deve implantar o armazenamento de arquivamento usando um banco de dados do SQL Server. O Lync Server 2013 oferece suporte às seguintes versões de 64 bits do SQL Server:
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 padrão
    
    <div>
    

    > [!NOTE]  
    > O Microsoft SQL Server 2008 R2 Express e o Microsoft SQL Server 2012 Express não têm suporte para arquivamento. Não há suporte para as versões de 32 bits do SQL Server. Para obter requisitos e restrições adicionais do SQL Server, confira <A href="lync-server-2013-database-software-support.md">suporte a software de banco de dados no Lync Server 2013</A> na documentação de planejamento ou na documentação de capacidade de suporte.

    
    </div>
    
    Você deve configurar as plataformas do SQL Server antes de implantar e habilitar o arquivamento. Se a conta utilizada para publicar a topologia tiver os direitos e permissões apropriados, é possível criar o banco de dados de arquivamento (LcsLog) ao publicar a topologia. Também é possível criar o banco de dados posteriormente, incluindo-o como parte do procedimento de instalação. Para obter detalhes sobre o SQL Server, consulte o TechCenter do [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045)SQL Server em.

</div>

</div>

<span> </span>

</div>

</div>

</div>

