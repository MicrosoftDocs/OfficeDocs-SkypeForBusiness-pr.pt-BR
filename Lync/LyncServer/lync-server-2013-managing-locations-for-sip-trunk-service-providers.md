---
title: 'Lync Server 2013: Gerenciando locais para provedores de serviço de tronco SIP'
description: 'Lync Server 2013: Gerenciando locais para provedores de serviço de tronco SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 062c55f6e8484121c91b28f4926e37f85a25c0a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545187"
---
# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a>Gerenciando locais para provedores de serviço de tronco SIP no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

Para configurar o Lync Server para localizar automaticamente clientes dentro de uma rede, você precisa preencher o banco de dados do serviço de informações de local com um Wiremap de rede e publicar os locais ou vincular a um banco de dados externo que já contém os mapeamentos corretos. Como parte desse processo, é necessário validar os endereços cívicos dos locais com seu provedor de serviço de E9-1-1. Para obter detalhes, consulte [Configure the Location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.

Você preenche o banco de dados de serviço de Informação de Local com um Local de Resposta de Emergência (ERL), que consiste de um endereço civil e o endereço específico dentro de uma construção. O campo **local** do serviço de informações de local, que é o local específico dentro de um edifício, tem um comprimento máximo de 20 caracteres (incluindo espaços). Dentro desse comprimento limitado, tente incluir o seguinte:

  - Forneça um nome fácil de entender que identifica o local do chamador de 911 para garantir que os respondentes de emergência encontrem a localização específica prontamente, assim que eles chegarem ao endereço residencial. Esse nome de local pode incluir um número de edifício, número do andar, designador de ala, número do quarto, etc. Evite usar apelidos que apenas os funcionários conheçam, pois isso pode fazer com que os respondentes de emergência cheguem ao local errado.

  - Um identificador de local que ajuda os usuários a ver facilmente que seu cliente do Lync obteve o local correto. O cliente Lync concatena e exibe automaticamente os campos **Location** e **City** descobertos em seu cabeçalho. Uma boa prática é adicionar o endereço de rua da construção a cada identificador de local (por exemplo, "primeiro andar \<street number\> "). Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer construção na cidade.

  - Se o local for aproximado por ser determinado por um ponto de acesso sem fio, convém adicionar a palavra Near (por exemplo, "próximo ao 1º andar, 1234").

<div>


> [!NOTE]  
> Os locais adicionados ao banco de dados de local central não estão disponíveis para o cliente até serem publicados usando um comando do Shell de gerenciamento do Lync Server e são replicados para os repositórios locais do pool. Para obter detalhes, consulte <A href="lync-server-2013-publish-the-location-database.md">publicar o banco de dados de localização no Lync Server 2013</A> na documentação de implantação.



</div>

As seções a seguir discutem as considerações que devem ser analisadas ao preencher e manter o banco de dados de local.

<div>

## <a name="populating-the-location-database"></a>Preenchendo o banco de dados Local

As seguintes perguntas podem ajudar a determinar como você preencherá o banco de dados de local.

  - **Qual processo você usará para preencher o banco de dados de local?**  
    Onde os dados existem e quais etapas você precisa executar para converter os dados para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?

<!-- end list -->

  - **Você tem um banco de dados de terceiros que já contém um mapeamento de locais?**  
    Usando a opção de serviço de informações de local secundário do Lync Server para se conectar a um banco de dados de terceiros, é possível agrupar e gerenciar locais usando uma plataforma offline. Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário. Isso significa que o serviço de informações de local pode retornar vários endereços, originários do serviço de informações de local secundário, para um cliente do Lync Server. Em seguida, o usuário pode escolher o local mais apropriado.
    
    Para integrar com o serviço de informações de local, o banco de dados de terceiros deve seguir o esquema de solicitação/resposta de local do Lync Server. Para obter detalhes, consulte " \[ MS-E911WS \] : Web Service for E911 support Protocol Specification" em <https://go.microsoft.com/fwlink/p/?linkid=213819> . Para obter detalhes sobre a implantação de um serviço de informações de local secundário, consulte [configurar um serviço de informações de local secundário no Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) na documentação de implantação.

Para obter detalhes sobre como preencher o banco de dados de local, consulte [Configure the Location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Manutenção do banco de dados Local

Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede muda. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.

  - **Como você atualizará o banco de dados de local?**  
    Há diversos cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de WAPs, recabeamento do escritório (resultando em atribuições de comutação diferentes) e expansão da subrede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?

<!-- end list -->

  - **Você usará um aplicativo SNMP para corresponder a endereços do MAC do cliente do Lync a identificadores de porta e de comutador?**  
    Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de chassi de comutador e de porta consistentes entre o aplicativo SNMP e o banco de dados de local. Se o aplicativo SNMP retornar um endereço IP de chassi ou uma ID de porta que não esteja incluída no banco de dados, o serviço de informações de local não poderá retornar um local ao cliente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

