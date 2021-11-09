---
title: Gerenciar locais para provedores de serviços de tronco SIP em Skype for Business Server
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
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Decisões necessárias para o planejamento de um banco de dados de informações de localização ou um banco de dados externo semelhante para uma implantação do E9-1-1 usando provedores de tronco SIP, em Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 4667ea571fe3bbb022c8dd1ee1483e6195165ec9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855288"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Gerenciar locais para provedores de serviços de tronco SIP em Skype for Business Server

Decisões necessárias para o planejamento de um banco de dados de informações de localização ou um banco de dados externo semelhante para uma implantação do E9-1-1 usando provedores de tronco SIP, em Skype for Business Server Enterprise Voice.

Para configurar o Skype for Business Server para localizar automaticamente clientes em uma rede, você precisa preencher o banco de dados de serviço informações de local com um mapa de rede e publicar os locais ou vincular a um banco de dados externo que já contém os mapeamentos corretos. Como parte desse processo, é necessário validar os endereços cívicos dos locais com seu provedor de serviço de E9-1-1. Para obter detalhes, consulte [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) na documentação Implantação.

Você preenche o banco de dados de serviço de Informação de Local com um Local de Resposta de Emergência (ERL), que consiste de um endereço civil e o endereço específico dentro de uma construção. O campo  Local do serviço de Informações de Local, que é o local específico dentro de um edifício, tem um comprimento máximo de 20 caracteres (incluindo espaços). Dentro desse comprimento limitado, tente incluir o seguinte:

- Forneça um nome fácil de entender que identifica o local do chamador de 911 para garantir que os respondentes de emergência encontrem a localização específica prontamente, assim que eles chegarem ao endereço residencial. Esse nome de local pode incluir um número de edifício, número do andar, designador de ala, número do quarto, etc. Evite usar apelidos que apenas os funcionários conheçam, pois isso pode fazer com que os respondentes de emergência cheguem ao local errado.

- Um identificador de local que ajuda os usuários a ver facilmente que o cliente Skype for Business escolheu o local correto. O Skype for Business cliente automaticamente concatena e exibe os campos **Local** e **Cidade** descobertos em seu header. Uma boa prática é adicionar o endereço de rua do edifício a cada identificador de local (por exemplo, "1º Andar \<street number> "). Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer construção na cidade.

- Se o local for aproximado porque ele é determinado por um ponto de acesso sem fio, você pode adicionar a palavra **[Near]** (por exemplo, "Próximo ao 1º Andar 1234").

> [!NOTE]
> Os locais adicionados ao banco de dados de localização central não estarão disponíveis para o cliente até que sejam publicados usando um comando Skype for Business Server Shell de Gerenciamento e sejam replicados para os armazenamentos locais do pool. Para obter detalhes, consulte [Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database) na documentação Implantação.

As seções a seguir discutem as considerações que devem ser analisadas ao preencher e manter o banco de dados de local.

## <a name="populating-the-location-database"></a>Preenchendo o banco de dados Local

As seguintes perguntas podem ajudar a determinar como você preencherá o banco de dados de local.

 **Qual processo você usará para preencher o banco de dados de local?**

Onde os dados existem e quais etapas você precisa executar para converter os dados para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?

 **Você tem um banco de dados de terceiros que já contém um mapeamento de locais?**

Usando a opção serviço Informações de Local Secundário para se conectar a um banco de dados de terceiros, você pode agrupar e gerenciar locais usando uma plataforma offline. Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário. Isso significa que o serviço informações de local pode retornar vários endereços, provenientes do serviço Informações de Localização Secundária, para um cliente Skype for Business local. Em seguida, o usuário pode escolher o local mais apropriado.

Para integrar-se ao serviço Informações de Local, o banco de dados de terceiros deve seguir o esquema de Solicitação/Resposta de Local do Lync Server. Para obter detalhes, consulte  ["[MS-E911WS]: Web Service for E911 Support Protocol Specification"](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd). Para obter detalhes sobre como implantar um serviço de Informações de Localização Secundária, consulte [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) na documentação implantação.

Para obter detalhes sobre como preencher o banco de dados de localização, consulte [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) na documentação de Implantação.

## <a name="maintaining-the-location-database"></a>Manutenção do banco de dados Local

Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede muda. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.

 **Como você atualizará o banco de dados de local?**

Há diversos cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de WAPs, recabeamento do escritório (resultando em atribuições de comutação diferentes) e expansão da subrede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?

 **Você usará um aplicativo SNMP para corresponder a endereços do MAC do cliente do Lync a identificadores de porta e de comutador?**

Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de chassi de comutador e de porta consistentes entre o aplicativo SNMP e o banco de dados de local. Se o aplicativo SNMP retornar um endereço IP de chassi ou uma ID de porta que não está incluído no banco de dados, o serviço de Informações de Local não poderá retornar um local para o cliente.