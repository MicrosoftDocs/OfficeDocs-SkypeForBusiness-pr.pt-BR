---
title: Definir os elementos de rede usados para determinar a localização no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Decisões necessárias para o planejamento de quais componentes de rede você usará para mapear chamadores para locais para implantação do E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 473ef9efc8598b303d6c7a05b902d57e0ad8ffd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813631"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definir os elementos de rede usados para determinar a localização no Skype for Business Server
 
Decisões necessárias para o planejamento de quais componentes de rede você usará para mapear chamadores para locais para implantação do E9-1-1 no Skype for Business Server Enterprise Voice.
  
Se você estiver configurando sua infraestrutura do Skype for Business Server para dar suporte à detecção automática de localização do cliente, primeiro você precisa decidir quais elementos de rede você usará para mapear chamadores para locais. No Skype for Business Server, você pode associar os seguintes elementos de rede de Camada 2 e Camada 3 a locais:
  
- Endereços de BSSID (Identificação de Conjunto de Serviço Básico) do ponto de acesso sem fio (WAP) (Camada 2)
    
- Porta de comutador LLDP (Camada 2)
    
- IDs de chassi do comutador LLDP (Camada 2)
    
- Sub-redes IP (Camada 3)
    
- Endereços MAC do cliente (Camada 2)
    
Os elementos de rede estão listados em ordem de precedência. Se um cliente puder ser localizado usando mais de um elemento de rede, o Skype for Business Server usará a ordem de precedência para determinar qual mecanismo usar. 
  
As seções a seguir fornecem mais detalhes de uso de cada elemento da rede.
  
> [!IMPORTANT]
> Quando você usa elementos de rede para mapear chamadores para locais, é extremamente importante manter o banco de dados do serviço de Informações de Local atualizado. Por exemplo, se você adicionar ou alterar um elemento de rede (como adicionar um WAP), será necessário excluir a entrada antiga e adicionar a nova no banco de dados de local. 
  
## <a name="wireless-access-point"></a>Ponto de acesso sem fio

Quando um cliente se conecta à rede sem fio, a solicitação de local usa o endereço BSSID do WAP para determinar a sua localização. Se o cliente estiver em roaming, o WAP indicado pode não ser o mais próximo, e até mesmo é possível pegar um WAP que está em um andar diferente do edifício. Para indicar que o local é aproximado, você pode anexar o valor do local com um descritor **[Near]** ou **[Closeto].**
  
Este método local supõe que o BSSID de cada WAP é estático. No entanto, se o fornecedor wap usa BSSIDs atribuídos dinamicamente, a BSSID obtida de um WAP pode mudar (isso pode acontecer após uma alteração de configuração WAP) e clientes sem fio podem ser deixados em uma situação em que não recebem um local. Para evitar essa possibilidade, você precisa preencher o banco de dados do serviço de Informações de Local com ERLs para todos os endereços BSSID possíveis usados por cada WAP. 
  
## <a name="lldp-ports-and-switches"></a>Comutadores e portas LLDP

Os comutadores Ethernet gerenciados que oferecem suporte ao protocolo LLDP-MED podem anunciar suas informações de identidade e a porta a clientes compatíveis com LLDP-MED, que podem ser consultados em relação ao banco de dados de local para fornecer o local do dispositivo. Você pode associar ERLs exclusivamente na identificação de chassi de comutador ou pode mapeá-los ao nível de porta.
  
> [!NOTE]
> O Skype for Business Server dá suporte ao uso de LLDP-MED para determinar locais apenas de dispositivos Lync Phone Edition e clientes do Skype for Business em execução no Windows 8. Se você precisar usar dados de Camada 2 de nível de opção para determinar o local de outros clientes do Skype for Business Server baseados em computador com fio, será necessário usar o método de endereço MAC do cliente. 
  
## <a name="subnet"></a>Sub-rede

As sub-redes IP da Camada 3 fornecem um mecanismo suportado por todos os clientes do Skype for Business Server que podem ser usados para detectar automaticamente o local do cliente. O uso de sub-redes IP é o método de localização mais fácil de configurar e gerenciar os clientes com fio. Porém, antes de decidir usar as sub-redes, você deve usar as seguintes perguntas para ajudar a determinar se a especificidade do local da sub-rede é boa o suficiente para localizar com precisão um cliente:
  
- Uma ou mais sub-redes de cliente abrangem vários andares?
    
- Uma ou mais sub-redes abrangem mais de um edifício?
    
- Quanto espaço é coberto por cada sub-rede do cliente?
    
Se a sub-rede abrange uma área muito ampla, talvez seja necessário usar outro mecanismo para localizar clientes. No entanto, se for prático, recomendamos que os clientes reorganizem suas sub-redes IP para atender aos requisitos de especificidade de local ERL, em vez de assumir os custos e a complexidade de soluções de terceiros baseadas em SNMP.
  
## <a name="client-mac-address"></a>Endereço MAC do cliente

Para usar o endereço MAC de um computador cliente para localizar um chamador, você precisa de comutadores Ethernet gerenciados e deve implantar uma solução SNMP de terceiros que possa descobrir os endereços MAC de clientes do Skype for Business conectados a (ou por meio) dessas opções. A solução SNMP continuamente controla os comutadores gerenciados para obter mapeamentos atuais dos endereços MAC de extremidade conectados a cada porta e obtém os IDs de porta correspondentes. Durante a solicitação de um cliente do Skype for Business para o serviço de Informações de Local, o serviço de Informações de Local consulta o aplicativo de terceiros usando o endereço MAC do cliente e retorna os endereços IP e as IDs de porta correspondentes. O serviço de Informações de Local usa essas informações para consultar seu mapa de grafado de Camada 2 publicado para um registro correspondente e retorna o local para o cliente. Se você usar esta opção, verifique se os identificadores de porta do comutador são consistentes entre o aplicativo SNMP e os registros publicados do banco de dados de local.
  
> [!NOTE]
> Algumas soluções SNMP de terceiros podem dar suporte a comutadores de acesso não autorizados; se a opção que atende o cliente Skype for Business não for gerenciada, mas tiver um uplink para um comutador de distribuição gerenciado, o comutador gerenciado poderá relatar de volta ao aplicativo SNMP os endereços MAC dos clientes conectados ao comutador de acesso. Essas informações permitem que o serviço de Informações de Local identifique o local do usuário. No entanto, só é possível atribuir um único ERL a todas as portas no comutador não gerenciado, para que a especificidade do local só esteja disponível a nível do chassi do comutador de acesso, não a nível de porta. 
  

