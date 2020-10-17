---
title: 'Lync Server 2013: configurar FQDNs de farm da Web'
description: 'Lync Server 2013: configurar FQDNs de farm da Web.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a07faac4d4809ffe10e7ca3699e7441e6dbcb7b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566657"
---
# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>Configurar FQDNs do Web farm para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-29_

Ao definir a configuração do servidor Standard Edition, pool de front-ends, diretor ou pool de diretores no construtor de topologias, você configura um FQDN (nome de domínio totalmente qualificado) dos serviços Web externos. Durante o processo de logon de um cliente hospedado no servidor Standard Edition ou no pool de front-ends, os FQDNs de serviços Web configurados são enviados por meio de provisionamento em banda. Se você precisar adicionar ou alterar a URL de serviços Web externos, use o construtor de topologias para configurar ou reconfigurar a configuração dos serviços Web usando o procedimento neste tópico.

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>Para configurar um FQDN de pool externo para serviços da Web

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  No construtor de topologias, na árvore de console em **front-ends Standard Edition**, **front-ends Enterprise Edition**e **diretores**, clique com o botão direito do mouse no nome do pool que você precisa editar e clique em **Editar propriedades**.

3.  Na seção **Serviços da Web**, adicione ou edite o **FQDN de serviços da Web externos**.

4.  Revise e ajuste as **Portas do ouvinte** para HTTP e HTTPS. Os padrões serão:
    
      - **Portas do ouvinte:** HTTP 8080, HTTPS 4443
    
      - **Portas publicadas:** HTTP 80, HTTPS 443
    
    Onde as **Portas do ouvinte** são as portas onde os serviços da Web externos serão configurados para receber solicitações do proxy inverso e as **Portas publicadas** são as portas publicadas externamente pelo proxy inverso e são comunicadas para clientes durante o provisionamento em banda.

5.  Ao concluir as adições e atualizações, clique em **OK** para continuar.

6.  Clique com o botão direito do mouse em **Lync Server 2013**e clique em **publicar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Após a publicação concluir com sucesso, um link pode ser apresentado informando que existem etapas adicionais que precisam ser realizadas. O link, se clicado, abre uma lista de servidores afetados pelas alterações feitas no construtor de topologias que exigirão que você execute novamente o assistente de implantação do Lync Server em cada servidor listado para atualizar a configuração dos componentes adicionados, removidos ou alterados.

    
    </div>

7.  Repita essas etapas para cada servidor Standard Edition, pool de front-ends, diretor ou pool diretor na organização.

</div>

</div>

<span> </span>

</div>

</div>

</div>

