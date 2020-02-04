---
title: 'Lync Server 2013: Posicionamento do servidor em uma implantação do servidor Standard Edition'
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
ms.openlocfilehash: 6fa25655fd9bdd2551e10d1fbbf0de617b89be64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Posicionamento do servidor em uma implantação do servidor Standard Edition para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-20_

Esta seção descreve as funções de servidor, bancos de dados e compartilhamentos de arquivos que você pode colocar em uma implantação do servidor do Lync Server 2013 Standard Edition.

<div>

## <a name="server-roles"></a>Funções de servidor

No Lync Server 2013, o serviço de conferência A/V, o serviço de mediação, o monitoramento e o arquivamento são posicionados no servidor do Standard Edition, mas é necessária configuração adicional para habilitá-los. Você pode optar por implantar o serviço de mediação em servidores separados.

Você pode posicionar um servidor de aplicativos confiável com um servidor Standard Edition.

As seguintes funções de servidor devem ser implantadas em um computador separado:

  - Diretor

  - Servidor de Borda

  - Servidor de mediação (se não estiver posicionado com o servidor Standard Edition)

  - Servidor Office Web Apps

</div>

<div>

## <a name="databases"></a>Bancos de dados

Por padrão, o banco de dados back-end do SQL Server Express está posicionado no servidor Standard Edition. Você não pode movê-la para um computador separado. Com uma exceção, você não pode colocar outros bancos de dados no servidor Standard Edition. Se você optar por implantar o servidor de chat persistente em um servidor Standard Edition, poderá colocar o banco de dados de chat persistente e o banco de dados de conformidade de chat persistente no mesmo servidor Standard Edition.

Você pode posicionar cada um dos seguintes bancos de dados em um único servidor de banco de dados:

  - Banco de dados de monitoramento

  - Banco de dados de arquivamento

  - Um banco de dados back-end para um pool de front-end da Enterprise Edition

Você pode colocar qualquer um ou todos esses bancos de dados em uma única instância SQL ou usar uma instância SQL separada para cada um, com as seguintes limitações:

  - Cada instância do SQL pode conter apenas um único banco de dados back-end (para um pool de front-end do Enterprise Edition), um banco de dados de monitoramento único, um banco de dados de único chat persistente e um único banco de dados de conformidade de chat persistente.

  - O servidor de banco de dados não pode dar suporte a mais de um pool de front-end da Enterprise Edition, um servidor executando o arquivamento, um servidor com monitoramento, um banco de dados persistente de chat único e um único banco de dados de conformidade de chat persistente, mas ele pode oferecer suporte a cada um Não importa se os bancos de dados usam a mesma instância do SQL Server ou instâncias separadas do SQL Server.

Você pode posicionar um compartilhamento de arquivos com os bancos de dados, conforme descrito mais adiante nesta seção.

<div>


> [!NOTE]  
> No Lync Server 2013, você tem a opção de integrar o monitoramento e o armazenamento de arquivamento com o armazenamento do Exchange 2013 para alguns ou todos os usuários da sua implantação. Você não pode implantar servidores que estejam executando o Lync Server ou componentes nos mesmos servidores que o armazenamento do Exchange.



</div>

<div>


> [!IMPORTANT]  
> Embora a colocação de bancos de dados seja compatível, o tamanho dos bancos de dados pode crescer rapidamente. Por exemplo, quando você considera posicionar o banco de dados de arquivamento com outros bancos de dados, lembre-se de que, se você estiver arquivando as mensagens de mais de alguns usuários, o espaço em disco necessário para o banco de dados do arquivamento pode crescer muito grande. Por esse motivo, não recomendamos colocar vários bancos de dados, especialmente o banco de dados de arquivamento, o banco de dados de chat persistente e o banco de dados de conformidade de chat persistente com o banco de dados back-end de um pool corporativo.



</div>

</div>

<div>

## <a name="file-shares"></a>Compartilhamentos de arquivos

O compartilhamento de arquivos pode ser um servidor separado ou pode ser posicionado no mesmo servidor que qualquer um ou todos os seguintes itens:

  - Servidor de banco de dados, incluindo o servidor back-end de um pool Front-end da Enterprise Edition

  - Banco de dados de arquivamento

  - Banco de dados de monitoramento

  - Banco de dados de chat persistente

  - Banco de dados de conformidade de chat persistente

Um único compartilhamento de arquivo pode ser usado para vários pools de front-end, servidores Standard Edition (todos no mesmo site).

<div>


> [!NOTE]  
> No Lync Server 2013, o monitoramento e o arquivamento usam o compartilhamento de arquivos do Lync Server como o servidor Standard Edition.



</div>

</div>

<div>

## <a name="other-components"></a>Outros componentes

Você não pode colocar um servidor proxy reverso, que não é um componente do Lync Server 2013, mas é necessário em sua implantação se quiser dar suporte ao compartilhamento de conteúdo da Web para usuários federados com qualquer função de servidor do Lync Server 2013. No entanto, você pode implementar o suporte de proxy reverso para uma implantação do Lync Server 2013 Configurando o suporte em um servidor de proxy reverso existente em sua organização que é usado para outros aplicativos.

Você não pode colocar nenhum componente de UM do Exchange ou componente do SharePoint com qualquer função do Lync Server 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

