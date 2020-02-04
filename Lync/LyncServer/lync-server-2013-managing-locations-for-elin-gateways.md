---
title: 'Lync Server 2013: gerenciar locais para gateways ELIN'
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
ms.openlocfilehash: ba5a7e9067e4cd59ca42e60c620dbb4e8ee5b901
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a>Gerenciando locais para gateways do ELIN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

Para que o Lync Server forneça automaticamente locais para clientes em uma rede, você precisa executar as seguintes tarefas:

  - Preencha o banco de dados do serviço de informações de localização com uma rede Wiremap e inclua os números de identificação de localização de emergência (ELINs) no campo CompanyName.

  - Publique os locais para que estejam disponíveis para clientes em sua rede.

  - Carregue os ELINs no banco de dados de Identificação de Localização Automática (ALI) da transportadora PSTN.

Para obter detalhes sobre como executar essas tarefas, consulte [Configurar o banco de dados de localização no Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.

<div>


> [!NOTE]  
> Os locais adicionados ao banco de dados do local central não estarão disponíveis para o cliente até serem publicados usando um comando shell do Shell de gerenciamento do Lync Server e serão duplicados para os armazenamentos locais do pool. Para obter detalhes, consulte <A href="lync-server-2013-publish-the-location-database.md">publicar o banco de dados de local do Lync Server 2013</A> na documentação de implantação.



</div>

Esta seção descreve coisas a considerar conforme você planeja atualizar e manter o banco de dados de localização.

<div>

## <a name="planning-emergency-locations"></a>Planejamento de locais de emergência

Ao usar gateways do ELIN, você preenche o banco de dados do serviço de informações de localização com o endereço cívico, um local específico dentro de um edifício e pelo menos um ELIN para cada local. Durante a fase de planejamento, é uma boa ideia decidir como deseja nomear os locais e como você deseja atribuir os ELINs.

<div>

## <a name="planning-location-names"></a>Planejamento dos nomes de local

O campo **local** do serviço de informações de localização, que contém o local específico dentro de um edifício, tem um comprimento máximo de 20 caracteres (incluindo espaços). Dentro deste comprimento limitado, tente incluir o seguinte:

  - Um nome fácil de compreender que identifica o local do chamador 911 para ajudar a garantir que os respondedores da emergência encontrem o local específico rapidamente quando chegarem ao endereço civil. Este nome de local pode incluir um número de construção, número do piso, designador de asa, número da sala e assim por diante. Evite apelidos que são conhecidos apenas pelos funcionários, que pode fazer com que os respondedores de emergência vão para o local incorreto.

  - Um identificador de localização que ajuda os usuários a ver facilmente que o cliente do Lync selecionou o local correto. O cliente Lync concatena e exibe automaticamente os campos **local** e **cidade** descobertos no cabeçalho. Uma prática recomendada é adicionar o endereço do edifício a cada identificador de localização (por exemplo, "número \<\>do 1ª andar"). Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer edifício na cidade.

  - Se o local for aproximado por ser determinado por um ponto de acesso sem fio, convém adicionar a palavra  Near (por exemplo, próximo ao 1º andar, 1234).

</div>

<div>

## <a name="planning-elins"></a>Planejamento de ELINs

Após decidir como você deseja dividir o espaço da construção em locais, é necessário decidir quantos ELINs atribuir em cada local. Por exemplo, em uma construção de vários locais ou pisos, diferentes áreas na construção podem ser atribuídas com zonas de emergência diferentes. Geralmente, cada piso na construção é designado como um local. Cada local é atribuído com um ou mais ELINs, que são usados como números de chamada durante uma chamada de emergência. Entre em contato com sua transportadora PSTN para obter os números de telefone que você pode usar para ELINs. A tabela a seguir oferece um exemplo de locais para um endereço específico.

### <a name="sample-location-and-elin-assignments"></a>Local de amostra e Atribuições de ELIN

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Área de construção</th>
<th>Local</th>
<th>ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Primeiro andar</p></td>
<td><p>1</p></td>
<td><p>425-555-0100</p></td>
</tr>
<tr class="even">
<td><p>Segundo andar</p></td>
<td><p>2</p></td>
<td><p>425-555-0111</p></td>
</tr>
<tr class="odd">
<td><p>Terceiro andar</p></td>
<td><p>3</p></td>
<td><p>425-555-0123</p></td>
</tr>
</tbody>
</table>


Os locais definidos devem atender os seguintes requisitos:

  - Cumpre os regulamentos locais e nacionais/regionais em termos de área máxima por local e número de locais por endereço.

  - São específicos o suficiente para tornar fácil localizar o chamador de emergência.

</div>

</div>

<div>

## <a name="populating-the-location-database"></a>Preenchendo o banco de dados Local

As seguintes perguntas ajudarão a determinar como preencher o banco de dados de local.

  - **Qual processo você usará para preencher o banco de dados de local?**  
    Onde estão os dados e quais etapas você precisa executar para convertê-los para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?

<!-- end list -->

  - **Você tem um banco de dados de terceiro que já contém um mapeamento de locais?**  
    Ao usar a opção do serviço de informações de localização secundária do Lync Server para se conectar a um banco de dados de terceiros, você pode agrupar e gerenciar locais usando uma plataforma offline. Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário. Isso significa que o serviço de informações de localização pode retornar vários endereços, originários do serviço de informações de localização secundário, para um cliente do Lync Server. Em seguida, o usuário pode escolher o local mais apropriado.
    
    Para integrar-se com o serviço informações de localização, o banco de dados de terceiros deve seguir o esquema de solicitação/resposta de localização do Lync Server. Para obter detalhes, <http://go.microsoft.com/fwlink/p/?linkid=213819>consulte. Para obter detalhes sobre a implantação de um serviço de informações de localização secundário, consulte [configurar um serviço de informações de localização secundário no Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) na documentação de implantação.

Para obter detalhes sobre como preencher o banco de dados de localização, consulte [Configurar o banco de dados de localização no Lync Server 2013](lync-server-2013-configure-the-location-database.md) na documentação de implantação.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Manutenção do banco de dados de local

Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede mudar. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.

  - **Como você atualizará o banco de dados de local?**  
    Há diversos cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de WAPs (pontos de acesso sem fio), recabeamento do escritório (resultando em atribuições de comutação diferentes) e expansão da subrede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?

<!-- end list -->

  - **Você usará um aplicativo SNMP para que os endereços do MAC do cliente do Skype sejam compatíveis aos identificadores de porta e de comutador?**  
    Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de porta e chassis de comutador consistentes entre o aplicativo SNMP e o banco de dados de local. Se o aplicativo SNMP retornar um endereço IP de chassi ou uma ID de porta que não está incluída no banco de dados, o serviço de informações de localização não poderá retornar um local ao cliente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

