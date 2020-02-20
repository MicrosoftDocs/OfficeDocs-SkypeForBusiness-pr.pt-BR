---
title: Localização do servidor do Lync Server 2013 em uma implantação do servidor Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7390c3cee8be94f6bead96ff990e380b06011eb7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Colocação de servidor em uma implantação de servidor Standard Edition para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-20_

Esta seção descreve as funções de servidor, os bancos de dados e os compartilhamentos de arquivos que podem ser colocados em uma implantação do servidor do Lync Server 2013 Standard Edition.

<div>

## <a name="server-roles"></a>Funções do Servidor

No Lync Server 2013, o serviço de conferência A/V, o serviço de mediação, o monitoramento e o arquivamento são colocados no servidor Standard Edition, mas é necessária configuração adicional para habilitá-los. Você pode optar por implantar o serviço de Mediação em servidores separados.

É possível colocar um servidor de aplicativo confiável com o Servidor Standard Edition.

As funções do servidor mostradas a seguir devem ser implantadas cada uma em um computador separado:

  - Be

  - Servidor de Borda

  - Servidor de mediação (se não colocado com o servidor Standard Edition)

  - Servidor do Office Web Apps

</div>

<div>

## <a name="databases"></a>Bancos de dados

Por padrão, o banco de dados back-end do SQL Server Express está posicionado no servidor Standard Edition. Você não pode movê-la para um computador separado. Com uma exceção, não é possível colocar outros bancos de dados no servidor Standard Edition. Se você optar por implantar o servidor de chat persistente em um servidor Standard Edition, poderá colocar o banco de dados de chat persistente e o banco de dados de conformidade de chat persistente no mesmo servidor Standard Edition.

Você pode colocar cada um dos seguintes bancos de dados em um único servidor de banco de dados:

  - Banco de dados de monitoramento

  - Banco de dados de arquivamento

  - Um banco de dados back-end para um pool de front-ends Enterprise Edition

Você pode colocar qualquer um ou todos esses bancos de dados em uma única instância SQL ou usar instâncias SQL separadas para cada um, com as seguintes limitações:

  - Cada instância SQL pode conter apenas um único banco de dados back-end (para um pool de front-ends Enterprise Edition), um banco de dados de monitoramento único, um banco de dados de arquivamento único, um banco de dados de chat persistente único e um banco de dados de conformidade de chat

  - O servidor de banco de dados não pode dar suporte a mais de um pool de front-ends Enterprise Edition, um servidor executando o arquivamento, um servidor executando monitoramento, um banco de dados de chat persistente único e um banco de dados de conformidade de chat persistente único, mas pode suportar um de cada, independentemente de os bancos de dados usarem a mesma instância do SQL Server ou instâncias separadas do SQL Server.

É possível colocar um compartilhamento de arquivo com um banco de dados, conforme será descrito ainda nesta seção.

<div>


> [!NOTE]  
> No Lync Server 2013, você tem a opção de integrar o monitoramento e o armazenamento de arquivamento com o armazenamento do Exchange 2013 para alguns ou todos os usuários em sua implantação. Você não pode implantar servidores que executam o Lync Server ou componentes nos mesmos servidores que o armazenamento do Exchange.



</div>

<div>


> [!IMPORTANT]  
> Embora a colocação de bancos de dados seja suportada, o tamanho dos bancos de dados pode aumentar muito rápido. Por exemplo, quando você considera colocar o banco de dados de Arquivamento com outros bancos de dados, se estiver arquivando as mensagens de mais de alguns usuários, o espaço em disco exigido pelo banco de dados de Arquivamento poderá aumentar bastante. Por esse motivo, não recomendamos a colocação de vários bancos de dados, especialmente o banco de dados de arquivamento, banco de dados de chat persistente e banco de dados de conformidade de chat persistente com o banco de dados back-end de um pool corporativo.



</div>

</div>

<div>

## <a name="file-shares"></a>Compartilhamentos de arquivos

O compartilhamento de arquivo pode ser um servidor separado ou pode ser colocado no mesmo servidor como qualquer um ou todos a seguir:

  - Servidor de banco de dados, incluindo o Servidor Back-End de um pool de Front-Ends Enterprise Edition

  - Banco de dados de arquivamento

  - Banco de dados de monitoramento

  - Banco de dados de chat persistente

  - Banco de dados de conformidade de chat persistente

Um compartilhamento de arquivo único pode ser usado para múltiplos pools de Front-Ends, servidores Standard Edition (todos no mesmo site).

<div>


> [!NOTE]  
> No Lync Server 2013, o monitoramento e o arquivamento usam o compartilhamento de arquivos do Lync Server como o servidor Standard Edition.



</div>

</div>

<div>

## <a name="other-components"></a>Outros componentes

Não é possível colocar um servidor proxy reverso, que não é um componente do Lync Server 2013, mas é necessário em sua implantação se você quiser dar suporte ao compartilhamento de conteúdo da Web para usuários federados com qualquer função de servidor do Lync Server 2013. No entanto, você pode implementar o suporte de proxy reverso para uma implantação do Lync Server 2013 Configurando o suporte em um servidor de proxy reverso existente em sua organização que é usado para outros aplicativos.

Não é possível colocar nenhum componente do Exchange ou UM componente do SharePoint com nenhuma função do Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

