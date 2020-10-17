---
title: 'Lync Server 2013: Gerenciando locais para gateways do ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e33f05f0a05b1225f1687faa00cf48af02fa1410
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498158"
---
# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a>Gerenciando locais para gateways do ELIN no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

Para que o Lync Server forneça automaticamente locais para clientes dentro de uma rede, você precisa executar as seguintes tarefas:

  - Preencha o banco de dados do serviço de informações de local com um Wiremap de rede e inclua os números de identificação de local de emergência (ELINs) no campo CompanyName.

  - Publique as localizações, dessa forma, elas estarão disponíveis para os clientes da sua rede.

  - Carregue o ELINs para o banco de dados de identificação de local automática (ALI) da operadora de rede telefônica pública comutada (PSTN).

Para obter detalhes sobre como executar essas tarefas, consulte [Configure the Location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.

<div>


> [!NOTE]  
> Os locais adicionados ao banco de dados de local central não estão disponíveis para o cliente até serem publicados usando um comando do Shell de gerenciamento do Lync Server e são replicados para os repositórios locais do pool. Para obter detalhes, consulte <A href="lync-server-2013-publish-the-location-database.md">publicar o banco de dados de localização no Lync Server 2013</A> na documentação de implantação.



</div>

Essa seção descreve coisas a serem consideradas conforme você planeja atualizar e manter seu banco de dados de locais.

<div>

## <a name="planning-emergency-locations"></a>Planejando locais de emergência

Ao usar os gateways do ELIN, você preenche o banco de dados do serviço de informações de local com o endereço cívico, um local específico dentro de um edifício e pelo menos um ELIN para cada local. Durante a fase de planejamento, é uma boa ideia decidir como você deseja nomear as localizações e como deseja atribuir ELINs.

<div>

## <a name="planning-location-names"></a>Planejando nomes dos locais

O campo **local** do serviço de informações de local, que mantém o local específico dentro de um edifício, tem um comprimento máximo de 20 caracteres (incluindo espaços). Dentro desse comprimento limitado, tente incluir o seguinte:

  - Um nome fácil de entender que identifica o local do chamador 911 para ajudar a garantir que os respondedores de emergência encontrem o local específico imediatamente quando chegarem ao endereço civil. Esse nome de local pode incluir um número de edifício, um número de chão, um designador de asa, um número de sala e assim por diante. Evite apelidos que são conhecidos apenas por funcionários, que podem fazer com que os respondentes de emergência vá para o local errado.

  - Um identificador de local que ajuda os usuários a ver facilmente que seu cliente do Lync obteve o local correto. O cliente Lync concatena e exibe automaticamente os campos **Location** e **City** descobertos em seu cabeçalho. Uma boa prática é adicionar o endereço de rua da construção a cada identificador de local (por exemplo, "primeiro andar \<street number\> "). Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer construção na cidade.

  - Se o local for aproximado por ser determinado por um ponto de acesso sem fio, é possível adicionar uma palavra Near (por exemplo, "próximo ao 1º andar, 1234").

</div>

<div>

## <a name="planning-elins"></a>Planejando ELINs

Depois de decidir como você deseja dividir o espaço de construção em locais, você precisa decidir quantas ELINs atribuir a cada local. Por exemplo, em um prédio de multisolo ou de vários locatários, diferentes áreas no edifício podem ser atribuídas a diferentes zonas de emergência. Normalmente, cada andar de um edifício é designado como um local. Em seguida, cada local é atribuído a um ou mais ELINs, que são usados como os números de chamada durante uma chamada de emergência. Entre em contato com a sua operadora da PSTN para números de telefone que você possa com ELIs. A tabela a seguir fornece um exemplo de locais para um endereço de rua específico.

### <a name="sample-location-and-elin-assignments"></a>Exemplo de local e atribuições de ELIN

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Área do edifício</th>
<th>Local</th>
<th>ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1º andar</p></td>
<td><p>1</p></td>
<td><p>425-555-0100</p></td>
</tr>
<tr class="even">
<td><p>2º andar</p></td>
<td><p>duas</p></td>
<td><p>425-555-0111</p></td>
</tr>
<tr class="odd">
<td><p>3º andar</p></td>
<td><p>3D</p></td>
<td><p>425-555-0123</p></td>
</tr>
</tbody>
</table>


Os locais definidos devem atender aos seguintes requisitos:

  - Cumpra as regulamentações locais e nacionais/regionais em termos de área máxima por local e número de locais por endereço.

  - Sejam específicos o suficiente para tornar mais fácil localizar o chamador da emergância.

</div>

</div>

<div>

## <a name="populating-the-location-database"></a>Preenchimento do Banco de dados de locais

As perguntas a seguir o ajudarão a determinar como preencher o banco de dados de localização.

  - **Qual processo você usará para preencher o banco de dados de local?**  
    Onde os dados existem e quais etapas você precisa executar para converter os dados para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?

<!-- end list -->

  - **Você tem um banco de dados de terceiros que já contém um mapeamento de locais?**  
    Usando a opção de serviço de informações de local secundário do Lync Server para se conectar a um banco de dados de terceiros, é possível agrupar e gerenciar locais usando uma plataforma offline. Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário. Isso significa que o serviço de informações de local pode retornar vários endereços, originários do serviço de informações de local secundário, para um cliente do Lync Server. Em seguida, o usuário pode escolher o local mais apropriado.
    
    Para integrar com o serviço de informações de local, o banco de dados de terceiros deve seguir o esquema de solicitação/resposta de local do Lync Server. Para obter detalhes, consulte <https://go.microsoft.com/fwlink/p/?linkid=213819> . Para obter detalhes sobre a implantação de um serviço de informações de local secundário, consulte [configurar um serviço de informações de local secundário no Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) na documentação de implantação.

Para obter detalhes sobre como preencher o banco de dados de local, consulte [Configure the Location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Manutenção do banco de dados Local

Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede muda. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.

  - **Como você atualizará o banco de dados de local?**  
    Há vários cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de pontos de acesso sem fio (WAPs), recabeamento do Office (resultando em diferentes atribuições de comutação) e expansão de sub-rede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?

<!-- end list -->

  - **Você usará um aplicativo SNMP para corresponder a endereços MAC do cliente do Lync a identificadores de porta e de comutador?**  
    Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de chassi de comutador e de porta consistentes entre o aplicativo SNMP e o banco de dados de local. Se o aplicativo SNMP retornar um endereço IP de chassi ou uma ID de porta que não esteja incluída no banco de dados, o serviço de informações de local não poderá retornar um local ao cliente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

