---
title: Definir o escopo da implantação do E9-1-1 no Skype for Business Server
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
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Decisões necessárias para planejar uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 648713ce3474779a588d638e3e81272fbd62e2f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276458"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Definir o escopo da implantação do E9-1-1 no Skype for Business Server

Decisões necessárias para planejar uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice.

Antes de configurar o Skype for Business para E9-1-1, você precisa planejar sua implantação do E9-1-1. Algumas das questões a serem consideradas são:

 **Quais são as obrigações legais e de política da sua organização em relação ao E9-1-1?**

 Os requisitos legais de E9-1-1 para PBXs (chamados de Multi-line Telephone Systems, ou MLTS, no linguajar de E9-1-1) diferem de acordo com o estado. Você deve consultar sua equipe jurídica para entender as obrigações que podem ser aplicadas à sua implantação do Skype for Business em seus países importantes.

 **Quais áreas dentro de sua empresa precisam estar habilitadas para E9-1-1?**

 É possível habilitar o E9-1-1 para toda a empresa ou para locais selecionados. Por exemplo, talvez você tenha requisitos variados de E9-1-1 para escritórios em estados diferentes ou queira excluir locais fora dos EUA.

 **Como você implantará o E9-1-1 em sites de filiais?**

 A resiliência de voz é um conceito importante para compreender quando implantar o E9-1-1 no site local. Se você tiver troncos SIP do E-9-1-1 centralizados e ocorrer uma falha de WAN, os clientes que entrarem podem não conseguir obter um local do serviço de informações sobre o local ou para se conectar ao provedor de serviços de serviços de emergência. O Skype for Business oferece várias estratégias para lidar com a resiliência de voz em filiais, incluindo: redes de dados resistentes, implantação de um tronco SIP em cada filial ou envio de chamadas de emergência para o gateway local durante paralisações. Para obter detalhes, consulte  [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).

 **Você habilitará o E9-1-1 para usuários trabalhando fora da rede?**

 A aquisição automática de localização está disponível somente para clientes localizados dentro da rede da organização, para que a sua organização precise decidir se será compatível com chamadas E9-1-1 feitas a partir de clientes do Skype for Business enquanto estiver fora do local. Por exemplo, você habilitará usuários para fazer chamadas de emergência se eles estiverem trabalhando de cada ou no local de um cliente? Se um cliente estiver localizado fora da rede empresarial, ele poderá ser configurado para solicitar ao usuário um local. No entanto, como esses locais fornecidos pelo usuário não podem ser pré-validados com base no MSAG (Catálogo de Endereços Principal), o despachante do provedor de serviços de emergência necessitarão confirmar a validade do local verbalmente com o chamador antes de rotear a chamada para o PSAP (ponto de atendimento público seguro).

> [!NOTE]
> Os clientes do Skype for Business de usuários que se conectam à rede da sua organização usando a VPN podem pegar informações de endereço IP interno, mas como esses endereços não podem ser usados para identificar o local real do usuário, é essencial que sub-redes VPN sejam excluídas do serviço de informações de localização.

 **Você deseja fornecer roteamento de chamada de emergência para sites fora dos EUA?**

 Talvez você queira fornecer roteamento de emergência para áreas de sua empresa que não são atendidas por um provedor de serviços de emergência (por exemplo, locais internacionais). Para fazer isso, crie um novo local e atribua políticas de voz aos locais que se referem a um uso do PSTN que roteia a chamada pelo gateway PSTN local.


