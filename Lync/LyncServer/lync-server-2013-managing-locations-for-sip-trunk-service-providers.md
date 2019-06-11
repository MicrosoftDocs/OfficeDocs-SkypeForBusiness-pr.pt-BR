---
title: 'Lync Server 2013: gerenciar locais para provedores de serviço de tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eba237ae4e984169a354339ce0222dfd58f324c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a>Gerenciando locais para provedores de serviço de tronco SIP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

Para configurar o Lync Server para localizar automaticamente clientes em uma rede, você precisa preencher o banco de dados do serviço de informações de localização com um Wiremap de rede e publicar os locais, ou vincular a um banco de dados externo que já contém o mapeamentos. Como parte desse processo, é necessário validar os endereços cívicos dos locais com seu provedor de serviço de E9-1-1. Para obter detalhes, consulte [Configurar o banco de dados de localização no Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.

Você preenche o banco de dados do Serviço de Informações de Local com um Local de Resposta de Emergência (ERL), que consiste de um endereço civil e o endereço específico dentro de um edifício. O campo **local** do serviço de informações de localização, que é o local específico dentro de um edifício, tem um tamanho máximo de 20 caracteres (incluindo espaços). Dentro deste comprimento limitado, tente incluir o seguinte:

  - Um nome fácil de entender que identifica o local do chamador de 911 para ajudar a garantir que os respondentes de emergência encontrem o local correto quando chegarem ao endereço cívico. Esse nome de local pode incluir um número de edifício, número do andar, designador de ala, número da sala, etc. Evite apelidos conhecidos apenas pelos funcionários, que pode fazer com que os respondentes de emergência cheguem ao local errado.

  - Um identificador de localização que ajuda os usuários a ver facilmente que o cliente do Lync selecionou o local correto. O cliente Lync concatena e exibe automaticamente os campos **local** e **cidade** descobertos no cabeçalho. Uma prática recomendada é adicionar o endereço do edifício a cada identificador de localização (por exemplo, "número \<\>do 1ª andar"). Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer edifício na cidade.

  - Se o local for aproximado por ser determinado por um ponto de acesso sem fio, convém adicionar a palavra Near (por exemplo, "próximo ao 1º andar, 1234").

<div>


> [!NOTE]  
> Os locais adicionados ao banco de dados do local central não estarão disponíveis para o cliente até serem publicados usando um comando shell do Shell de gerenciamento do Lync Server e serão duplicados para os armazenamentos locais do pool. Para obter detalhes, consulte <A href="lync-server-2013-publish-the-location-database.md">publicar o banco de dados de local do Lync Server 2013</A> na documentação de implantação.



</div>

As seções a seguir discutem as considerações que devem ser analisadas ao preencher e manter o banco de dados de local.

<div>

## <a name="populating-the-location-database"></a>Preenchendo o banco de dados de local

As seguintes perguntas ajudam a determinar como você preencherá o banco de dados de local.

  - **Qual processo você usará para preencher o banco de dados de local?**  
    Onde estão os dados e quais etapas você precisa executar para convertê-los para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?

<!-- end list -->

  - **Você tem um banco de dados de terceiro que já contém um mapeamento de locais?**  
    Ao usar a opção do serviço de informações de localização secundária do Lync Server para se conectar a um banco de dados de terceiros, você pode agrupar e gerenciar locais usando uma plataforma offline. Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário. Isso significa que o serviço de informações de localização pode retornar vários endereços, originários do serviço de informações de localização secundário, para um cliente do Lync Server. Em seguida, o usuário pode escolher o local mais apropriado.
    
    Para integrar-se com o serviço informações de localização, o banco de dados de terceiros deve seguir o esquema de solicitação/resposta de localização do Lync Server. Para obter detalhes, consulte\["MS-\]E911WS: Web Service for E911 support Protocol Specification" <http://go.microsoft.com/fwlink/p/?linkid=213819>em. Para obter detalhes sobre a implantação de um serviço de informações de localização secundário, consulte [configurar um serviço de informações de localização secundário no Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) na documentação de implantação.

Para obter detalhes sobre como preencher o banco de dados de localização, consulte [Configurar o banco de dados de localização no Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Manutenção do banco de dados de local

Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede mudar. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.

  - **Como você atualizará o banco de dados de local?**  
    Há diversos cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de WAPs, recabeamento do escritório (resultando em atribuições de comutação diferentes) e expansão da subrede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?

<!-- end list -->

  - **Você usará um aplicativo SNMP para que os endereços do MAC do cliente do Skype sejam compatíveis aos identificadores de porta e de comutador?**  
    Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de porta e chassis de comutador consistentes entre o aplicativo SNMP e o banco de dados de local. Se o aplicativo SNMP retornar um endereço IP de chassi ou uma ID de porta que não está incluída no banco de dados, o serviço de informações de localização não poderá retornar um local ao cliente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

