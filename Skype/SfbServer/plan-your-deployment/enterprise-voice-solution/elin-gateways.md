---
title: Gerenciar locais para gateways do ELIN no Skype for Business Server
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
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: Decisões necessárias para planejar um banco de dados de informações de localização ou um banco de dados externo semelhante para uma implantação do E9-1-1 usando gateways do ELIN, no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: e1645be8ed1c6188d1976d794727d0668b79c12e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276926"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Gerenciar locais para gateways do ELIN no Skype for Business Server

Decisões necessárias para planejar um banco de dados de informações de localização ou um banco de dados externo semelhante para uma implantação do E9-1-1 usando gateways do ELIN, no Skype for Business Server Enterprise Voice.

Para que o Skype for Business Server forneça automaticamente locais para clientes em uma rede, você precisa executar as seguintes tarefas:

- Preencha o banco de dados do serviço de informações de localização com uma rede Wiremap e inclua os números de identificação de localização de emergência (ELINs) no campo CompanyName.

- Publique os locais para que estejam disponíveis para clientes em sua rede.

- Carregue os ELINs no banco de dados de Identificação de Localização Automática (ALI) da transportadora PSTN.

Para obter detalhes sobre como realizar estas tarefas, consulte [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) na documentação de Implantação.

> [!NOTE]
> Os locais adicionados ao banco de dados de localização central não estarão disponíveis para o cliente até serem publicados usando um comando shell do Shell de gerenciamento do Skype for Business Server e serão replicados nas lojas locais do pool. Para obter detalhes, consulte [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) na documentação Implantação.

Esta seção descreve coisas a considerar conforme você planeja atualizar e manter o banco de dados de localização.

## <a name="planning-emergency-locations"></a>Planejamento de locais de emergência

Ao usar gateways do ELIN, você preenche o banco de dados do serviço de informações de localização com o endereço cívico, um local específico dentro de um edifício e pelo menos um ELIN para cada local. Durante a fase de planejamento, é uma boa ideia decidir como deseja nomear os locais e como você deseja atribuir os ELINs.

### <a name="planning-location-names"></a>Planejamento dos nomes de local

O campo **local** do serviço de informações de localização, que contém o local específico dentro de um edifício, tem um comprimento máximo de 20 caracteres (incluindo espaços). Dentro deste comprimento limitado, tente incluir o seguinte:

- Um nome fácil de compreender que identifica o local do chamador 911 para ajudar a garantir que os respondedores da emergência encontrem o local específico rapidamente quando chegarem ao endereço civil. Este nome de local pode incluir um número de construção, número do piso, designador de asa, número da sala e assim por diante. Evite apelidos que são conhecidos apenas pelos funcionários, que pode fazer com que os respondedores de emergência vão para o local incorreto.

- Um identificador de local que ajuda os usuários a ver facilmente que seu cliente obteve o local correto. O cliente Skype for Business concatena e exibe automaticamente os campos **local** e **cidade** descobertos no cabeçalho. Uma prática recomendada é adicionar o endereço do edifício a cada identificador de localização (por exemplo, "primeiro andar <street number>"). Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer edifício na cidade.

- Se a localização for aproximada, pois é determinada por um ponto de acesso sem fio, talvez você queira adicionar a palavra **[Near]** (por exemplo, "próximo do 1º andar 1234").

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

Usando a opção do serviço de informações de localização secundária para se conectar a um banco de dados de terceiros, você pode agrupar e gerenciar locais usando uma plataforma offline. Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário. Isso significa que o serviço de informações de localização pode retornar vários endereços, originários do serviço de informações de localização secundário, para um cliente Skype for Business. Em seguida, o usuário pode escolher o local mais apropriado.

Para integrar-se com o serviço informações de localização, o banco de dados de terceiros deve seguir o esquema de solicitação/resposta do local do Skype for Business Server. Para obter detalhes, consulte [protocolo de suporte do serviço Web para E911](https://go.microsoft.com/fwlink/p/?linkid=213819). Para obter detalhes sobre a implantação de um serviço de informações de localização secundário, consulte [configurar um serviço de informações de localização secundário no Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) na documentação de implantação.

Para obter detalhes sobre como preencher o banco de dados de local, consulte [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) na documentação Implantação.

## <a name="maintaining-the-location-database"></a>Manutenção do banco de dados de local

Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede mudar. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.

 **Como você atualizará o banco de dados de local?**

Há diversos cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de WAPs (pontos de acesso sem fio), recabeamento do escritório (resultando em atribuições de comutação diferentes) e expansão da subrede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?

 **Você usará um aplicativo SNMP para fazer a correspondência dos endereços MAC do cliente Skype for Business com os identificadores de portabilidade e comutador?**

Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de porta e chassis de comutador consistentes entre o aplicativo SNMP e o banco de dados de local. Se o aplicativo SNMP retornar um endereço IP de chassi ou uma ID de porta que não está incluída no banco de dados, o serviço de informações de localização não poderá retornar um local ao cliente.


