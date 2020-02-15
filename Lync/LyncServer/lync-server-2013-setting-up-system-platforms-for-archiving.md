---
title: 'Lync Server 2013: Configurando plataformas do sistema para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88e1a8aea999fdf134b0152a9d37b2d36fc81ee8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Configurando plataformas do sistema para arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-09_

Antes de iniciar a implantação do Arquivamento, você deve instalar o sistema operacional necessário e qualquer outro software pré-requisito no hardware que atende os requisitos do sistema:

  - **Lync Server 2013 plataforma**   Lync Server 2013 as implantações não têm servidores de arquivamento. Em vez disso, os agentes de coleta de dados unificados são executados em servidores front-end e servidores Standard Edition para capturar dados para arquivamento, portanto, nenhuma plataforma de sistema separada é necessária para hospedar o arquivamento.

  - **Plataforma de armazenamento de dados**   no Lync Server 2013, você pode armazenar dados usando um dos seguintes:
    
      - **Integração com**   o Microsoft Exchange se você quiser armazenar dados de arquivamento do Lync Server 2013 usando sua implantação do Exchange 2013, em vez de ou além de configurar um banco de dados separado para armazenamento de dados de arquivamento, sua implantação do Exchange deverá estar executando o Exchange 2013. Para obter detalhes sobre como configurar plataformas de sistema para o Exchange 2013, consulte a documentação do produto Exchange.
    
      - **SQL Server**   se você quiser usar um banco de dados separado do SQL Server para armazenamento de dados de arquivamento, em vez de ou além de usar a integração do Microsoft Exchange, você deve configurar a plataforma do sistema para o banco de dados antes da implantação do arquivamento. Os requisitos específicos da plataforma do sistema dependem se você usa o Microsoft SQL Server 2008 R2 ou o Microsoft SQL Server 2012 para o banco de dados de arquivamento. Para obter detalhes sobre como configurar plataformas de sistema para esses bancos de dados, consulte a documentação do produto Microsoft SQL Server 2008 R2 e Microsoft SQL Server 2012.

  - **Plataforma de servidor de arquivos**   o Lync Server 2013 armazena arquivos de arquivamento do Lync Server no mesmo local especificado para armazenamento de arquivos quando você configura seus servidores front-end ou servidores Standard Edition. Não é possível especificar um local separado para arquivar o armazenamento de arquivos, portanto, nenhuma plataforma de sistema separada é necessária para arquivar o armazenamento de arquivos. Se você usar a integração com o Microsoft Exchange, o Exchange 2013 os arquivos para comunicações arquivadas do Lync são armazenados nos servidores do Exchange 2013 para usuários hospedados nesses servidores do Exchange.

</div>

<span> </span>

</div>

</div>

</div>

