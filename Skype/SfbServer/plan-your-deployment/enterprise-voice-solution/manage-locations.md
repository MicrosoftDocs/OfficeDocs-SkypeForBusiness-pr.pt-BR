---
title: Gerenciar locais para provedores de serviços de tronco SIP no Skype para Business Server
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
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Decisões necessárias para planejar um banco de dados de informações de local ou um semelhante banco de dados externo, para uma implantação do E9-1-1 usando provedores de tronco SIP, em Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 07b6c95ad36e740d5dec6bb882766f876da52626
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206723"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Gerenciar locais para provedores de serviços de tronco SIP no Skype para Business Server

Decisões necessárias para planejar um banco de dados de informações de local ou um semelhante banco de dados externo, para uma implantação do E9-1-1 usando provedores de tronco SIP, em Skype para Business Server Enterprise Voice.

Para configurar o Skype para Business Server localize automaticamente clientes dentro de uma rede, você precisa preencher o banco de dados de serviço de informações de local com um wiremap de rede e publicar os locais ou vincular a um banco de dados externo que já contenha os mapeamentos corretos. Como parte desse processo, é necessário validar os endereços cívicos dos locais com seu provedor de serviço de E9-1-1. Para obter detalhes, consulte [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) na documentação Implantação.

Você preenche o banco de dados do Serviço de Informações de Local com um Local de Resposta de Emergência (ERL), que consiste de um endereço civil e o endereço específico dentro de um edifício. Campo de **local** do serviço de informações de local, que é o local específico dentro de um edifício, tem um tamanho máximo de 20 caracteres (incluindo espaços). Dentro deste comprimento limitado, tente incluir o seguinte:

- Um nome fácil de entender que identifica o local do chamador de 911 para ajudar a garantir que os respondentes de emergência encontrem o local correto quando chegarem ao endereço cívico. Esse nome de local pode incluir um número de edifício, número do andar, designador de ala, número da sala, etc. Evite apelidos conhecidos apenas pelos funcionários, que pode fazer com que os respondentes de emergência cheguem ao local errado.

- Um identificador de localidade que ajuda os usuários a ver facilmente que seus Skype para cliente corporativos buscada o local correto. O Skype para o cliente de negócios concatena e exibe os campos de **local** e **cidade** descobertos em seu cabeçalho automaticamente. Uma boa prática é adicionar o endereço do edifício para cada identificador de localidade (por exemplo, "1º andar <street number>"). Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer edifício na cidade.

- Se o local for aproximado por ser determinado por um ponto de acesso sem fio, você pode adicionar a palavra **[perto]** (por exemplo, "próximo ao 1º andar 1234").

> [!NOTE]
> Locais adicionados ao banco de dados local central não estão disponíveis para o cliente até que eles são publicados usando um Skype para o comando do Shell de gerenciamento do servidor de negócios e são replicados para as lojas locais do pool. Para obter detalhes, consulte [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) na documentação Implantação.

As seções a seguir discutem as considerações que devem ser analisadas ao preencher e manter o banco de dados de local.

## <a name="populating-the-location-database"></a>Preenchendo o banco de dados de local

As seguintes perguntas ajudam a determinar como você preencherá o banco de dados de local.

 **Qual processo você usará para preencher o banco de dados de local?**

Onde estão os dados e quais etapas você precisa executar para convertê-los para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?

 **Você tem um banco de dados de terceiro que já contém um mapeamento de locais?**

Usando a opção de serviço de informações de localização secundário para se conectar a um banco de dados de terceiros, você pode agrupar e gerenciar locais usando uma plataforma offline. Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário. Isso significa que o serviço de informações de local pode retornar vários endereços, originário do serviço de informações de localização secundário, para um Skype para o cliente de negócios. Em seguida, o usuário pode escolher o local mais apropriado.

Para integrar com o serviço de informações de local, o banco de dados de terceiros deve seguir o esquema de solicitação/resposta do Lync Server local. Para obter detalhes, consulte ["[MS-E911WS]: o serviço Web para a especificação de protocolo do E911 suporte"](https://go.microsoft.com/fwlink/p/?linkid=213819). Para obter detalhes sobre como implantar um serviço de informações de localização secundária, consulte [Configure um serviço de informações de localização secundário no Skype para Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) na documentação de implantação.

Para obter detalhes sobre como preencher o banco de dados de local, consulte [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) na documentação Implantação.

## <a name="maintaining-the-location-database"></a>Manutenção do banco de dados de local

Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede mudar. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.

 **Como você atualizará o banco de dados de local?**

Há diversos cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de WAPs, recabeamento do escritório (resultando em atribuições de comutação diferentes) e expansão da subrede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?

 **Você usará um aplicativo SNMP para que os endereços do MAC do cliente do Skype sejam compatíveis aos identificadores de porta e de comutador?**

Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de porta e chassis de comutador consistentes entre o aplicativo SNMP e o banco de dados de local. Se o aplicativo SNMP retorna uma chassi IP endereço ou porta ID que não está incluída no banco de dados, o serviço de informações de local não poderão retornar uma localização para o cliente.


