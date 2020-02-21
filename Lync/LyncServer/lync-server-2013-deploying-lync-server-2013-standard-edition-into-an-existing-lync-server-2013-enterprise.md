---
title: 'Lync Server 2013: Implantando o Lync Server 2013 Standard Edition em um Lync Server 2013 Enterprise existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 733dcadc52550c665cc74407a81cddbfbd5ea640
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>Implantando o Lync Server 2013 Standard Edition em um Lync Server 2013 Enterprise existente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

A implantação de um servidor Standard Edition em uma implantação existente do Enterprise Edition é semelhante à implantação de funções de servidor adicionais. Um servidor Standard Edition pode ser implantado em outro site, permitindo que os usuários desse site sejam hospedados no servidor Standard Edition, e não no pool de front-ends em uma rede de longa distância (WAN). Os procedimentos para instalar o novo site e os servidores desse site já estão definidos em outras seções da documentação [implantando o Lync Server 2013](lync-server-2013-deploying-lync-server.md) .

<div id="sectionSection0" class="section">

**Para definir um novo site**

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  Na árvore do console, clique com o botão direito do mouse em **Lync Server 2013**e, em seguida, clique em **novo site central**.

3.  Na página **Identificar o site**, nomeie o site e insira uma descrição (opcional).

4.  Siga os procedimentos para definir o restante da topologia do site. Para obter detalhes, consulte [definindo e configurando a topologia no Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

5.  Publique a topologia atualizada. Para obter detalhes, consulte [publish the Topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).

6.  Configurar e instalar um servidor Standard Edition.
    
    <div>
    

    > [!Caution]  
    > Se você tiver implantado um ambiente com apenas um servidor Standard Edition, você terá iniciado o processo de instalação do assistente de implantação do Lync Server usando o link <STRONG>preparar primeiro servidor Standard Edition</STRONG> para instalar os arquivos de banco de dados iniciais no novo servidor Standard Edition. <STRONG>Não</STRONG> siga esse processo ao instalar um servidor Standard Edition em uma implantação existente do Lync Server 2013.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

