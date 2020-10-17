---
title: Lync Server 2013 colocação de servidor em uma implantação de pool de front-ends Enterprise Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0162a4338a1504ed425015e5b9391fca9903d4ab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510278"
---
# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>Colocação de servidor em uma implantação de pool de front-ends Enterprise Edition para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-11_

Esta seção descreve as funções de servidor, os bancos de dados e os compartilhamentos de arquivos que podem ser colocados em uma implantação de pool de front-ends do Lync Server 2013.

<div>

## <a name="server-roles"></a>Funções do Servidor

No Lync Server 2013, o serviço de conferência A/V, o serviço de mediação, o monitoramento e o arquivamento são colocados no servidor front-end, mas é necessária configuração adicional para habilitá-los. Se você não os posicionar no Servidor de Mediação com o Servidor Front-End, poderá implantá-lo como um Servidor de Mediação autônomo em um computador separado.

É possível colocar um servidor de aplicativo confiável com o Servidor Front-End.

As funções do servidor mostradas a seguir devem ser implantadas cada uma em um computador separado:

  - Diretor

  - Servidor de Borda

  - Servidor de Mediação (se não colocado junto ao Servidor Front-End)

  - Servidor do Office Web Apps

Não é possível colocar a função de servidor de chat persistente com o servidor front-end.

</div>

<div>

## <a name="databases"></a>Bancos de dados

Você pode colocar cada um dos bancos de dados a seguir no mesmo servidor de banco de dados:

  - Banco de dados de back-end

  - Banco de dados de monitoramento

  - Banco de dados de arquivamento

  - Banco de dados de chat persistente

  - Banco de dados de conformidade de chat persistente

Você pode colocar qualquer um ou todos esses bancos de dados em uma única instância do SQL Server ou usar uma instância separada do SQL Server para cada, com as seguintes limitações:

  - Cada instância do SQL Server pode conter apenas um único banco de dados de back-end, um único banco de dados de monitoramento, um único banco de dados de arquivamento, um único banco de dados de chat persistente e um único banco de dados de conformidade de chat persistente.

  - O servidor de banco de dados não pode dar suporte a mais de um pool de front-ends, uma implantação de arquivamento e uma implantação de monitoramento, mas pode dar suporte a um de cada, independentemente de os bancos de dados usarem a mesma instância do SQL Server ou instâncias separadas do SQL Server.

É possível colocar um compartilhamento de arquivo com um banco de dados, conforme será descrito ainda nesta seção.

<div>


> [!NOTE]  
> No Lync Server 2013, você tem a opção de integrar o armazenamento de arquivamento ao armazenamento do Exchange 2013 para alguns ou todos os usuários em sua implantação. Você não pode implantar servidores que executam o Lync Server ou componentes nos mesmos servidores que o armazenamento do Exchange.



</div>

<div>


> [!IMPORTANT]  
> Embora a colocação de bancos de dados seja suportada, o tamanho dos bancos de dados pode aumentar muito rápido. Por exemplo, quando você considera colocar o banco de dados de Arquivamento com outros bancos de dados, se estiver arquivando as mensagens de mais de alguns usuários, o espaço em disco exigido pelo banco de dados de Arquivamento poderá aumentar bastante. Por esse motivo, não recomendamos a colocação de vários bancos de dados, especialmente o banco de dados de arquivamento, o banco de dados de chat persistente ou o banco de dados de conformidade de chat persistente com o banco de dados back-end.



</div>

</div>

<div>

## <a name="file-share"></a>Compartilhamento de arquivo

O compartilhamento de arquivo pode ser um servidor separado ou pode ser colocado no mesmo servidor como qualquer um ou todos a seguir:

  - Servidor de banco de dados, incluindo o Servidor Back-End de um pool de Front-Ends Enterprise Edition

  - Banco de dados de arquivamento

  - Banco de dados de monitoramento

  - Banco de dados de chat persistente

  - Banco de dados de conformidade de chat persistente

Um compartilhamento de arquivo único pode ser usado para múltiplos pools de Front-Ends, servidores Standard Edition (todos no mesmo site).

<div>


> [!NOTE]  
> No Lync Server 2013, o monitoramento e o arquivamento usam o compartilhamento de arquivo do Lync Server como servidor de front-end.



</div>

</div>

<div>

## <a name="other-components"></a>Outros componentes

Não é possível colocar um servidor proxy reverso, que não é um componente do Lync Server 2013, mas é necessário em sua implantação se você quiser dar suporte ao compartilhamento de conteúdo da Web para usuários federados com qualquer função de servidor do Lync Server 2013. No entanto, você pode implementar o suporte de proxy reverso para uma implantação do Lync Server 2013 Configurando o suporte em um servidor de proxy reverso existente em sua organização que é usado para outros aplicativos.

Não é possível colocar nenhum componente da Unificação de mensagens (UM) do Exchange ou componente do SharePoint com nenhuma função de servidor do SharePoint.

</div>

</div>

<span> </span>

</div>

</div>

</div>

