---
title: Gerenciar locais para gateways ELIN em Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: Decisões necessárias para o planejamento de um banco de dados de informações de local ou um banco de dados externo semelhante para uma implantação do E9-1-1 usando gateways ELIN, em Skype for Business Server Enterprise Voice.
ms.openlocfilehash: ddc92645a39b007c3bb0d1e72e009ff1bf303b37
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404663"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Gerenciar locais para gateways ELIN em Skype for Business Server

Decisões necessárias para o planejamento de um banco de dados de informações de local ou um banco de dados externo semelhante para uma implantação do E9-1-1 usando gateways ELIN, em Skype for Business Server Enterprise Voice.

Para que Skype for Business Server locais para clientes em uma rede, você precisa executar as seguintes tarefas:

- Preencha o banco de dados do serviço informações de local com um mapa de rede e inclua os NÚMEROS de Identificação de Local de Emergência (ELINs) no campo CompanyName.

- Publique as localizações, dessa forma, elas estarão disponíveis para os clientes da sua rede.

- Upload os ELINs para o banco de dados ali da sua rede telefônica pública comutado (PSTN).

Para obter detalhes sobre como executar essas tarefas, consulte [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) na Documentação de Implantação.

> [!NOTE]
> Os locais adicionados ao banco de dados de localização central não estarão disponíveis para o cliente até que tenham sido publicados usando um comando Skype for Business Server Shell de Gerenciamento e sejam replicados para os armazenamentos locais do pool. Para obter detalhes, consulte [Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database) na Documentação da Implantação.

Essa seção descreve coisas a serem consideradas conforme você planeja atualizar e manter seu banco de dados de locais.

## <a name="planning-emergency-locations"></a>Planejando locais de emergência

Quando você usa gateways ELIN, preenche o banco de dados do serviço informações de localização com o endereço cívico, um local específico dentro de um edifício e pelo menos um ELIN para cada local . Durante a fase de planejamento, é uma boa ideia decidir como você deseja nomear as localizações e como deseja atribuir ELINs.

### <a name="planning-location-names"></a>Planejando nomes dos locais

O campo Local do  serviço de Informações de Localização, que contém o local específico dentro de um edifício, tem um comprimento máximo de 20 caracteres (incluindo espaços). Dentro desse comprimento limitado, tente incluir o seguinte:

- Um nome fácil de entender que identifica o local do chamador 911 para ajudar a garantir que os respondentes de emergência encontrem o local específico prontamente quando chegarem ao endereço cívico. Esse nome de local pode incluir um número de construção, um número de piso, um designador de asa, um número de sala e assim por diante. Evite apelidos conhecidos apenas pelos funcionários, o que pode fazer com que os respondentes de emergência acessem o local errado.

- Um identificador de local que ajuda os usuários a ver facilmente que seu cliente escolheu o local correto. O Skype for Business cliente automaticamente concatena e exibe os campos **Local** e **Cidade** descobertos em seu header. Uma boa prática é adicionar o endereço de rua do edifício a cada identificador de local (por exemplo, "1º Andar \<street number>"). Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer construção na cidade.

- Se o local for aproximado porque ele é determinado por um ponto de acesso sem fio, talvez você queira adicionar a palavra **[Near]** (por exemplo, "Próximo ao 1º Andar 1234").

### <a name="planning-elins"></a>Planejando ELINs

Depois de decidir como deseja dividir seu espaço de construção em locais, você precisa decidir quantos ELINs atribuir a cada local. Por exemplo, em um edifício multifloor ou multitenente, áreas diferentes no edifício podem ser atribuídas a zonas de emergência diferentes. Normalmente, cada andar em um edifício é designado como um local. Em seguida, cada local é atribuído a um ou mais ELINs, que são usados como os números de chamada durante uma chamada de emergência. Entre em contato com a sua operadora da PSTN para números de telefone que você possa com ELIs. A tabela a seguir fornece um exemplo de locais para um endereço de rua específico.

**Localização de Exemplo e Atribuições de ELIN**

|**Área do edifício**|**Localização**|**ELIN**|
|:-----|:-----|:-----|
|1º andar  <br/> |1  <br/> |425-555-0100  <br/> |
|2º andar  <br/> |2  <br/> |425-555-0111  <br/> |
|3º andar  <br/> |3  <br/> |425-555-0123  <br/> |

Os locais definidos devem atender aos seguintes requisitos:

- Cumpra os regulamentos locais e nacionais/regionais em termos de área máxima por local e número de locais por endereço de rua.

- Sejam específicos o suficiente para tornar mais fácil localizar o chamador da emergância.

## <a name="populating-the-location-database"></a>Preenchimento do Banco de dados de locais

As perguntas a seguir ajudarão você a determinar como preencher o banco de dados de localização.

 **Qual processo você usará para preencher o banco de dados de local?**

Onde os dados existem e quais etapas você precisa executar para converter os dados para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?

 **Você tem um banco de dados de terceiros que já contém um mapeamento de locais?**

Usando a opção serviço Informações de Local Secundário para se conectar a um banco de dados de terceiros, você pode agrupar e gerenciar locais usando uma plataforma offline. Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário. Isso significa que o serviço informações de local pode retornar vários endereços, provenientes do serviço Informações de Localização Secundária, para um cliente Skype for Business local. Em seguida, o usuário pode escolher o local mais apropriado.

Para integrar-se ao serviço informações de local, o banco de dados de terceiros deve seguir o esquema de solicitação/resposta Skype for Business Server local. Para obter detalhes, [consulte Web Service for E911 Support Protocol](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd). Para obter detalhes sobre como implantar um serviço de Informações de Localização Secundária, consulte [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) na documentação implantação.

Para obter detalhes sobre como preencher o banco de dados de localização, consulte [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) na documentação de Implantação.

## <a name="maintaining-the-location-database"></a>Manutenção do banco de dados Local

Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede muda. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.

 **Como você atualizará o banco de dados de local?**

Há vários cenários que exigem uma atualização para o banco de dados de localização, incluindo a adição de waps (pontos de acesso sem fio), recorrência do office (resultando em atribuições de comutadores diferentes) e expansão de sub-rede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?

 **Você usará um aplicativo SNMP para corresponder Skype for Business mac cliente a identificadores de porta e de opção?**

Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de chassi de comutador e de porta consistentes entre o aplicativo SNMP e o banco de dados de local. Se o aplicativo SNMP retornar um endereço IP de chassi ou uma ID de porta que não está incluído no banco de dados, o serviço de Informações de Local não poderá retornar um local para o cliente.