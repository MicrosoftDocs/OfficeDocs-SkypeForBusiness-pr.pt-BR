---
title: Gerenciar locais para gateways ELIN no Skype for Business Server
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
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: Decisões necessárias para o planejamento de um banco de dados de informações de local, ou um banco de dados externo semelhante, para uma implantação E9-1-1 usando gateways ELIN, no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 387b94ca59ef7750a80d06c88b371a0afef9313d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834391"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Gerenciar locais para gateways ELIN no Skype for Business Server

Decisões necessárias para o planejamento de um banco de dados de informações de local, ou um banco de dados externo semelhante, para uma implantação E9-1-1 usando gateways ELIN, no Skype for Business Server Enterprise Voice.

Para que o Skype for Business Server forneça automaticamente locais para clientes em uma rede, você precisa executar as seguintes tarefas:

- Preencha o banco de dados do serviço de Informações de Local com um mapa de rede e inclua os ELINs (Números de Identificação de Local de Emergência) no campo CompanyName.

- Publique as localizações, dessa forma, elas estarão disponíveis para os clientes da sua rede.

- Carregue os ELINs no banco de dados ali da sua operadora de rede telefônica pública comutado (PSTN).

Para obter detalhes sobre como executar essas tarefas, consulte [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) na Documentação de Implantação.

> [!NOTE]
> Os locais adicionados ao banco de dados de localização central não estarão disponíveis para o cliente até que tenham sido publicados usando um comando do Shell de Gerenciamento do Skype for Business Server e replicados para os armazenamentos locais do pool. Para obter detalhes, consulte [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) na Documentação da Implantação.

Essa seção descreve coisas a serem consideradas conforme você planeja atualizar e manter seu banco de dados de locais.

## <a name="planning-emergency-locations"></a>Planejando locais de emergência

Ao usar gateways ELIN, você preenche o banco de dados do serviço de Informações de Local com o endereço residencial, um local específico dentro de um edifício e pelo menos um ELIN para cada local. Durante a fase de planejamento, é uma boa ideia decidir como você deseja nomear as localizações e como deseja atribuir ELINs.

### <a name="planning-location-names"></a>Planejando nomes dos locais

O campo Local do **Serviço** de Informações de Local, que contém o local específico dentro de um edifício, tem um comprimento máximo de 20 caracteres (incluindo espaços). Dentro desse comprimento limitado, tente incluir o seguinte:

- Um nome fácil de entender que identifica o local do chamador 911 para ajudar a garantir que os respondentes de emergência encontrem o local específico imediatamente quando chegarem ao endereço cívico. Esse nome de local pode incluir um número de edifício, número do piso, designador de asa, número da sala e assim por diante. Evite apelidos conhecidos apenas por funcionários, o que pode fazer com que os respondentes de emergência acessem o local errado.

- Um identificador de local que ajuda os usuários a ver facilmente que seu cliente escolheu o local correto. O cliente Skype for Business concatena automaticamente e exibe os campos **Localização** e Cidade **descobertos** em seu header. Uma boa prática é adicionar o endereço do edifício a cada identificador de local (por exemplo, "1º <street number> andar"). Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer construção na cidade.

- Se o local for aproximado porque é determinado por um ponto de acesso sem fio, talvez você queira adicionar a palavra **[Near]** (por exemplo, "Próximo ao 1º andar, 1234").

### <a name="planning-elins"></a>Planejando ELINs

Depois de decidir como deseja dividir o espaço de construção em locais, você precisa decidir quantos ELINs atribuir a cada local. Por exemplo, em um edifício multifloor ou multi-intencional, áreas diferentes no edifício podem ser atribuídas a zonas de emergência diferentes. Normalmente, cada piso de um edifício é designado como um local. Cada local é atribuído a um ou mais ELINs, que são usados como número(s) de chamada durante uma chamada de emergência. Entre em contato com a sua operadora da PSTN para números de telefone que você possa com ELIs. A tabela a seguir fornece um exemplo de locais para um endereço específico.

**Localização de exemplo e atribuições de ELIN**

|**Área do edifício**|**Location**|**ELIN**|
|:-----|:-----|:-----|
|1º andar  <br/> |1   <br/> |425-555-0100  <br/> |
|2º andar  <br/> |2   <br/> |425-555-0111  <br/> |
|3º andar  <br/> |3   <br/> |425-555-0123  <br/> |

Os locais definidos devem atender aos seguintes requisitos:

- Estar em conformidade com os regulamentos locais e nacionais/regionais em termos de área máxima por local e número de locais por endereço.

- Sejam específicos o suficiente para tornar mais fácil localizar o chamador da emergância.

## <a name="populating-the-location-database"></a>Preenchimento do Banco de dados de locais

As perguntas a seguir ajudarão você a determinar como preencherá o banco de dados de localização.

 **Qual processo você usará para preencher o banco de dados de local?**

Onde os dados existem e quais etapas você precisa executar para converter os dados para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?

 **Você tem um banco de dados de terceiros que já contém um mapeamento de locais?**

Usando a opção de serviço Informações de Local Secundária para se conectar a um banco de dados de terceiros, você pode agrupar e gerenciar locais usando uma plataforma offline. Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário. Isso significa que o serviço de Informações de Local pode retornar vários endereços, provenientes do serviço informações de localização secundária, para um cliente do Skype for Business. Em seguida, o usuário pode escolher o local mais apropriado.

Para integrar-se ao serviço de Informações de Local, o banco de dados de terceiros deve seguir o esquema de Solicitação/Resposta de Local do Skype for Business Server. Para obter detalhes, [consulte Web Service for E911 Support Protocol](https://go.microsoft.com/fwlink/p/?linkid=213819). Para obter detalhes sobre como implantar um serviço de Informações de Local Secundário, consulte [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.

Para obter detalhes sobre como preencher o banco de dados de localização, [consulte Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.

## <a name="maintaining-the-location-database"></a>Manutenção do banco de dados Local

Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede muda. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.

 **Como você atualizará o banco de dados de local?**

Há diversos cenários que exigem uma atualização para o banco de dados de localização, incluindo a adição de WAPs (pontos de acesso sem fio), recabação do escritório (resultando em atribuições de comutadores diferentes) e expansão da sub-rede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?

 **Você usará um aplicativo SNMP para corresponder os endereços MAC do cliente Skype for Business aos identificadores de porta e de comutadores?**

Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de chassi de comutador e de porta consistentes entre o aplicativo SNMP e o banco de dados de local. Se o aplicativo SNMP retornar um endereço IP de chassi ou ID de porta que não está incluído no banco de dados, o serviço de Informações de Local não poderá retornar um local para o cliente.


