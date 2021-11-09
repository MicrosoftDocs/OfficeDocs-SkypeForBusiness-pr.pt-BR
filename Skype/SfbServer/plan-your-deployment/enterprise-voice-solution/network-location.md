---
title: Definir os elementos de rede usados para determinar o local no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Decisões necessárias para o planejamento de quais componentes de rede você usará para mapear chamadores para locais para implantação do E9-1-1 em Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 6de3d960dd68dfc0f34ce0e67fef569c36e44612
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861108"
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server"></a>Definir os elementos de rede usados para determinar o local no Skype for Business Server
 
Decisões necessárias para o planejamento de quais componentes de rede você usará para mapear chamadores para locais para implantação do E9-1-1 em Skype for Business Server Enterprise Voice.
  
Se você estiver configurando sua infraestrutura de Skype for Business Server para dar suporte à detecção automática de localização do cliente, primeiro você precisará decidir quais elementos de rede você usará para mapear os chamadores para locais. Em Skype for Business Server, você pode associar os seguintes elementos de rede da Camada 2 e da Camada 3 a locais:
  
- Endereços de BSSID (Identificação de Conjunto de Serviço Básico) do ponto de acesso sem fio (WAP) (Camada 2)
    
- Porta de comutador LLDP (Camada 2)
    
- IDs de chassi do comutador LLDP (Camada 2)
    
- Sub-redes IP (Camada 3)
    
- Endereços MAC do cliente (Camada 2)
    
Os elementos de rede estão listados em ordem de precedência. Se um cliente pode ser localizado usando mais de um elemento de rede, Skype for Business Server usa a ordem de precedência para determinar qual mecanismo usar. 
  
As seções a seguir fornecem mais detalhes de uso de cada elemento da rede.
  
> [!IMPORTANT]
> Quando você usa elementos de rede para mapear chamadores para locais, é de extrema importância que você mantenha o banco de dados de serviço de Informações de Local atualizado. Por exemplo, se você adicionar ou alterar um elemento de rede (como adicionar um WAP), será necessário excluir a entrada antiga e adicionar a nova no banco de dados de local. 
  
## <a name="wireless-access-point"></a>Ponto de acesso sem fio

Quando um cliente se conecta à rede sem fio, a solicitação de local usa o endereço BSSID do WAP para determinar a sua localização. Se o cliente estiver em roaming, o WAP indicado pode não ser o mais próximo, e até mesmo é possível escolher um WAP que está em um piso diferente do edifício. Para indicar que o local é aproximado, você pode pré-anexar o valor de local com um descritor **[Near]** ou **[Closeto].**
  
Este método local supõe que o BSSID de cada WAP é estático. No entanto, se o fornecedor WAP usar BSSIDs atribuídos dinamicamente, o BSSID obtido de um WAP poderá mudar (isso pode acontecer após uma alteração de configuração WAP) e os clientes sem fio poderão ser deixados em uma situação em que eles não recebem um local. Para evitar essa possibilidade, você precisa preencher o banco de dados de serviço de Informações de Local com ERLs para todos os endereços BSSID possíveis usados por cada WAP. 
  
## <a name="lldp-ports-and-switches"></a>Comutadores e portas LLDP

Os comutadores Ethernet gerenciados que oferecem suporte ao protocolo LLDP-MED podem anunciar suas informações de identidade e a porta a clientes compatíveis com LLDP-MED, que podem ser consultados em relação ao banco de dados de local para fornecer o local do dispositivo. Você pode associar ERLs exclusivamente na identificação de chassi de comutador ou pode mapeá-los ao nível de porta.
  
> [!NOTE]
> Skype for Business Server suporte ao uso de LLDP-MED para determinar locais apenas de dispositivos Lync Telefone Edition e clientes Skype for Business em execução em Windows 8. Se você precisar usar dados da Camada 2 no nível de opção para determinar a localização de outros clientes baseados em computador Skype for Business Server com fio, você precisará usar o método de endereço MAC do cliente. 
  
## <a name="subnet"></a>Sub-rede

As sub-redes IP da Camada 3 fornecem um mecanismo suportado por todos os clientes Skype for Business Server que podem ser usados para detectar automaticamente a localização do cliente. O uso de sub-redes IP é o método de localização mais fácil de configurar e gerenciar os clientes com fio. Porém, antes de decidir usar as sub-redes, você deve usar as seguintes perguntas para ajudar a determinar se a especificidade do local da sub-rede é boa o suficiente para localizar com precisão um cliente:
  
- Uma ou mais sub-redes de cliente abrangem vários andares?
    
- Uma ou mais sub-redes abrangem mais de um edifício?
    
- Quanto espaço é coberto por cada sub-rede do cliente?
    
Se a sub-rede abrange uma área muito ampla, talvez seja necessário usar outro mecanismo para localizar clientes. No entanto, se for prático, recomendamos que os clientes reorganizem suas sub-redes IP para atender aos requisitos de especificidade de local ERL, em vez de assumir os custos e a complexidade de soluções de terceiros baseadas em SNMP.
  
## <a name="client-mac-address"></a>Endereço MAC do cliente

Para usar o endereço MAC de um computador cliente para localizar um chamador, você precisa de comutadores Ethernet gerenciados e deve implantar uma solução SNMP de terceiros que possa descobrir os endereços MAC de clientes Skype for Business conectados a (ou por meio) dessas opções. A solução SNMP continuamente controla os comutadores gerenciados para obter mapeamentos atuais dos endereços MAC de extremidade conectados a cada porta e obtém os IDs de porta correspondentes. Durante a solicitação de um cliente Skype for Business para o serviço Informações de Local, o serviço Informações de Local consulta o aplicativo de terceiros usando o endereço MAC do cliente e retorna quaisquer endereços IP de comudores correspondentes e IDs de porta. O serviço de Informações de Localização usa essas informações para consultar seu mapa publicado da Camada 2 para um registro correspondente e retorna o local para o cliente. Se você usar esta opção, verifique se os identificadores de porta do comutador são consistentes entre o aplicativo SNMP e os registros publicados do banco de dados de local.
  
> [!NOTE]
> Algumas soluções SNMP de terceiros podem dar suporte a comutadores de acesso não autorizados; se a opção que atende o cliente Skype for Business for não gerenciada, mas tiver um uplink para uma opção de distribuição gerenciada, a opção gerenciada poderá relatar ao aplicativo SNMP os endereços MAC dos clientes conectados à opção de acesso. Essas informações permitem que o serviço informações de local identifique o local do usuário. No entanto, só é possível atribuir um único ERL a todas as portas no comutador não gerenciado, para que a especificidade do local só esteja disponível a nível do chassi do comutador de acesso, não a nível de porta. 
  

