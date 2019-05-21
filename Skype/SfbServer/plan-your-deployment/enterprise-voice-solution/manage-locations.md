---
title: Gerenciar locais para provedores de serviço de tronco SIP no Skype for Business Server
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
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Decisões necessárias para planejar um banco de dados de informações de localização ou um banco de dados externo semelhante para uma implantação do E9-1-1 usando provedores de entroncamento SIP no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: aafe35f4978ac18897d11aa55f229df501d555ed
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276723"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Gerenciar locais para provedores de serviço de tronco SIP no Skype for Business Server

Decisões necessárias para planejar um banco de dados de informações de localização ou um banco de dados externo semelhante para uma implantação do E9-1-1 usando provedores de entroncamento SIP no Skype for Business Server Enterprise Voice.

Para configurar o Skype for Business Server para localizar automaticamente clientes em uma rede, você precisa preencher o banco de dados do serviço de informações de localização com um Wiremap de rede e publicar os locais ou vincular a um banco de dados externo que já contém os mapeamentos corretos. Como parte desse processo, é necessário validar os endereços cívicos dos locais com seu provedor de serviço de E9-1-1. Para obter detalhes, consulte [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) na documentação Implantação.

Você preenche o banco de dados do Serviço de Informações de Local com um Local de Resposta de Emergência (ERL), que consiste de um endereço civil e o endereço específico dentro de um edifício. O campo **local** do serviço de informações de localização, que é o local específico dentro de um edifício, tem um tamanho máximo de 20 caracteres (incluindo espaços). Dentro deste comprimento limitado, tente incluir o seguinte:

- Um nome fácil de entender que identifica o local do chamador de 911 para ajudar a garantir que os respondentes de emergência encontrem o local correto quando chegarem ao endereço cívico. Esse nome de local pode incluir um número de edifício, número do andar, designador de ala, número da sala, etc. Evite apelidos conhecidos apenas pelos funcionários, que pode fazer com que os respondentes de emergência cheguem ao local errado.

- Um identificador de localização que ajuda os usuários a ver facilmente que o cliente Skype for Business selecionou o local correto. O cliente Skype for Business concatena e exibe automaticamente os campos **local** e **cidade** descobertos no cabeçalho. Uma prática recomendada é adicionar o endereço do edifício a cada identificador de localização (por exemplo, "primeiro andar <street number>"). Sem o endereço físico, um identificador de local genérico como "1° andar" pode ser aplicado a qualquer edifício na cidade.

- Se a localização for aproximada, pois é determinada por um ponto de acesso sem fio, você pode adicionar a palavra **[Near]** (por exemplo, "perto do 1º andar 1234").

> [!NOTE]
> Os locais adicionados ao banco de dados de localização central não estarão disponíveis para o cliente até serem publicados usando um comando shell do Shell de gerenciamento do Skype for Business Server e serão replicados nas lojas locais do pool. Para obter detalhes, consulte [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) na documentação Implantação.

As seções a seguir discutem as considerações que devem ser analisadas ao preencher e manter o banco de dados de local.

## <a name="populating-the-location-database"></a>Preenchendo o banco de dados de local

As seguintes perguntas ajudam a determinar como você preencherá o banco de dados de local.

 **Qual processo você usará para preencher o banco de dados de local?**

Onde estão os dados e quais etapas você precisa executar para convertê-los para o formato necessário pelo banco de dados de local? Você adicionará locais individualmente ou em lote usando um arquivo CSV?

 **Você tem um banco de dados de terceiro que já contém um mapeamento de locais?**

Usando a opção do serviço de informações de localização secundária para se conectar a um banco de dados de terceiros, você pode agrupar e gerenciar locais usando uma plataforma offline. Um benefício dessa abordagem é que além de associar locais aos identificadores de rede, é possível associar locais a um usuário. Isso significa que o serviço de informações de localização pode retornar vários endereços, originários do serviço de informações de localização secundário, para um cliente Skype for Business. Em seguida, o usuário pode escolher o local mais apropriado.

Para integrar-se com o serviço informações de localização, o banco de dados de terceiros deve seguir o esquema de solicitação/resposta de localização do Lync Server. Para obter detalhes, consulte ["[MS-E911WS]: serviço Web para a especificação do protocolo de suporte do E911"](https://go.microsoft.com/fwlink/p/?linkid=213819). Para obter detalhes sobre a implantação de um serviço de informações de localização secundário, consulte [configurar um serviço de informações de localização secundário no Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) na documentação de implantação.

Para obter detalhes sobre como preencher o banco de dados de local, consulte [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) na documentação Implantação.

## <a name="maintaining-the-location-database"></a>Manutenção do banco de dados de local

Depois de preencher o banco de dados de local, é necessário desenvolver uma estratégia para atualização do banco de dados à medida que a configuração de rede mudar. As seguintes perguntas ajudarão a determinar como você manterá o banco de dados de local.

 **Como você atualizará o banco de dados de local?**

Há diversos cenários que exigem uma atualização para o banco de dados de local, incluindo a adição de WAPs, recabeamento do escritório (resultando em atribuições de comutação diferentes) e expansão da subrede. Você atualizará diretamente cada local individual ou realizará uma atualização em massa de todos os locais usando um arquivo CSV?

 **Você usará um aplicativo SNMP para que os endereços do MAC do cliente do Skype sejam compatíveis aos identificadores de porta e de comutador?**

Se você usar um aplicativo SNMP, precisará desenvolver um processo manual para manter as informações de porta e chassis de comutador consistentes entre o aplicativo SNMP e o banco de dados de local. Se o aplicativo SNMP retornar um endereço IP de chassi ou uma ID de porta que não está incluída no banco de dados, o serviço de informações de localização não poderá retornar um local ao cliente.


