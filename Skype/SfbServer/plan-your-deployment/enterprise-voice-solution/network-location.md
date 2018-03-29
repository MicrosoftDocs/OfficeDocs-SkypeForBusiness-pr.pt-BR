---
title: Definir os elementos de rede usados para determinar o local no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
description: Decisões necessárias para planejar quais componentes de rede que você usará para mapear os chamadores para locais para a implantação do E9-1-1 em Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 2d371b2abfd8e3c871f0d9f49409d2b8169268c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="define-the-network-elements-used-to-determine-location-in-skype-for-business-server-2015"></a>Definir os elementos de rede usados para determinar o local no Skype for Business Server 2015
 
Decisões necessárias para planejar quais componentes de rede que você usará para mapear os chamadores para locais para a implantação do E9-1-1 em Skype for Business Server Enterprise Voice.
  
Se você estiver configurando o Skype sua infra-estrutura de servidor de negócios para dar suporte a detecção automática do cliente local, você precisará primeiro decidir qual rede elementos você pretende usar para mapear os chamadores para locais. No Skype para Business Server, você pode associar os seguintes elementos de rede de camada 2 e camada 3 locais:
  
- Endereços de BSSID (Identificação de Conjunto de Serviço Básico) do ponto de acesso sem fio (WAP) (Camada 2)
    
- Porta de comutador LLDP (Camada 2)
    
- IDs de chassi do comutador LLDP (Camada 2)
    
- Sub-redes IP (Camada 3)
    
- Endereços MAC do cliente (Camada 2)
    
Os elementos de rede estão listados em ordem de precedência. Se um cliente pode estar localizado usando mais de um elemento da rede, Skype para Business Server usa a ordem de precedência para determinar qual mecanismo de usar. 
  
As seções a seguir fornecem mais detalhes de uso de cada elemento da rede.
  
> [!IMPORTANT]
> Quando você usa os elementos de rede para mapear os chamadores para locais, é tem importância que você mantenha o banco de dados de serviço de informações de local atualizadas. Por exemplo, se você adicionar ou alterar um elemento de rede (como adicionar um WAP), será necessário excluir a entrada antiga e adicionar a nova no banco de dados de local. 
  
## <a name="wireless-access-point"></a>Ponto de acesso sem fio

Quando um cliente se conecta à rede sem fio, a solicitação de local usa o endereço BSSID do WAP para determinar a sua localização. Se o cliente estiver em roaming, WAP indicado talvez não estejam mais próximos aquele e também é possível pegar um WAP que está em outro andar do edifício. Para indicar que o local for aproximado, o valor de local com um descritor **[perto]** ou **[fechar]** pode ser anexado.
  
Este método local supõe que o BSSID de cada WAP é estático. No entanto, se o seu fornecedor WAP usa BSSIDs dinamicamente atribuída, o BSSID obtidas de um WAP poderia alterar (esse pode acontecer após uma alteração de configuração do WAP) e clientes sem fio poderia ser deixados em uma situação na qual eles não receberem um local. Para evitar essa possibilidade, você precisará preencher dados de serviço do informações de local com ERLs para todos os endereços BSSID possíveis usado por cada WAP. 
  
## <a name="lldp-ports-and-switches"></a>Comutadores e portas LLDP

Os comutadores Ethernet gerenciados que oferecem suporte ao protocolo LLDP-MED podem anunciar suas informações de identidade e a porta a clientes compatíveis com LLDP-MED, que podem ser consultados em relação ao banco de dados de local para fornecer o local do dispositivo. Você pode associar ERLs exclusivamente na identificação de chassi de comutador ou pode mapeá-los ao nível de porta.
  
> [!NOTE]
> Skype para Business Server suporta o uso LLDP-MED para a determinação dos locais somente dos dispositivos Lync Phone Edition e Skype para clientes corporativos em execução no Windows 8. Se você precisar usar os dados de camada 2 de comutador nível para determinar o local dos outro Skype de baseadas em PC com fio para clientes Business Server, você precisará usar o método de endereço MAC do cliente. 
  
## <a name="subnet"></a>Sub-rede

Subredes IP camada 3 fornecem um mecanismo com suporte Skype todos os clientes de Business Server que pode ser usado para detectar automaticamente a localização do cliente. O uso de sub-redes IP é o método de localização mais fácil de configurar e gerenciar os clientes com fio. Porém, antes de decidir usar as sub-redes, você deve usar as seguintes perguntas para ajudar a determinar se a especificidade do local da sub-rede é boa o suficiente para localizar com precisão um cliente:
  
- Uma ou mais sub-redes de cliente abrangem vários andares?
    
- Uma ou mais sub-redes abrangem mais de um edifício?
    
- Quanto espaço é coberto por cada sub-rede do cliente?
    
Se a sub-rede abrange uma área muito ampla, talvez seja necessário usar outro mecanismo para localizar clientes. No entanto, se for prático, recomendamos que os clientes reorganizem suas sub-redes IP para atender aos requisitos de especificidade de local ERL, em vez de assumir os custos e a complexidade de soluções de terceiros baseadas em SNMP.
  
## <a name="client-mac-address"></a>Endereço MAC do cliente

Para usar o endereço MAC do cliente de um computador para localizar um chamador, você precisa comutadores de Ethernet gerenciados e você deve implantar uma solução SNMP de terceiros que pode descobrir os endereços MAC do Skype para clientes corporativos conectados à (ou por meio de) desses comutadores. A solução SNMP continuamente controla os comutadores gerenciados para obter mapeamentos atuais dos endereços MAC de extremidade conectados a cada porta e obtém os IDs de porta correspondentes. Durante um Skype para a solicitação do cliente de negócios para o serviço de informações de local, o serviço de informações de local consulta o aplicativo de terceiros usando o endereço MAC do cliente e, em seguida, retorna quaisquer endereços IP de opção correspondentes e IDs de porta. O serviço de informações de local usa essas informações para consultar seu wiremap de camada 2 publicado para um registro correspondente e retorna o local para o cliente. Se você usar esta opção, verifique se os identificadores de porta do comutador são consistentes entre o aplicativo SNMP e os registros publicados do banco de dados de local.
  
> [!NOTE]
> Algumas soluções de terceiros SNMP podem oferecer suporte a acesso não gerenciado switches; Se a opção que os serviços do Skype para o cliente de negócios é gerenciada, mas tiver uma conexão a um comutador de distribuição gerenciada, a opção gerenciada possível denunciar volta para o aplicativo SNMP os endereços MAC dos clientes conectados ao comutador acesso. Essas informações habilita o serviço de informações de local identificar o local do usuário. No entanto, só é possível atribuir um único ERL a todas as portas no comutador não gerenciado, para que a especificidade do local só esteja disponível a nível do chassi do comutador de acesso, não a nível de porta. 
  

