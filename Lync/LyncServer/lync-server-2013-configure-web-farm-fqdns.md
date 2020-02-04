---
title: 'Lync Server 2013: Configurar FQDNs da web farm'
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
ms.openlocfilehash: 4bd01b02cef8d806f390b6b700fa42acd37e27d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>Configurar FQDNs da web farm para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-29_

Quando você definiu a configuração do servidor Standard Edition, do servidor de front-end, do director ou do diretor do criador no construtor de topologias, você configura um nome de domínio totalmente qualificado (FQDN) dos serviços Web externos. Durante o processo de logon de um cliente hospedado no servidor Standard Edition ou no pool de front-end, os FQDNs dos serviços Web configurados são enviados por meio de provisionamento em banda. Se você precisar adicionar ou alterar a URL de serviços Web externos, use o construtor de topologias para configurar ou reconfigurar a configuração de serviços Web usando o procedimento deste tópico.

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>Para configurar um FQDN do pool externo para serviços Web

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  No construtor de topologias, na árvore de console, em **front-ends da edição padrão**, **front-ends**e **directors**da edição Enterprise, clique com o botão direito do mouse no nome do pool que você precisa editar e clique em **Editar propriedades**.

3.  Na seção **Serviços Web** , adicione ou edite o **FQDN dos serviços Web externos**.

4.  Revise e ajuste as **portas de escuta** para http e HTTPS. Os padrões serão:
    
      - **Portas de escuta:** HTTP 8080, HTTPS 4443
    
      - **Portas publicadas:** HTTP 80, HTTPS 443
    
    Onde as **portas de escuta** são a porta que os serviços Web externos serão configurados para receber solicitações do proxy reverso, e as **portas publicadas** são as portas publicadas externamente pelo proxy reverso e são comunicadas aos clientes durante o provisionamento em banda.

5.  Quando tiver concluído suas adições e atualizações, clique em **OK** para continuar.

6.  Clique com o botão direito do mouse no **Lync Server 2013**e, em seguida, clique em **publicar**.
    
    <div>
    

    > [!IMPORTANT]  
    > Após a publicação ser concluída com êxito, pode ser apresentado um link que informa que há etapas adicionais que precisam ser executadas. O link, se clicado, abre uma lista de servidores afetados pelas alterações feitas no construtor de topologias que exigirão que você execute novamente o assistente de implantação do Lync Server em cada servidor listado para atualizar a configuração de componentes adicionados, removidos ou alterados.

    
    </div>

7.  Repita essas etapas para cada servidor Standard Edition, o pool de front-end, o diretor ou o pool do diretor da organização.

</div>

</div>

<span> </span>

</div>

</div>

</div>

