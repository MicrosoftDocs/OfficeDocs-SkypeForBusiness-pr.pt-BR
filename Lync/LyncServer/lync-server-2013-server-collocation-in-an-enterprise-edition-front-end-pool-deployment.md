---
title: 'Lync Server 2013: Posicionamento do servidor em uma implantação do pool de front-ends do Enterprise Edition'
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
ms.openlocfilehash: ad549c614fc14b74126a7e81e0223ad584e68141
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>Posicionamento do servidor em uma implantação do pool de front-ends do Enterprise Edition para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-11_

Esta seção descreve as funções de servidor, bancos de dados e compartilhamentos de arquivos que você pode colocar em uma implantação de pool de front-end do Lync Server 2013.

<div>

## <a name="server-roles"></a>Funções de servidor

No Lync Server 2013, o serviço de conferência A/V, o serviço de mediação, o monitoramento e o arquivamento são posicionados no servidor front-end, mas é necessária configuração adicional para habilitá-los. Se você não quiser posicionar o servidor de mediação com o servidor front-end, poderá implantá-lo como um servidor de mediação autônomo em um computador separado.

Você pode posicionar um servidor de aplicativos confiável com o servidor front-end.

As seguintes funções de servidor devem ser implantadas em um computador separado:

  - Diretor

  - Servidor de Borda

  - Servidor de mediação (se não estiver posicionado com o servidor front-end)

  - Servidor Office Web Apps

Não é possível colocar a função de servidor de chat persistente com o servidor front-end.

</div>

<div>

## <a name="databases"></a>Bancos de dados

Você pode posicionar cada um dos seguintes bancos de dados no mesmo servidor de banco de dados:

  - Banco de dados back-end

  - Banco de dados de monitoramento

  - Banco de dados de arquivamento

  - Banco de dados de chat persistente

  - Banco de dados de conformidade de chat persistente

Você pode colocar qualquer um ou todos esses bancos de dados em uma única instância do SQL Server ou usar uma instância separada do SQL Server para cada um deles, com as seguintes limitações:

  - Cada instância do SQL Server pode conter apenas um único banco de dados back-end, um único banco de dados de monitoramento, um único banco de dados de arquivamento, um único banco de dados persistente de chat e um único banco de dados de conformidade de chat persistente.

  - O servidor de banco de dados não pode dar suporte a mais de um pool de front-end, uma implantação de arquivamento e uma implantação de monitoramento, mas ele pode dar suporte a um de cada, independentemente de os bancos de dados usarem a mesma instância do SQL Server ou instâncias separadas do SQL Server.

Você pode posicionar um compartilhamento de arquivos com os bancos de dados, conforme descrito mais adiante nesta seção.

<div>


> [!NOTE]  
> No Lync Server 2013, você tem a opção de integrar o armazenamento de arquivamento com o armazenamento do Exchange 2013 para alguns ou todos os usuários em sua implantação. Você não pode implantar servidores que estejam executando o Lync Server ou componentes nos mesmos servidores que o armazenamento do Exchange.



</div>

<div>


> [!IMPORTANT]  
> Embora a colocação de bancos de dados seja compatível, o tamanho dos bancos de dados pode crescer rapidamente. Por exemplo, quando você considera posicionar o banco de dados de arquivamento com outros bancos de dados, lembre-se de que, se você estiver arquivando as mensagens de mais de alguns usuários, o espaço em disco necessário para o banco de dados do arquivamento pode crescer muito grande. Por esse motivo, não recomendamos a colocação de vários bancos de dados, especialmente o banco de dados de arquivamento, o banco de dados de chat persistente ou o banco de dados de conformidade de chat persistente com o banco de dados back-end.



</div>

</div>

<div>

## <a name="file-share"></a>Compartilhamento de arquivo

O compartilhamento de arquivos pode ser um servidor separado ou pode ser posicionado no mesmo servidor que qualquer um ou todos os seguintes itens:

  - Servidor de banco de dados, incluindo o servidor back-end de um pool Front-end da Enterprise Edition

  - Banco de dados de arquivamento

  - Banco de dados de monitoramento

  - Banco de dados de chat persistente

  - Banco de dados de conformidade de chat persistente

Um único compartilhamento de arquivo pode ser usado para vários pools de front-end, servidores Standard Edition (todos no mesmo site).

<div>


> [!NOTE]  
> No Lync Server 2013, o monitoramento e o arquivamento usam o compartilhamento de arquivos do Lync Server como o servidor front-end.



</div>

</div>

<div>

## <a name="other-components"></a>Outros componentes

Você não pode colocar um servidor proxy reverso, que não é um componente do Lync Server 2013, mas é necessário em sua implantação se quiser dar suporte ao compartilhamento de conteúdo da Web para usuários federados com qualquer função de servidor do Lync Server 2013. No entanto, você pode implementar o suporte de proxy reverso para uma implantação do Lync Server 2013 Configurando o suporte em um servidor de proxy reverso existente em sua organização que é usado para outros aplicativos.

Você não pode colocar nenhum componente de Unificação de mensagens (UM) do Exchange ou componente do SharePoint com qualquer função do SharePoint Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

