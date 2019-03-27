---
title: Gerenciar locais para gateways ELIN no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: Decisões necessárias para planejar um banco de dados de informações de local ou um semelhante banco de dados externo, para uma implantação do E9-1-1 usando gateways ELIN, no Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 858493089c6c0e274a45616ea4b93a3fdf69e010
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894688"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Gerenciar locais para gateways ELIN no Skype para Business Server

Decisões necessárias para planejar um banco de dados de informações de local ou um semelhante banco de dados externo, para uma implantação do E9-1-1 usando gateways ELIN, no Skype para Business Server Enterprise Voice.

Para fazer com que o Skype para Business Server ofereça automaticamente locais para clientes dentro de uma rede, você precisa executar as seguintes tarefas:

- Preencher o banco de dados de serviço de informações de local com um wiremap de rede e inclua os números de identificação de local de emergência (ELINs) no campo CompanyName.

- Publique os locais para que estejam disponíveis para clientes em sua rede.

- Carregue os ELINs no banco de dados de Identificação de Localização Automática (ALI) da transportadora PSTN.

Para obter detalhes sobre como realizar estas tarefas, consulte [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) na documentação de Implantação.

> [!NOTE]
> Locais adicionados ao banco de dados local central não estão disponíveis para o cliente até que tenham sido publicadas usando um Skype para o comando do Shell de gerenciamento do servidor de negócios e são replicados para as lojas locais do pool. Para obter detalhes, consulte [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) na documentação Implantação.

Esta seção descreve coisas a considerar conforme você planeja atualizar e manter o banco de dados de localização.

## <a name="planning-emergency-locations"></a>Planejamento de locais de emergência

Quando você usa gateways ELIN, você popular o banco de dados de serviço de informações de local com o endereço residencial, um local específico dentro de um edifício e pelo menos um ELIN para cada localidade. Durante a fase de planejamento, é uma boa ideia decidir como deseja nomear os locais e como você deseja atribuir os ELINs.

### <a name="planning-location-names"></a>Planejamento dos nomes de local

O campo de **local** de serviço de informações de local, que contém o local específico dentro de um edifício, tem um tamanho máximo de 20 caracteres (incluindo espaços). Dentro deste comprimento limitado, tente incluir o seguinte:

- Um nome fácil de compreender que identifica o local do chamador 911 para ajudar a garantir que os respondedores da emergência encontrem o local específico rapidamente quando chegarem ao endereço civil. Este nome de local pode incluir um número de construção, número do piso, designador de asa, número da sala e assim por diante. Evite apelidos que são conhecidos apenas pelos funcionários, que pode fazer com que os respondedores de emergência vão para o local incorreto.

- Um identificador de local que ajuda os usuários a ver facilmente que seu cliente obteve o local correto. O Skype para o cliente de negócios concatena e exibe os campos de **local** e **cidade** descobertos em seu cabeçalho automaticamente. Uma boa prática é adicionar o endereço do edifício para cada identificador de localidade (por exemplo, "1º andar <street number>"). Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer edifício na cidade.

- Se o local for aproximado por ser determinado por um ponto de acesso sem fio, convém adicionar a palavra **[perto]** (por exemplo, "próximo ao 1º andar 1234").

### <a name="planning-elins"></a>Planejamento de ELINs

Após decidir como você deseja dividir o espaço da construção em locais, é necessário decidir quantos ELINs atribuir em cada local. Por exemplo, em uma construção de vários locais ou pisos, diferentes áreas na construção podem ser atribuídas com zonas de emergência diferentes. Geralmente, cada piso na construção é designado como um local. Cada local é atribuído com um ou mais ELINs, que são usados como números de chamada durante uma chamada de emergência. Entre em contato com sua transportadora PSTN para obter os números de telefone que você pode usar para ELINs. A tabela a seguir oferece um exemplo de locais para um endereço específico.

**Local de amostra e Atribuições de ELIN**

|**Área de construção**|**Local**|**ELIN**|
|:-----|:-----|:-----|
|Primeiro andar  <br/> |1  <br/> |425-555-0100  <br/> |
|Segundo andar  <br/> |2  <br/> |425-555-0111  <br/> |
|Terceiro andar  <br/> |3  <br/> |425-555-0123  <br/> |

Os locais definidos devem atender os seguintes requisitos:

- Cumpre os regulamentos locais e nacionais/regionais em termos de área máxima por local e número de locais por endereço.

- São específicos o suficiente para tornar fácil localizar o chamador de emergência.

## <a name="populating-the-location-database"></a>Preenchendo o banco de dados Local

As seguintes perguntas ajudarão a determinar como preencher o banco de dados de local.

 **Qual processo você usará para preencher o banco de dados de local?**

Onde estão os dados e quais etapas você precisa executar para convertê-los para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?

 **Você tem um banco de dados de terceiro que já contém um mapeamento de locais?**

Usando a opção de serviço de informações de localização secundário para se conectar a um banco de dados de terceiros, você pode agrupar e gerenciar locais usando uma plataforma offline. Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário. Isso significa que o serviço de informações de local pode retornar vários endereços, originário do serviço de informações de localização secundário, para um Skype para o cliente de negócios. Em seguida, o usuário pode escolher o local mais apropriado.

Para integrar com o serviço de informações de local, o banco de dados de terceiros deve seguir o Skype para esquema de solicitação/resposta do Business servidor local. Para obter detalhes, consulte o [Serviço Web para o protocolo de suporte do E911](https://go.microsoft.com/fwlink/p/?linkid=213819). Para obter detalhes sobre como implantar um serviço de informações de localização secundária, consulte [Configure um serviço de informações de localização secundário no Skype para Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) na documentação de implantação.

Para obter detalhes sobre como preencher o banco de dados de local, consulte [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) na documentação Implantação.

## <a name="maintaining-the-location-database"></a>Manutenção do banco de dados de local

Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede mudar. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.

 **Como você atualizará o banco de dados de local?**

Há diversos cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de WAPs (pontos de acesso sem fio), recabeamento do escritório (resultando em atribuições de comutação diferentes) e expansão da subrede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?

 **Você usará um aplicativo SNMP para corresponder Skype para endereços de MAC do cliente de negócios para a porta e opção identificadores?**

Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de porta e chassis de comutador consistentes entre o aplicativo SNMP e o banco de dados de local. Se o aplicativo SNMP retorna uma chassi IP endereço ou porta ID que não está incluída no banco de dados, o serviço de informações de local não poderão retornar uma localização para o cliente.


