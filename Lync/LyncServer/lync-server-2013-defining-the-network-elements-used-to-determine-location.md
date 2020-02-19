---
title: 'Lync Server 2013: definindo os elementos de rede usados para determinar o local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adcd8b78d73ee5f15f893466183f36b2f2ecef32
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a>Definir os elementos de rede usados para determinar o local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-29_

Se você estiver configurando sua infraestrutura do Lync Server para oferecer suporte à detecção automática de local de cliente, primeiro será necessário decidir quais elementos de rede você usará para mapear chamadores para locais. No Lync Server 2013, você pode associar os seguintes elementos de rede de camada 2 e camada 3 com locais:

  - Endereços de BSSID (Identificação de Conjunto de Serviço Básico) do ponto de acesso sem fio (WAP) (Camada 2)

  - Porta de comutador LLDP (Camada 2)

  - IDs de chassi do comutador LLDP (Camada 2)

  - Sub-redes IP (Camada 3)

  - Endereços MAC do cliente (Camada 2)

Os elementos de rede estão listados em ordem de precedência. Se um cliente puder ser localizado usando mais de um elemento de rede, o Lync Server usará a ordem de precedência para determinar o mecanismo a ser usado.

As seções a seguir fornecem mais detalhes de uso de cada elemento da rede.

<div>


> [!IMPORTANT]  
> Quando você usa elementos de rede para mapear chamadores para locais, é da importância máxima em que você mantém atualizado o banco de dados do serviço de informações de local. Por exemplo, se você adicionar ou alterar um elemento de rede (como adicionar um WAP), será necessário excluir a entrada antiga e adicionar a nova no banco de dados de local.



</div>

<div>

## <a name="wireless-access-point"></a>Ponto de acesso sem fio

Quando um cliente se conecta à rede sem fio, a solicitação de local usa o endereço BSSID do WAP para determinar a sua localização. Se o cliente estiver em roaming, o WAP indicado pode não ser o mais próximo, e é até possível obter um WAP que esteja em outro andar do edifício. Para indicar que o local é aproximado, você pode colocar o valor do local com um descritor Near ou Close to.

Este método local supõe que o BSSID de cada WAP é estático. Entretanto, se o seu fornecedor WAP usa BSSIDs atribuídos dinamicamente, o BSSID obtido de um WAP poderia ser alterado (isso pode acontecer após a alteração de uma configuração WAP) e clientes sem fio podem ser deixados em uma situação onde não recebem um local. Para evitar essa possibilidade, você precisa preencher o banco de dados do serviço de informações de local com o ERLs para todos os endereços BSSID possíveis usados por cada WAP.

</div>

<div>

## <a name="lldp-ports-and-switches"></a>Comutadores e portas LLDP

Os comutadores Ethernet gerenciados que oferecem suporte ao protocolo LLDP-MED podem anunciar suas informações de identidade e a porta a clientes compatíveis com LLDP-MED, que podem ser consultados em relação ao banco de dados de local para fornecer o local do dispositivo. Você pode associar ERLs exclusivamente na identificação de chassi de comutador ou pode mapeá-los ao nível de porta.

<div>


> [!NOTE]  
> O Lync Server 2013 oferece suporte ao uso de LLDP-MED para determinar os locais apenas dos dispositivos do Lync Phone Edition e do Lync 2013 em execução no Windows 8. Se você precisar usar dados de camada 2 de nível de alternância para determinar o local de outros clientes Lync baseados em computador com fio, será necessário usar o método de endereço MAC do cliente.



</div>

</div>

<div>

## <a name="subnet"></a>-

As sub-redes IP de camada 3 fornecem um mecanismo suportado por todos os clientes do Lync Server que podem ser usados para detectar automaticamente o local do cliente. O uso de sub-redes IP é o método de localização mais fácil de configurar e gerenciar os clientes com fio. Porém, antes de decidir usar as sub-redes, você deve usar as seguintes perguntas para ajudar a determinar se a especificidade do local da sub-rede é boa o suficiente para localizar com precisão um cliente:

  - Uma ou mais sub-redes de cliente abrangem vários andares?

  - Uma ou mais sub-redes abrangem mais de um edifício?

  - Quanto espaço é coberto por cada sub-rede do cliente?

Se a sub-rede abrange uma área muito ampla, talvez seja necessário usar outro mecanismo para localizar clientes. No entanto, se for prático, recomendamos que os clientes reorganizem suas sub-redes IP para atender aos requisitos de especificidade de local ERL, em vez de assumir os custos e a complexidade de soluções de terceiros baseadas em SNMP.

</div>

<div>

## <a name="client-mac-address"></a>Endereço MAC do cliente

Para usar o endereço MAC do computador cliente para localizar um chamador, você precisa de comutadores Ethernet gerenciados e deve implantar uma solução SNMP de terceiros que possa descobrir os endereços MAC de clientes Lync conectados a (ou através de) esses comutadores. A solução SNMP continuamente controla os comutadores gerenciados para obter mapeamentos atuais dos endereços MAC de extremidade conectados a cada porta e obtém os IDs de porta correspondentes. Durante uma solicitação do cliente Lync para o serviço de informações de local, o serviço de informações de local consulta o aplicativo de terceiros usando o endereço MAC do cliente e, em seguida, retorna qualquer endereço IP de comutação correspondente e IDs de porta. O serviço de informações de local usa essas informações para consultar sua Wiremap da camada 2 publicada de um registro correspondente e retorna o local para o cliente. Se você usar esta opção, verifique se os identificadores de porta do comutador são consistentes entre o aplicativo SNMP e os registros publicados do banco de dados de local.

<div>


> [!NOTE]  
> Algumas soluções SNMP de terceiros podem oferecer suporte a comutadores de acesso não gerenciados; se a opção de atendimento ao cliente Lync não for gerenciada, mas tem um uplink a um comutador de distribuição gerenciado, o comutador gerenciado pode relatar os endereços MAC dos clientes conectados ao comutador de acesso ao aplicativo SNMP. Essas informações permitem que o serviço de informações de local identifique o local do usuário. No entanto, só é possível atribuir um único ERL a todas as portas no comutador não gerenciado, para que a especificidade do local só esteja disponível a nível do chassi do comutador de acesso, não a nível de porta.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

