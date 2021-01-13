---
title: Gerenciar locais para provedores de serviços de tronco SIP no Skype for Business Server
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
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Decisões necessárias para o planejamento de um banco de dados de informações de local, ou um banco de dados externo semelhante, para uma implantação de E9-1-1 usando provedores de tronco SIP, no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 9918fc2cb6bc9d05166d648ab3285a964d15f290
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825431"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Gerenciar locais para provedores de serviços de tronco SIP no Skype for Business Server

Decisões necessárias para o planejamento de um banco de dados de informações de local, ou um banco de dados externo semelhante, para uma implantação de E9-1-1 usando provedores de tronco SIP, no Skype for Business Server Enterprise Voice.

Para configurar o Skype for Business Server para localizar automaticamente clientes em uma rede, você precisa preencher o banco de dados do serviço de Informações de Local com um mapa de conexão de rede e publicar os locais ou vincular a um banco de dados externo que já contém os mapeamentos corretos. Como parte desse processo, é necessário validar os endereços cívicos dos locais com seu provedor de serviço de E9-1-1. Para obter detalhes, consulte [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) na documentação Implantação.

Você preenche o banco de dados de serviço de Informação de Local com um Local de Resposta de Emergência (ERL), que consiste de um endereço civil e o endereço específico dentro de uma construção. O campo Local do **Serviço** de Informações de Local, que é o local específico dentro de um edifício, tem um comprimento máximo de 20 caracteres (incluindo espaços). Dentro desse comprimento limitado, tente incluir o seguinte:

- Forneça um nome fácil de entender que identifica o local do chamador de 911 para garantir que os respondentes de emergência encontrem a localização específica prontamente, assim que eles chegarem ao endereço residencial. Esse nome de local pode incluir um número de edifício, número do andar, designador de ala, número do quarto, etc. Evite usar apelidos que apenas os funcionários conheçam, pois isso pode fazer com que os respondentes de emergência cheguem ao local errado.

- Um identificador de local que ajuda os usuários a ver facilmente que seu cliente Skype for Business escolheu o local correto. O cliente Skype for Business concatena automaticamente e exibe os campos **Localização** e Cidade **descobertos** em seu header. Uma boa prática é adicionar o endereço do edifício a cada identificador de local (por exemplo, "1º <street number> andar"). Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer construção na cidade.

- Se o local for aproximado porque é determinado por um ponto de acesso sem fio, você pode adicionar a palavra **[Near]** (por exemplo, "Próximo ao 1º andar, 1234").

> [!NOTE]
> Os locais adicionados ao banco de dados de localização central não estarão disponíveis para o cliente até que sejam publicados usando um comando do Shell de Gerenciamento do Skype for Business Server e sejam replicados para os armazenamentos locais do pool. Para obter detalhes, consulte [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) na documentação Implantação.

As seções a seguir discutem as considerações que devem ser analisadas ao preencher e manter o banco de dados de local.

## <a name="populating-the-location-database"></a>Preenchendo o banco de dados Local

As seguintes perguntas podem ajudar a determinar como você preencherá o banco de dados de local.

 **Qual processo você usará para preencher o banco de dados de local?**

Onde os dados existem e quais etapas você precisa executar para converter os dados para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?

 **Você tem um banco de dados de terceiros que já contém um mapeamento de locais?**

Usando a opção de serviço Informações de Local Secundária para se conectar a um banco de dados de terceiros, você pode agrupar e gerenciar locais usando uma plataforma offline. Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário. Isso significa que o serviço de Informações de Local pode retornar vários endereços, provenientes do serviço informações de localização secundária, para um cliente do Skype for Business. Em seguida, o usuário pode escolher o local mais apropriado.

Para integrar-se ao serviço de Informações de Local, o banco de dados de terceiros deve seguir o esquema de Solicitação/Resposta de Local do Lync Server. Para obter detalhes, consulte  ["[MS-E911WS]: Especificação](https://go.microsoft.com/fwlink/p/?linkid=213819)do Protocolo de Suporte do Serviço Web para E911". Para obter detalhes sobre como implantar um serviço de Informações de Local Secundário, consulte [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) in the Deployment documentation.

Para obter detalhes sobre como preencher o banco de dados de localização, [consulte Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) in the Deployment documentation.

## <a name="maintaining-the-location-database"></a>Manutenção do banco de dados Local

Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede muda. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.

 **Como você atualizará o banco de dados de local?**

Há diversos cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de WAPs, recabeamento do escritório (resultando em atribuições de comutação diferentes) e expansão da subrede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?

 **Você usará um aplicativo SNMP para corresponder a endereços do MAC do cliente do Lync a identificadores de porta e de comutador?**

Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de chassi de comutador e de porta consistentes entre o aplicativo SNMP e o banco de dados de local. Se o aplicativo SNMP retornar um endereço IP de chassi ou ID de porta que não está incluído no banco de dados, o serviço de Informações de Local não poderá retornar um local para o cliente.


