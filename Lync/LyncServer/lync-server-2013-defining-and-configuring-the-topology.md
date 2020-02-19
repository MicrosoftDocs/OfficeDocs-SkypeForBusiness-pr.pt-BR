---
title: 'Lync Server 2013: definindo e configurando a topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a443aaa7cf523e1cb02beb3d944ec53632732291
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>Definindo e configurando a topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-14_

Você define e configura sua topologia usando o construtor de topologias. O construtor de topologias não exige que você seja membro do grupo Administradores local ou de um grupo de domínio privilegiado (como administradores de domínio). Você pode definir sua topologia como um usuário padrão. Quando você iniciar o construtor de topologia no primeiro uso e nas sessões de edição subsequentes, será solicitado o local em que deseja que o construtor de topologia carregue o documento de configuração atual. As opções são as seguintes:

  - Baixar a topologia da implantação existente

  - Abrir a topologia de um arquivo local

  - Nova topologia

Se já tiver definido uma topologia e tiver estabelecido o repositório de gerenciamento central, você deverá optar por baixar uma topologia de uma implantação existente. O construtor de topologias lerá o banco de dados e recuperará a definição atual. Se você tiver um repositório de gerenciamento central existente, você deve sempre escolher esta opção.

Se você não tiver estabelecido um repositório de gerenciamento central e quiser editar uma configuração salva anteriormente, deverá optar por abrir a topologia de um arquivo local. O arquivo que será aberto seria o arquivo de configuração salvo em uma sessão anterior. Você pode usar esta opção para editar a topologia salva anteriormente.

<div>


> [!WARNING]  
> Se você já tem uma topologia publicada, não deve carregar um arquivo de configuração local. Você deve baixar topologia de uma implantação existente.



</div>

Escolha criar uma nova topologia, se você quiser criar uma nova configuração do construtor de topologias. Um projeto salvo anteriormente não é substituído, a menos que você escolha salvá-lo como o mesmo arquivo criado em uma sessão anterior do design.

Em cada uma dessas opções, você será solicitado a fornecer um local para armazenar o arquivo de configuração do construtor de topologias. O local do arquivo poderia ser local, um local compartilhado em um compartilhamento de arquivos estabelecido ou uma mídia removível.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Definir e configurar uma topologia no construtor de topologias para o Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Definir e configurar um pool Front-end ou um servidor Standard Edition no Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Implantando pools front-end emparelhados para recuperação de desastre no Lync Server 2013](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Implantando o espelhamento SQL para alta disponibilidade do servidor back-end no Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Editar ou configurar URLs simples no Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Selecionar o servidor de gerenciamento central no Lync Server 2013](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

