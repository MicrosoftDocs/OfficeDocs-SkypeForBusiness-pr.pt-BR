---
title: 'Lync Server 2013: Definindo e configurando a topologia'
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
ms.openlocfilehash: 8430ec5cc8b362aa78f97afc24ab0e588c7bc650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>Definindo e configurando a topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-14_

Você define e configura sua topologia usando o construtor de topologias. O construtor de topologias não requer que você seja membro do grupo Administradores local ou de um grupo de domínio privilegiado (como administradores de domínio). Você pode definir sua topologia como um usuário padrão. Ao iniciar o construtor de topologia na primeira utilização e em sessões de edição subsequentes, você será solicitado a fornecer o local onde deseja que o construtor de topologias carregue o documento de configuração atual. As opções são as seguintes:

  - Baixar topologia da implantação existente

  - Abrir a topologia de um arquivo local

  - Nova topologia

Se já definiu uma topologia e estabeleceu o repositório de gerenciamento central, você deve optar por baixar uma topologia de uma implantação existente. O construtor de topologias lerá o banco de dados e recuperará a definição atual. Se você tiver um repositório de gerenciamento central existente, você deve sempre escolher essa opção.

Se você não tiver estabelecido um repositório de gerenciamento central e quiser editar uma configuração salva anteriormente, deve optar por abrir a topologia a partir de um arquivo local. O arquivo que você abrir será o arquivo de configuração que foi salvo em uma sessão anterior. Você pode usar essa opção para editar a topologia salva anteriormente.

<div>


> [!WARNING]  
> Se já tiver uma topologia publicada, você não deverá carregar um arquivo de configuração local. Você deve optar por baixar a topologia de uma implantação existente.



</div>

Escolha se deseja criar uma nova topologia, se você quiser criar uma nova configuração do construtor de topologias. Um design salvo anteriormente não será substituído, a menos que você opte por salvá-lo como o mesmo arquivo que você criou em uma sessão de design anterior.

Em cada uma dessas opções, você será solicitado a fornecer um local para armazenar o arquivo de configuração do construtor de topologias. O local para o arquivo pode ser um local local, um local compartilhado em um compartilhamento de arquivos estabelecido ou uma mídia removível.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Definir e configurar uma topologia no Construtor de Topologia para Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Definir e configurar um pool Front-End ou um servidor Standard Edition no Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Implantando pools Front-End emparelhados para recuperação de desastre no Lync Server 2013](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Implantando espelhamento SQL para alta disponibilidade de Servidor Back-End no Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Editar ou configurar URLs simples no Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Selecionar o Servidor de Gerenciamento Central no Lync Server 2013](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

