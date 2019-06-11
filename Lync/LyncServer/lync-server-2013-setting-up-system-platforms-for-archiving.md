---
title: 'Lync Server 2013: Configurando plataformas do sistema para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8d9499d68bcca3848e1e069b4962bb7526091d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Configurando plataformas do sistema para arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-09_

Antes de iniciar a implantação do arquivamento, você deve instalar o sistema operacional necessário e qualquer outro software de pré-requisito em hardware que atenda aos requisitos do sistema:

  - **Plataforma Lync Server 2013**   as implantações do Lync Server 2013 não têm servidores de arquivamento. Em vez disso, os agentes de coleta de dados unificados são executados em servidores de front-end e servidores Standard Edition para capturar dados para arquivamento, portanto, não é preciso ter uma plataforma de sistema separada para hospedar o arquivamento.

  - **Plataforma de armazenamento de dados**   no Lync Server 2013, você pode armazenar dados usando um dos seguintes procedimentos:
    
      - **Integração com**   o Microsoft Exchange se você deseja armazenar dados de arquivamento do Lync Server 2013 usando a implantação do Exchange 2013, em vez de ou em conjunto com a configuração de um banco de dados separado para armazenamento de dados de arquivamento, a implantação do Exchange deve ser executando o Exchange 2013. Para obter detalhes sobre a configuração de plataformas do sistema para o Exchange 2013, consulte a documentação do produto Exchange.
    
      - **SQL Server**   se você quiser usar um banco de dados separado do SQL Server para armazenamento de dados de arquivamento, em vez de usar a integração do Microsoft Exchange, você deve configurar a plataforma do sistema para o banco de dados antes da implantação do arquivamento. Os requisitos da plataforma do sistema específico dependem se você usa o Microsoft SQL Server 2008 R2 ou o Microsoft SQL Server 2012 para o banco de dados de arquivamento. Para obter detalhes sobre a configuração de plataformas do sistema para esses bancos de dados, consulte a documentação do Microsoft SQL Server 2008 R2 e do Microsoft SQL Server 2012.

  - **Plataforma de servidor de arquivos**   Lync Server 2013 armazena arquivos de arquivamento do Lync Server no mesmo local que você especificar para armazenamento de arquivos ao configurar seus servidores front-end ou servidores Standard Edition. Você não pode especificar um local separado para arquivar o armazenamento de arquivos, portanto, nenhuma plataforma de sistema separada é necessária para arquivar o armazenamento de arquivos. Se você usa a integração do Microsoft Exchange, o Exchange 2013 os arquivos das comunicações arquivadas do Lync são armazenados nos servidores Exchange 2013 para usuários hospedados nesses servidores Exchange.

</div>

<span> </span>

</div>

</div>

</div>

