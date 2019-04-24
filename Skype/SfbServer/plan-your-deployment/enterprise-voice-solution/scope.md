---
title: Definir o escopo da implantação do E9-1-1 Skype para Business Server
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
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Decisões necessárias para planejar uma implantação do E9-1-1 em Skype Business Server Enterprise Voice.
ms.openlocfilehash: 014ef9a07679341a7d5eada4ecbad382a9576b61
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206477"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Definir o escopo da implantação do E9-1-1 Skype para Business Server

Decisões necessárias para planejar uma implantação do E9-1-1 em Skype Business Server Enterprise Voice.

Antes de configurar Skype for Business para E9-1-1, você precisará planejar sua implantação do E9-1-1. Algumas das questões a serem consideradas são:

 **Cite a política da sua organização e as obrigações com relação ao E9-1-1.**

 Os requisitos legais de E9-1-1 para PBXs (chamados de Multi-line Telephone Systems, ou MLTS, no linguajar de E9-1-1) diferem de acordo com o estado. Você deve consultar sua equipe legal para compreender as obrigações que possam se aplicar à sua implantação do Skype for Business no seus regiões relevantes.

 **Quais áreas dentro de sua empresa precisam estar habilitadas para E9-1-1?**

 É possível habilitar o E9-1-1 para toda a empresa ou para locais selecionados. Por exemplo, talvez você tenha requisitos variados de E9-1-1 para escritórios em estados diferentes ou queira excluir locais fora dos EUA.

 **Como você implantará o E9-1-1 em sites de filiais?**

 A resiliência de voz é um conceito importante para compreender quando implantar o E9-1-1 no site local. Se você tiver centralizados troncos SIP F-9-1-1 e ocorre uma interrupção da WAN, clientes entrando não poderá obter um local de serviço de informações de local ou para se conectar ao provedor de serviços de serviços de emergência. Skype para negócios fornece várias estratégias para manipular a resiliência de voz em filiais, incluindo: tendo redes de dados resiliente, implantando um tronco SIP em cada ramificação da árvore ou envio de chamadas de emergência check-out para o gateway local durante interrupções. Para obter detalhes, consulte  [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).

 **Você habilitará o E9-1-1 para usuários trabalhando fora da rede?**

 Aquisição de local automática está disponível somente para os clientes localizados dentro da rede da organização, para a sua organização precisa decidir se ele dará suporte a chamadas de E9-1-1 feitas a partir Skype para clientes corporativos enquanto fora do local. Por exemplo, você habilitará usuários para fazer chamadas de emergência se eles estiverem trabalhando de cada ou no local de um cliente? Se um cliente estiver localizado fora da rede empresarial, ele poderá ser configurado para solicitar ao usuário um local. No entanto, como esses locais fornecidos pelo usuário não podem ser pré-validados com base no MSAG (Catálogo de Endereços Principal), o despachante do provedor de serviços de emergência necessitarão confirmar a validade do local verbalmente com o chamador antes de rotear a chamada para o PSAP (ponto de atendimento público seguro).

> [!NOTE]
> Skype para clientes de negócios de usuários que se conectam à rede da sua organização por meio da VPN pode pegue informações de endereço IP internas, mas porque esses endereços não podem ser usados para identificar o local real do usuário, é essencial que as sub-redes VPN são excluídas do serviço de informações de local.

 **Você deseja fornecer roteamento de chamada de emergência para sites fora dos EUA?**

 Talvez você queira fornecer roteamento de emergência para áreas de sua empresa que não são atendidas por um provedor de serviços de emergência (por exemplo, locais internacionais). Para fazer isso, crie um novo local e atribua políticas de voz aos locais que se referem a um uso do PSTN que roteia a chamada pelo gateway PSTN local.


