---
title: Definir os elementos de rede usados para determinar o local no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Decisões necessárias para planejar quais componentes de rede você usará para mapear chamadores para locais para a implantação do E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: a68f1517d038f82e62a7aca3ef909e4e67d25e4e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276688"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definir os elementos de rede usados para determinar o local no Skype for Business Server
 
Decisões necessárias para planejar quais componentes de rede você usará para mapear chamadores para locais para a implantação do E9-1-1 no Skype for Business Server Enterprise Voice.
  
Se você estiver configurando sua infraestrutura do Skype for Business Server para dar suporte à detecção automática de localização de cliente, primeiro precisará decidir quais elementos de rede você vai usar para mapear os chamadores para locais. No Skype for Business Server, você pode associar os seguintes elementos de rede de camada 2 e camada 3 com locais:
  
- Endereços de BSSID (Identificação de Conjunto de Serviço Básico) do ponto de acesso sem fio (WAP) (Camada 2)
    
- Porta de comutador LLDP (Camada 2)
    
- IDs de chassi do comutador LLDP (Camada 2)
    
- Sub-redes IP (Camada 3)
    
- Endereços MAC do cliente (Camada 2)
    
Os elementos de rede estão listados em ordem de precedência. Se um cliente puder ser localizado usando mais de um elemento de rede, o Skype for Business Server usará a ordem de precedência para determinar qual mecanismo usar. 
  
As seções a seguir fornecem mais detalhes de uso de cada elemento da rede.
  
> [!IMPORTANT]
> Quando você usa elementos de rede para mapear os chamadores para locais, é de importância máxima que você mantenha atualizado o banco de dados do serviço de informações de localização. Por exemplo, se você adicionar ou alterar um elemento de rede (como adicionar um WAP), será necessário excluir a entrada antiga e adicionar a nova no banco de dados de local. 
  
## <a name="wireless-access-point"></a>Ponto de acesso sem fio

Quando um cliente se conecta à rede sem fio, a solicitação de local usa o endereço BSSID do WAP para determinar a sua localização. Se o cliente estiver em roaming, o WAP indicado pode não ser o mais próximo, e até mesmo pode pegar um WAP que está em um andar diferente do edifício. Para indicar que o local é aproximado, você pode colocar o valor de local com um descritor **[próximo]** ou **[fecharto]** .
  
Este método local supõe que o BSSID de cada WAP é estático. No entanto, se o seu fornecedor de WAP usar o BSSIDs atribuído dinamicamente, o BSSID obtido de um WAP pode mudar (isso pode acontecer após uma alteração de configuração de WAP), e os clientes sem fio podem ser deixados em uma situação em que eles não recebem um local. Para evitar essa possibilidade, você precisa preencher o banco de dados do serviço de informações de localização com o ERLs para todos os endereços BSSID possíveis usados por cada WAP. 
  
## <a name="lldp-ports-and-switches"></a>Comutadores e portas LLDP

Os comutadores Ethernet gerenciados que oferecem suporte ao protocolo LLDP-MED podem anunciar suas informações de identidade e a porta a clientes compatíveis com LLDP-MED, que podem ser consultados em relação ao banco de dados de local para fornecer o local do dispositivo. Você pode associar ERLs exclusivamente na identificação de chassi de comutador ou pode mapeá-los ao nível de porta.
  
> [!NOTE]
> O Skype for Business Server é compatível com o uso de LLDP-MED para a determinação de locais somente em dispositivos do Lync Phone Edition e clientes do Skype for Business executados no Windows 8. Se você precisar usar dados de camada 2 no nível da opção para determinar a localização de outros clientes do Skype for Business Server baseados em computador, será necessário usar o método de endereço MAC do cliente. 
  
## <a name="subnet"></a>Sub-rede

As sub-redes IP de camada 3 fornecem um mecanismo compatível com todos os clientes do Skype for Business Server que podem ser usados para detectar automaticamente a localização do cliente. O uso de sub-redes IP é o método de localização mais fácil de configurar e gerenciar os clientes com fio. Porém, antes de decidir usar as sub-redes, você deve usar as seguintes perguntas para ajudar a determinar se a especificidade do local da sub-rede é boa o suficiente para localizar com precisão um cliente:
  
- Uma ou mais sub-redes de cliente abrangem vários andares?
    
- Uma ou mais sub-redes abrangem mais de um edifício?
    
- Quanto espaço é coberto por cada sub-rede do cliente?
    
Se a sub-rede abrange uma área muito ampla, talvez seja necessário usar outro mecanismo para localizar clientes. No entanto, se for prático, recomendamos que os clientes reorganizem suas sub-redes IP para atender aos requisitos de especificidade de local ERL, em vez de assumir os custos e a complexidade de soluções de terceiros baseadas em SNMP.
  
## <a name="client-mac-address"></a>Endereço MAC do cliente

Para usar o endereço MAC de um computador cliente para localizar um chamador, você precisa de switches Ethernet gerenciados, e você deve implantar uma solução SNMP de terceiros que possa descobrir os endereços MAC dos clientes Skype for Business conectados a (ou até) essas opções. A solução SNMP continuamente controla os comutadores gerenciados para obter mapeamentos atuais dos endereços MAC de extremidade conectados a cada porta e obtém os IDs de porta correspondentes. Durante uma solicitação do cliente do Skype for Business para o serviço de informações de localização, o serviço de informações de localização consulta o aplicativo de terceiros usando o endereço MAC do cliente e, em seguida, retorna qualquer endereço IP de switch e IDs de porta correspondentes. O serviço de informações de localização usa essas informações para consultar seu Wiremap de camada 2 publicado para um registro correspondente e retorna o local para o cliente. Se você usar esta opção, verifique se os identificadores de porta do comutador são consistentes entre o aplicativo SNMP e os registros publicados do banco de dados de local.
  
> [!NOTE]
> Algumas soluções SNMP de terceiros podem dar suporte a switches de acesso não gerenciados; se a opção que atende ao cliente Skype for Business não for gerenciada, mas tiver um uplink para uma chave de distribuição gerenciada, a opção gerenciada poderá relatar de volta para o aplicativo SNMP os endereços MAC dos clientes conectados ao switch de acesso. Essas informações permitem que o serviço de informações de localização identifique o local do usuário. No entanto, só é possível atribuir um único ERL a todas as portas no comutador não gerenciado, para que a especificidade do local só esteja disponível a nível do chassi do comutador de acesso, não a nível de porta. 
  

